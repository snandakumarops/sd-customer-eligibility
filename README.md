
```
oc new-app java:8~https://github.com/snandakumar87/sd-customer-eligibility --name=sd-customer-eligibility 
--build-env=NEXUSREPO="http://nexus-nexus.apps.cluster-cc6c.cc6c.example.opentlc.com"

```
Build environment will need to be passed in with the URL for the nexus repo.

```
oc expose svc/sd-customer-eligibility
```

Swagger can be found at: ```{URL}/swagger-ui```

Sample Request for Evaluate Eligibility
```
POST<customer-product-eligibility-url>/customer-product-service-eligibility/CEAEA1234/customer-eligibility-assessment/evaluation
{
      "data": {
        "customerEligibilityAssessmentEvaluateActionRecord": {},
        "customerEligibilityAssessmentInstanceRecord": {
         "customerReference":"CUST5678",
         "productServiceType":"e-Wallet"
        }
      }
    }
```

Sample Request for Update Customer Eligibility(Product usage)

```
PUT http://localhost:8081/customer-product-service-eligibility/SD22323/customer-eligibility-assessment/CR23242/update
{
  "data": {
    "customerEligibilityAssessmentInstanceRecord": {
      
      "customerReference": "CUST789",
      "productServiceType": "e-wallet"
    },
    "customerEligibilityAssessmentInstanceReference": "string",
    "customerEligibilityAssessmentUpdateActionTaskRecord": {},
    "customerProductServiceEligibilityServicingSessionReference": "string",
    "date": "string",
    "updateActionRequest": "string"
  }
}
```
