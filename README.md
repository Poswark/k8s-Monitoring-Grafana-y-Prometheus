# k8s-Monitoring-Grafana-y-Prometheus
Kubernetes cluster monitoring.


[root@k8s-master1]# kubectl create ns monitoring
namespace/monitoring created
cd.
[root@k8s-master1]# kubectl create -f .
clusterrole.rbac.authorization.k8s.io/prometheus created
clusterrolebinding.rbac.authorization.k8s.io/prometheus created
configmap/prometheus-server-conf created
deployment.apps/prometheus-deployment created
service/prometheus-service created


[root@k8s-master1 kubernetes-grafana]# kubectl create  -f .
deployment.apps/grafana created
configmap/grafana-datasources created
service/grafana created

Pods
[root@k8s-master1 ~]# kubectl get pods -n monitoring
NAME                                     READY   STATUS    RESTARTS   AGE
grafana-548fdc7598-ns6kr                 1/1     Running   0          37s
prometheus-deployment-54686956bd-hvcjj   1/1     Running   0          6m59s

[root@k8s-master1 ~]# kubectl get svc -n monitoring
NAME                 TYPE       CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
grafana              NodePort   10.111.45.132    <none>        3000:32150/TCP   51s
prometheus-service   NodePort   10.105.135.187   <none>        8080:32100/TCP   7m13s
[root@k8s-master1 ~]# 



