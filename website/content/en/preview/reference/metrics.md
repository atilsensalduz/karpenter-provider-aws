---
title: "Metrics"
linkTitle: "Metrics"
weight: 7

description: >
  Inspect Karpenter Metrics
---
<!-- this document is generated from hack/docs/metrics_gen_docs.go -->
Karpenter makes several metrics available in Prometheus format to allow monitoring cluster provisioning status. These metrics are available by default at `karpenter.kube-system.svc.cluster.local:8080/metrics` configurable via the `METRICS_PORT` environment variable documented [here](../settings)
### `karpenter_build_info`
A metric with a constant '1' value labeled by version from which karpenter was built.
- Stability Level: STABLE

## Nodepools Metrics

### `operator_nodepool_termination_duration_seconds`
The amount of time taken by a nodepool to terminate completely.
- Stability Level: BETA

### `operator_nodepool_termination_current_time_seconds`
The current amount of time in seconds that a nodepool has been in terminating state.
- Stability Level: BETA

### `operator_nodepool_status_condition_transitions_total`
The count of transitions of a nodepool, type and status.
- Stability Level: BETA

### `operator_nodepool_status_condition_transition_seconds`
The amount of time a condition was in a given state before transitioning.
- Stability Level: BETA

### `operator_nodepool_status_condition_current_status_seconds`
The current amount of time in seconds that a status condition has been in a specific state.
- Stability Level: BETA

### `operator_nodepool_status_condition_count`
The number of a condition for a nodepool, type and status.
- Stability Level: BETA

### `karpenter_nodepools_usage`
The amount of resources that have been provisioned for a nodepool. Labeled by nodepool name and resource type.
- Stability Level: ALPHA

### `karpenter_nodepools_limit`
Limits specified on the nodepool that restrict the quantity of resources provisioned. Labeled by nodepool name and resource type.
- Stability Level: ALPHA

### `karpenter_nodepools_allowed_disruptions`
The number of nodes for a given NodePool that can be concurrently disrupting at a point in time. Labeled by NodePool. Note that allowed disruptions can change very rapidly, as new nodes may be created and others may be deleted at any point.
- Stability Level: ALPHA

## Nodeclaims Metrics

### `operator_nodeclaim_termination_duration_seconds`
The amount of time taken by a nodeclaim to terminate completely.
- Stability Level: BETA

### `operator_nodeclaim_termination_current_time_seconds`
The current amount of time in seconds that a nodeclaim has been in terminating state.
- Stability Level: BETA

### `operator_nodeclaim_status_condition_transitions_total`
The count of transitions of a nodeclaim, type and status.
- Stability Level: BETA

### `operator_nodeclaim_status_condition_transition_seconds`
The amount of time a condition was in a given state before transitioning.
- Stability Level: BETA

### `operator_nodeclaim_status_condition_current_status_seconds`
The current amount of time in seconds that a status condition has been in a specific state.
- Stability Level: BETA

### `operator_nodeclaim_status_condition_count`
The number of a condition for a nodeclaim, type and status.
- Stability Level: BETA

### `karpenter_nodeclaims_unhealthy_disrupted_total`
Number of unhealthy nodeclaims disrupted in total by Karpenter. Labeled by condition on the node was disrupted, the owning nodepool, and the image ID.
- Stability Level: ALPHA

### `karpenter_nodeclaims_termination_duration_seconds`
Duration of NodeClaim termination in seconds.
- Stability Level: BETA

### `karpenter_nodeclaims_terminated_total`
Number of nodeclaims terminated in total by Karpenter. Labeled by the owning nodepool.
- Stability Level: STABLE

### `karpenter_nodeclaims_instance_termination_duration_seconds`
Duration of CloudProvider Instance termination in seconds.
- Stability Level: BETA

### `karpenter_nodeclaims_disrupted_total`
Number of nodeclaims disrupted in total by Karpenter. Labeled by reason the nodeclaim was disrupted and the owning nodepool.
- Stability Level: ALPHA

### `karpenter_nodeclaims_created_total`
Number of nodeclaims created in total by Karpenter. Labeled by reason the nodeclaim was created and the owning nodepool.
- Stability Level: STABLE

## Nodes Metrics

### `operator_node_termination_duration_seconds`
The amount of time taken by a node to terminate completely.
- Stability Level: BETA

### `operator_node_termination_current_time_seconds`
The current amount of time in seconds that a node has been in terminating state.
- Stability Level: BETA

### `operator_node_status_condition_transitions_total`
The count of transitions of a node, type and status.
- Stability Level: BETA

