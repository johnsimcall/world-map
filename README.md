This is a simple application to demonstrate OpenShift's simplicity.

If you're deploying this app via the OpenShift GUI, make sure you're using
NodeJS version 10.  Version 12 is know to not build properly.  :disappointed:

To compile/build and launch this application in OpenShift simply:

```bash
oc new-project world-map
oc new-app nodejs:10~https://github.com/johnsimcall/world-map.git --name=world-map
oc expose service world-map
oc get route/world-map --template=http://{{.spec.host}}
```

More details can be found in the [Cesium README](README-CesiumJS.md)
