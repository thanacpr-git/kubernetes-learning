# kubernetes-learning
Export manifest from existing deployment in clean version ( without timestamp , other non -related detail )

kubectl get deployment guestbook-ui  -n team-riker -o=json | jq 'del(.metadata.resourceVersion,.metadata.uid,.metadata.selfLink,.metadata.creationTimestamp,.metadata.annotations,.metadata.generation,.metadata.ownerReferences,.status)' | yq eval . --prettyPrint
