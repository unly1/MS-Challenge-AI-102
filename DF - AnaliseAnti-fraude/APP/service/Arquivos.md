## Código Utilizado na Atividade

### 1. Blob Service - Envio de Arquivos para o Azure Blob Storage

Esse trecho de código realiza o upload de um arquivo para o Azure Blob Storage.

```python
import os
import streamlit as st
from utils.Config import Config
from azure.storage.blob import BlobServiceClient

def upload_blob(file, file_name):
    try:
        # Cria um cliente de serviço para o Blob Storage utilizando a connection string
        blob_service_client = BlobServiceClient.from_connection_string(Config.AZURE_STORAGE_CONNECTION_STRING)
        
        # Obtém o cliente de blob para um container específico e define o nome do arquivo
        blob_client = blob_service_client.get_blob_client(container=Config.CONTAINER_NAME, blob=file_name)
        
        # Realiza o upload do arquivo para o Azure Blob, substituindo qualquer arquivo existente
        blob_client.upload_blob(file, overwrite=True)
        
        # Retorna a URL do blob após o upload
        return blob_client.url
    except Exception as ex:
        # Caso ocorra algum erro, exibe uma mensagem de erro no Streamlit
        st.error(f"Erro ao enviar o arquivo para o Azure Blob Storage: {ex}")
        return None

```
### 2. Credit Card - Análise de Informações de Cartão de Crédito

Esse trecho de código utiliza o Azure AI Document Intelligence para analisar documentos de cartões de crédito.
```python
from azure.core.credentials import AzureKeyCredential
from azure.ai.documentintelligence import DocumentIntelligenceClient
from azure.ai.documentintelligence.models import AnalyzeDocumentRequest
from utils.Config import Config

def analyze_credit_card(card_url):
    # Inicializa as credenciais e o cliente de Document Intelligence
    credential = AzureKeyCredential(Config.KEY)
    document_client = DocumentIntelligenceClient(Config.ENDPOINT, credential)
    
    # Envia a URL do documento para o serviço de análise de cartão de crédito
    card_info = document_client.begin_analyze_document("prebuilt-creditCard", AnalyzeDocumentRequest(url_source=card_url))
    
    # Obtém o resultado da análise
    result = card_info.result()
    
    # Extrai as informações relevantes do cartão de crédito
    for document in result.documents:
        fields = document.get('fields', {})

        return {
            "card_name": fields.get('CardHolderName', {}).get('content'),
            "card_number": fields.get('CardNumber', {}).get('content'),
            "expiry_date": fields.get('ExpirationDate', {}).get('content'),
            "bank_name": fields.get('IssuingBank', {}).get('content'),
        }

```