### `operator_node_status_condition_transition_seconds`
The amount of time a condition was in a given state before transitioning.
- Stability Level: BETA

### `operator_node_status_condition_current_status_seconds`
The current amount of time in seconds that a status condition has been in a specific state.
- Stability Level: BETA

### `operator_node_status_condition_count`
The number of a condition for a node, type and status.
- Stability Level: BETA

### `operator_node_event_total`
The total number of events of a given type and reason for a node
- Stability Level: BETA

### `karpenter_nodes_total_pod_requests`
Node total pod requests are the resources requested by pods bound to nodes, including the DaemonSet pods.
- Stability Level: BETA

### `karpenter_nodes_total_pod_limits`
Node total pod limits are the resources specified by pod limits, including the DaemonSet pods.
- Stability Level: BETA

### `karpenter_nodes_total_daemon_requests`
Node total daemon requests are the resource requested by DaemonSet pods bound to nodes.
- Stability Level: BETA

### `karpenter_nodes_total_daemon_limits`
Node total daemon limits are the resources specified by DaemonSet pod limits.
- Stability Level: BETA

### `karpenter_nodes_termination_duration_seconds`
The time taken between a node's deletion request and the removal of its finalizer
- Stability Level: BETA

### `karpenter_nodes_terminated_total`
Number of nodes terminated in total by Karpenter. Labeled by owning nodepool.
- Stability Level: STABLE

### `karpenter_nodes_system_overhead`
Node system daemon overhead are the resources reserved for system overhead, the difference between the node's capacity and allocatable values are reported by the status.
- Stability Level: BETA

### `karpenter_nodes_lifetime_duration_seconds`
The lifetime duration of the nodes since creation.
- Stability Level: ALPHA

### `karpenter_nodes_eviction_requests_total`
The total number of eviction requests made by Karpenter
- Stability Level: ALPHA

### `karpenter_nodes_drained_total`
The total number of nodes drained by Karpenter
- Stability Level: ALPHA

### `karpenter_nodes_current_lifetime_seconds`
Node age in seconds
- Stability Level: ALPHA

### `karpenter_nodes_created_total`
Number of nodes created in total by Karpenter. Labeled by owning nodepool.
- Stability Level: STABLE

### `karpenter_nodes_allocatable`
Node allocatable are the resources allocatable by nodes.
- Stability Level: BETA

## Pods Metrics

### `karpenter_pods_unstarted_time_seconds`
The time from pod creation until the pod is running.
- Stability Level: ALPHA

### `karpenter_pods_unbound_time_seconds`
The time from pod creation until the pod is bound.
- Stability Level: ALPHA

### `karpenter_pods_state`
Pod state is the current state of pods. This metric can be used several ways as it is labeled by the pod name, namespace, owner, node, nodepool name, zone, architecture, capacity type, instance type and pod phase.
- Stability Level: BETA

### `karpenter_pods_startup_duration_seconds`
The time from pod creation until the pod is running.
- Stability Level: STABLE

### `karpenter_pods_scheduling_decision_duration_seconds`
The time it takes for Karpenter to first try to schedule a pod after it's been seen.
- Stability Level: ALPHA

### `karpenter_pods_provisioning_unstarted_time_seconds`
The time from when Karpenter first thinks the pod can schedule until the pod is running. Note: this calculated from a point in memory, not by the pod creation timestamp.
- Stability Level: ALPHA

### `karpenter_pods_provisioning_unbound_time_seconds`
The time from when Karpenter first thinks the pod can schedule until it binds. Note: this calculated from a point in memory, not by the pod creation timestamp.
- Stability Level: ALPHA

### `karpenter_pods_provisioning_startup_duration_seconds`
The time from when Karpenter first thinks the pod can schedule until the pod is running. Note: this calculated from a point in memory, not by the pod creation timestamp.
- Stability Level: ALPHA

### `karpenter_pods_provisioning_scheduling_undecided_time_seconds`
The time from when Karpenter has seen a pod without making a scheduling decision for the pod. Note: this calculated from a point in memory, not by the pod creation timestamp.
- Stability Level: ALPHA

### `karpenter_pods_provisioning_bound_duration_seconds`
The time from when Karpenter first thinks the pod can schedule until it binds. Note: this calculated from a point in memory, not by the pod creation timestamp.
- Stability Level: ALPHA

### `karpenter_pods_bound_duration_seconds`
The time from pod creation until the pod is bound.
- Stability Level: ALPHA

