---
coverY: 0
---

# 🔥 Mapping Set

It has the following information

* Source Object : It's a reference to the entire slot(or response) object, that will act as the source of the information.
* Target Object : It's a reference to the entire slot object, that will act as the consumer of the information.
* Mappings : They have the information that what property has to be accessed from the source and target, and what values have to be assigned in them.

#### There are 2 types of Mappings that can be added in a mapping set

* Direct Mapping :  Sometimes you have a pre-decided value that you just want to set into the target object. It does not need you to fetch a value from a source object. For eg you want to set the _<mark style="color:yellow;">hidden</mark>_ property of the source to _<mark style="color:yellow;">true</mark>_. <mark style="color:red;">**So it does not matter what is the source object you have selected for direct mapping.**</mark>
* Referential Mapping : Unlike Direct Mapping, in this, you actually want to copy a value from the source object, and paste it to the target object.

#### Each Mappings will have these informations:

* Target Property : Now, inside the target object, there has to be specific thing, that you would want to change. For instance if the slot is a widget slot, having a typography widget, you might want to change its text, on some other time, you might want to change its style.\
  So target property is the "actual thing" on the target slot, that you would change.
* Source Property \[<mark style="color:purple;">**Only valid in Referential Mapping**</mark>] : Just like target property, source property is the property that you would like to be "copied" to the target. For instance if the source is '\_response', then you might want to copy the message key from response to a typography widget. So the target property is the '_message_'.
* Target Value \[<mark style="color:purple;">**Only valid in Direct Mapping**</mark>] : In direct mapping, you would like to set a value to the target property. The "value" is the target value.

#### Some unique target objects

1. <mark style="color:green;">**`_reponse`**</mark> : you need to select this as target object, when \
   a. you have the trigger selected as  _<mark style="color:orange;">Submit Api Action</mark>_. \
   b. You want to refer to the reponse of the submit API as a source of the information transfer\
   c. You are adding a referential mapping.
