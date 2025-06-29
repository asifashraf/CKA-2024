# Kubectl Commands

This document provides a comprehensive list of `kubectl` commands for interacting with Kubernetes clusters. The commands are organized by category for ease of reference. Each command includes a brief description of its purpose.

## Cluster Management
1. **kubectl cluster-info**  
   Displays the cluster information, including the Kubernetes control plane and add-ons endpoints.

2. **kubectl version**  
   Shows the client and server versions of Kubernetes.

3. **kubectl api-versions**  
   Lists the API versions supported by the cluster.

4. **kubectl api-resources**  
   Displays the available API resources in the cluster, including their names, short names, and whether they are namespaced.

5. **kubectl config view**  
   Shows the current kubeconfig settings.

6. **kubectl config get-contexts**  
   Lists all available contexts in the kubeconfig.

7. **kubectl config use-context <context-name>**  
   Switches to the specified context in the kubeconfig.

8. **kubectl config set-cluster <cluster-name>**  
   Sets a cluster entry in the kubeconfig.

9. **kubectl config set-context <context-name>**  
   Sets a context entry in the kubeconfig.

10. **kubectl config set-credentials <user-name>**  
    Sets a user entry in the kubeconfig.

11. **kubectl config delete-cluster <cluster-name>**  
    Deletes the specified cluster from the kubeconfig.

12. **kubectl config delete-context <context-name>**  
    Deletes the specified context from the kubeconfig.

## Resource Management
13. **kubectl get <resource>**  
    Lists resources (e.g., pods, services, deployments) in the current namespace. Use `--all-namespaces` for all namespaces.

14. **kubectl describe <resource> <name>**  
    Shows detailed information about a specific resource.

15. **kubectl create <resource>**  
    Creates a resource from a file or stdin (e.g., `kubectl create -f file.yaml`).

16. **kubectl apply <resource>**  
    Applies a configuration to a resource by file or stdin, creating or updating as needed.

17. **kubectl edit <resource> <name>**  
    Edits a resource directly in the cluster using the default editor.

18. **kubectl delete <resource> <name>**  
    Deletes a specified resource.

19. **kubectl replace <resource>**  
    Replaces a resource with a new configuration from a file or stdin.

20. **kubectl patch <resource> <name>**  
    Updates specific fields of a resource using a patch (e.g., JSON or strategic merge patch).

21. **kubectl label <resource> <name> <key>=<value>**  
    Adds or updates labels on a resource.

22. **kubectl annotate <resource> <name> <key>=<value>**  
    Adds or updates annotations on a resource.

23. **kubectl set <attribute> <resource> <name>**  
    Sets specific attributes (e.g., image, resources) on a resource (e.g., `kubectl set image deployment/myapp`).

## Pod Management
24. **kubectl run <name> --image=<image>**  
    Creates and runs a pod with the specified image.

25. **kubectl exec <pod-name> [-c <container>] -- <command>**  
    Executes a command inside a container in a pod.

26. **kubectl logs <pod-name> [-c <container>]**  
    Retrieves the logs of a pod or a specific container.

27. **kubectl port-forward <pod-name> <local-port>:<pod-port>**  
    Forwards a local port to a port on a pod.

28. **kubectl attach <pod-name> [-c <container>]**  
    Attaches to a running container in a pod to interact with its stdin/stdout.

29. **kubectl cp <pod-name>:/path/to/remote /path/to/local**  
    Copies files or directories to/from a pod.

## Deployment and Scaling
30. **kubectl scale <resource> <name> --replicas=<count>**  
    Scales the number of replicas for a deployment, replica set, or stateful set.

31. **kubectl rollout status <resource> <name>**  
    Checks the status of a rollout for a deployment or daemonset.

32. **kubectl rollout history <resource> <name>**  
    Views the rollout history of a deployment.

33. **kubectl rollout undo <resource> <name>**  
    Rolls back a deployment to the previous revision.

34. **kubectl rollout restart <resource> <name>**  
    Restarts a deployment by triggering a new rollout.

35. **kubectl autoscale <resource> <name> --min=<min> --max=<max>**  
    Creates a horizontal pod autoscaler for a resource.

