---
description: >-
  This component is a full table which shall contain data in a tabular format
  only to be part of a schema of CompositeComponent like Form.
---

# 📐 TableInputComponent

> ### "_Table as part of a Form_" - Neon devs

Some properties to note here,\
**orientation** -> TableOrientation explains the orientation of the tabular input visual. Can be \
&#x20;    **ROW\_MAJOR ->** Refers that the data is present as ROWS and the COLUMNS are defined by the tableVector.\
&#x20;    **COLUMN\_MAJOR ->** Refers that the data is present as COLUMNS and the ROWS are defined by the tableVector.

&#x20;**uniqueKeyName ->** This field refers to a property/key inside each value array Map object which can be used to uniquely identify the row. This field can be used when the nature of data is bounded and the uniqueKey is of a type upon which one can think of creating valid conditions or logics.

**tableVector ->** Provides the definition of a row/column (inversely related to orientation value) with the data field name against a pairing of headerLabel and the component definition.

\
&#x20;      &#x20;

```json
{
    "iComponentType": "tableInputComponent",
    "name": "inputTableExample",
    "label": "Table Label",
    "orientation": "ROW_MAJOR",
    "disabled": false,
    "readOnly": false,
    "hidden": false,
    "tableVector": {
        "name": {
            "headerLabel": "Customer Name",
            "component": {
                "iComponentType": "formKeyMapComponent",
                "name": "name",
                "label": null,
                "value": null,
                "hidden": false,
                "customStyles": {}
            }
        },
        "loanAccountNo": {
            "headerLabel": "Loan Account Number",
            "component": {
                "iComponentType": "formKeyMapComponent",
                "name": "loanAccountNo",
                "label": null,
                "value": null,
                "hidden": false,
                "customStyles": {}
            }
        },
        "sourceName": {
            "headerLabel": "SourceName",
            "component": {
                "iComponentType": "selectComponent",
                "name": "sourceName",
                "label": null,
                "value": null,
                "multiselect": false,
                "disabled": false,
                "readOnly": false,
                "hidden": false,
                "warningFlag": false,
                "warningText": null,
                "validationType": null,
                "options": [],
                "validationRules": [],
                "popUpTitle": null,
                "customStyles": {},
                "placeholder": null,
                "variant": null,
                "inputSize": null,
                "triggerActionsMap": []
            }
        }
    },
    "tableVectorOrdering": [
        "loanAccountNo",
        "name",
        "sourceName"
    ],
    "uniqueKeyName": null,
    "customStyles": {},
    "triggerActionsMap": [],
    "value": [
        {
            "loanAccount": "LAN001",
            "name": "Ash",
            "sourceName": null
        },
        {
            "loanAccount": "LAN002",
            "name": "Brock",
            "sourceName": null
        },
        {
            "loanAccount": "LAN003",
            "name": "Misty",
            "sourceName": null
        }
    ]
}
```

This is how the tableInputComponent will look like inside a UICompositeComponent,

```json
{
    "iComponentType": "formComponentV2",
    "name": "new_lead_form",
    "title": "New lead",
    "schema": {
        "email": {
            "iComponentType": "textInputComponent",
            "name": "email",
            "label": "Email",
            "value": null,
            "disabled": false,
            "readOnly": false,
            "warningFlag": false,
            "warningText": "",
            "validationType": "string",
            "validationRules": [
                {
                    "rule": "nullable",
                    "params": [
                        "true"
                    ]
                },
                {
                    "rule": "email",
                    "params": [
                        "Enter a valid email"
                    ]
                }
            ],
            "customStyles": {
                "marginBottom": "24px"
            },
            "inputAdornment": null,
            "variant": null,
            "inputSize": null,
            "triggerActionsMap": []
        },
        "inputTableExample": {
            "iComponentType": "tableInputComponent",
            "name": "inputTableExample",
            "label": "Table Label",
            "orientation": "ROW_MAJOR",
            "disabled": false,
            "readOnly": false,
            "hidden": false,
            "tableVector": {
                "name": {
                    "headerLabel": "Customer Name",
                    "component": {
                        "iComponentType": "formKeyMapComponent",
                        "name": "name",
                        "label": null,
                        "value": null,
                        "hidden": false,
                        "customStyles": {}
                    }
                },
                "loanAccountNo": {
                    "headerLabel": "Loan Account Number",
                    "component": {
                        "iComponentType": "formKeyMapComponent",
                        "name": "loanAccountNo",
                        "label": null,
                        "value": null,
                        "hidden": false,
                        "customStyles": {}
                    }
                },
                "sourceName": {
                    "headerLabel": "SourceName",
                    "component": {
                        "iComponentType": "selectComponent",
                        "name": "sourceName",
                        "label": null,
                        "value": null,
                        "multiselect": false,
                        "disabled": false,
                        "readOnly": false,
                        "hidden": false,
                        "warningFlag": false,
                        "warningText": null,
                        "validationType": null,
                        "options": [],
                        "validationRules": [],
                        "popUpTitle": null,
                        "customStyles": {},
                        "placeholder": null,
                        "variant": null,
                        "inputSize": null,
                        "triggerActionsMap": []
                    }
                }
            },
            "tableVectorOrdering": [
                "loanAccountNo",
                "name",
                "sourceName"
            ],
            "uniqueKeyName": null,
            "customStyles": {},
            "triggerActionsMap": [],
            "value": []
        }
    },
    "schemaOrder": [
        "email",
        "myTableInput"
    ],
    "uniqueKeyName": "details",
    "customStyles": {},
    "data": {
        "iComponentData": "formData",
        "model": {
            "email": "admin.mail@mail.com",
            "inputTableExample": [
                {
                    "loanAccount": "LAN001",
                    "name": "Ash",
                    "sourceName": null
                },
                {
                    "loanAccount": "LAN002",
                    "name": "Brock",
                    "sourceName": null
                },
                {
                    "loanAccount": "LAN003",
                    "name": "Misty",
                    "sourceName": null
                }
            ]
        }
    },
    "errors": {},
    "warnings": {},
    "options": {
        "inputTableExample.sourceName": [
            {
                "iStaticDataType": "staticData",
                "label": "Agent",
                "value": "AGENT"
            },
            {
                "iStaticDataType": "staticData",
                "label": "Builder",
                "value": "BUILDER"
            }
        ]
    }
}
}
```

**NOTE** how the data for the 'sourceName' selectComponent Options come in FormData options.&#x20;
