---
coverY: 0
---

# 🌵 Setup on React Project

The client will have to add _Shuri_ as a npm dependency and use it to render the pages configured on the dashboard.\
First we will install _Shuri_ in the client project.

```
npm i @navi/shuri
```

`Also install the peer-deps if not already installed in the client.`

```
npm i @navi/web-ui react-hook-form yup @hookform/resolvers regex-parser
```

***

Now, in the component where you want to use Neon, we just need to import _Shuri_ and use it as shown here -

```
... other imports ....
import { ShuriLink } from "@navi/shuri";

// We are passing an endpoint to Shuri (the URL mentioned while configuring the page)
// and a client callback for error/success etc communication, more details below

function onShuriCallback(name: string, payload: any){
  console.log("NAME OF SHURI EVENT RECEIVED", name, payload);
}

const endpoint : string =  <some absolute url of the config>
const payload : Record<string, any> = {"name": "shuri"}
function App() {
  return (
    <ShuriLink endpoint={endpoint} callback={onShuriCallback} payload={payload}/>
  );
}

export default App;

```

}

**About the Props :**

> `endpoint` : We are passing an endpoint to _Shuri_ (the URL mentioned while configuring the page) and a client callback for error/success etc communication.
>
> Note - endpoint must be an absolute URL - ${BFF\_LAYER\_BASE\_URL}/${URL\_MENTIONED\_ON\_DASHBOARD}
>
> BFF\_LAYER\_BASE\_URL = [https://dev-crm-web-bff.np.navi-sa.in](https://dev-crm-web-bff.np.navi-sa.in)
>
> So, in our case endpoint turns out to be - [https://dev-crm-web-bff.np.navi-sa.in/sample-form](https://dev-crm-web-bff.np.navi-sa.in/sample-form)

***

> `callback` : when a trigger is configured to be handled by the client, the that callback is received in the **callback** prop, having the event name and the payload

***

> `payload` : `Record<string, any>` optional prop to pass in as a payload to the request made on the endpoint prop.

> `apiOptions` &#x20;
