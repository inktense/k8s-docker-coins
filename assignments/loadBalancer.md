## Objectives:

    We need to create two deployments: 
    one for v1 (NGINX), another for v2 (Apache).
    They will be exposed through a single service.
    The selector of that service will need to match the pods created by *both* deployments.
    For that, we will need to change the deployment specification to add an extra label, to be used solely by the service.
    That label should be different from the pre-existing labels of our deployments, otherwise, our deployments will step on each other's toes.
    We're not at the point of writing our own YAML from scratch, so you'll need to use the kubectl edit command to modify existing resources.

### Steps for the assignment:

Create the 2 deployments:
``` bash
k create deployment v1 --image nginx
k create deployment v2 --image httpd

k create service nodeport v1 --tcp=80


k edit service/v1

k edit deployment.apps/v1
k edit deployment.apps/v2
```
    