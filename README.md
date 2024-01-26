you can docker build & push, kubernetes deploy with this pipeline.

# gitlab-agent install

on gitlab project page

Infrastructure > Kubernetes > Connect cluster with agent

<img width="1208" alt="image" src="https://github.com/alperen-selcuk/gitlab-cicd-gitlabagent/assets/78741582/ba5efbed-d470-4841-8a3e-5fc20d7ff8ef">

you can create new agent

<img width="797" alt="image" src="https://github.com/alperen-selcuk/gitlab-cicd-gitlabagent/assets/78741582/8723c667-e9e0-4670-a636-86559bfb8b14">

type a name and create agent. after that click register

<img width="633" alt="image" src="https://github.com/alperen-selcuk/gitlab-cicd-gitlabagent/assets/78741582/2c7ad2c2-5412-4562-92fb-79cd4e4d6552">

gitlab gave you token and helm command to install gitlab-agent

# gitlab-agent clusterrole

i recommend that gave gitlab-agent cluster-admin so you can deploy easily with permission.

```
kubectl create clusterrolebinding gitlab-agent --clusterrole=cluster-admin --serviceaccount=gitlab-agent:gitlab-agent -n gitlab-agent
```

# use kubernetes context

after installation and give permission you can use pipeline your kubernetes cluster.

```
kubectl config use-context "groupname/projectname:kubernetesconnectname"
```
