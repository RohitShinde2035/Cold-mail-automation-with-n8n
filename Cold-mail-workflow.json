{
    "data": {
        "createdAt": "2025-08-24T08:17:29.567Z",
        "updatedAt": "2025-08-24T11:18:16.000Z",
        "id": "Jezjtyh9hNUGjlUT",
        "name": "Cold Mail",
        "active": false,
        "isArchived": false,
        "nodes": [
            {
                "parameters": {},
                "type": "n8n-nodes-base.manualTrigger",
                "typeVersion": 1,
                "position": [
                    80,
                    16
                ],
                "id": "e5f32961-c7e2-4d6e-9d35-5604597dbfbc",
                "name": "When clicking ‘Execute workflow’"
            },
            {
                "parameters": {
                    "documentId": {
                        "__rl": true,
                        "value": "1S_aSkNodCV0nrCjpI4OVrrfXdC6mEwvB4QOEuRDTJKs",
                        "mode": "list",
                        "cachedResultName": "Lead Sheet",
                        "cachedResultUrl": "https://docs.google.com/spreadsheets/d/1S_aSkNodCV0nrCjpI4OVrrfXdC6mEwvB4QOEuRDTJKs/edit?usp=drivesdk"
                    },
                    "sheetName": {
                        "__rl": true,
                        "value": "gid=0",
                        "mode": "list",
                        "cachedResultName": "Sheet1",
                        "cachedResultUrl": "https://docs.google.com/spreadsheets/d/1S_aSkNodCV0nrCjpI4OVrrfXdC6mEwvB4QOEuRDTJKs/edit#gid=0"
                    },
                    "options": {}
                },
                "type": "n8n-nodes-base.googleSheets",
                "typeVersion": 4.7,
                "position": [
                    240,
                    0
                ],
                "id": "2f3de88d-a9d7-4bd9-b704-6aa2b848ca02",
                "name": "Get row(s) in sheet",
                "credentials": {
                    "googleSheetsOAuth2Api": {
                        "id": "uzA9PICTNev8VzHM",
                        "name": "Google Sheets account"
                    }
                }
            },
            {
                "parameters": {
                    "conditions": {
                        "options": {
                            "caseSensitive": true,
                            "leftValue": "",
                            "typeValidation": "strict",
                            "version": 2
                        },
                        "conditions": [
                            {
                                "id": "fbdbd708-32e7-4460-9097-672dc8dda47d",
                                "leftValue": "={{ $json['Sent Status'] }}",
                                "rightValue": "SENT",
                                "operator": {
                                    "type": "string",
                                    "operation": "equals"
                                }
                            }
                        ],
                        "combinator": "and"
                    },
                    "options": {}
                },
                "type": "n8n-nodes-base.if",
                "typeVersion": 2.2,
                "position": [
                    416,
                    -16
                ],
                "id": "cf15f2e6-5977-44e0-98d7-dd154ec521c2",
                "name": "If"
            },
            {
                "parameters": {
                    "options": {}
                },
                "type": "n8n-nodes-base.splitInBatches",
                "typeVersion": 3,
                "position": [
                    608,
                    0
                ],
                "id": "b5f0ecad-7112-442a-ae83-e7085e3e7433",
                "name": "Loop Over Items"
            },
            {
                "parameters": {
                    "documentId": {
                        "__rl": true,
                        "value": "1S_aSkNodCV0nrCjpI4OVrrfXdC6mEwvB4QOEuRDTJKs",
                        "mode": "list",
                        "cachedResultName": "Lead Sheet",
                        "cachedResultUrl": "https://docs.google.com/spreadsheets/d/1S_aSkNodCV0nrCjpI4OVrrfXdC6mEwvB4QOEuRDTJKs/edit?usp=drivesdk"
                    },
                    "sheetName": {
                        "__rl": true,
                        "value": 1554978092,
                        "mode": "list",
                        "cachedResultName": "Sheet2",
                        "cachedResultUrl": "https://docs.google.com/spreadsheets/d/1S_aSkNodCV0nrCjpI4OVrrfXdC6mEwvB4QOEuRDTJKs/edit#gid=1554978092"
                    },
                    "options": {}
                },
                "type": "n8n-nodes-base.googleSheets",
                "typeVersion": 4.7,
                "position": [
                    752,
                    -192
                ],
                "id": "c83c965d-24dd-4366-a48a-2828291c44e7",
                "name": "Get row(s) in sheet1",
                "credentials": {
                    "googleSheetsOAuth2Api": {
                        "id": "uzA9PICTNev8VzHM",
                        "name": "Google Sheets account"
                    }
                }
            },
            {
                "parameters": {
                    "jsCode": "// Get templates from previous node\nconst templates = items.map(item => item.json);\n\n// Check if templates exist\nif (!templates || templates.length === 0) {\n  throw new Error('No templates found');\n}\n\n// Pick a random template\nconst index = Math.floor(Math.random() * templates.length);\nconst template = templates[index];\n\n// Convert body to HTML\nconst bodyHtml = template.Body.replace(/\\n/g, '<br>');\n\n// Return in n8n-compatible format\nreturn [\n  {\n    json: {\n      subject: template.Subject,\n      body: bodyHtml\n    }\n  }\n];"
                },
                "type": "n8n-nodes-base.code",
                "typeVersion": 2,
                "position": [
                    944,
                    -208
                ],
                "id": "531ef533-38b5-4be3-8e27-8df4529d21fc",
                "name": "Code"
            },
            {
                "parameters": {
                    "mode": "combine",
                    "combineBy": "combineByPosition",
                    "options": {}
                },
                "type": "n8n-nodes-base.merge",
                "typeVersion": 3.2,
                "position": [
                    1136,
                    -128
                ],
                "id": "022296f9-76b4-49b4-bab3-ffec9137b407",
                "name": "Merge"
            },
            {
                "parameters": {
                    "assignments": {
                        "assignments": [
                            {
                                "id": "5a8d5f5d-ff41-45fe-bdb9-a0a6de4878e1",
                                "name": "body",
                                "value": "={{ $json.body.replace(\"[name]\", $json[\"Name\"] && $json[\"Name\"].trim() !== '' ? $json[\"Name\"].trim() : \"there\") }}",
                                "type": "string"
                            }
                        ]
                    },
                    "includeOtherFields": true,
                    "options": {}
                },
                "type": "n8n-nodes-base.set",
                "typeVersion": 3.4,
                "position": [
                    1296,
                    -224
                ],
                "id": "212ae803-d982-44ee-8d5a-d300eabcd22d",
                "name": "Edit Fields"
            },
            {
                "parameters": {
                    "sendTo": "={{ $json.Email }}",
                    "subject": "={{ $json.subject }}",
                    "message": "={{ $json.body }}",
                    "options": {
                        "appendAttribution": false,
                        "senderName": "Rohit bhau"
                    }
                },
                "type": "n8n-nodes-base.gmail",
                "typeVersion": 2.1,
                "position": [
                    1472,
                    -32
                ],
                "id": "068f8df8-7307-48d4-87b7-4376c11a1b59",
                "name": "Send a message",
                "webhookId": "ccdbbc8d-c290-49ab-a024-7a5d4b6fe729",
                "credentials": {
                    "gmailOAuth2": {
                        "id": "QSxX6PwAX2mj6NiM",
                        "name": "Gmail account"
                    }
                }
            },
            {
                "parameters": {
                    "mode": "combine",
                    "combineBy": "combineByPosition",
                    "options": {}
                },
                "type": "n8n-nodes-base.merge",
                "typeVersion": 3.2,
                "position": [
                    1600,
                    -256
                ],
                "id": "aadaed57-1391-418a-86a4-b07919d6dadf",
                "name": "Merge1"
            },
            {
                "parameters": {
                    "operation": "update",
                    "documentId": {
                        "__rl": true,
                        "value": "1S_aSkNodCV0nrCjpI4OVrrfXdC6mEwvB4QOEuRDTJKs",
                        "mode": "list",
                        "cachedResultName": "Lead Sheet",
                        "cachedResultUrl": "https://docs.google.com/spreadsheets/d/1S_aSkNodCV0nrCjpI4OVrrfXdC6mEwvB4QOEuRDTJKs/edit?usp=drivesdk"
                    },
                    "sheetName": {
                        "__rl": true,
                        "value": "gid=0",
                        "mode": "list",
                        "cachedResultName": "Sheet1",
                        "cachedResultUrl": "https://docs.google.com/spreadsheets/d/1S_aSkNodCV0nrCjpI4OVrrfXdC6mEwvB4QOEuRDTJKs/edit#gid=0"
                    },
                    "columns": {
                        "mappingMode": "defineBelow",
                        "value": {
                            "Email": "={{ $json.Email }}",
                            "Sent Status": "={{ $json.labelIds[0] }}",
                            "Time": "={{ new Date().toLocaleTimeString(\"en-GB\", { timeZone: \"Asia/Kolkata\", hour12: false }) }}"
                        },
                        "matchingColumns": [
                            "Email"
                        ],
                        "schema": [
                            {
                                "id": "Name",
                                "displayName": "Name",
                                "required": false,
                                "defaultMatch": false,
                                "display": true,
                                "type": "string",
                                "canBeUsedToMatch": true,
                                "removed": true
                            },
                            {
                                "id": "Email",
                                "displayName": "Email",
                                "required": false,
                                "defaultMatch": false,
                                "display": true,
                                "type": "string",
                                "canBeUsedToMatch": true,
                                "removed": false
                            },
                            {
                                "id": "Sent Status",
                                "displayName": "Sent Status",
                                "required": false,
                                "defaultMatch": false,
                                "display": true,
                                "type": "string",
                                "canBeUsedToMatch": true
                            },
                            {
                                "id": "Time",
                                "displayName": "Time",
                                "required": false,
                                "defaultMatch": false,
                                "display": true,
                                "type": "string",
                                "canBeUsedToMatch": true
                            },
                            {
                                "id": "row_number",
                                "displayName": "row_number",
                                "required": false,
                                "defaultMatch": false,
                                "display": true,
                                "type": "number",
                                "canBeUsedToMatch": true,
                                "readOnly": true,
                                "removed": true
                            }
                        ],
                        "attemptToConvertTypes": false,
                        "convertFieldsToString": false
                    },
                    "options": {}
                },
                "type": "n8n-nodes-base.googleSheets",
                "typeVersion": 4.7,
                "position": [
                    1776,
                    -256
                ],
                "id": "09c156d3-4037-4b0e-8985-c3d99b82e2eb",
                "name": "Update row in sheet",
                "credentials": {
                    "googleSheetsOAuth2Api": {
                        "id": "uzA9PICTNev8VzHM",
                        "name": "Google Sheets account"
                    }
                }
            },
            {
                "parameters": {},
                "type": "n8n-nodes-base.wait",
                "typeVersion": 1.1,
                "position": [
                    1664,
                    0
                ],
                "id": "e5377010-3e07-42ba-a4ba-3fbcc20e640b",
                "name": "Wait",
                "webhookId": "28d79443-2d63-472e-884d-dd239f451389"
            }
        ],
        "connections": {
            "When clicking ‘Execute workflow’": {
                "main": [
                    [
                        {
                            "node": "Get row(s) in sheet",
                            "type": "main",
                            "index": 0
                        }
                    ]
                ]
            },
            "Get row(s) in sheet": {
                "main": [
                    [
                        {
                            "node": "If",
                            "type": "main",
                            "index": 0
                        }
                    ]
                ]
            },
            "If": {
                "main": [
                    [],
                    [
                        {
                            "node": "Loop Over Items",
                            "type": "main",
                            "index": 0
                        }
                    ]
                ]
            },
            "Loop Over Items": {
                "main": [
                    [],
                    [
                        {
                            "node": "Get row(s) in sheet1",
                            "type": "main",
                            "index": 0
                        },
                        {
                            "node": "Merge",
                            "type": "main",
                            "index": 1
                        }
                    ]
                ]
            },
            "Get row(s) in sheet1": {
                "main": [
                    [
                        {
                            "node": "Code",
                            "type": "main",
                            "index": 0
                        }
                    ]
                ]
            },
            "Code": {
                "main": [
                    [
                        {
                            "node": "Merge",
                            "type": "main",
                            "index": 0
                        }
                    ]
                ]
            },
            "Merge": {
                "main": [
                    [
                        {
                            "node": "Edit Fields",
                            "type": "main",
                            "index": 0
                        }
                    ]
                ]
            },
            "Edit Fields": {
                "main": [
                    [
                        {
                            "node": "Send a message",
                            "type": "main",
                            "index": 0
                        },
                        {
                            "node": "Merge1",
                            "type": "main",
                            "index": 0
                        }
                    ]
                ]
            },
            "Send a message": {
                "main": [
                    [
                        {
                            "node": "Merge1",
                            "type": "main",
                            "index": 1
                        },
                        {
                            "node": "Wait",
                            "type": "main",
                            "index": 0
                        }
                    ]
                ]
            },
            "Merge1": {
                "main": [
                    [
                        {
                            "node": "Update row in sheet",
                            "type": "main",
                            "index": 0
                        }
                    ]
                ]
            },
            "Wait": {
                "main": [
                    [
                        {
                            "node": "Loop Over Items",
                            "type": "main",
                            "index": 0
                        }
                    ]
                ]
            }
        },
        "settings": {
            "executionOrder": "v1"
        },
        "staticData": null,
        "meta": {
            "templateCredsSetupCompleted": true
        },
        "pinData": {},
        "versionId": "28673a21-5333-409c-9d5e-579ab213299f",
        "triggerCount": 0,
        "tags": [],
        "scopes": [
            "workflow:create",
            "workflow:delete",
            "workflow:execute",
            "workflow:list",
            "workflow:move",
            "workflow:read",
            "workflow:share",
            "workflow:update"
        ]
    }
}
