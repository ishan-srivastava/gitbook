---
description: >-
  The agenda will be to make a form, with validations, that takes in a
  buildernname and selected project, and then sends the data to an endpoint.
coverY: 0
---

# 💾 Simple Form

* First Lets make a new page on our application. Create on 'Create Page' button and enter the basic details about there config.
* Fill in the page details - `Page URL`, `title,` and `description` and click on create button. Now you will be able to see the playground to create widgets

<figure><img src="../../.gitbook/assets/ezgif.com-gif-maker (8).gif" alt=""><figcaption></figcaption></figure>

*   Click on the add widget button and configure your widget by entering the following details - `name`, `title,` and `provision type`.

    _<mark style="color:red;">Provision type is used to declare the data stubbing APIs on the BFF layer for a particular widget. For Example - APIs to get options for the select widgets (In our case - projects of a builder).</mark>_
*   Select the form widget



    <figure><img src="../../.gitbook/assets/ezgif.com-gif-maker (11).gif" alt=""><figcaption></figcaption></figure>
* Add sub widgets by clicking on the add sub widget button.
* Select the `text input` widget (for builder name) and fill in the required details. Similarly, select a `select widget` (for builder projects)
*   You can add custom styling and input field validations(We currently support Yup validation) as per requirement. Please refer to the screenshots below.

    _<mark style="color:yellow;">Custom styles have to be a valid React inlineStyle objects like</mark> <mark style="color:yellow;"></mark><mark style="color:yellow;">`{"marginTop": "10px"}`</mark>_

    _<mark style="color:yellow;"></mark>_

_<mark style="color:yellow;"></mark>_

<figure><img src="../../.gitbook/assets/ezgif.com-gif-maker (12).gif" alt=""><figcaption><p>Adding text input fields</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/ezgif.com-gif-maker (13) (1).gif" alt=""><figcaption><p>adding a desktop select</p></figcaption></figure>

* Now add a `button` widget ( **just like we added input and dropdown widgets )** for the form to save you from responses.Next is configuring the button behaviour, for this you need to understand about [actions.md](../../knowledge/actions.md "mention") and [triggers.md](../../knowledge/triggers.md "mention").

<figure><img src="../../.gitbook/assets/ezgif.com-gif-maker (15).gif" alt=""><figcaption><p>Adding button</p></figcaption></figure>

*   **NB** [**💬**](https://emojipedia.org/speech-balloon/) - Actions are called in the **order in which it is defined** on the dashboard

    The form is now configured and ready for the user. Please **preview** your changes and click on the **save** **page** button&#x20;
