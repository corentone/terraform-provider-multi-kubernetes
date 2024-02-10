---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "multikubernetes_cluster_role Resource - terraform-provider-multikubernetes"
subcategory: ""
description: |-
  
---

# multikubernetes_cluster_role (Resource)





<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `cluster` (String) Cluster to which apply the resource
- `metadata` (Block List, Min: 1, Max: 1) Standard clusterRole's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))

### Optional

- `aggregation_rule` (Block List, Max: 1) Describes how to build the Rules for this ClusterRole. (see [below for nested schema](#nestedblock--aggregation_rule))
- `rule` (Block List) List of PolicyRules for this ClusterRole (see [below for nested schema](#nestedblock--rule))

### Read-Only

- `id` (String) The ID of this resource.

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- `annotations` (Map of String) An unstructured key value map stored with the clusterRole that may be used to store arbitrary metadata. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/annotations/
- `generate_name` (String) Prefix, used by the server, to generate a unique name ONLY IF the `name` field has not been provided. This value will also be combined with a unique suffix. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#idempotency
- `labels` (Map of String) Map of string keys and values that can be used to organize and categorize (scope and select) the clusterRole. May match selectors of replication controllers and services. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/
- `name` (String) Name of the clusterRole, must be unique. Cannot be updated. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names

Read-Only:

- `generation` (Number) A sequence number representing a specific generation of the desired state.
- `resource_version` (String) An opaque value that represents the internal version of this clusterRole that can be used by clients to determine when clusterRole has changed. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- `uid` (String) The unique in time and space value for this clusterRole. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#uids


<a id="nestedblock--aggregation_rule"></a>
### Nested Schema for `aggregation_rule`

Optional:

- `cluster_role_selectors` (Block List) A list of selectors which will be used to find ClusterRoles and create the rules. (see [below for nested schema](#nestedblock--aggregation_rule--cluster_role_selectors))

<a id="nestedblock--aggregation_rule--cluster_role_selectors"></a>
### Nested Schema for `aggregation_rule.cluster_role_selectors`

Optional:

- `match_expressions` (Block List) A list of label selector requirements. The requirements are ANDed. (see [below for nested schema](#nestedblock--aggregation_rule--cluster_role_selectors--match_expressions))
- `match_labels` (Map of String) A map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of `match_expressions`, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.

<a id="nestedblock--aggregation_rule--cluster_role_selectors--match_expressions"></a>
### Nested Schema for `aggregation_rule.cluster_role_selectors.match_expressions`

Optional:

- `key` (String) The label key that the selector applies to.
- `operator` (String) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists` and `DoesNotExist`.
- `values` (Set of String) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.




<a id="nestedblock--rule"></a>
### Nested Schema for `rule`

Required:

- `verbs` (List of String) Verbs is a list of Verbs that apply to ALL the ResourceKinds and AttributeRestrictions contained in this rule. VerbAll represents all kinds.

Optional:

- `api_groups` (List of String) APIGroups is the name of the APIGroup that contains the resources. If multiple API groups are specified, any action requested against one of the enumerated resources in any API group will be allowed.
- `non_resource_urls` (List of String) NonResourceURLs is a set of partial urls that a user should have access to. *s are allowed, but only as the full, final step in the path Since non-resource URLs are not namespaced, this field is only applicable for ClusterRoles referenced from a ClusterRoleBinding. Rules can either apply to API resources (such as "pods" or "secrets") or non-resource URL paths (such as "/api"), but not both.
- `resource_names` (List of String) ResourceNames is an optional white list of names that the rule applies to. An empty set means that everything is allowed.
- `resources` (List of String) Resources is a list of resources this rule applies to. ResourceAll represents all resources.