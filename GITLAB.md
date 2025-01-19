Récup du repo : https://github.com/srozange/create-k3d-cluster

Commandes :

export CLUSTER_NAME=gitlab
scripts/k3d.sh setup

** Installation de gitlab **

helm repo add gitlab https://charts.gitlab.io/
helm repo update
helm upgrade --install gitlab gitlab/gitlab --timeout 600s --set global.hosts.domain=my-gitlab.com --set certmanager-issuer.email=gitlab@my-gitlab.com --set global.edition=ce --namespace gitlab --create-namespace

** MAJ du host **

127.0.0.1 gitlab.my-gitlab.com
127.0.0.1 minio.my-gitlab.com
127.0.0.1 registry.my-gitlab.com
127.0.0.1 kas.my-gitlab.com