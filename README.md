you can docker build & push, kubernetes deploy with this pipeline.

# pre-request

gitlab kubernetes connection     
gitlab runner host

# gitlab-agent install

helm repo add gitlab https://charts.gitlab.io  
helm repo update
helm upgrade --install gitlab-agent gitlab/gitlab-agent  \
--namespace gitlab-agent --create-namespace \
--set config.token=< gitlab kubernetes connection token > \
--set config.kasAddress=wss://< your gitlab address >/-/kubernetes-agent