## Termination Metrics

### `operator_termination_duration_seconds`
The amount of time taken by an object to terminate completely.
- Stability Level: DEPRECATED

### `operator_termination_current_time_seconds`
The current amount of time in seconds that an object has been in terminating state.
- Stability Level: DEPRECATED

## Ec2nodeclass Metrics

### `operator_ec2nodeclass_termination_duration_seconds`
The amount of time taken by a ec2nodeclass to terminate completely.
- Stability Level: BETA

### `operator_ec2nodeclass_termination_current_time_seconds`
The current amount of time in seconds that a ec2nodeclass has been in terminating state.
- Stability Level: BETA

### `operator_ec2nodeclass_status_condition_transitions_total`
The count of transitions of a ec2nodeclass, type and status.
- Stability Level: BETA

### `operator_ec2nodeclass_status_condition_transition_seconds`
The amount of time a condition was in a given state before transitioning.
- Stability Level: BETA

### `operator_ec2nodeclass_status_condition_current_status_seconds`
The current amount of time in seconds that a status condition has been in a specific state.
- Stability Level: BETA

### `operator_ec2nodeclass_status_condition_count`
The number of a condition for a ec2nodeclass, type and status.
- Stability Level: BETA

## Voluntary Disruption Metrics

### `karpenter_voluntary_disruption_queue_failures_total`
The number of times that an enqueued disruption decision failed. Labeled by disruption method.
- Stability Level: BETA

### `karpenter_voluntary_disruption_eligible_nodes`
Number of nodes eligible for disruption by Karpenter. Labeled by disruption reason.
- Stability Level: BETA

### `karpenter_voluntary_disruption_decisions_total`
Number of disruption decisions performed. Labeled by disruption decision, reason, and consolidation type.
- Stability Level: STABLE

### `karpenter_voluntary_disruption_decision_evaluation_duration_seconds`
Duration of the disruption decision evaluation process in seconds. Labeled by method and consolidation type.
- Stability Level: BETA

### `karpenter_voluntary_disruption_consolidation_timeouts_total`
Number of times the Consolidation algorithm has reached a timeout. Labeled by consolidation type.
- Stability Level: BETA

## Scheduler Metrics

### `karpenter_scheduler_unschedulable_pods_count`
The number of unschedulable Pods.
- Stability Level: ALPHA

### `karpenter_scheduler_unfinished_work_seconds`
How many seconds of work has been done that is in progress and hasn't been observed by scheduling_duration_seconds.
- Stability Level: ALPHA

### `karpenter_scheduler_scheduling_duration_seconds`
Duration of scheduling simulations used for deprovisioning and provisioning in seconds.
- Stability Level: STABLE

### `karpenter_scheduler_queue_depth`
The number of pods currently waiting to be scheduled.
- Stability Level: BETA

### `karpenter_scheduler_ignored_pods_count`
Number of pods ignored during scheduling by Karpenter
- Stability Level: ALPHA

## Interruption Metrics

### `karpenter_interruption_received_messages_total`
Count of messages received from the SQS queue. Broken down by message type and whether the message was actionable.
- Stability Level: STABLE

### `karpenter_interruption_message_queue_duration_seconds`
Amount of time an interruption message is on the queue before it is processed by karpenter.
- Stability Level: STABLE

### `karpenter_interruption_deleted_messages_total`
Count of messages deleted from the SQS queue.
- Stability Level: STABLE

## Cluster Metrics

### `karpenter_cluster_utilization_percent`
Utilization of allocatable resources by pod requests
- Stability Level: ALPHA

## Cluster State Metrics

### `karpenter_cluster_state_unsynced_time_seconds`
The time for which cluster state is not synced
- Stability Level: STABLE

### `karpenter_cluster_state_synced`
Returns 1 if cluster state is synced and 0 otherwise. Synced checks that nodeclaims and nodes that are stored in the APIServer have the same representation as Karpenter's cluster state
- Stability Level: STABLE

### `karpenter_cluster_state_node_count`
Current count of nodes in cluster state
- Stability Level: STABLE

## Cloudprovider Metrics

### `karpenter_cloudprovider_instance_type_offering_price_estimate`
Instance type offering estimated hourly price used when making informed decisions on node cost calculation, based on instance type, capacity type, and zone.
- Stability Level: BETA

### `karpenter_cloudprovider_instance_type_offering_available`
Instance type offering availability, based on instance type, capacity type, and zone
- Stability Level: BETA

