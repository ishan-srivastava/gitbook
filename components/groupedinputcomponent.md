# 👫 GroupedInputComponent

Presenting LLD for GroupedInputComponent. This component is built to give grouping and nesting support to Composite components.\
\
eg. When you need an address details section in your form, there is an obvious need of something which binds all the fields related to that address as they make more sense as a group rather than an individual element.\
\
**Important:** A thing to note here is that now element access notation to components inside the groupedInputComponent will be like permanentAddress.line1 wrt example posted below.\


### V2

```json
{
    "iComponentType": "groupedInputComponentV2",
    "name": "inputGroup1",
    "label": "Group Fields",
    "disabled": false,
    "readOnly": false,
    "hidden": false,
    "warningFlag": false,
    "warningText": null,
    "schema": {
        "text": {
            "iComponentType": "textInputComponent",
            "name": "text",
            "label": null,
            "value": null,
            "disabled": false,
            "readOnly": false,
            "warningFlag": false,
            "warningText": null,
            "validationType": null,
            "validationRules": [],
            "customStyles": {},
            "inputAdornment": null,
            "variant": null,
            "inputSize": null,
            "triggerActionsMap": []
        },
        "myNumber": {
            "iComponentType": "numberInputComponent",
            "name": "myNumber",
            "label": null,
            "value": null,
            "disabled": false,
            "readOnly": false,
            "warningFlag": false,
            "warningText": null,
            "validationType": null,
            "validationRules": [],
            "customStyles": {},
            "inputAdornment": null,
            "variant": null,
            "inputSize": null,
            "triggerActionsMap": []
        }
    },
    "schemaOrder":["myNumber","text"],
    "customStyles": {},
    "triggerActionsMap": []
}
```

### V1

```json
{
    "iComponentType": "groupedInputComponent",
    "type": null,
    "name": "permanentAddress",
    "label": "Group Fields",
    "disabled": false,
    "readOnly": false,
    "hidden": false,
    "warningFlag": false,
    "warningText": null,
    "schema": [
        {
            "iComponentType": "textInputComponent",
            "name": "line1",
            "label": null,
            "value": null,
            "disabled": false,
            "readOnly": false,
            "warningFlag": false,
            "warningText": null,
            "validationType": null,
            "validationRules": [],
            "customStyles": {},
            "inputAdornment": null,
            "variant": null,
            "inputSize": null,
            "triggerActionsMap": []
        },
        {
            "iComponentType": "numberInputComponent",
            "name": null,
            "label": null,
            "value": null,
            "disabled": false,
            "readOnly": false,
            "warningFlag": false,
            "warningText": null,
            "validationType": null,
            "validationRules": [],
            "customStyles": {},
            "inputAdornment": null,
            "variant": null,
            "inputSize": null,
            "triggerActionsMap": []
        }
    ],
    "customStyles": {}
}
```

And the data shall be present inside the composite components' data portion as follows,

```json
{
  "permanentAddress" : {
    "line1" : "",
    ...
  },
  ...
}
```
