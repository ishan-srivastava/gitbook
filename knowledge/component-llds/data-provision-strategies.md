# 🕵♂ Data Provision Strategies

## NoFetchStaticStrategy

Use this strategy type if you want your Widget doesn't need any data from a down stream resource. Choosing this option will enable you to enter defaults or static values for your widget in Black Panther.

```json
{
    "iSlotType": "widgetSlot",
    "id": "23",
    "parentId": "34",
    "widget": {
        "iComponentType": "textInputComponent",
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
    },
    "dataProvisionStrategy": {
        "provisionType": "noFetchStaticStrategy"
    },
    "hidden": false,
    "layoutParams": {},
    "customStyles": {}
}
```
