---
layout: post
title: CA downscale evictions priority
parent: Management tools
---
The problem is that the cluster-autoscaler on the downscale process sends a SIGTERM signal to all pods in the node, and some pods like fluentbit are exiting before the other pods, causing the loss of logs.

### Solution

In a general CA tolerates the graceful termination of pods, but some pods can imeddiate exit, to avoid this problem, you can set add the annotation that will make CA to skip the pod, wait when other pods are terminated and then kill the annotated one. Annotation:

```yaml
cluster-autoscaler.kubernetes.io/enable-ds-eviction: "false"
```

kubernetes
{: .label }
cluster-autoscaler
{: .label }
fluentbit
{: .label }
