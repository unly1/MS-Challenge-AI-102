## Conclusão

### Resultado

```json
{
	"status": "succeeded",
	"createdDateTime": "2024-11-22T19:30:29Z",
	"lastUpdatedDateTime": "2024-11-22T19:30:32Z",
	"analyzeResult": {
		"apiVersion": "2024-07-31-preview",
		"modelId": "prebuilt-creditCard",
		"stringIndexType": "utf16CodeUnit",
		"content": "YOUA BANK NAME *\n1234 5678 1234 5678\nVALID 01/25\nCARDHOLDER NAME",
		"pages": [
			{
				"pageNumber": 1,
				"angle": 0.3370184898376465,
				"width": 612,
				"height": 416,
				"unit": "pixel",
				"words": [
					{
						"content": "YOUA",
						"polygon": [
							389,
							118,
							409,
							118,
							409,
							127,
							389,
							127
						],
						"confidence": 0.862,
						"span": {
							"offset": 0,
							"length": 4
						}
					},
					{
						"content": "BANK",
						"polygon": [
							411,
							118,
							432,
							118,
							432,
							128,
							411,
							127
						],
						"confidence": 0.981,
						"span": {
							"offset": 5,
							"length": 4
						}
					},
					{
						"content": "NAME",
						"polygon": [
							434,
							118,
							457,
							118,
							457,
							128,
							434,
							128
						],
						"confidence": 0.989,
						"span": {
							"offset": 10,
							"length": 4
						}
					},
					{
						"content": "*",
						"polygon": [
							464,
							118,
							469,
							118,
							469,
							128,
							464,
							128
						],
						"confidence": 0.79,
						"span": {
							"offset": 15,
							"length": 1
						}
					},
					{
						"content": "1234",
						"polygon": [
							160,
							224,
							214,
							224,
							214,
							247,
							161,
							247
						],
						"confidence": 0.974,
						"span": {
							"offset": 17,
							"length": 4
						}
					},
					{
						"content": "5678",
						"polygon": [
							236,
							224,
							293,
							224,
							294,
							246,
							237,
							246
						],
						"confidence": 0.993,
						"span": {
							"offset": 22,
							"length": 4
						}
					},
					{
						"content": "1234",
						"polygon": [
							319,
							224,
							373,
							224,
							373,
							247,
							319,
							247
						],
						"confidence": 0.992,
						"span": {
							"offset": 27,
							"length": 4
						}
					},
					{
						"content": "5678",
						"polygon": [
							396,
							224,
							451,
							224,
							451,
							247,
							396,
							247
						],
						"confidence": 0.993,
						"span": {
							"offset": 32,
							"length": 4
						}
					},
					{
						"content": "VALID",
						"polygon": [
							160,
							259,
							178,
							259,
							178,
							272,
							160,
							269
						],
						"confidence": 0.517,
						"span": {
							"offset": 37,
							"length": 5
						}
					},
					{
						"content": "01/25",
						"polygon": [
							181,
							259,
							226,
							259,
							226,
							274,
							181,
							272
						],
						"confidence": 0.972,
						"span": {
							"offset": 43,
							"length": 5
						}
					},
					{
						"content": "CARDHOLDER",
						"polygon": [
							160,
							288,
							256,
							289,
							256,
							303,
							160,
							304
						],
						"confidence": 0.994,
						"span": {
							"offset": 49,
							"length": 10
						}
					},
					{
						"content": "NAME",
						"polygon": [
							262,
							289,
							304,
							289,
							304,
							303,
							261,
							303
						],
						"confidence": 0.993,
						"span": {
							"offset": 60,
							"length": 4
						}
					}
				],
				"lines": [
					{
						"content": "YOUA BANK NAME *",
						"polygon": [
							387,
							118,
							472,
							118,
							472,
							128,
							387,
							127
						],
						"spans": [
							{
								"offset": 0,
								"length": 16
							}
						]
					},
					{
						"content": "1234 5678 1234 5678",
						"polygon": [
							159,
							223,
							454,
							223,
							454,
							246,
							159,
							246
						],
						"spans": [
							{
								"offset": 17,
								"length": 19
							}
						]
					},
					{
						"content": "VALID 01/25",
						"polygon": [
							159,
							258,
							229,
							259,
							228,
							274,
							159,
							271
						],
						"spans": [
							{
								"offset": 37,
								"length": 11
							}
						]
					},
					{
						"content": "CARDHOLDER NAME",
						"polygon": [
							159,
							287,
							305,
							287,
							305,
							303,
							159,
							303
						],
						"spans": [
							{
								"offset": 49,
								"length": 15
							}
						]
					}
				],
				"spans": [
					{
						"offset": 0,
						"length": 64
					}
				]
			}
		],
		"styles": [],
		"documents": [
			{
				"docType": "creditCard",
				"boundingRegions": [
					{
						"pageNumber": 1,
						"polygon": [
							0,
							0,
							612,
							0,
							612,
							416,
							0,
							416
						]
					}
				],
				"fields": {
					"CardHolderName": {
						"type": "string",
						"content": "CARDHOLDER NAME",
						"boundingRegions": [
							{
								"pageNumber": 1,
								"polygon": [
									160,
									288,
									304,
									288,
									304,
									304,
									160,
									304
								]
							}
						],
						"confidence": 0.995,
						"spans": [
							{
								"offset": 49,
								"length": 15
							}
						]
					},
					"CardNumber": {
						"type": "string",
						"content": "1234 5678 1234 5678",
						"boundingRegions": [
							{
								"pageNumber": 1,
								"polygon": [
									160,
									224,
									451,
									224,
									451,
									247,
									160,
									247
								]
							}
						],
						"confidence": 0.995,
						"spans": [
							{
								"offset": 17,
								"length": 19
							}
						]
					},
					"ExpirationDate": {
						"type": "date",
						"content": "01/25",
						"boundingRegions": [
							{
								"pageNumber": 1,
								"polygon": [
									181,
									259,
									226,
									259,
									226,
									274,
									181,
									272
								]
							}
						],
						"confidence": 0.995,
						"spans": [
							{
								"offset": 43,
								"length": 5
							}
						]
					}
				},
				"confidence": 1,
				"spans": [
					{
						"offset": 0,
						"length": 64
					}
				]
			}
		],
		"contentFormat": "text"
	}
}
```
