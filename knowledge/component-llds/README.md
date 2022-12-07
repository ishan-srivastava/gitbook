---
coverY: 0
---

# 🍧 Component LLDs

* WidgetSlot Update
* TypographyComponent
* MapDisplayComponent
* FormKeyMapComponent (Reusable in UICompositeComponent’s schema)
* Button Component
* Icon Component
* SliderInputComponent
* MobileSelectComponent
* SelectInputComponent
* RadioInputComponent
* New Schema for triggers and behaviours

#### WidgetSlot Update <a href="#componentlld-widgetslotupdate" id="componentlld-widgetslotupdate"></a>

```
// One with downstream fetch
{
    "iSlotType": "widgetSlot",
    "id": "23",
    "parentId": "34",
    "widget": {
        "iComponentType": "textInputComponent",
        "type": "INPUT",
        "subtype": "TEXT",
        "name": null,
        "label": null,
        "value": null,
        "disabled": false,
        "readOnly": false,
        "warningFlag": false,
        "warningText": null,
        "validationType": null,
        "validationRules": [],
        "customStyles": {}
    },
    "dataProvisionStrategy": {
        "provisionType": "singleApiFetch",
        "dataProviderServiceName": "lead-manager-service",
        "dataProviderApiPlaceholder": "apiPlaceHolder"
    },
    "layoutParams": {}
}


// One with No Api Request Data Adapt Logic 
{
    "iSlotType": "widgetSlot",
    "id": "23",
    "parentId": "34",
    "widget": {
        "iComponentType": "textInputComponent",
        "type": "INPUT",
        "subtype": "TEXT",
        "name": null,
        "label": null,
        "value": null,
        "disabled": false,
        "readOnly": false,
        "warningFlag": false,
        "warningText": null,
        "validationType": null,
        "validationRules": [],
        "customStyles": {}
    },
    "dataProvisionStrategy": {
        "provisionType": "noFetchRequestMapping",
        "requestAdapterPlaceholderName": "placeholderString"
    },
    "layoutParams": {}
}
```

#### TypographyComponent <a href="#componentlld-typographycomponent" id="componentlld-typographycomponent"></a>

```
{
    "iComponentType": "typographyComponent",
    "name": "textField",
    "variant": "display",
    "as": "p",
    "value": "value as text",
    "customStyles": {}
}
```

#### MapDisplayComponent <a href="#componentlld-mapdisplaycomponent" id="componentlld-mapdisplaycomponent"></a>

```
{
    "iComponentType": "mapDisplayComponent",
    "name": "displayProperties",
    "label": "Show Properties",
    "hidden": false,
    "fieldOrder": [
        {
            "key": "key1",
            "label": "Label 1"
        },
        {
            "key": "key2",
            "label": "Label 2"
        }
    ],
    "data": {
        "iComponentData": "mapDisplayData",
        "model": {
            "key1": "value1",
            "key2": "value2"
        }
    },
    "customStyles": {
        "customStyle": "UI Component default implementation"
    }
}
```

#### FormKeyMapComponent (Reusable in UICompositeComponent’s schema) <a href="#componentlld-formkeymapcomponent-reusableinuicompositecomponentsschema" id="componentlld-formkeymapcomponent-reusableinuicompositecomponentsschema"></a>

```
{
    "iComponentType": "formKeyMapComponent",
    "name": "formElementKey",
    "label": "Label",
    "value": "value",
    "hidden": false,
    "customStyles": {}
}
```

#### Button Component <a href="#componentlld-buttoncomponent" id="componentlld-buttoncomponent"></a>

```
{
    "iComponentType": "buttonComponent",
    "name": "myButton",
    "label": "Click Me !",
    "variant": "primary",
    "disabled": false,
    "size": "small",
    "fullWidth": false,
    "className": "myButtonClass",
    "customStyles": {},
    "triggerActionsMap": []
}
```

***

#### Icon Component <a href="#componentlld-iconcomponent" id="componentlld-iconcomponent"></a>

Icons supported have similar json, only iComponentType value changes,

Support icons right now are → checkIcon, closeIcon, cancelIcon

```
{
    "iComponentType": "checkIcon",
    "name": "myCheckIcon",
    "size": "lg",
    "width": null,
    "height": "50",
    "color": null,
    "customStyles": {}
}
```

***

#### SliderInputComponent <a href="#componentlld-sliderinputcomponent" id="componentlld-sliderinputcomponent"></a>

