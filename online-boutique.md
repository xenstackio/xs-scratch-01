
output of kubectl -n online-boutique get pods
```
root@kubernetes1:~/istio-1.9.1/online-boutique# kubectl -n online-boutique get pods
NAME                                     READY   STATUS    RESTARTS   AGE
adservice-7659d48d84-c664r               2/2     Running   0          2m2s
cartservice-65c987d449-9lgkh             2/2     Running   2          2m3s
checkoutservice-8bddb89db-l4rt8          2/2     Running   0          2m3s
currencyservice-7978fb77d8-9dw92         2/2     Running   0          2m2s
emailservice-8848674-2pcjh               2/2     Running   0          2m3s
frontend-58594bf684-gdsvq                2/2     Running   0          2m3s
paymentservice-77979f5c66-jlxgr          2/2     Running   0          2m3s
productcatalogservice-7d5f94d858-krbwt   2/2     Running   0          2m2s
recommendationservice-764dc66688-jpwfj   2/2     Running   0          2m3s
redis-cart-74594bd569-gtg7j              2/2     Running   0          2m2s
shippingservice-589dc45c5d-zmjb2         2/2     Running   0          2m2s
root@kubernetes1:~/istio-1.9.1/online-boutique#
```
