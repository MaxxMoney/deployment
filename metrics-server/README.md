https://github.com/kubernetes-sigs/metrics-server

cd deploy/1.8+


修改metrics-server-deployment.yaml

image: registry.cn-hangzhou.aliyuncs.com/google_containers/metrics-server-amd64:v0.3.6

args:
        - --kubelet-insecure-tls		# 避免x509: cannot validate certificate

        - --kubelet-preferred-address-types=InternalDNS,InternalIP,ExternalDNS,ExternalIP,Hostname

应用deploy中所有文件
kubectl create -f .


https://zhuanlan.zhihu.com/p/84480734
https://github.com/kubernetes-sigs/metrics-server/issues/157