```
{
    "iComponentType": "sliderInputComponent",
    "name": "sliderInput",
    "label": "Label",
    "value": null,
    "disabled": false,
    "hidden": false,
    "showInput": false,
    "handleOutOfRangeInput": true,
    "sliderMinValue": 0,
    "sliderMaxValue": 104.34,
    "sliderStepSize": null,
    "errorText": null,
    "validationType": null,
    "validationRules": [],
    "customStyles": {},
    "leftInputAdornment": "Rs",
    "rightInputAdornment": null
}
```

***

#### MobileSelectComponent <a href="#componentlld-mobileselectcomponent" id="componentlld-mobileselectcomponent"></a>

```
{
    "iComponentType": "mobileSelectComponent",
    "customStyles": {},
    "name": "mobileSelect",
    "label": "LAbel",
    "value": null,
    "disabled": false,
    "readOnly": false,
    "warningFlag": false,
    "hidden": false,
    "warningText": null,
    "validationType": null,
    "options": [
        {
            "iStaticDataType": "staticData",
            "label": "Option 1",
            "value": "option1"
        },
        {
            "iStaticDataType": "staticData",
            "label": "Option 2",
            "value": "option2"
        }
    ],
    "validationRules": [],
    "popUpTitle": "Select Option",
    "fullWidth": false,
    "variant": "BORDERLESS" // or BORDERED
}
```

***

#### SelectInputComponent <a href="#componentlld-selectinputcomponent" id="componentlld-selectinputcomponent"></a>

```
{
    "iComponentType": "selectComponent",
    "name": "selectComponent",
    "label": "Label",
    "value": null,
    "multiselect": false,
    "disabled": false,
    "readOnly": false,
    "hidden": false,
    "warningFlag": false,
    "warningText": null,
    "validationType": null,
    "options": [
        {
            "iStaticDataType": "staticData",
            "label": "Option 1",
            "value": "option1"
        },
        {
            "iStaticDataType": "staticData",
            "label": "Option 2",
            "value": "option2"
        }
    ],
    "validationRules": [],
    "popUpTitle": null,
    "customStyles": {}
}
```

***

#### RadioInputComponent <a href="#componentlld-radioinputcomponent" id="componentlld-radioinputcomponent"></a>

```
{
    "iComponentType": "radioInputComponent",
    "name": "radioGroupInput",
    "label": "Label",
    "value": null,
    "disabled": false,
    "readOnly": false,
    "hidden": false,
    "warningFlag": false,
    "warningText": null,
    "validationType": null,
    "validationRules": [],
    "options": [
        {
            "iStaticDataType": "staticData",
            "label": "Option 1",
            "value": "option1"
        },
        {
            "iStaticDataType": "staticData",
            "label": "Option 2",
            "value": "option2"
        }
    ],
    "customStyles": {}
}
```

#### New Schema for triggers and behaviours <a href="#componentlld-newschemafortriggersandbehaviours" id="componentlld-newschemafortriggersandbehaviours"></a>

```
[
    {
        "trigger": {
            "iTriggerName": "mouseEvent",
            "type": "onClick"
        },
        "actions": [
            {
                "iActionName": "CLIENT_HANDLED_EVENT",
                "callBackEventName": "EVENT_NAME",
                "callBackPayload": {
                    "prop1": "value1"
                }
            },
            {
                "iActionName": "SHURI_COMMUNICATION_ACTION",
                "applicableCommunicationSetNames": [
                    "set1",
                    "set2"
                ]
            },
            {
                "iActionName": "SHOW_TOAST_ACTION",
                "type": "success",
                "template": "Static message on Toast"
            }
        ]
    },
    {
        "trigger": {
            "iTriggerName": "onSubmit",
            "submitApi": {
                "apiVersion": "v1",
                "method": "POST",
                "uri": "/submit-here"
            }
        },
        "actions": [
            {
                "iActionName": "POST_SUBMIT_RESPONSE_ACTION",
                "responseActions": [
                    {
                        "responseCodes": [
                            "2XX",
                            "200",
                            "201"
                        ],
                        "applicableActions": [
                            {
                                "iActionName": "SHURI_COMMUNICATION_ACTION",
                                "applicableCommunicationSetNames": [
                                    "set1",
                                    "set2"
                                ]
                            },
                            {
                                "iActionName": "SHOW_TOAST_ACTION",
                                "type": "success",
                                "template": "Static message on Toast"
                            }
                        ]
                    }
                ]
            }
        ]
    }
]
```
