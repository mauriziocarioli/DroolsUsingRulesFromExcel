Drools Using Rules From Excel
=============================

Applying discounts to customers using Drools spreadsheets. Adapted from https://www.baeldung.com/drools-excel

Execute with the POST REST API http://localhost:8080/kie-server/services/rest/server/containers/instances/DroolsUsingRulesFromExcel_1.0.0

with body

{
    "lookup": "customerdiscount-stateless-ksession",
    "commands": [
        {
            "insert": {
                "object": {
                    "com.baeldung.drools.model.Customer": {
                        "type": "INDIVIDUAL",
                        "years": 5,
                        "discount": 0
                    }
                },
                "out-identifier": "customer",
                "return-object": true
            }
        },
        {
            "fire-all-rules": {}
        },
        {
            "dispose": {}
        }
    ]
}

