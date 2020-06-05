
```
oc new-app java:8~https://github.com/snandakumar87/sd-customer-eligibility --name=sd-customer-eligibility 
--build-env=NEXUSREPO="http://nexus-nexus.apps.cluster-cc6c.cc6c.example.opentlc.com"

```
Build environment will need to be passed in with the URL for the nexus repo.

```
oc expose svc/sd-customer-eligibility
```

