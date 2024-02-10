---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "multikubernetes_namespace_v1 Data Source - terraform-provider-multikubernetes"
subcategory: ""
description: |-
  
---

# multikubernetes_namespace_v1 (Data Source)





<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `cluster` (String) Cluster to which apply the resource
- `metadata` (Block List, Min: 1, Max: 1) Standard namespace's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))

### Read-Only

- `id` (String) The ID of this resource.
- `spec` (List of Object) Spec defines the behavior of the Namespace. (see [below for nested schema](#nestedatt--spec))

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- `annotations` (Map of String) An unstructured key value map stored with the namespace that may be used to store arbitrary metadata. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/annotations/
- `labels` (Map of String) Map of string keys and values that can be used to organize and categorize (scope and select) the namespace. May match selectors of replication controllers and services. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/
- `name` (String) Name of the namespace, must be unique. Cannot be updated. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names

Read-Only:

- `generation` (Number) A sequence number representing a specific generation of the desired state.
- `resource_version` (String) An opaque value that represents the internal version of this namespace that can be used by clients to determine when namespace has changed. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- `uid` (String) The unique in time and space value for this namespace. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#uids


<a id="nestedatt--spec"></a>
### Nested Schema for `spec`

Read-Only:

- `finalizers` (List of String)