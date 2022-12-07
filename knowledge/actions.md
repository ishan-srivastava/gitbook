---
description: >-
  TODO: Add individual pages for each action: to show how to add it, and what
  all properties it has.
coverY: 0
---

# 🦐 Actions

* Client Handled Actions : This is when we want the client to take control of the process. The callback that is passed to ShuriLink will get the event for which this is added

{% hint style="info" %}
If the trigger to this action is Submit Api Trigger, Client Handled Action can have context to the response, just add \
a. the key as 'data'\
b. the value as '\_response'
{% endhint %}

* Show Toast Action : This is used to inform the client about something needs to be shown as a toast. The "showing of toast" is done by client.

{% hint style="info" %}
If the trigger to this action is Submit Api Trigger, Show Toast  Action can have context to the response, inside the template refer to any key in the response and surround it in '$'. \
Eg : "Great! $\_response.somekey.someOtherKey$ and $\_response.key2.key3$"\

{% endhint %}

* Run Logic Action : This is used to execute a Logic Set that you might have added.
* Post Submit Action :  This action only works when the trigger was 'Submit', it helps you define what further action to take based on response codes of the 'submit'.

