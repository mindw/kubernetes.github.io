---
---

## kubectl set image

Update image of a pod template

### Synopsis



Update existing container image(s) of resources.

Possible resources include (case insensitive):
  pod (po), replicationcontroller (rc), deployment, daemonset (ds), job, replicaset (rs)

```
kubectl set image (-f FILENAME | TYPE NAME) CONTAINER_NAME_1=CONTAINER_IMAGE_1 ... CONTAINER_NAME_N=CONTAINER_IMAGE_N
```

### Examples

```

# Set a deployment's nginx container image to 'nginx:1.9.1', and its busybox container image to 'busybox'.
kubectl set image deployment/nginx busybox=busybox nginx=nginx:1.9.1

# Update all deployments' and rc's nginx container's image to 'nginx:1.9.1'
kubectl set image deployments,rc nginx=nginx:1.9.1 --all

# Update image of all containers of daemonset abc to 'nginx:1.9.1'
kubectl set image daemonset abc *=nginx:1.9.1

# Print result (in yaml format) of updating nginx container image from local file, without hitting the server 
kubectl set image -f path/to/file.yaml nginx=nginx:1.9.1 --local -o yaml
```

### Options

```
      --all                     select all resources in the namespace of the specified resource types
  -f, --filename value          Filename, directory, or URL to a file identifying the resource to get from a server. (default [])
      --local                   If true, set image will NOT contact api-server but run locally.
      --no-headers              When using the default or custom-column output format, don't print headers.
  -o, --output string           Output format. One of: json|yaml|wide|name|custom-columns=...|custom-columns-file=...|go-template=...|go-template-file=...|jsonpath=...|jsonpath-file=... See custom columns [http://kubernetes.io/docs/user-guide/kubectl-overview/#custom-columns], golang template [http://golang.org/pkg/text/template/#pkg-overview] and jsonpath template [http://kubernetes.io/docs/user-guide/jsonpath].
      --output-version string   Output the formatted object with the given group version (for ex: 'extensions/v1beta1').
      --record                  Record current kubectl command in the resource annotation. If set to false, do not record the command. If set to true, record the command. If not set, default to updating the existing annotation value only if one already exists.
  -R, --recursive               Process the directory used in -f, --filename recursively. Useful when you want to manage related manifests organized within the same directory.
  -l, --selector string         Selector (label query) to filter on
  -a, --show-all                When printing, show all resources (default hide terminated pods.)
      --show-labels             When printing, show all labels as the last column (default hide labels column)
      --sort-by string          If non-empty, sort list types using this field specification.  The field specification is expressed as a JSONPath expression (e.g. '{.metadata.name}'). The field in the API resource specified by this JSONPath expression must be an integer or a string.
      --template string         Template string or path to template file to use when -o=go-template, -o=go-template-file. The template format is golang templates [http://golang.org/pkg/text/template/#pkg-overview].
```

### Options inherited from parent commands

```
      --alsologtostderr value          log to standard error as well as files
      --as string                      Username to impersonate for the operation
      --certificate-authority string   Path to a cert. file for the certificate authority
      --client-certificate string      Path to a client certificate file for TLS
      --client-key string              Path to a client key file for TLS
      --cluster string                 The name of the kubeconfig cluster to use
      --context string                 The name of the kubeconfig context to use
      --insecure-skip-tls-verify       If true, the server's certificate will not be checked for validity. This will make your HTTPS connections insecure
      --kubeconfig string              Path to the kubeconfig file to use for CLI requests.
      --log-backtrace-at value         when logging hits line file:N, emit a stack trace (default :0)
      --log-dir value                  If non-empty, write log files in this directory
      --logtostderr value              log to standard error instead of files
      --match-server-version           Require server version to match client version
  -n, --namespace string               If present, the namespace scope for this CLI request
      --password string                Password for basic authentication to the API server
  -s, --server string                  The address and port of the Kubernetes API server
      --stderrthreshold value          logs at or above this threshold go to stderr (default 2)
      --token string                   Bearer token for authentication to the API server
      --user string                    The name of the kubeconfig user to use
      --username string                Username for basic authentication to the API server
  -v, --v value                        log level for V logs
      --vmodule value                  comma-separated list of pattern=N settings for file-filtered logging
```

### SEE ALSO

* [kubectl set](kubectl_set.md)	 - Set specific features on objects

###### Auto generated by spf13/cobra on 2-Sep-2016





<!-- BEGIN MUNGE: GENERATED_ANALYTICS -->
[![Analytics](https://kubernetes-site.appspot.com/UA-36037335-10/GitHub/docs/user-guide/kubectl/kubectl_set_image.md?pixel)]()
<!-- END MUNGE: GENERATED_ANALYTICS -->
