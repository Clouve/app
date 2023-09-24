### Release 3.2.3:

- Remove Delete button for expired deployments to fix already paused issue
- Allow Cancel Subscription option for an active deployment (will pause)
- Allow subscribe after cancel (will resume)
- Allow authorized user deletion for orgs - Disable user instead to maintain history - Not Doable
- Subscription email address should come from the user (not the org) - Works as expected
- Pause should scale down StatefulSets as well
- FTA -> View deployments and support by client