## Service and Networking
36. **kubectl expose <resource> <name> --port=<port> --type=<type>**  
    Creates a service for a resource, exposing it via the specified port and service type (e.g., ClusterIP, NodePort).

37. **kubectl get endpoints**  
    Lists the endpoints for services in the cluster.

38. **kubectl proxy**  
    Runs a proxy to the Kubernetes API server, allowing access to cluster resources.

39. **kubectl get ingress**  
    Lists ingress resources in the cluster.

## Troubleshooting and Debugging
40. **kubectl describe node <node-name>**  
    Shows detailed information about a specific node.

41. **kubectl top <resource> [<name>]**  
    Displays resource (CPU/memory) usage for pods or nodes.

42. **kubectl events**  
    Lists events in the cluster for troubleshooting.

43. **kubectl debug <resource> <name>**  
    Starts a debugging session for a pod, node, or ephemeral container.

## Configuration and Secrets
44. **kubectl create configmap <name> --from-file=<file>**  
    Creates a configmap from a file, directory, or literal value.

45. **kubectl create secret <type> <name>**  
    Creates a secret (e.g., generic, docker-registry, tls) with provided data.

46. **kubectl get configmap <name>**  
    Retrieves details of a configmap.

47. **kubectl get secret <name>**  
    Retrieves details of a secret (note: sensitive data is not displayed in plain text).

## Namespace Management
48. **kubectl get namespaces**  
    Lists all namespaces in the cluster.

49. **kubectl create namespace <name>**  
    Creates a new namespace.

50. **kubectl delete namespace <name>**  
    Deletes a namespace and all its resources.

51. **kubectl config set-context --current --namespace=<name>**  
    Sets the default namespace for the current context.

## Miscellaneous
52. **kubectl diff -f <file>**  
    Shows the differences between a local manifest and the cluster state.

53. **kubectl wait <resource> <name> --for=<condition>**  
    Waits for a specific condition on a resource (e.g., `condition=Ready`).

54. **kubectl kustomize <directory>**  
    Builds a kustomization from a directory or URL.

55. **kubectl apply -k <directory>**  
    Applies a kustomization from a directory.

56. **kubectl auth can-i <verb> <resource>**  
    Checks if the current user can perform an action on a resource.

57. **kubectl explain <resource>**  
    Provides documentation for a resource and its fields.

58. **kubectl completion <shell>**  
    Generates shell completion scripts for `kubectl` (e.g., bash, zsh).

59. **kubectl cordon <node-name>**  
    Marks a node as unschedulable, preventing new pods from being scheduled on it.

60. **kubectl uncordon <node-name>**  
    Marks a node as schedulable, allowing new pods to be scheduled.

61. **kubectl drain <node-name>**  
    Drains a node by evicting pods in preparation for maintenance.

62. **kubectl taint nodes <node-name> <key>=<value>:<effect>**  
    Applies a taint to a node to repel pods unless they tolerate the taint.

63. **kubectl certificate approve <csr-name>**  
    Approves a certificate signing request (CSR).

64. **kubectl certificate deny <csr-name>**  
    Denies a certificate signing request (CSR).

65. **kubectl alpha <subcommand>**  
    Accesses experimental or alpha features in `kubectl`.

66. **kubectl plugin list**  
    Lists available `kubectl` plugins.

## Command Options
- **-o <format>**  
  Specifies the output format (e.g., `json`, `yaml`, `wide`, `name`).
- **--namespace=<namespace>**  
  Targets a specific namespace for the command.
- **-f <file>**  
  Specifies a file or directory containing resource definitions.
- **--all-namespaces**  
  Operates on all namespaces in the cluster.
- **--selector=<key>=<value>**  
  Filters resources based on labels.
- **--dry-run=<mode>**  
  Simulates a command without making changes (modes: `client`, `server`).

## Notes
- Use `kubectl help` or `kubectl <command> --help` for detailed help on any command.
- Many commands support shortcuts (e.g., `po` for pods, `svc` for services, `deploy` for deployments).
- Commands can be combined with options like `-o yaml` or `-o json` for structured output.
- Always ensure you have the correct context and namespace set to avoid unintended operations.

This list covers the most commonly used `kubectl` commands as of Kubernetes 1.29. For the latest updates or additional commands, refer to the official Kubernetes documentation or run `kubectl --help`.