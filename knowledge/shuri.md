---
coverY: 0
---

# 🐞 Shuri

#### Passing path params/addtional headers to Shuri?

There would be a use case where you would just want to add some data to the path of the api endpoint that Shuri would hit, you have the data on the client, but you want to the endpoint to consume that data and generate dynamic URL.\
Or you would want to provide additional headers to your request.\
\
You can do that via `apiOptions` prop

```
apiOptions : {
  additionalHeaders?: Record<string, any>;
  pathReplacementMap?: Record<string, any>;
}
```

* `additionalHeaders` : map that you can send to the ShuriLink component, and it will be appended to all the requests originating from that instance of ShuriLink
* `pathReplacementMap`  : map that you can send to the shuriLink component, and it will replace the occurrence on all outgoing API's from that that instance of ShuriLink.\
  We need to wrap our `key` with the pattern <mark style="color:red;">\_</mark>_<mark style="color:red;">client\_map\_</mark>_ . For eg, if my pathReplacementMap has a key called "customerId", then wherever in my API endpoint I want to replace it I will add the pattern <mark style="color:red;">\_client\_map\_customerId\_client\_map\_.</mark> \ <mark style="color:red;"></mark>This also holds true while writing SubmitActions or ApiCallActions .

```javascript
const clientApiOptions = 
{
  "pathReplacementMap": {
    "customerId": "123123123"
  },
  "additionalHeaders": {
    "key1": "val1"
  }
}



<ShuriLink 
endpoint={"https://someUrl.com/mock/_client_map_customerId_client_map_"} 
callback={onShuriCallback}
apiOptions={clientApiOptions} 
/>
```

\
