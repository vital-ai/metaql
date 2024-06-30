# Graph Query



```groovy

GRAPH {
    value segments: ["mydata"]
ARC {
          node_constraint { Email.class }
          constraint { "?person1 != ?person2" }
          ARC_AND {
              ARC {
                edge_constraint { Edge_hasSender.class }
                node_constraint {Person.props().emailAddress.equalTo("john@example.org")
                node_constraint { Person.class }
                node_provides { "person1 = URI" }
             }
              ARC {
                edge_constraint { Edge_hasRecipient.class }
                node_constraint { Person.class }
                node_provides { "person2 = URI" }
             }
          }
        }
    }
```
