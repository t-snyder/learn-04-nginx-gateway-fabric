# Learn-04-Nginx-Gateway-Fabric

## Nginx Gateway Fabric Documentation Used
  1. https://docs.nginx.com/nginx-gateway-fabric/installation/installing-ngf/manifests/
  2. https://docs.nginx.com/nginx-gateway-fabric/how-to/traffic-management/routing-traffic-to-your-app/
  3. https://docs.nginx.com/nginx-gateway-fabric/how-to/traffic-management/tls-passthrough/
  
## Project Summary
The reason for testing the Nginx Gateway Fabric (NGF) is that it provides a GA implementation of a 
Gateway Controller Implementation. Other projects in this series use the Istio implemenation which is
also GA. The purpose was to review the functionality provided to determine is there were any
significant differences making one more attractive than the other. 

Based upon the results of working on this prototype with Nginx Gateway Fabric I found that I
personnally prefer the Istio implementation. The major reason for this is that the NGF only supports
a single Gateway per kubernetes cluster, whereas Istio supports multiple Gateways within a cluster.

See the GatewayClass - https://docs.nginx.com/nginx-gateway-fabric/overview/gateway-api-compatibility/

## Project Implemenation
The project scripts deploy the Kubernetes Gateway API CRDs and then the Nginx Gateway Fabric 
CRDs. After this it deploys the sample cafe app found within the documentation above into the
default namespace. After the sample app deployment the Apple HTTP Echo app is deployed, also to
the default namespace. Tests of these deployments use curl.

Due to the limitation of a single Gateway Class instance, no further work was done on extending
this prototype.

