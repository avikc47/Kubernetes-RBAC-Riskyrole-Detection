# Automated detection of Risky Permissions in Kubernetes Clusters
 

ExtensiveRoleCheck.py is a Python tool that scans the Kubernetes RBAC for risky roles.

Requirements:
ExtensiveRoleCheck requires python3

ExtensiveRoleCheck works in offline mode. This means that you should first export the following JSON from your Kubernetes cluster configuration:

Roles
ClusterRoles
RoleBindings
ClusterRoleBindings
To export those files you will need access permissions in the Kubernetes cluster. To export them, you might use the following commands: 

Export RBAC Roles:

kubectl get roles --all-namespaces -o json > Roles.json

Export RBAC ClusterRoles:

kubectl get clusterroles -o json > clusterroles.json

Export RBAC RolesBindings:

kubectl get rolebindings --all-namespaces -o json > rolebindings.json

Export RBAC Cluster RolesBindings:

kubectl get clusterrolebindings -o json > clusterrolebindings.json


Usage

python ExtensiveRoleCheck.py --clusterRole clusterroles.json  --role Roles.json --rolebindings rolebindings.json --cluseterolebindings clusterrolebindings.json
Output example