### `karpenter_cloudprovider_instance_type_memory_bytes`
Memory, in bytes, for a given instance type.
- Stability Level: BETA

### `karpenter_cloudprovider_instance_type_cpu_cores`
VCPUs cores for a given instance type.
- Stability Level: BETA

### `karpenter_cloudprovider_errors_total`
Total number of errors returned from CloudProvider calls.
- Stability Level: BETA

### `karpenter_cloudprovider_duration_seconds`
Duration of cloud provider method calls. Labeled by the controller, method name and provider.
- Stability Level: BETA

## Cloudprovider Batcher Metrics

### `karpenter_cloudprovider_batcher_batch_time_seconds`
Duration of the batching window per batcher
- Stability Level: BETA

### `karpenter_cloudprovider_batcher_batch_size`
Size of the request batch per batcher
- Stability Level: BETA

## Controller Runtime Metrics

### `controller_runtime_terminal_reconcile_errors_total`
Total number of terminal reconciliation errors per controller
- Stability Level: STABLE

### `controller_runtime_reconcile_total`
Total number of reconciliations per controller
- Stability Level: STABLE

### `controller_runtime_reconcile_time_seconds`
Length of time per reconciliation per controller
- Stability Level: STABLE

### `controller_runtime_reconcile_panics_total`
Total number of reconciliation panics per controller
- Stability Level: STABLE

### `controller_runtime_reconcile_errors_total`
Total number of reconciliation errors per controller
- Stability Level: STABLE

### `controller_runtime_max_concurrent_reconciles`
Maximum number of concurrent reconciles per controller
- Stability Level: STABLE

### `controller_runtime_active_workers`
Number of currently used workers per controller
- Stability Level: STABLE

## Workqueue Metrics

### `workqueue_work_duration_seconds`
How long in seconds processing an item from workqueue takes.
- Stability Level: STABLE

### `workqueue_unfinished_work_seconds`
How many seconds of work has been done that is in progress and hasn't been observed by work_duration. Large values indicate stuck threads. One can deduce the number of stuck threads by observing the rate at which this increases.
- Stability Level: STABLE

### `workqueue_retries_total`
Total number of retries handled by workqueue
- Stability Level: STABLE

### `workqueue_queue_duration_seconds`
How long in seconds an item stays in workqueue before being requested
- Stability Level: STABLE

### `workqueue_longest_running_processor_seconds`
How many seconds has the longest running processor for workqueue been running.
- Stability Level: STABLE

### `workqueue_depth`
Current depth of workqueue
- Stability Level: STABLE

### `workqueue_adds_total`
Total number of adds handled by workqueue
- Stability Level: STABLE

## Status Condition Metrics

### `operator_status_condition_transitions_total`
The count of transitions of a given object, type and status.
- Stability Level: DEPRECATED

### `operator_status_condition_transition_seconds`
The amount of time a condition was in a given state before transitioning.
- Stability Level: DEPRECATED

### `operator_status_condition_current_status_seconds`
The current amount of time in seconds that a status condition has been in a specific state.
- Stability Level: DEPRECATED

### `operator_status_condition_count`
The number of a condition for a given object, type and status.
- Stability Level: DEPRECATED

## Client Go Metrics

### `client_go_request_total`
Number of HTTP requests, partitioned by status code and method.
- Stability Level: STABLE

### `client_go_request_duration_seconds`
Request latency in seconds. Broken down by verb, group, version, kind, and subresource.
- Stability Level: STABLE

## AWS SDK Go Metrics

### `aws_sdk_go_request_total`
The total number of AWS SDK Go requests
- Stability Level: STABLE

### `aws_sdk_go_request_retry_count`
The total number of AWS SDK Go retry attempts per request
- Stability Level: STABLE

### `aws_sdk_go_request_duration_seconds`
Latency of AWS SDK Go requests
- Stability Level: STABLE

### `aws_sdk_go_request_attempt_total`
The total number of AWS SDK Go request attempts
- Stability Level: STABLE

### `aws_sdk_go_request_attempt_duration_seconds`
Latency of AWS SDK Go request attempts
- Stability Level: STABLE

## Leader Election Metrics

### `leader_election_slowpath_total`
Total number of slow path exercised in renewing leader leases. 'name' is the string used to identify the lease. Please make sure to group by name.
- Stability Level: STABLE

### `leader_election_master_status`
Gauge of if the reporting system is master of the relevant lease, 0 indicates backup, 1 indicates master. 'name' is the string used to identify the lease. Please make sure to group by name.
- Stability Level: STABLE
