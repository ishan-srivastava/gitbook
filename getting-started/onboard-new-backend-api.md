---
coverY: 0
---

# 📝 Onboard new backend API

Use the `api-registry`([GitHub](https://github.cmd.navi-tech.in/medici/wakanda/tree/master/api-registry))> to record a new API. Api registry module is a binder of different backend APIs from which we connect backend data models/DAOs to widget-specific data.

Concluding everything from [Component Downstream Contract](https://navihq.atlassian.net/wiki/spaces/BNKP/pages/456327786), these are the steps needed to be taken to integrate backend API with a UI widget through api-registry,

1. Create a ResponseModelClass which implements component specific `ComponentDataAdpater` interface to convert data into specific `ComponentData`.\
   Here we create an adapter class type based on the downstream API response DAO which returns the widget-specific data according to requirement.
2. Add the REST API as `GenericApi` object in downstream specific `registry`. The Generic API contains all the information that is required to hit the API at runtime. Any external header will get added later at runtime. Here we also mention the adapter class typed in the previous step. If the registry doesn’t exist already, we just need to make a one-time effort to create a new downstream-specific registry service and add our APIs there.

After these steps, we declare a new version of `api-registry` and then use this version in our Wakanda/application and BFF.

\
