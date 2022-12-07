---
description: >-
  The agenda will be to make a simple form that takes in name, sends it to API.
  If the response is successful, show certain UI, else show an error UI.
coverY: 0
---

# ⛑ Adding Logics



* Make a simple form having a text field add a button to it, like mentioned in [simple-form.md](simple-form.md "mention").

<figure><img src="../../.gitbook/assets/ezgif.com-gif-maker (16).gif" alt=""><figcaption><p>simple form creation </p></figcaption></figure>

*   Next,  add a typography widget like shown.

    <figure><img src="../../.gitbook/assets/ezgif.com-gif-maker (17).gif" alt=""><figcaption><p>adding the typography widget</p></figcaption></figure>
*   ### Let's start with the logic part.

    Here is what we would want to do
* Add a trigger to the submit button  _"Submit Api Trigger"_ , as we know this will give the feature of for data submission to a API.
* After the submit, \
  a. If success, we would like to show the message from the API in the typography widget.\
  b. If failed we would like to show "FORM SUBMIT FAILED", message.
* Let's make a logic set for the Success case first.\
  a. First we add a name to this logic\
  b. Then click on `+ Add mapping set`

<figure><img src="../../.gitbook/assets/ezgif.com-gif-maker (18).gif" alt=""><figcaption></figcaption></figure>
