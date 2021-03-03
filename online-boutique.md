
output of kubectl -n online-boutique get pods
```
istioctl verify-install
1 Istio control planes detected, checking --revision "default" only
✔ ClusterRole: istiod-istio-system.istio-system checked successfully
✔ ClusterRole: istio-reader-istio-system.istio-system checked successfully
✔ ClusterRoleBinding: istio-reader-istio-system.istio-system checked successfully
✔ ClusterRoleBinding: istiod-istio-system.istio-system checked successfully
✔ Role: istiod-istio-system.istio-system checked successfully
✔ RoleBinding: istiod-istio-system.istio-system checked successfully
✔ ServiceAccount: istio-reader-service-account.istio-system checked successfully
✔ ServiceAccount: istiod-service-account.istio-system checked successfully
✔ ValidatingWebhookConfiguration: istiod-istio-system.istio-system checked successfully
✔ CustomResourceDefinition: destinationrules.networking.istio.io.istio-system checked successfully
✔ CustomResourceDefinition: envoyfilters.networking.istio.io.istio-system checked successfully
✔ CustomResourceDefinition: gateways.networking.istio.io.istio-system checked successfully
✔ CustomResourceDefinition: serviceentries.networking.istio.io.istio-system checked successfully
✔ CustomResourceDefinition: sidecars.networking.istio.io.istio-system checked successfully
✔ CustomResourceDefinition: virtualservices.networking.istio.io.istio-system checked successfully
✔ CustomResourceDefinition: workloadentries.networking.istio.io.istio-system checked successfully
✔ CustomResourceDefinition: workloadgroups.networking.istio.io.istio-system checked successfully
✔ CustomResourceDefinition: authorizationpolicies.security.istio.io.istio-system checked successfully
✔ CustomResourceDefinition: peerauthentications.security.istio.io.istio-system checked successfully
✔ CustomResourceDefinition: requestauthentications.security.istio.io.istio-system checked successfully
✔ CustomResourceDefinition: istiooperators.install.istio.io.istio-system checked successfully
✔ ConfigMap: istio.istio-system checked successfully
✔ Deployment: istiod.istio-system checked successfully
✔ ConfigMap: istio-sidecar-injector.istio-system checked successfully
✔ MutatingWebhookConfiguration: istio-sidecar-injector.istio-system checked successfully
✔ PodDisruptionBudget: istiod.istio-system checked successfully
✔ Service: istiod.istio-system checked successfully
✔ EnvoyFilter: metadata-exchange-1.8.istio-system checked successfully
✔ EnvoyFilter: tcp-metadata-exchange-1.8.istio-system checked successfully
✔ EnvoyFilter: stats-filter-1.8.istio-system checked successfully
✔ EnvoyFilter: tcp-stats-filter-1.8.istio-system checked successfully
✔ EnvoyFilter: metadata-exchange-1.9.istio-system checked successfully
✔ EnvoyFilter: tcp-metadata-exchange-1.9.istio-system checked successfully
✔ EnvoyFilter: stats-filter-1.9.istio-system checked successfully
✔ EnvoyFilter: tcp-stats-filter-1.9.istio-system checked successfully
✔ Deployment: istio-ingressgateway.istio-system checked successfully
✔ PodDisruptionBudget: istio-ingressgateway.istio-system checked successfully
✔ Role: istio-ingressgateway-sds.istio-system checked successfully
✔ RoleBinding: istio-ingressgateway-sds.istio-system checked successfully
✔ Service: istio-ingressgateway.istio-system checked successfully
✔ ServiceAccount: istio-ingressgateway-service-account.istio-system checked successfully
✔ Deployment: istio-egressgateway.istio-system checked successfully
✔ PodDisruptionBudget: istio-egressgateway.istio-system checked successfully
✔ Role: istio-egressgateway-sds.istio-system checked successfully
✔ RoleBinding: istio-egressgateway-sds.istio-system checked successfully
✔ Service: istio-egressgateway.istio-system checked successfully
✔ ServiceAccount: istio-egressgateway-service-account.istio-system checked successfully
Checked 12 custom resource definitions
Checked 3 Istio Deployments
✔ Istio is installed and verified successfully
```

curl http://104.197.166.37/wrongpath
404 page not found

```
kubectl -n online-boutique logs -l app=frontend  -c istio-proxy --tail=1 | jq .
{
  "route_name": "default",
  "bytes_received": 0,
  "request_id": "a8318119-bc68-9c65-bd27-4c1679a0eae3",
  "bytes_sent": 19,
  "user_agent": "curl/7.64.1",
  "response_code": 404,
  "downstream_remote_address": "10.128.0.4:0",
  "response_code_details": "via_upstream",
  "requested_server_name": "outbound_.80_._.frontend.online-boutique.svc.cluster.local",
  "start_time": "2021-03-03T02:02:55.222Z",
  "upstream_cluster": "inbound|8080||",
  "authority": "104.197.166.37",
  "upstream_local_address": "127.0.0.1:33656",
  "response_flags": "-",
  "path": "/wrongpath",
  "upstream_host": "127.0.0.1:8080",
  "method": "GET",
  "duration": 1,
  "downstream_local_address": "10.104.1.6:8080",
  "upstream_transport_failure_reason": null,
  "connection_termination_details": null,
  "upstream_service_time": "0",
  "protocol": "HTTP/1.1",
  "x_forwarded_for": "10.128.0.4"
}
```
