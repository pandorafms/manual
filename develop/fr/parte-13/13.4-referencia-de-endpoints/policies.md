# Policies

Policies and everything they apply: agents, groups, modules, plugins, alerts, collections and the policy queue.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/copy`](#post-policy-idpolicy-copy) | Copy a policy using the legacy copy scope |
| <span class="api-method api-post">POST</span> | [`/policy`](#post-policy) | Create a policy |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}`](#get-policy-idpolicy) | Get a policy |
| <span class="api-method api-put">PUT</span> | [`/policy/{idPolicy}`](#put-policy-idpolicy) | Update a policy |
| <span class="api-method api-delete">DELETE</span> | [`/policy/{idPolicy}`](#delete-policy-idpolicy) | Delete an empty policy |
| <span class="api-method api-get">GET</span> | [`/policy/list`](#get-policy-list) | List policies |
| <span class="api-method api-post">POST</span> | [`/policy/list`](#post-policy-list) | List policies |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/purge`](#post-policy-idpolicy-purge) | Queue removal of every agent from a policy |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/agent`](#post-policy-idpolicy-agent) | Add or reactivate an agent in a policy |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/agent/{idPolicyAgent}`](#get-policy-idpolicy-agent-idpolicyagent) | Get a policy agent relation |
| <span class="api-method api-delete">DELETE</span> | [`/policy/{idPolicy}/agent/{idPolicyAgent}`](#delete-policy-idpolicy-agent-idpolicyagent) | Mark a policy agent for deletion |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/agent/list`](#get-policy-idpolicy-agent-list) | List agents linked to a policy |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/agent/list`](#post-policy-idpolicy-agent-list) | List agents linked to a policy |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/agent/{idPolicyAgent}/restore`](#post-policy-idpolicy-agent-idpolicyagent-restore) | Undo a policy agent deletion |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/group`](#post-policy-idpolicy-group) | Add or reactivate a group in a policy |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/group/{idPolicyGroup}`](#get-policy-idpolicy-group-idpolicygroup) | Get a policy group relation |
| <span class="api-method api-delete">DELETE</span> | [`/policy/{idPolicy}/group/{idPolicyGroup}`](#delete-policy-idpolicy-group-idpolicygroup) | Mark a policy group for deletion |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/group/list`](#get-policy-idpolicy-group-list) | List groups linked to a policy using query pagination |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/group/list`](#post-policy-idpolicy-group-list) | List groups linked to a policy |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/group/{idPolicyGroup}/restore`](#post-policy-idpolicy-group-idpolicygroup-restore) | Restore a policy group pending deletion |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/module/{idPolicyModule}`](#get-policy-idpolicy-module-idpolicymodule) | Get a local policy module |
| <span class="api-method api-put">PUT</span> | [`/policy/{idPolicy}/module/{idPolicyModule}`](#put-policy-idpolicy-module-idpolicymodule) | Partially update a policy module |
| <span class="api-method api-delete">DELETE</span> | [`/policy/{idPolicy}/module/{idPolicyModule}`](#delete-policy-idpolicy-module-idpolicymodule) | Mark a module for deletion on policy application |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/module/{idPolicyModule}/restore`](#post-policy-idpolicy-module-idpolicymodule-restore) | Revert pending deletion |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/module/{idPolicyModule}/enable`](#post-policy-idpolicy-module-idpolicymodule-enable) | Enable a policy module |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/module/{idPolicyModule}/disable`](#post-policy-idpolicy-module-idpolicymodule-disable) | Disable a policy module |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/module`](#post-policy-idpolicy-module) | Create a policy module |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/module/list`](#get-policy-idpolicy-module-list) | List local policy modules |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/module/list`](#post-policy-idpolicy-module-list) | Filter local policy modules |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/logModule`](#post-policy-idpolicy-logmodule) | Create a policy log module |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/logModule/{idPolicyLogModule}`](#get-policy-idpolicy-logmodule-idpolicylogmodule) | Get a local policy log module |
| <span class="api-method api-put">PUT</span> | [`/policy/{idPolicy}/logModule/{idPolicyLogModule}`](#put-policy-idpolicy-logmodule-idpolicylogmodule) | Partially update a policy log module |
| <span class="api-method api-delete">DELETE</span> | [`/policy/{idPolicy}/logModule/{idPolicyLogModule}`](#delete-policy-idpolicy-logmodule-idpolicylogmodule) | Mark a policy log module pending deletion |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/logModule/{idPolicyLogModule}/disable`](#post-policy-idpolicy-logmodule-idpolicylogmodule-disable) | Disable a policy log module idempotently |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/logModule/{idPolicyLogModule}/enable`](#post-policy-idpolicy-logmodule-idpolicylogmodule-enable) | Enable a policy log module idempotently |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/logModule/list`](#get-policy-idpolicy-logmodule-list) | List local policy log modules using query pagination and sorting |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/logModule/list`](#post-policy-idpolicy-logmodule-list) | List local policy log modules with advanced filters |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/logModule/{idPolicyLogModule}/restore`](#post-policy-idpolicy-logmodule-idpolicylogmodule-restore) | Revert pending deletion of a policy log module |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/plugin/bulk/delete`](#post-policy-idpolicy-plugin-bulk-delete) | Mark policy plugins pending deletion |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/plugin/bulk/restore`](#post-policy-idpolicy-plugin-bulk-restore) | Restore policy plugins pending deletion |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/plugin/bulk/enable`](#post-policy-idpolicy-plugin-bulk-enable) | Enable policy plugins |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/plugin/bulk/disable`](#post-policy-idpolicy-plugin-bulk-disable) | Disable policy plugins |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/plugin`](#post-policy-idpolicy-plugin) | Create a policy plugin |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/plugin/{idPolicyPlugin}`](#get-policy-idpolicy-plugin-idpolicyplugin) | Get a local policy plugin |
| <span class="api-method api-put">PUT</span> | [`/policy/{idPolicy}/plugin/{idPolicyPlugin}`](#put-policy-idpolicy-plugin-idpolicyplugin) | Partially update a policy plugin |
| <span class="api-method api-delete">DELETE</span> | [`/policy/{idPolicy}/plugin/{idPolicyPlugin}`](#delete-policy-idpolicy-plugin-idpolicyplugin) | Mark a policy plugin pending deletion |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/plugin/{idPolicyPlugin}/disable`](#post-policy-idpolicy-plugin-idpolicyplugin-disable) | Disable a policy plugin |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/plugin/{idPolicyPlugin}/enable`](#post-policy-idpolicy-plugin-idpolicyplugin-enable) | Enable a policy plugin |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/plugin/list`](#get-policy-idpolicy-plugin-list) | List local policy plugins using query pagination and sorting |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/plugin/list`](#post-policy-idpolicy-plugin-list) | List local policy plugins with advanced filters |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/plugin/{idPolicyPlugin}/restore`](#post-policy-idpolicy-plugin-idpolicyplugin-restore) | Cancel pending policy plugin deletion |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/alert`](#post-policy-idpolicy-alert) | Create an alert for a policy module |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/alert/{idPolicyAlert}`](#get-policy-idpolicy-alert-idpolicyalert) | Get a policy module alert |
| <span class="api-method api-put">PUT</span> | [`/policy/{idPolicy}/alert/{idPolicyAlert}`](#put-policy-idpolicy-alert-idpolicyalert) | Update policy alert status |
| <span class="api-method api-delete">DELETE</span> | [`/policy/{idPolicy}/alert/{idPolicyAlert}`](#delete-policy-idpolicy-alert-idpolicyalert) | Mark policy alert for deletion |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/alert/list`](#get-policy-idpolicy-alert-list) | List policy module alerts |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/alert/list`](#post-policy-idpolicy-alert-list) | Filter policy module alerts |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/alert/{idPolicyAlert}/restore`](#post-policy-idpolicy-alert-idpolicyalert-restore) | Restore policy alert pending deletion |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/alert/{idPolicyAlert}/action`](#post-policy-idpolicy-alert-idpolicyalert-action) | Add an action to a policy alert |
| <span class="api-method api-delete">DELETE</span> | [`/policy/{idPolicy}/alert/{idPolicyAlert}/action/{idPolicyAlertAction}`](#delete-policy-idpolicy-alert-idpolicyalert-action-idpolicyalertaction) | Remove an action from a policy alert |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/alert/{idPolicyAlert}/action/list`](#get-policy-idpolicy-alert-idpolicyalert-action-list) | List actions on a policy alert |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/alert/{idPolicyAlert}/action/list`](#post-policy-idpolicy-alert-idpolicyalert-action-list) | Filter actions on a policy alert |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/externalAlert`](#post-policy-idpolicy-externalalert) | Create an external policy alert |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}`](#get-policy-idpolicy-externalalert-idpolicyexternalalert) | Get an external policy alert |
| <span class="api-method api-delete">DELETE</span> | [`/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}`](#delete-policy-idpolicy-externalalert-idpolicyexternalalert) | Mark an external alert for deletion at the next policy application |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/externalAlert/list`](#get-policy-idpolicy-externalalert-list) | List external policy alerts |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/externalAlert/list`](#post-policy-idpolicy-externalalert-list) | Filter external policy alerts |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}/restore`](#post-policy-idpolicy-externalalert-idpolicyexternalalert-restore) | Revert external alert deletion |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}/action`](#post-policy-idpolicy-externalalert-idpolicyexternalalert-action) | Add an external alert action |
| <span class="api-method api-delete">DELETE</span> | [`/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}/action/{idPolicyExternalAlertAction}`](#delete-policy-idpolicy-externalalert-idpolicyexternalalert-action-idpolicyexternalalertaction) | Remove an external alert action |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}/action/list`](#get-policy-idpolicy-externalalert-idpolicyexternalalert-action-list) | List external alert actions |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}/action/list`](#post-policy-idpolicy-externalalert-idpolicyexternalalert-action-list) | Filter external alert actions |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/collection`](#post-policy-idpolicy-collection) | Associate a collection with a policy |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/collection/{idPolicyCollection}`](#get-policy-idpolicy-collection-idpolicycollection) | Get a policy collection association |
| <span class="api-method api-delete">DELETE</span> | [`/policy/{idPolicy}/collection/{idPolicyCollection}`](#delete-policy-idpolicy-collection-idpolicycollection) | Mark a policy collection for deletion |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/collection/available/list`](#get-policy-idpolicy-collection-available-list) | List available collections using query filters |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/collection/available/list`](#post-policy-idpolicy-collection-available-list) | List available collections using advanced filters |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/collection/list`](#get-policy-idpolicy-collection-list) | List policy collections using query filters |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/collection/list`](#post-policy-idpolicy-collection-list) | List policy collections using advanced filters |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/collection/{idPolicyCollection}/restore`](#post-policy-idpolicy-collection-idpolicycollection-restore) | Undo pending policy collection deletion |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/fim`](#get-policy-idpolicy-fim) | Get policy FIM configuration |
| <span class="api-method api-put">PUT</span> | [`/policy/{idPolicy}/fim`](#put-policy-idpolicy-fim) | Save policy FIM configuration |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/linking/bulk/link`](#post-policy-idpolicy-linking-bulk-link) | Relink selected policy agent modules |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/linking/{idAgentModule}/link`](#post-policy-idpolicy-linking-idagentmodule-link) | Relink an existing policy agent module |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/linking/list`](#get-policy-idpolicy-linking-list) | List unlinked modules using query filters |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/linking/list`](#post-policy-idpolicy-linking-list) | List unlinked modules using advanced filters |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/queue/applyPending`](#post-policy-idpolicy-queue-applypending) | Enqueue application and removal for authorized pending policy agents |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/queue/clear`](#post-policy-idpolicy-queue-clear) | Clear matching waiting or completed operations on one console |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/queue`](#post-policy-idpolicy-queue) | Enqueue a policy operation |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/queue/{idPolicyQueue}`](#get-policy-idpolicy-queue-idpolicyqueue) | Get a queue operation and its current progress |
| <span class="api-method api-delete">DELETE</span> | [`/policy/{idPolicy}/queue/{idPolicyQueue}`](#delete-policy-idpolicy-queue-idpolicyqueue) | Delete a waiting or completed queue operation |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/queue/list`](#get-policy-idpolicy-queue-list) | List queue operations using query filters |
| <span class="api-method api-post">POST</span> | [`/policy/{idPolicy}/queue/list`](#post-policy-idpolicy-queue-list) | List queue operations using advanced filters |
| <span class="api-method api-get">GET</span> | [`/policy/{idPolicy}/queue/summary`](#get-policy-idpolicy-queue-summary) | Get pending policy changes and authorized agent/group counters |

## Policies

API Endpoints for policies

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/copy` { #post-policy-idpolicy-copy }

Copy a policy using the legacy copy scope

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string, nullable |  |  |
| `idGroup` | integer, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idGroup": 0
    }
    ```

**Response 200**: Policy

Schema: [`PolicyResponse`](#model-policyresponse)

Error responses: `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-post">POST</span> `/policy` { #post-policy }

Create a policy

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string | yes |  |
| `description` | string |  |  |
| `idGroup` | integer |  |  |
| `forceApply` | boolean |  |  |
| `applyToSecondaryGroups` | boolean |  |  |
| `createLinkedModules` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "forceApply": false,
      "applyToSecondaryGroups": false,
      "createLinkedModules": true
    }
    ```

**Response 200**: Policy

Schema: [`PolicyResponse`](#model-policyresponse)

Error responses: `400`, `401`, `403`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}` { #get-policy-idpolicy }

Get a policy

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Response 200**: Policy

Schema: [`PolicyResponse`](#model-policyresponse)

Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/policy/{idPolicy}` { #put-policy-idpolicy }

Update a policy

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string |  |  |
| `description` | string |  |  |
| `idGroup` | integer |  |  |
| `forceApply` | boolean |  |  |
| `applyToSecondaryGroups` | boolean |  |  |
| `createLinkedModules` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "forceApply": false,
      "applyToSecondaryGroups": false,
      "createLinkedModules": false
    }
    ```

**Response 200**: Policy

Schema: [`PolicyResponse`](#model-policyresponse)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-delete">DELETE</span> `/policy/{idPolicy}` { #delete-policy-idpolicy }

Delete an empty policy

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/policy/list` { #get-policy-list }

List policies

Supports pagination, sorting, and filters through query parameters.

**Response 200**: Policy list

??? note "Response fields (18 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].description` | string |  |  |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].status` | integer |  |  |
    | `data.[].forceApply` | boolean |  |  |
    | `data.[].applyToSecondaryGroups` | boolean |  |  |
    | `data.[].createLinkedModules` | boolean |  |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/policy/list` { #post-policy-list }

List policies

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idPolicy` | integer |  |  |
| `name` | string |  |  |
| `description` | string |  |  |
| `idGroup` | integer |  |  |
| `status` | integer |  |  |
| `forceApply` | boolean |  |  |
| `applyToSecondaryGroups` | boolean |  |  |
| `createLinkedModules` | boolean |  |  |
| `freeSearch` | string, nullable |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idPolicy`, `name`, `description`, `idGroup`, `status`, `forceApply`, `applyToSecondaryGroups`, `createLinkedModules` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idPolicy`, `name`, `description`, `idGroup`, `status`, `forceApply`, `applyToSecondaryGroups`, `createLinkedModules` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "forceApply": false,
      "applyToSecondaryGroups": false,
      "createLinkedModules": true,
      "freeSearch": "string",
      "requestedFields": [
        "idPolicy"
      ],
      "fieldConditions": [
        {
          "field": "idPolicy",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idPolicy",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idPolicy",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Policy list

??? note "Response fields (18 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].description` | string |  |  |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].status` | integer |  |  |
    | `data.[].forceApply` | boolean |  |  |
    | `data.[].applyToSecondaryGroups` | boolean |  |  |
    | `data.[].createLinkedModules` | boolean |  |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/purge` { #post-policy-idpolicy-purge }

Queue removal of every agent from a policy

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Response 200**: Purge request queued

Error responses: `401`, `403`, `404`, `409`, `500`.

## PolicyAgents

API Endpoints for agents assigned to policies

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/agent` { #post-policy-idpolicy-agent }

Add or reactivate an agent in a policy

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgent` | integer | yes |  |
| `serverId` | integer |  | Node target on a metaconsole |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": 0,
      "serverId": 0
    }
    ```

**Response 200**: Policy agent

Schema: [`PolicyAgent`](#model-policyagent)

Error responses: `400`, `401`, `403`, `404`, `409`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/agent/{idPolicyAgent}` { #get-policy-idpolicy-agent-idpolicyagent }

Get a policy agent relation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyAgent` | path | integer | yes |  |
| `serverId` | query | integer |  | Required on a metaconsole for a single relation |

**Response 200**: Policy agent

Schema: [`PolicyAgent`](#model-policyagent)

Error responses: `400`, `401`, `403`, `404`.

### <span class="api-method api-delete">DELETE</span> `/policy/{idPolicy}/agent/{idPolicyAgent}` { #delete-policy-idpolicy-agent-idpolicyagent }

Mark a policy agent for deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyAgent` | path | integer | yes |  |
| `serverId` | query | integer |  | Required on a metaconsole for a single relation |

**Response 200**: Pending deletion

Schema: [`PolicyAgent`](#model-policyagent)

Error responses: `400`, `401`, `403`, `404`, `409`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/agent/list` { #get-policy-idpolicy-agent-list }

List agents linked to a policy

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Response 200**: Policy agents list

??? note "Response fields (17 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyAgent` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].idNode` | integer |  |  |
    | `data.[].policyApplied` | boolean |  |  |
    | `data.[].pendingDelete` | boolean |  |  |
    | `data.[].lastApplyUtimestamp` | integer |  |  |


Error responses: `400`, `401`, `403`, `404`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/agent/list` { #post-policy-idpolicy-agent-list }

List agents linked to a policy

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `serverId` | integer, nullable |  |  |
| `idAgent` | integer, nullable |  |  |
| `pendingDelete` | boolean, nullable |  |  |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `sortField` | string, nullable |  |  |
| `sortDirection` | enum: `ASC`, `DESC` |  |  |
| `requestedFields` | array of string |  |  |
| `fieldConditions` | array of object |  | Only field, operator and value are supported; table and jsonPath are not accepted. |
| `fieldConditions.[].field` | string | yes | Filter field name. Use the API field name accepted by the filter, for example name, idGroup, createdAt or a field mapped to a JSON column. |
| `fieldConditions.[].jsonPath` | string, nullable |  | Optional JSON path inside the selected field when it is a JSON column. Accepted formats include customer.id, $.customer.id and items[0].name. Operators in and not_in over JSON paths are evaluated as comma-separated lists using FIND_IN_SET. |
| `fieldConditions.[].operator` | enum: `=`, `!=`, `<>`, `>`, `<`, `>=`, `<=`, `like`, `not_like`, `regex`, `not_regex`, `in`, `not_in`, `between`, `not_between`, `is_null`, `is_not_null`, `is_empty`, `is_not_empty` | yes | Condition operator. Aliases such as eq, ne, gt, gte, lt, lte, regexp and not_regexp are also accepted by the API. |
| `fieldConditions.[].value` |  |  | Condition value. Use an array for in, not_in, between and not_between. Value is ignored for is_null, is_not_null, is_empty and is_not_empty. |
| `fieldConditions.[].table` | string, nullable |  | Optional SQL table alias for joined queries. In most API requests this must be omitted. |
| `multipleSearch` | object |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString` | object |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idPolicyAgent`, `idPolicy`, `idAgent`, `policyApplied`, `pendingDelete`, `lastApplyUtimestamp` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idPolicyAgent`, `idPolicy`, `idAgent`, `policyApplied`, `pendingDelete`, `lastApplyUtimestamp` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idPolicyAgent"
      ],
      "fieldConditions": [
        {
          "field": "idPolicyAgent",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "serverId": 0,
      "idAgent": 0,
      "pendingDelete": false,
      "sortField": "string",
      "sortDirection": "ASC",
      "multipleSearch": {
        "field": "idPolicyAgent",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idPolicyAgent",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Policy agents list

??? note "Response fields (17 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyAgent` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].idNode` | integer |  |  |
    | `data.[].policyApplied` | boolean |  |  |
    | `data.[].pendingDelete` | boolean |  |  |
    | `data.[].lastApplyUtimestamp` | integer |  |  |


Error responses: `400`, `401`, `403`, `404`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/agent/{idPolicyAgent}/restore` { #post-policy-idpolicy-agent-idpolicyagent-restore }

Undo a policy agent deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyAgent` | path | integer | yes |  |
| `serverId` | query | integer |  | Required on a metaconsole for a single relation |

**Response 200**: Restored relation

Schema: [`PolicyAgent`](#model-policyagent)

Error responses: `400`, `401`, `403`, `404`, `409`.

## PolicyGroups

API Endpoints for groups assigned to policies

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/group` { #post-policy-idpolicy-group }

Add or reactivate a group in a policy

Idempotent: adding an already linked group returns the existing association with HTTP 200.
If the group is pending deletion, adding it reactivates the association.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idGroup` | integer | yes |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroup": 0
    }
    ```

**Response 200**: Policy group

Schema: [`PolicyGroup`](#model-policygroup)

Error responses: `400`, `401`, `403`, `404`, `409`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/group/{idPolicyGroup}` { #get-policy-idpolicy-group-idpolicygroup }

Get a policy group relation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyGroup` | path | integer | yes |  |

**Response 200**: Policy group

Schema: [`PolicyGroup`](#model-policygroup)

Error responses: `400`, `401`, `403`, `404`.

### <span class="api-method api-delete">DELETE</span> `/policy/{idPolicy}/group/{idPolicyGroup}` { #delete-policy-idpolicy-group-idpolicygroup }

Mark a policy group for deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyGroup` | path | integer | yes |  |

**Response 200**: Policy group

Schema: [`PolicyGroup`](#model-policygroup)

Error responses: `400`, `401`, `403`, `404`, `409`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/group/list` { #get-policy-idpolicy-group-list }

List groups linked to a policy using query pagination

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Response 200**: Policy groups list

??? note "Response fields (16 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyGroup` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].policyApplied` | boolean |  |  |
    | `data.[].pendingDelete` | boolean |  |  |
    | `data.[].lastApplyUtimestamp` | integer |  |  |


Error responses: `400`, `401`, `403`, `404`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/group/list` { #post-policy-idpolicy-group-list }

List groups linked to a policy

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idGroup` | integer, nullable |  |  |
| `pendingDelete` | boolean, nullable |  |  |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `sortField` | string, nullable |  |  |
| `sortDirection` | enum: `ASC`, `DESC` |  |  |
| `requestedFields` | array of string |  |  |
| `fieldConditions` | array of object |  |  |
| `fieldConditions.[].field` | string | yes | Filter field name. Use the API field name accepted by the filter, for example name, idGroup, createdAt or a field mapped to a JSON column. |
| `fieldConditions.[].jsonPath` | string, nullable |  | Optional JSON path inside the selected field when it is a JSON column. Accepted formats include customer.id, $.customer.id and items[0].name. Operators in and not_in over JSON paths are evaluated as comma-separated lists using FIND_IN_SET. |
| `fieldConditions.[].operator` | enum: `=`, `!=`, `<>`, `>`, `<`, `>=`, `<=`, `like`, `not_like`, `regex`, `not_regex`, `in`, `not_in`, `between`, `not_between`, `is_null`, `is_not_null`, `is_empty`, `is_not_empty` | yes | Condition operator. Aliases such as eq, ne, gt, gte, lt, lte, regexp and not_regexp are also accepted by the API. |
| `fieldConditions.[].value` |  |  | Condition value. Use an array for in, not_in, between and not_between. Value is ignored for is_null, is_not_null, is_empty and is_not_empty. |
| `fieldConditions.[].table` | string, nullable |  | Optional SQL table alias for joined queries. In most API requests this must be omitted. |
| `multipleSearch` | object |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString` | object |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idPolicyGroup`, `idPolicy`, `idGroup`, `policyApplied`, `pendingDelete`, `lastApplyUtimestamp` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idPolicyGroup`, `idPolicy`, `idGroup`, `policyApplied`, `pendingDelete`, `lastApplyUtimestamp` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idPolicyGroup"
      ],
      "fieldConditions": [
        {
          "field": "idPolicyGroup",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idGroup": 0,
      "pendingDelete": false,
      "sortField": "string",
      "sortDirection": "ASC",
      "multipleSearch": {
        "field": "idPolicyGroup",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idPolicyGroup",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Policy groups list

??? note "Response fields (16 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyGroup` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].policyApplied` | boolean |  |  |
    | `data.[].pendingDelete` | boolean |  |  |
    | `data.[].lastApplyUtimestamp` | integer |  |  |


Error responses: `400`, `401`, `403`, `404`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/group/{idPolicyGroup}/restore` { #post-policy-idpolicy-group-idpolicygroup-restore }

Restore a policy group pending deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyGroup` | path | integer | yes |  |

**Response 200**: Policy group

Schema: [`PolicyGroup`](#model-policygroup)

Error responses: `400`, `401`, `403`, `404`, `409`.

## PolicyModules

API Endpoints for synchronized policy modules

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/module/{idPolicyModule}` { #get-policy-idpolicy-module-idpolicymodule }

Get a local policy module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyModule` | path | integer | yes |  |

**Response 200**: Policy module

Schema: [`PolicyModuleResponse`](#model-policymoduleresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/policy/{idPolicy}/module/{idPolicyModule}` { #put-policy-idpolicy-module-idpolicymodule }

Partially update a policy module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyModule` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idPolicyModule` | integer |  |  |
| `idPolicy` | integer |  |  |
| `moduleType` | enum: `data`, `icmp`, `tcp`, `snmp`, `wmi`, `remotecmd`, `web`, `prediction`, `plugin`, `wux`, `api_retrieve`, `api_custom`, `sat_icmp`, `sat_snmp`, `sat_ssh`, `sat_tcp`, `sat_exec`, `sat_wmi` |  |  |
| `name` | string |  |  |
| `description` | string |  |  |
| `idModule` | integer |  |  |
| `idModuleType` | integer |  |  |
| `configurationData` | string, nullable |  | Native configuration is normalized: each line is trimmed, empty lines are removed, line endings are normalized and non-empty text ends with a final newline. Satellite configuration is parsed and regenerated by the module manager. |
| `unit` | string, nullable |  |  |
| `max` | integer (int64), nullable |  |  |
| `min` | integer (int64), nullable |  |  |
| `moduleInterval` | integer, nullable |  |  |
| `ipTarget` | string, nullable |  |  |
| `tcpPort` | integer, nullable |  |  |
| `tcpSend` | string, nullable |  |  |
| `tcpRcv` | string, nullable |  |  |
| `snmpOid` | string, nullable |  |  |
| `idModuleGroup` | integer, nullable |  |  |
| `flag` | integer |  |  |
| `disabled` | boolean |  |  |
| `idExport` | integer, nullable |  |  |
| `pluginUser` | string, nullable |  |  |
| `pluginParameter` | string, nullable |  |  |
| `idPlugin` | integer, nullable |  |  |
| `postProcess` | number, nullable |  |  |
| `predictionModule` | integer, nullable |  |  |
| `maxTimeout` | integer, nullable |  |  |
| `maxRetries` | integer, nullable |  |  |
| `customId` | string, nullable |  |  |
| `historyData` | boolean, nullable |  |  |
| `minWarning` | number, nullable |  |  |
| `maxWarning` | number, nullable |  |  |
| `strWarning` | string, nullable |  |  |
| `minCritical` | number, nullable |  |  |
| `maxCritical` | number, nullable |  |  |
| `strCritical` | string, nullable |  |  |
| `minFfEvent` | integer, nullable |  |  |
| `customInteger1` | integer, nullable |  |  |
| `customInteger2` | integer, nullable |  |  |
| `pendingDelete` | boolean |  |  |
| `criticalInstructions` | string, nullable |  |  |
| `warningInstructions` | string, nullable |  |  |
| `unknownInstructions` | string, nullable |  |  |
| `criticalInverse` | boolean, nullable |  |  |
| `warningInverse` | boolean, nullable |  |  |
| `idCategory` | integer, nullable |  |  |
| `moduleFfInterval` | integer, nullable |  |  |
| `quiet` | boolean |  |  |
| `cronInterval` | string, nullable |  |  |
| `macros` | array, nullable |  |  |
| `disabledTypesEvent` | object, nullable |  |  |
| `moduleMacros` | object, nullable |  |  |
| `minFfEventNormal` | integer, nullable |  |  |
| `minFfEventWarning` | integer, nullable |  |  |
| `minFfEventCritical` | integer, nullable |  |  |
| `ffType` | boolean, nullable |  |  |
| `eachFf` | boolean, nullable |  |  |
| `ffTimeout` | integer, nullable |  |  |
| `dynamicInterval` | integer, nullable |  |  |
| `dynamicMax` | integer, nullable |  |  |
| `dynamicMin` | integer, nullable |  |  |
| `dynamicNext` | integer |  |  |
| `dynamicTwoTailed` | boolean, nullable |  |  |
| `predictionSampleWindow` | integer, nullable |  |  |
| `predictionSamples` | integer, nullable |  |  |
| `predictionThreshold` | integer, nullable |  |  |
| `apiTimeout` | integer, nullable |  |  |
| `apiUrl` | string, nullable |  |  |
| `apiMethod` | string, nullable |  |  |
| `apiIgnoreCert` | boolean |  |  |
| `apiJsonq` | string, nullable |  |  |
| `apiErrorCodes` | string, nullable |  |  |
| `apiConditions` | array, nullable |  |  |
| `cps` | boolean |  |  |
| `percentageWarning` | boolean, nullable |  |  |
| `percentageCritical` | boolean, nullable |  |  |
| `warningTime` | integer, nullable |  |  |
| `madeEnabled` | boolean, nullable |  |  |
| `ignoreUnknown` | boolean |  |  |
| `satelliteType` | string, nullable |  |  |
| `parentPolicyModuleId` | integer |  |  |
| `idDataTranslation` | integer, nullable |  |  |
| `tags` | array of integer |  |  |
| `predictionFormula` | array of object |  |  |
| `snmpCommunity` | string, nullable |  | SNMP credential. Accepted on input only; never returned. |
| `pluginPass` | string, nullable |  | Plugin or SNMP authentication password. Accepted on input only; never returned. |
| `customString1` | string, nullable |  | SNMP privacy protocol or WUX/module configuration. Input only; never returned. |
| `customString2` | string, nullable |  | SNMPv3 privacy password or module-specific configuration. Input only; never returned. |
| `customString3` | string, nullable |  | SNMP security level or module-specific configuration. Input only; never returned. |
| `apiBody` | string, nullable |  | HTTP request body; may contain credentials. Accepted on input only; never returned. |
| `apiHeaders` | object, nullable |  | HTTP request headers; may contain authentication tokens. Input only; never returned. |
| `moduleType` | string |  | Module family. Set only on creation; rejected in update requests. |
| `idModule` | integer |  | Module server type. Set only on creation; rejected in update requests. |
| `idModuleType` | integer |  | Module data type. Set only on creation; rejected in update requests. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "moduleType": "data",
      "name": "string",
      "description": "string",
      "idModule": 0,
      "idModuleType": 0,
      "configurationData": "string",
      "unit": "string",
      "max": 0,
      "min": 0,
      "moduleInterval": 0,
      "ipTarget": "string",
      "tcpPort": 0,
      "tcpSend": "string",
      "tcpRcv": "string",
      "snmpOid": "string",
      "idModuleGroup": 0,
      "idExport": 0,
      "pluginUser": "string",
      "pluginParameter": "string",
      "idPlugin": 0,
      "postProcess": 0,
      "predictionModule": 0,
      "maxTimeout": 0,
      "maxRetries": 0,
      "customId": "string",
      "historyData": false,
      "minWarning": 0,
      "maxWarning": 0,
      "strWarning": "string",
      "minCritical": 0,
      "maxCritical": 0,
      "strCritical": "string",
      "minFfEvent": 0,
      "customInteger1": 0,
      "customInteger2": 0,
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "criticalInverse": false,
      "warningInverse": false,
      "idCategory": 0,
      "moduleFfInterval": 0,
      "quiet": false,
      "cronInterval": "string",
      "macros": [
        {}
      ],
      "disabledTypesEvent": {},
      "moduleMacros": {},
      "minFfEventNormal": 0,
      "minFfEventWarning": 0,
      "minFfEventCritical": 0,
      "ffType": false,
      "eachFf": false,
      "ffTimeout": 0,
      "dynamicInterval": 0,
      "dynamicMax": 0,
      "dynamicMin": 0,
      "dynamicTwoTailed": false,
      "predictionSampleWindow": 0,
      "predictionSamples": 0,
      "predictionThreshold": 0,
      "apiTimeout": 0,
      "apiUrl": "string",
      "apiMethod": "string",
      "apiIgnoreCert": false,
      "apiJsonq": "string",
      "apiErrorCodes": "string",
      "apiConditions": [
        {}
      ],
      "cps": false,
      "percentageWarning": false,
      "percentageCritical": false,
      "warningTime": 0,
      "madeEnabled": false,
      "ignoreUnknown": false,
      "parentPolicyModuleId": 0,
      "idDataTranslation": 0,
      "tags": [
        0
      ],
      "predictionFormula": [
        {}
      ],
      "snmpCommunity": "string",
      "pluginPass": "string",
      "customString1": "string",
      "customString2": "string",
      "customString3": "string",
      "apiBody": "string",
      "apiHeaders": {}
    }
    ```

**Response 200**: Updated module

Schema: [`PolicyModuleResponse`](#model-policymoduleresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/policy/{idPolicy}/module/{idPolicyModule}` { #delete-policy-idpolicy-module-idpolicymodule }

Mark a module for deletion on policy application

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyModule` | path | integer | yes |  |

**Response 200**: Pending deletion

Schema: [`PolicyModuleResponse`](#model-policymoduleresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/module/{idPolicyModule}/restore` { #post-policy-idpolicy-module-idpolicymodule-restore }

Revert pending deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyModule` | path | integer | yes |  |

**Response 200**: Restored module

Schema: [`PolicyModuleResponse`](#model-policymoduleresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/module/{idPolicyModule}/enable` { #post-policy-idpolicy-module-idpolicymodule-enable }

Enable a policy module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyModule` | path | integer | yes |  |

**Response 200**: Enabled module

Schema: [`PolicyModuleResponse`](#model-policymoduleresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/module/{idPolicyModule}/disable` { #post-policy-idpolicy-module-idpolicymodule-disable }

Disable a policy module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyModule` | path | integer | yes |  |

**Response 200**: Disabled module

Schema: [`PolicyModuleResponse`](#model-policymoduleresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/module` { #post-policy-idpolicy-module }

Create a policy module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idPolicyModule` | integer |  |  |
| `idPolicy` | integer |  |  |
| `moduleType` | enum: `data`, `icmp`, `tcp`, `snmp`, `wmi`, `remotecmd`, `web`, `prediction`, `plugin`, `wux`, `api_retrieve`, `api_custom`, `sat_icmp`, `sat_snmp`, `sat_ssh`, `sat_tcp`, `sat_exec`, `sat_wmi` | yes |  |
| `name` | string | yes |  |
| `description` | string |  |  |
| `idModule` | integer |  |  |
| `idModuleType` | integer |  |  |
| `configurationData` | string, nullable |  | Native configuration is normalized: each line is trimmed, empty lines are removed, line endings are normalized and non-empty text ends with a final newline. Satellite configuration is parsed and regenerated by the module manager. |
| `unit` | string, nullable |  |  |
| `max` | integer (int64), nullable |  |  |
| `min` | integer (int64), nullable |  |  |
| `moduleInterval` | integer, nullable |  |  |
| `ipTarget` | string, nullable |  |  |
| `tcpPort` | integer, nullable |  |  |
| `tcpSend` | string, nullable |  |  |
| `tcpRcv` | string, nullable |  |  |
| `snmpOid` | string, nullable |  |  |
| `idModuleGroup` | integer, nullable |  |  |
| `flag` | integer |  |  |
| `disabled` | boolean |  |  |
| `idExport` | integer, nullable |  |  |
| `pluginUser` | string, nullable |  |  |
| `pluginParameter` | string, nullable |  |  |
| `idPlugin` | integer, nullable |  |  |
| `postProcess` | number, nullable |  |  |
| `predictionModule` | integer, nullable |  |  |
| `maxTimeout` | integer, nullable |  |  |
| `maxRetries` | integer, nullable |  |  |
| `customId` | string, nullable |  |  |
| `historyData` | boolean, nullable |  |  |
| `minWarning` | number, nullable |  |  |
| `maxWarning` | number, nullable |  |  |
| `strWarning` | string, nullable |  |  |
| `minCritical` | number, nullable |  |  |
| `maxCritical` | number, nullable |  |  |
| `strCritical` | string, nullable |  |  |
| `minFfEvent` | integer, nullable |  |  |
| `customInteger1` | integer, nullable |  |  |
| `customInteger2` | integer, nullable |  |  |
| `pendingDelete` | boolean |  |  |
| `criticalInstructions` | string, nullable |  |  |
| `warningInstructions` | string, nullable |  |  |
| `unknownInstructions` | string, nullable |  |  |
| `criticalInverse` | boolean, nullable |  |  |
| `warningInverse` | boolean, nullable |  |  |
| `idCategory` | integer, nullable |  |  |
| `moduleFfInterval` | integer, nullable |  |  |
| `quiet` | boolean |  |  |
| `cronInterval` | string, nullable |  |  |
| `macros` | array, nullable |  |  |
| `disabledTypesEvent` | object, nullable |  |  |
| `moduleMacros` | object, nullable |  |  |
| `minFfEventNormal` | integer, nullable |  |  |
| `minFfEventWarning` | integer, nullable |  |  |
| `minFfEventCritical` | integer, nullable |  |  |
| `ffType` | boolean, nullable |  |  |
| `eachFf` | boolean, nullable |  |  |
| `ffTimeout` | integer, nullable |  |  |
| `dynamicInterval` | integer, nullable |  |  |
| `dynamicMax` | integer, nullable |  |  |
| `dynamicMin` | integer, nullable |  |  |
| `dynamicNext` | integer |  |  |
| `dynamicTwoTailed` | boolean, nullable |  |  |
| `predictionSampleWindow` | integer, nullable |  |  |
| `predictionSamples` | integer, nullable |  |  |
| `predictionThreshold` | integer, nullable |  |  |
| `apiTimeout` | integer, nullable |  |  |
| `apiUrl` | string, nullable |  |  |
| `apiMethod` | string, nullable |  |  |
| `apiIgnoreCert` | boolean |  |  |
| `apiJsonq` | string, nullable |  |  |
| `apiErrorCodes` | string, nullable |  |  |
| `apiConditions` | array, nullable |  |  |
| `cps` | boolean |  |  |
| `percentageWarning` | boolean, nullable |  |  |
| `percentageCritical` | boolean, nullable |  |  |
| `warningTime` | integer, nullable |  |  |
| `madeEnabled` | boolean, nullable |  |  |
| `ignoreUnknown` | boolean |  |  |
| `satelliteType` | string, nullable |  |  |
| `parentPolicyModuleId` | integer |  |  |
| `idDataTranslation` | integer, nullable |  |  |
| `tags` | array of integer |  |  |
| `predictionFormula` | array of object |  |  |
| `snmpCommunity` | string, nullable |  | SNMP credential. Accepted on input only; never returned. |
| `pluginPass` | string, nullable |  | Plugin or SNMP authentication password. Accepted on input only; never returned. |
| `customString1` | string, nullable |  | SNMP privacy protocol or WUX/module configuration. Input only; never returned. |
| `customString2` | string, nullable |  | SNMPv3 privacy password or module-specific configuration. Input only; never returned. |
| `customString3` | string, nullable |  | SNMP security level or module-specific configuration. Input only; never returned. |
| `apiBody` | string, nullable |  | HTTP request body; may contain credentials. Accepted on input only; never returned. |
| `apiHeaders` | object, nullable |  | HTTP request headers; may contain authentication tokens. Input only; never returned. |
| `moduleType` | string | yes |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "moduleType": "string",
      "name": "string",
      "description": "string",
      "idModule": 0,
      "idModuleType": 0,
      "configurationData": "string",
      "unit": "string",
      "max": 0,
      "min": 0,
      "moduleInterval": 0,
      "ipTarget": "string",
      "tcpPort": 0,
      "tcpSend": "string",
      "tcpRcv": "string",
      "snmpOid": "string",
      "idModuleGroup": 0,
      "idExport": 0,
      "pluginUser": "string",
      "pluginParameter": "string",
      "idPlugin": 0,
      "postProcess": 0,
      "predictionModule": 0,
      "maxTimeout": 0,
      "maxRetries": 0,
      "customId": "string",
      "historyData": false,
      "minWarning": 0,
      "maxWarning": 0,
      "strWarning": "string",
      "minCritical": 0,
      "maxCritical": 0,
      "strCritical": "string",
      "minFfEvent": 0,
      "customInteger1": 0,
      "customInteger2": 0,
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "criticalInverse": false,
      "warningInverse": false,
      "idCategory": 0,
      "moduleFfInterval": 0,
      "quiet": false,
      "cronInterval": "string",
      "macros": [
        {}
      ],
      "disabledTypesEvent": {},
      "moduleMacros": {},
      "minFfEventNormal": 0,
      "minFfEventWarning": 0,
      "minFfEventCritical": 0,
      "ffType": false,
      "eachFf": false,
      "ffTimeout": 0,
      "dynamicInterval": 0,
      "dynamicMax": 0,
      "dynamicMin": 0,
      "dynamicTwoTailed": false,
      "predictionSampleWindow": 0,
      "predictionSamples": 0,
      "predictionThreshold": 0,
      "apiTimeout": 0,
      "apiUrl": "string",
      "apiMethod": "string",
      "apiIgnoreCert": false,
      "apiJsonq": "string",
      "apiErrorCodes": "string",
      "apiConditions": [
        {}
      ],
      "cps": false,
      "percentageWarning": false,
      "percentageCritical": false,
      "warningTime": 0,
      "madeEnabled": false,
      "ignoreUnknown": false,
      "parentPolicyModuleId": 0,
      "idDataTranslation": 0,
      "tags": [
        0
      ],
      "predictionFormula": [
        {}
      ],
      "snmpCommunity": "string",
      "pluginPass": "string",
      "customString1": "string",
      "customString2": "string",
      "customString3": "string",
      "apiBody": "string",
      "apiHeaders": {}
    }
    ```

**Response 200**: Created module

Schema: [`PolicyModuleResponse`](#model-policymoduleresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/module/list` { #get-policy-idpolicy-module-list }

List local policy modules

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Modules

Schema: [`PolicyModuleList`](#model-policymodulelist)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/module/list` { #post-policy-idpolicy-module-list }

Filter local policy modules

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idPolicyModule` | integer |  |  |
| `idPolicy` | integer |  |  |
| `name` | string |  |  |
| `idModule` | integer |  |  |
| `idModuleType` | integer |  |  |
| `pendingDelete` | boolean |  |  |
| `disabled` | boolean |  |  |
| `description` | string |  |  |
| `unit` | string |  |  |
| `max` | integer |  |  |
| `min` | integer |  |  |
| `moduleInterval` | integer |  |  |
| `ipTarget` | string |  |  |
| `tcpPort` | integer |  |  |
| `snmpOid` | string |  |  |
| `idModuleGroup` | integer |  |  |
| `flag` | integer |  |  |
| `idExport` | integer |  |  |
| `pluginUser` | string |  |  |
| `idPlugin` | integer |  |  |
| `postProcess` | number |  |  |
| `predictionModule` | integer |  |  |
| `maxTimeout` | integer |  |  |
| `maxRetries` | integer |  |  |
| `customId` | string |  |  |
| `historyData` | boolean |  |  |
| `minWarning` | number |  |  |
| `maxWarning` | number |  |  |
| `strWarning` | string |  |  |
| `minCritical` | number |  |  |
| `maxCritical` | number |  |  |
| `strCritical` | string |  |  |
| `minFfEvent` | integer |  |  |
| `customInteger1` | integer |  |  |
| `customInteger2` | integer |  |  |
| `criticalInstructions` | string |  |  |
| `warningInstructions` | string |  |  |
| `unknownInstructions` | string |  |  |
| `criticalInverse` | boolean |  |  |
| `warningInverse` | boolean |  |  |
| `idCategory` | integer |  |  |
| `moduleFfInterval` | integer |  |  |
| `quiet` | boolean |  |  |
| `cronInterval` | string |  |  |
| `minFfEventNormal` | integer |  |  |
| `minFfEventWarning` | integer |  |  |
| `minFfEventCritical` | integer |  |  |
| `ffType` | boolean |  |  |
| `eachFf` | boolean |  |  |
| `ffTimeout` | integer |  |  |
| `dynamicInterval` | integer |  |  |
| `dynamicMax` | integer |  |  |
| `dynamicMin` | integer |  |  |
| `dynamicNext` | integer |  |  |
| `dynamicTwoTailed` | boolean |  |  |
| `predictionSampleWindow` | integer |  |  |
| `predictionSamples` | integer |  |  |
| `predictionThreshold` | integer |  |  |
| `apiTimeout` | integer |  |  |
| `apiUrl` | string |  |  |
| `apiMethod` | string |  |  |
| `apiIgnoreCert` | boolean |  |  |
| `apiJsonq` | string |  |  |
| `apiErrorCodes` | string |  |  |
| `cps` | boolean |  |  |
| `percentageWarning` | boolean |  |  |
| `percentageCritical` | boolean |  |  |
| `warningTime` | integer |  |  |
| `madeEnabled` | boolean |  |  |
| `ignoreUnknown` | boolean |  |  |
| `satelliteType` | string |  |  |
| `parentPolicyModuleId` | integer |  |  |
| `idDataTranslation` | integer |  |  |
| `freeSearch` | string |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idPolicyModule`, `idPolicy`, `idModuleType`, `description`, `name`, `unit`, `max`, `min`, `moduleInterval`, `ipTarget`, `tcpPort`, `snmpOid`, `idModuleGroup`, `flag`, `idModule`, `disabled`, `idExport`, `pluginUser`, `idPlugin`, `postProcess`, `predictionModule`, `maxTimeout`, `maxRetries`, `customId`, `historyData`, `minWarning`, `maxWarning`, `strWarning`, `minCritical`, `maxCritical`, `strCritical`, `minFfEvent`, `customInteger1`, `customInteger2`, `pendingDelete`, `criticalInstructions`, `warningInstructions`, `unknownInstructions`, `criticalInverse`, `warningInverse`, `idCategory`, `moduleFfInterval`, `quiet`, `cronInterval`, `minFfEventNormal`, `minFfEventWarning`, `minFfEventCritical`, `ffType`, `eachFf`, `ffTimeout`, `dynamicInterval`, `dynamicMax`, `dynamicMin`, `dynamicNext`, `dynamicTwoTailed`, `predictionSampleWindow`, `predictionSamples`, `predictionThreshold`, `apiTimeout`, `apiUrl`, `apiMethod`, `apiIgnoreCert`, `apiJsonq`, `apiErrorCodes`, `cps`, `percentageWarning`, `percentageCritical`, `warningTime`, `madeEnabled`, `ignoreUnknown`, `satelliteType`, `parentPolicyModuleId`, `idDataTranslation` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idPolicyModule`, `idPolicy`, `idModuleType`, `description`, `name`, `unit`, `max`, `min`, `moduleInterval`, `ipTarget`, `tcpPort`, `snmpOid`, `idModuleGroup`, `flag`, `idModule`, `disabled`, `idExport`, `pluginUser`, `idPlugin`, `postProcess`, `predictionModule`, `maxTimeout`, `maxRetries`, `customId`, `historyData`, `minWarning`, `maxWarning`, `strWarning`, `minCritical`, `maxCritical`, `strCritical`, `minFfEvent`, `customInteger1`, `customInteger2`, `pendingDelete`, `criticalInstructions`, `warningInstructions`, `unknownInstructions`, `criticalInverse`, `warningInverse`, `idCategory`, `moduleFfInterval`, `quiet`, `cronInterval`, `minFfEventNormal`, `minFfEventWarning`, `minFfEventCritical`, `ffType`, `eachFf`, `ffTimeout`, `dynamicInterval`, `dynamicMax`, `dynamicMin`, `dynamicNext`, `dynamicTwoTailed`, `predictionSampleWindow`, `predictionSamples`, `predictionThreshold`, `apiTimeout`, `apiUrl`, `apiMethod`, `apiIgnoreCert`, `apiJsonq`, `apiErrorCodes`, `cps`, `percentageWarning`, `percentageCritical`, `warningTime`, `madeEnabled`, `ignoreUnknown`, `satelliteType`, `parentPolicyModuleId`, `idDataTranslation` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idPolicyModule"
      ],
      "fieldConditions": [
        {
          "field": "idPolicyModule",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idPolicyModule": 0,
      "name": "string",
      "idModule": 0,
      "idModuleType": 0,
      "pendingDelete": false,
      "disabled": false,
      "description": "string",
      "unit": "string",
      "max": 0,
      "min": 0,
      "moduleInterval": 0,
      "ipTarget": "string",
      "tcpPort": 0,
      "snmpOid": "string",
      "idModuleGroup": 0,
      "flag": 0,
      "idExport": 0,
      "pluginUser": "string",
      "idPlugin": 0,
      "postProcess": 0,
      "predictionModule": 0,
      "maxTimeout": 0,
      "maxRetries": 0,
      "customId": "string",
      "historyData": false,
      "minWarning": 0,
      "maxWarning": 0,
      "strWarning": "string",
      "minCritical": 0,
      "maxCritical": 0,
      "strCritical": "string",
      "minFfEvent": 0,
      "customInteger1": 0,
      "customInteger2": 0,
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "criticalInverse": false,
      "warningInverse": false,
      "idCategory": 0,
      "moduleFfInterval": 0,
      "quiet": false,
      "cronInterval": "string",
      "minFfEventNormal": 0,
      "minFfEventWarning": 0,
      "minFfEventCritical": 0,
      "ffType": false,
      "eachFf": false,
      "ffTimeout": 0,
      "dynamicInterval": 0,
      "dynamicMax": 0,
      "dynamicMin": 0,
      "dynamicNext": 0,
      "dynamicTwoTailed": false,
      "predictionSampleWindow": 0,
      "predictionSamples": 0,
      "predictionThreshold": 0,
      "apiTimeout": 0,
      "apiUrl": "string",
      "apiMethod": "string",
      "apiIgnoreCert": false,
      "apiJsonq": "string",
      "apiErrorCodes": "string",
      "cps": false,
      "percentageWarning": false,
      "percentageCritical": false,
      "warningTime": 0,
      "madeEnabled": false,
      "ignoreUnknown": false,
      "satelliteType": "string",
      "parentPolicyModuleId": 0,
      "idDataTranslation": 0,
      "freeSearch": "string",
      "multipleSearch": {
        "field": "idPolicyModule",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idPolicyModule",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Modules

Schema: [`PolicyModuleList`](#model-policymodulelist)

Error responses: `400`, `401`, `403`, `404`, `500`.

## PolicyLogModules

API Endpoints for synchronized log collection modules assigned to policies

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/logModule` { #post-policy-idpolicy-logmodule }

Create a policy log module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `collectorMode` | enum: `log_file`, `windows_event` |  | Required on creation; cannot change on update |
| `moduleName` | string |  |  |
| `source` | string |  |  |
| `sourceType` | string |  |  |
| `pattern` | string |  |  |
| `excludePatterns` | array of string |  | File mode only; entries cannot contain commas or line breaks |
| `eventType` | enum: `any`, `informational`, `warning`, `error`, `critical` |  |  |
| `eventCode` | string |  | Windows mode only |
| `enabled` | boolean |  |  |
| `enabled` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "collectorMode": "log_file",
      "moduleName": "string",
      "source": "string",
      "sourceType": "string",
      "pattern": "string",
      "excludePatterns": [
        "string"
      ],
      "eventType": "any",
      "eventCode": "string",
      "enabled": true
    }
    ```

**Response 200**: Created policy log module

Schema: [`PolicyLogModule`](#model-policylogmodule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/logModule/{idPolicyLogModule}` { #get-policy-idpolicy-logmodule-idpolicylogmodule }

Get a local policy log module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyLogModule` | path | integer | yes |  |

**Response 200**: Policy log module

Schema: [`PolicyLogModule`](#model-policylogmodule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/policy/{idPolicy}/logModule/{idPolicyLogModule}` { #put-policy-idpolicy-logmodule-idpolicylogmodule }

Partially update a policy log module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyLogModule` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `collectorMode` | enum: `log_file`, `windows_event` |  | Required on creation; cannot change on update |
| `moduleName` | string |  |  |
| `source` | string |  |  |
| `sourceType` | string |  |  |
| `pattern` | string |  |  |
| `excludePatterns` | array of string |  | File mode only; entries cannot contain commas or line breaks |
| `eventType` | enum: `any`, `informational`, `warning`, `error`, `critical` |  |  |
| `eventCode` | string |  | Windows mode only |
| `enabled` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "collectorMode": "log_file",
      "moduleName": "string",
      "source": "string",
      "sourceType": "string",
      "pattern": "string",
      "excludePatterns": [
        "string"
      ],
      "eventType": "any",
      "eventCode": "string",
      "enabled": false
    }
    ```

**Response 200**: Updated policy log module

Schema: [`PolicyLogModule`](#model-policylogmodule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/policy/{idPolicy}/logModule/{idPolicyLogModule}` { #delete-policy-idpolicy-logmodule-idpolicylogmodule }

Mark a policy log module pending deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyLogModule` | path | integer | yes |  |

**Response 200**: Policy log module pending deletion

Schema: [`PolicyLogModule`](#model-policylogmodule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/logModule/{idPolicyLogModule}/disable` { #post-policy-idpolicy-logmodule-idpolicylogmodule-disable }

Disable a policy log module idempotently

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyLogModule` | path | integer | yes |  |

**Response 200**: Disabled policy log module

Schema: [`PolicyLogModule`](#model-policylogmodule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/logModule/{idPolicyLogModule}/enable` { #post-policy-idpolicy-logmodule-idpolicylogmodule-enable }

Enable a policy log module idempotently

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyLogModule` | path | integer | yes |  |

**Response 200**: Enabled policy log module

Schema: [`PolicyLogModule`](#model-policylogmodule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/logModule/list` { #get-policy-idpolicy-logmodule-list }

List local policy log modules using query pagination and sorting

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Policy log module list

Schema: [`PolicyLogModuleList`](#model-policylogmodulelist)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/logModule/list` { #post-policy-idpolicy-logmodule-list }

List local policy log modules with advanced filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idPolicyLogModule` | integer |  |  |
| `idPolicy` | integer |  | Parent fixed by the route |
| `moduleLogExec` | string |  |  |
| `pendingDelete` | boolean |  |  |
| `freeSearch` | string |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idPolicyLogModule`, `idPolicy`, `moduleLogExec`, `pendingDelete` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idPolicyLogModule`, `idPolicy`, `moduleLogExec`, `pendingDelete` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idPolicyLogModule"
      ],
      "fieldConditions": [
        {
          "field": "idPolicyLogModule",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idPolicyLogModule": 0,
      "moduleLogExec": "string",
      "pendingDelete": false,
      "freeSearch": "string",
      "multipleSearch": {
        "field": "idPolicyLogModule",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idPolicyLogModule",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Policy log module list

Schema: [`PolicyLogModuleList`](#model-policylogmodulelist)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/logModule/{idPolicyLogModule}/restore` { #post-policy-idpolicy-logmodule-idpolicylogmodule-restore }

Revert pending deletion of a policy log module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyLogModule` | path | integer | yes |  |

**Response 200**: Restored policy log module

Schema: [`PolicyLogModule`](#model-policylogmodule)

Error responses: `400`, `401`, `403`, `404`, `500`.

## PolicyPlugins

API Endpoints for plugins assigned to policies

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/plugin/bulk/delete` { #post-policy-idpolicy-plugin-bulk-delete }

Mark policy plugins pending deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)


??? example "Example generated from the schema (placeholder values)"

    ```json
    [
      0
    ]
    ```

**Response 200**: Per-plugin results; missing plugins return an item error

Schema: [`PolicyPluginBulkResult`](#model-policypluginbulkresult)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/plugin/bulk/restore` { #post-policy-idpolicy-plugin-bulk-restore }

Restore policy plugins pending deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)


??? example "Example generated from the schema (placeholder values)"

    ```json
    [
      0
    ]
    ```

**Response 200**: Per-plugin results

Schema: [`PolicyPluginBulkResult`](#model-policypluginbulkresult)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/plugin/bulk/enable` { #post-policy-idpolicy-plugin-bulk-enable }

Enable policy plugins

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)


??? example "Example generated from the schema (placeholder values)"

    ```json
    [
      0
    ]
    ```

**Response 200**: Per-plugin results

Schema: [`PolicyPluginBulkResult`](#model-policypluginbulkresult)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/plugin/bulk/disable` { #post-policy-idpolicy-plugin-bulk-disable }

Disable policy plugins

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)


??? example "Example generated from the schema (placeholder values)"

    ```json
    [
      0
    ]
    ```

**Response 200**: Per-plugin results

Schema: [`PolicyPluginBulkResult`](#model-policypluginbulkresult)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/plugin` { #post-policy-idpolicy-plugin }

Create a policy plugin

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `pluginExecution` | string |  | Input-only DTO for the policy plugin configuration form; it is never persisted directly. Services build PolicyPlugin::pluginExec from these fields, and only PolicyPlugin reaches the DataMapper. A null property represents omission during a partial update; explicit null input is rejected by validation. |
| `timeout` | integer |  |  |
| `intervalMode` | enum: `default`, `absolute` |  |  |
| `interval` |  |  |  |
| `additionalOptions` | string |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "pluginExecution": "string",
      "timeout": 0,
      "intervalMode": "default",
      "interval": 0,
      "additionalOptions": "string"
    }
    ```

**Response 200**: Created policy plugin

Schema: [`PolicyPlugin`](#model-policyplugin)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/plugin/{idPolicyPlugin}` { #get-policy-idpolicy-plugin-idpolicyplugin }

Get a local policy plugin

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyPlugin` | path | integer | yes |  |

**Response 200**: Policy plugin

Schema: [`PolicyPlugin`](#model-policyplugin)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/policy/{idPolicy}/plugin/{idPolicyPlugin}` { #put-policy-idpolicy-plugin-idpolicyplugin }

Partially update a policy plugin

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyPlugin` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `pluginExecution` | string |  | Input-only DTO for the policy plugin configuration form; it is never persisted directly. Services build PolicyPlugin::pluginExec from these fields, and only PolicyPlugin reaches the DataMapper. A null property represents omission during a partial update; explicit null input is rejected by validation. |
| `timeout` | integer |  |  |
| `intervalMode` | enum: `default`, `absolute` |  |  |
| `interval` |  |  |  |
| `additionalOptions` | string |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "pluginExecution": "string",
      "timeout": 0,
      "intervalMode": "default",
      "interval": 0,
      "additionalOptions": "string"
    }
    ```

**Response 200**: Updated policy plugin

Schema: [`PolicyPlugin`](#model-policyplugin)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/policy/{idPolicy}/plugin/{idPolicyPlugin}` { #delete-policy-idpolicy-plugin-idpolicyplugin }

Mark a policy plugin pending deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyPlugin` | path | integer | yes |  |

**Response 200**: Plugin will be deleted on policy application

Schema: [`PolicyPlugin`](#model-policyplugin)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/plugin/{idPolicyPlugin}/disable` { #post-policy-idpolicy-plugin-idpolicyplugin-disable }

Disable a policy plugin

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyPlugin` | path | integer | yes |  |

**Response 200**: Disabled policy plugin

Schema: [`PolicyPlugin`](#model-policyplugin)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/plugin/{idPolicyPlugin}/enable` { #post-policy-idpolicy-plugin-idpolicyplugin-enable }

Enable a policy plugin

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyPlugin` | path | integer | yes |  |

**Response 200**: Enabled policy plugin

Schema: [`PolicyPlugin`](#model-policyplugin)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/plugin/list` { #get-policy-idpolicy-plugin-list }

List local policy plugins using query pagination and sorting

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Policy plugin list

Schema: [`PolicyPluginList`](#model-policypluginlist)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/plugin/list` { #post-policy-idpolicy-plugin-list }

List local policy plugins with advanced filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idPolicyPlugin` | integer |  |  |
| `idPolicy` | integer |  | Parent policy is fixed by the route |
| `pluginExec` | string |  |  |
| `pendingDelete` | boolean |  |  |
| `freeSearch` | string |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idPolicyPlugin`, `idPolicy`, `pluginExec`, `pendingDelete` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idPolicyPlugin`, `idPolicy`, `pluginExec`, `pendingDelete` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idPolicyPlugin"
      ],
      "fieldConditions": [
        {
          "field": "idPolicyPlugin",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idPolicyPlugin": 0,
      "pluginExec": "string",
      "pendingDelete": false,
      "freeSearch": "string",
      "multipleSearch": {
        "field": "idPolicyPlugin",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idPolicyPlugin",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Policy plugin list

Schema: [`PolicyPluginList`](#model-policypluginlist)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/plugin/{idPolicyPlugin}/restore` { #post-policy-idpolicy-plugin-idpolicyplugin-restore }

Cancel pending policy plugin deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyPlugin` | path | integer | yes |  |

**Response 200**: Restored policy plugin

Schema: [`PolicyPlugin`](#model-policyplugin)

Error responses: `400`, `401`, `403`, `404`, `500`.

## PolicyAlerts

API Endpoints for alerts assigned to policy modules

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/alert` { #post-policy-idpolicy-alert }

Create an alert for a policy module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idPolicyModule` | integer | yes |  |
| `idAlertTemplate` | integer | yes |  |
| `disabled` | boolean |  |  |
| `standby` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idPolicyModule": 0,
      "idAlertTemplate": 0,
      "disabled": false,
      "standby": false
    }
    ```

**Response 200**: Policy alert

Schema: [`PolicyAlert`](#model-policyalert)

Error responses: `400`, `401`, `403`, `404`, `409`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/alert/{idPolicyAlert}` { #get-policy-idpolicy-alert-idpolicyalert }

Get a policy module alert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyAlert` | path | integer | yes |  |

**Response 200**: Policy alert

Schema: [`PolicyAlert`](#model-policyalert)

Error responses: `400`, `401`, `403`, `404`.

### <span class="api-method api-put">PUT</span> `/policy/{idPolicy}/alert/{idPolicyAlert}` { #put-policy-idpolicy-alert-idpolicyalert }

Update policy alert status

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyAlert` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `disabled` | boolean |  |  |
| `standby` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "disabled": false,
      "standby": false
    }
    ```

**Response 200**: Policy alert

Schema: [`PolicyAlert`](#model-policyalert)

Error responses: `400`, `401`, `403`, `404`, `409`.

### <span class="api-method api-delete">DELETE</span> `/policy/{idPolicy}/alert/{idPolicyAlert}` { #delete-policy-idpolicy-alert-idpolicyalert }

Mark policy alert for deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyAlert` | path | integer | yes |  |

**Response 200**: Policy alert

Schema: [`PolicyAlert`](#model-policyalert)

Error responses: `400`, `401`, `403`, `404`, `409`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/alert/list` { #get-policy-idpolicy-alert-list }

List policy module alerts

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Policy alerts

??? note "Response fields (21 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyAlert` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idPolicyModule` | integer |  |  |
    | `data.[].idAlertTemplate` | integer |  |  |
    | `data.[].nameExternModule` | string, nullable |  |  |
    | `data.[].disabled` | boolean |  |  |
    | `data.[].standby` | boolean |  |  |
    | `data.[].pendingDelete` | boolean |  |  |
    | `data.[].exactMatch` | boolean |  |  |
    | `data.[].noShowDelete` | boolean |  |  |
    | `data.[].exactMatchFixed` | boolean |  |  |


Error responses: `400`, `401`, `403`, `404`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/alert/list` { #post-policy-idpolicy-alert-list }

Filter policy module alerts

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idPolicyModule` | integer |  |  |
| `idAlertTemplate` | integer |  |  |
| `disabled` | boolean |  |  |
| `standby` | boolean |  |  |
| `pendingDelete` | boolean |  |  |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `sortField` | string |  |  |
| `sortDirection` | enum: `ASC`, `DESC` |  |  |
| `requestedFields` | array of string |  |  |
| `fieldConditions` | array of object |  |  |
| `fieldConditions.[].field` | string | yes | Filter field name. Use the API field name accepted by the filter, for example name, idGroup, createdAt or a field mapped to a JSON column. |
| `fieldConditions.[].jsonPath` | string, nullable |  | Optional JSON path inside the selected field when it is a JSON column. Accepted formats include customer.id, $.customer.id and items[0].name. Operators in and not_in over JSON paths are evaluated as comma-separated lists using FIND_IN_SET. |
| `fieldConditions.[].operator` | enum: `=`, `!=`, `<>`, `>`, `<`, `>=`, `<=`, `like`, `not_like`, `regex`, `not_regex`, `in`, `not_in`, `between`, `not_between`, `is_null`, `is_not_null`, `is_empty`, `is_not_empty` | yes | Condition operator. Aliases such as eq, ne, gt, gte, lt, lte, regexp and not_regexp are also accepted by the API. |
| `fieldConditions.[].value` |  |  | Condition value. Use an array for in, not_in, between and not_between. Value is ignored for is_null, is_not_null, is_empty and is_not_empty. |
| `fieldConditions.[].table` | string, nullable |  | Optional SQL table alias for joined queries. In most API requests this must be omitted. |
| `multipleSearch` | object |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString` | object |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idPolicyAlert`, `idPolicy`, `idPolicyModule`, `idAlertTemplate` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idPolicyAlert`, `idPolicy`, `idPolicyModule`, `idAlertTemplate` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idPolicyAlert"
      ],
      "fieldConditions": [
        {
          "field": "idPolicyAlert",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idPolicyModule": 0,
      "idAlertTemplate": 0,
      "disabled": false,
      "standby": false,
      "pendingDelete": false,
      "sortField": "string",
      "sortDirection": "ASC",
      "multipleSearch": {
        "field": "idPolicyAlert",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idPolicyAlert",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Policy alerts

??? note "Response fields (21 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyAlert` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idPolicyModule` | integer |  |  |
    | `data.[].idAlertTemplate` | integer |  |  |
    | `data.[].nameExternModule` | string, nullable |  |  |
    | `data.[].disabled` | boolean |  |  |
    | `data.[].standby` | boolean |  |  |
    | `data.[].pendingDelete` | boolean |  |  |
    | `data.[].exactMatch` | boolean |  |  |
    | `data.[].noShowDelete` | boolean |  |  |
    | `data.[].exactMatchFixed` | boolean |  |  |


Error responses: `400`, `401`, `403`, `404`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/alert/{idPolicyAlert}/restore` { #post-policy-idpolicy-alert-idpolicyalert-restore }

Restore policy alert pending deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyAlert` | path | integer | yes |  |

**Response 200**: Policy alert

Schema: [`PolicyAlert`](#model-policyalert)

Error responses: `400`, `401`, `403`, `404`, `409`.

## PolicyAlertActions

API Endpoints for actions assigned to policy alerts

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/alert/{idPolicyAlert}/action` { #post-policy-idpolicy-alert-idpolicyalert-action }

Add an action to a policy alert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyAlert` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAlertAction` | integer | yes |  |
| `firesMin` | integer |  |  |
| `firesMax` | integer |  |  |
| `moduleActionThreshold` | integer |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAlertAction": 0,
      "firesMin": 0,
      "firesMax": 0,
      "moduleActionThreshold": 0
    }
    ```

**Response 200**: Action

??? note "Response fields (6 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicyAlertAction` | integer |  |  |
    | `idPolicyAlert` | integer |  |  |
    | `idAlertAction` | integer |  |  |
    | `firesMin` | integer |  |  |
    | `firesMax` | integer |  |  |
    | `moduleActionThreshold` | integer |  |  |


Error responses: `400`, `401`, `403`, `404`, `409`.

### <span class="api-method api-delete">DELETE</span> `/policy/{idPolicy}/alert/{idPolicyAlert}/action/{idPolicyAlertAction}` { #delete-policy-idpolicy-alert-idpolicyalert-action-idpolicyalertaction }

Remove an action from a policy alert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyAlert` | path | integer | yes |  |
| `idPolicyAlertAction` | path | integer | yes |  |

**Response 200**: Action removed

Error responses: `400`, `401`, `403`, `404`, `409`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/alert/{idPolicyAlert}/action/list` { #get-policy-idpolicy-alert-idpolicyalert-action-list }

List actions on a policy alert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyAlert` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Policy alert actions

??? note "Response fields (16 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyAlertAction` | integer |  |  |
    | `data.[].idPolicyAlert` | integer |  |  |
    | `data.[].idAlertAction` | integer |  |  |
    | `data.[].firesMin` | integer |  |  |
    | `data.[].firesMax` | integer |  |  |
    | `data.[].moduleActionThreshold` | integer |  |  |


Error responses: `400`, `401`, `403`, `404`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/alert/{idPolicyAlert}/action/list` { #post-policy-idpolicy-alert-idpolicyalert-action-list }

Filter actions on a policy alert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyAlert` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idAlertAction` | integer |  |  |
| `firesMin` | integer |  |  |
| `firesMax` | integer |  |  |
| `moduleActionThreshold` | integer |  |  |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `sortField` | string |  |  |
| `sortDirection` | enum: `ASC`, `DESC` |  |  |
| `requestedFields` | array of string |  |  |
| `fieldConditions` | array of object |  |  |
| `fieldConditions.[].field` | string | yes | Filter field name. Use the API field name accepted by the filter, for example name, idGroup, createdAt or a field mapped to a JSON column. |
| `fieldConditions.[].jsonPath` | string, nullable |  | Optional JSON path inside the selected field when it is a JSON column. Accepted formats include customer.id, $.customer.id and items[0].name. Operators in and not_in over JSON paths are evaluated as comma-separated lists using FIND_IN_SET. |
| `fieldConditions.[].operator` | enum: `=`, `!=`, `<>`, `>`, `<`, `>=`, `<=`, `like`, `not_like`, `regex`, `not_regex`, `in`, `not_in`, `between`, `not_between`, `is_null`, `is_not_null`, `is_empty`, `is_not_empty` | yes | Condition operator. Aliases such as eq, ne, gt, gte, lt, lte, regexp and not_regexp are also accepted by the API. |
| `fieldConditions.[].value` |  |  | Condition value. Use an array for in, not_in, between and not_between. Value is ignored for is_null, is_not_null, is_empty and is_not_empty. |
| `fieldConditions.[].table` | string, nullable |  | Optional SQL table alias for joined queries. In most API requests this must be omitted. |
| `multipleSearch` | object |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString` | object |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idPolicyAlertAction`, `idPolicyAlert`, `idAlertAction`, `firesMin`, `firesMax`, `moduleActionThreshold` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idPolicyAlertAction`, `idPolicyAlert`, `idAlertAction`, `firesMin`, `firesMax`, `moduleActionThreshold` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idPolicyAlertAction"
      ],
      "fieldConditions": [
        {
          "field": "idPolicyAlertAction",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idAlertAction": 0,
      "firesMin": 0,
      "firesMax": 0,
      "moduleActionThreshold": 0,
      "sortField": "string",
      "sortDirection": "ASC",
      "multipleSearch": {
        "field": "idPolicyAlertAction",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idPolicyAlertAction",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Policy alert actions

??? note "Response fields (16 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyAlertAction` | integer |  |  |
    | `data.[].idPolicyAlert` | integer |  |  |
    | `data.[].idAlertAction` | integer |  |  |
    | `data.[].firesMin` | integer |  |  |
    | `data.[].firesMax` | integer |  |  |
    | `data.[].moduleActionThreshold` | integer |  |  |


Error responses: `400`, `401`, `403`, `404`.

## PolicyExternalAlerts

External policy alerts matching module names or Perl patterns

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/externalAlert` { #post-policy-idpolicy-externalalert }

Create an external policy alert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAlertTemplate` | integer | yes |  |
| `nameExternModule` | string | yes |  |
| `exactMatch` | boolean |  | False uses a Perl regular expression, evaluated when applying the policy. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAlertTemplate": 0,
      "nameExternModule": "string",
      "exactMatch": true
    }
    ```

**Response 200**: External alert

Schema: [`PolicyExternalAlert`](#model-policyexternalalert)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}` { #get-policy-idpolicy-externalalert-idpolicyexternalalert }

Get an external policy alert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyExternalAlert` | path | integer | yes |  |

**Response 200**: External alert

Schema: [`PolicyExternalAlert`](#model-policyexternalalert)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}` { #delete-policy-idpolicy-externalalert-idpolicyexternalalert }

Mark an external alert for deletion at the next policy application

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyExternalAlert` | path | integer | yes |  |

**Response 200**: External alert pending deletion

Schema: [`PolicyExternalAlert`](#model-policyexternalalert)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/externalAlert/list` { #get-policy-idpolicy-externalalert-list }

List external policy alerts

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: External alerts

Schema: [`PolicyExternalAlertList`](#model-policyexternalalertlist)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/externalAlert/list` { #post-policy-idpolicy-externalalert-list }

Filter external policy alerts

When there are no explicit action associations, the template default action is used.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idAlertTemplate` | integer |  |  |
| `nameExternModule` | string |  |  |
| `moduleName` | string |  | Substring of the module name or pattern |
| `templateName` | string |  | Substring of the template name |
| `idAlertAction` | integer |  |  |
| `exactMatch` | boolean |  |  |
| `pendingDelete` | boolean |  |  |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `sortField` | string |  |  |
| `sortDirection` | enum: `ASC`, `DESC` |  |  |
| `requestedFields` | array of string |  |  |
| `fieldConditions` | array of object |  |  |
| `fieldConditions.[].field` | string | yes | Filter field name. Use the API field name accepted by the filter, for example name, idGroup, createdAt or a field mapped to a JSON column. |
| `fieldConditions.[].jsonPath` | string, nullable |  | Optional JSON path inside the selected field when it is a JSON column. Accepted formats include customer.id, $.customer.id and items[0].name. Operators in and not_in over JSON paths are evaluated as comma-separated lists using FIND_IN_SET. |
| `fieldConditions.[].operator` | enum: `=`, `!=`, `<>`, `>`, `<`, `>=`, `<=`, `like`, `not_like`, `regex`, `not_regex`, `in`, `not_in`, `between`, `not_between`, `is_null`, `is_not_null`, `is_empty`, `is_not_empty` | yes | Condition operator. Aliases such as eq, ne, gt, gte, lt, lte, regexp and not_regexp are also accepted by the API. |
| `fieldConditions.[].value` |  |  | Condition value. Use an array for in, not_in, between and not_between. Value is ignored for is_null, is_not_null, is_empty and is_not_empty. |
| `fieldConditions.[].table` | string, nullable |  | Optional SQL table alias for joined queries. In most API requests this must be omitted. |
| `multipleSearch` | object |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString` | object |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idPolicyExternalAlert`, `idPolicy`, `idAlertTemplate`, `nameExternModule` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idPolicyExternalAlert`, `idPolicy`, `idAlertTemplate`, `nameExternModule` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idPolicyExternalAlert"
      ],
      "fieldConditions": [
        {
          "field": "idPolicyExternalAlert",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idAlertTemplate": 0,
      "nameExternModule": "string",
      "moduleName": "string",
      "templateName": "string",
      "idAlertAction": 0,
      "exactMatch": false,
      "pendingDelete": false,
      "sortField": "string",
      "sortDirection": "ASC",
      "multipleSearch": {
        "field": "idPolicyExternalAlert",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idPolicyExternalAlert",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: External alerts

Schema: [`PolicyExternalAlertList`](#model-policyexternalalertlist)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}/restore` { #post-policy-idpolicy-externalalert-idpolicyexternalalert-restore }

Revert external alert deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyExternalAlert` | path | integer | yes |  |

**Response 200**: Restored external alert

Schema: [`PolicyExternalAlert`](#model-policyexternalalert)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

## PolicyExternalAlertActions

Actions associated with external policy alerts

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}/action` { #post-policy-idpolicy-externalalert-idpolicyexternalalert-action }

Add an external alert action

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyExternalAlert` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAlertAction` | integer | yes |  |
| `firesMin` | integer |  |  |
| `firesMax` | integer |  |  |
| `moduleActionThreshold` | integer |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAlertAction": 0,
      "firesMin": 0,
      "firesMax": 0,
      "moduleActionThreshold": 0
    }
    ```

**Response 200**: Action association

??? note "Response fields (6 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicyExternalAlertAction` | integer |  |  |
    | `idPolicyExternalAlert` | integer |  |  |
    | `idAlertAction` | integer |  |  |
    | `firesMin` | integer |  |  |
    | `firesMax` | integer |  |  |
    | `moduleActionThreshold` | integer |  |  |


Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-delete">DELETE</span> `/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}/action/{idPolicyExternalAlertAction}` { #delete-policy-idpolicy-externalalert-idpolicyexternalalert-action-idpolicyexternalalertaction }

Remove an external alert action

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyExternalAlert` | path | integer | yes |  |
| `idPolicyExternalAlertAction` | path | integer | yes |  |

**Response 200**: Action association deleted

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}/action/list` { #get-policy-idpolicy-externalalert-idpolicyexternalalert-action-list }

List external alert actions

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyExternalAlert` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Explicit action associations

Schema: [`PolicyExternalAlertActionList`](#model-policyexternalalertactionlist)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/externalAlert/{idPolicyExternalAlert}/action/list` { #post-policy-idpolicy-externalalert-idpolicyexternalalert-action-list }

Filter external alert actions

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyExternalAlert` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idAlertAction` | integer |  |  |
| `firesMin` | integer |  |  |
| `firesMax` | integer |  |  |
| `moduleActionThreshold` | integer |  |  |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `sortField` | string |  |  |
| `sortDirection` | enum: `ASC`, `DESC` |  |  |
| `requestedFields` | array of string |  |  |
| `fieldConditions` | array of object |  |  |
| `fieldConditions.[].field` | string | yes | Filter field name. Use the API field name accepted by the filter, for example name, idGroup, createdAt or a field mapped to a JSON column. |
| `fieldConditions.[].jsonPath` | string, nullable |  | Optional JSON path inside the selected field when it is a JSON column. Accepted formats include customer.id, $.customer.id and items[0].name. Operators in and not_in over JSON paths are evaluated as comma-separated lists using FIND_IN_SET. |
| `fieldConditions.[].operator` | enum: `=`, `!=`, `<>`, `>`, `<`, `>=`, `<=`, `like`, `not_like`, `regex`, `not_regex`, `in`, `not_in`, `between`, `not_between`, `is_null`, `is_not_null`, `is_empty`, `is_not_empty` | yes | Condition operator. Aliases such as eq, ne, gt, gte, lt, lte, regexp and not_regexp are also accepted by the API. |
| `fieldConditions.[].value` |  |  | Condition value. Use an array for in, not_in, between and not_between. Value is ignored for is_null, is_not_null, is_empty and is_not_empty. |
| `fieldConditions.[].table` | string, nullable |  | Optional SQL table alias for joined queries. In most API requests this must be omitted. |
| `multipleSearch` | object |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString` | object |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idPolicyExternalAlertAction`, `idPolicyExternalAlert`, `idAlertAction`, `firesMin`, `firesMax`, `moduleActionThreshold` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idPolicyExternalAlertAction`, `idPolicyExternalAlert`, `idAlertAction`, `firesMin`, `firesMax`, `moduleActionThreshold` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idPolicyExternalAlertAction"
      ],
      "fieldConditions": [
        {
          "field": "idPolicyExternalAlertAction",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idAlertAction": 0,
      "firesMin": 0,
      "firesMax": 0,
      "moduleActionThreshold": 0,
      "sortField": "string",
      "sortDirection": "ASC",
      "multipleSearch": {
        "field": "idPolicyExternalAlertAction",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idPolicyExternalAlertAction",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Explicit action associations

Schema: [`PolicyExternalAlertActionList`](#model-policyexternalalertactionlist)

Error responses: `400`, `401`, `403`, `404`, `500`.

## PolicyCollections

Collection associations in policies, including deferred removal and restoration

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/collection` { #post-policy-idpolicy-collection }

Associate a collection with a policy

Not idempotent: an existing policy/collection association returns HTTP 400.
If the association is pending deletion, use restore instead of adding it again.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idCollection` | integer | yes |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idCollection": 0
    }
    ```

**Response 200**: Created association

Schema: [`PolicyCollection`](#model-policycollection)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/collection/{idPolicyCollection}` { #get-policy-idpolicy-collection-idpolicycollection }

Get a policy collection association

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyCollection` | path | integer | yes | Policy collection association identifier, not the collection identifier |

**Response 200**: Policy collection association

Schema: [`PolicyCollection`](#model-policycollection)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/policy/{idPolicy}/collection/{idPolicyCollection}` { #delete-policy-idpolicy-collection-idpolicycollection }

Mark a policy collection for deletion

The association is removed during the next policy application, not immediately.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyCollection` | path | integer | yes | Policy collection association identifier, not the collection identifier |

**Response 200**: Association pending deletion

Schema: [`PolicyCollection`](#model-policycollection)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/collection/available/list` { #get-policy-idpolicy-collection-available-list }

List available collections using query filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `freeSearch` | query | string |  |  |

**Response 200**: ACL-scoped collection list

??? note "Response fields (16 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idCollection` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].shortName` | string |  | Immutable after creation. Empty or omitted generates fc_<timestamp>. |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].status` | enum: `0`, `1` |  | Persisted status: 0 pending apply, 1 applied. Updating metadata sets 1 as in the console. |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/collection/available/list` { #post-policy-idpolicy-collection-available-list }

List available collections using advanced filters

Existing associations, including pending deletions, are excluded from data and both totals.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idCollection` | integer |  |  |
| `name` | string |  |  |
| `shortName` | string |  |  |
| `idGroup` | integer |  |  |
| `description` | string, nullable |  |  |
| `status` | enum: `0`, `1` |  |  |
| `freeSearch` | string, nullable |  | Search name, shortName and description. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idCollection`, `name`, `shortName`, `idGroup`, `description`, `status` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idCollection`, `name`, `shortName`, `idGroup`, `description`, `status` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idCollection"
      ],
      "fieldConditions": [
        {
          "field": "idCollection",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idCollection": 0,
      "name": "string",
      "shortName": "string",
      "idGroup": 0,
      "description": "string",
      "status": 0,
      "freeSearch": "string",
      "multipleSearch": {
        "field": "idCollection",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idCollection",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: ACL-scoped collection list

??? note "Response fields (16 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idCollection` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].shortName` | string |  | Immutable after creation. Empty or omitted generates fc_<timestamp>. |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].status` | enum: `0`, `1` |  | Persisted status: 0 pending apply, 1 applied. Updating metadata sets 1 as in the console. |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/collection/list` { #get-policy-idpolicy-collection-list }

List policy collections using query filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `idCollection` | query | integer |  |  |
| `pendingDelete` | query | boolean |  |  |

**Response 200**: ACL-scoped policy collection associations

??? note "Response fields (14 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyCollection` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idCollection` | integer |  |  |
    | `data.[].pendingDelete` | boolean |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/collection/list` { #post-policy-idpolicy-collection-list }

List policy collections using advanced filters

Body filters override query filters. Parent and collection ACL scope apply to both totals.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idPolicyCollection` | integer |  |  |
| `idPolicy` | integer |  |  |
| `idCollection` | integer |  |  |
| `pendingDelete` | boolean |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idPolicyCollection`, `idPolicy`, `idCollection`, `pendingDelete` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idPolicyCollection`, `idPolicy`, `idCollection`, `pendingDelete` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idPolicyCollection"
      ],
      "fieldConditions": [
        {
          "field": "idPolicyCollection",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idPolicyCollection": 0,
      "idCollection": 0,
      "pendingDelete": false,
      "multipleSearch": {
        "field": "idPolicyCollection",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idPolicyCollection",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: ACL-scoped policy collection associations

??? note "Response fields (14 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyCollection` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idCollection` | integer |  |  |
    | `data.[].pendingDelete` | boolean |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/collection/{idPolicyCollection}/restore` { #post-policy-idpolicy-collection-idpolicycollection-restore }

Undo pending policy collection deletion

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyCollection` | path | integer | yes | Policy collection association identifier, not the collection identifier |

**Response 200**: Restored association

Schema: [`PolicyCollection`](#model-policycollection)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

## PolicyFim

Synchronized FIM configuration assigned to policies

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/fim` { #get-policy-idpolicy-fim }

Get policy FIM configuration

Returns FIM defaults with a null idPolicyFim when the policy has no saved configuration.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Response 200**: Policy FIM configuration

Schema: [`PolicyFim`](#model-policyfim)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/policy/{idPolicy}/fim` { #put-policy-idpolicy-fim }

Save policy FIM configuration

Creates or partially updates FIM settings and marks the policy pending full application.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`): [`PolicyFim`](#model-policyfim)

**Response 200**: Saved policy FIM configuration

Schema: [`PolicyFim`](#model-policyfim)

Error responses: `400`, `401`, `403`, `404`, `500`.

## PolicyLinking

Unlinked policy agent modules and individual or bulk relinking

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/linking/bulk/link` { #post-policy-idpolicy-linking-bulk-link }

Relink selected policy agent modules

Per-module results; successful items are not rolled back when another item fails.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `[].idAgentModule` | integer | yes |  |
| `[].serverId` | integer, nullable |  | Required on a metaconsole; omit on a node |

??? example "Example generated from the schema (placeholder values)"

    ```json
    [
      {
        "idAgentModule": 0,
        "serverId": 0
      }
    ]
    ```

**Response 200**: Per-module results

??? note "Response fields (18 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `successCount` | integer |  |  |
    | `errorCount` | integer |  |  |
    | `results` | array of object |  |  |
    | `results.[].idAgentModule` | integer |  |  |
    | `results.[].serverId` | integer, nullable |  |  |
    | `results.[].success` | boolean |  |  |
    | `results.[].status` | integer |  |  |
    | `results.[].data` | object |  |  |
    | `results.[].data.idPolicy` | integer |  |  |
    | `results.[].data.idAgentModule` | integer |  |  |
    | `results.[].data.idAgent` | integer |  |  |
    | `results.[].data.agentAlias` | string |  |  |
    | `results.[].data.name` | string |  |  |
    | `results.[].data.idPolicyModule` | integer |  |  |
    | `results.[].data.policyLinked` | enum: `0`, `1`, `10`, `11` |  | 0 unlinked, 1 linked, 10 pending unlink, 11 pending link |
    | `results.[].data.policyAdopted` | boolean |  |  |
    | `results.[].data.serverId` | integer, nullable |  |  |
    | `results.[].error` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/linking/{idAgentModule}/link` { #post-policy-idpolicy-linking-idagentmodule-link }

Relink an existing policy agent module

Idempotent for states 1 and 11. State 0 becomes 11; state 10 becomes 1.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idAgentModule` | path | integer | yes | Agent module instance identifier belonging to the requested policy |
| `serverId` | query | integer |  | Node selector on a metaconsole; required for mutations, optional for aggregated lists |

**Response 200**: Resulting policy link state

??? note "Response fields (9 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicy` | integer |  |  |
    | `idAgentModule` | integer |  |  |
    | `idAgent` | integer |  |  |
    | `agentAlias` | string |  |  |
    | `name` | string |  |  |
    | `idPolicyModule` | integer |  |  |
    | `policyLinked` | enum: `0`, `1`, `10`, `11` |  | 0 unlinked, 1 linked, 10 pending unlink, 11 pending link |
    | `policyAdopted` | boolean |  |  |
    | `serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/linking/list` { #get-policy-idpolicy-linking-list }

List unlinked modules using query filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `serverId` | query | integer |  | Node selector on a metaconsole; required for mutations, optional for aggregated lists |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `freeSearch` | query | string |  |  |

**Response 200**: ACL-scoped unlinked modules

??? note "Response fields (19 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idAgentModule` | integer |  |  |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].agentAlias` | string |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].idPolicyModule` | integer |  |  |
    | `data.[].policyLinked` | enum: `0`, `1`, `10`, `11` |  | 0 unlinked, 1 linked, 10 pending unlink, 11 pending link |
    | `data.[].policyAdopted` | boolean |  |  |
    | `data.[].serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/linking/list` { #post-policy-idpolicy-linking-list }

List unlinked modules using advanced filters

Body filters override query filters. Without serverId, metaconsole reads aggregate nodes.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `serverId` | query | integer |  | Node selector on a metaconsole; required for mutations, optional for aggregated lists |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `sortField` | string, nullable |  |  |
| `sortDirection` | enum: `ASC`, `DESC` |  |  |
| `requestedFields` | array of string |  |  |
| `fieldConditions` | array of object |  |  |
| `fieldConditions.[].field` | string | yes | Filter field name. Use the API field name accepted by the filter, for example name, idGroup, createdAt or a field mapped to a JSON column. |
| `fieldConditions.[].jsonPath` | string, nullable |  | Optional JSON path inside the selected field when it is a JSON column. Accepted formats include customer.id, $.customer.id and items[0].name. Operators in and not_in over JSON paths are evaluated as comma-separated lists using FIND_IN_SET. |
| `fieldConditions.[].operator` | enum: `=`, `!=`, `<>`, `>`, `<`, `>=`, `<=`, `like`, `not_like`, `regex`, `not_regex`, `in`, `not_in`, `between`, `not_between`, `is_null`, `is_not_null`, `is_empty`, `is_not_empty` | yes | Condition operator. Aliases such as eq, ne, gt, gte, lt, lte, regexp and not_regexp are also accepted by the API. |
| `fieldConditions.[].value` |  |  | Condition value. Use an array for in, not_in, between and not_between. Value is ignored for is_null, is_not_null, is_empty and is_not_empty. |
| `fieldConditions.[].table` | string, nullable |  | Optional SQL table alias for joined queries. In most API requests this must be omitted. |
| `multipleSearch` | object |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString` | object |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `freeSearch` | string, nullable |  | Search module names and agent aliases |
| `idAgentModule` | integer |  |  |
| `idAgent` | integer |  |  |
| `idPolicyModule` | integer |  |  |
| `name` | string |  |  |
| `agentAlias` | string |  |  |
| `policyLinked` | enum: `0`, `1`, `10`, `11` |  |  |
| `policyAdopted` | boolean |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idAgentModule`, `idAgent`, `idPolicy`, `idPolicyModule`, `name`, `agentAlias`, `policyLinked`, `policyAdopted` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAgentModule`, `idAgent`, `idPolicy`, `idPolicyModule`, `name`, `agentAlias`, `policyLinked`, `policyAdopted` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idAgentModule"
      ],
      "fieldConditions": [
        {
          "field": "idAgentModule",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "sortField": "string",
      "sortDirection": "ASC",
      "multipleSearch": {
        "field": "idAgentModule",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAgentModule",
        "data": [
          "string"
        ]
      },
      "freeSearch": "string",
      "idAgentModule": 0,
      "idAgent": 0,
      "idPolicyModule": 0,
      "name": "string",
      "agentAlias": "string",
      "policyLinked": 0,
      "policyAdopted": false
    }
    ```

**Response 200**: ACL-scoped unlinked modules

??? note "Response fields (19 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idAgentModule` | integer |  |  |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].agentAlias` | string |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].idPolicyModule` | integer |  |  |
    | `data.[].policyLinked` | enum: `0`, `1`, `10`, `11` |  | 0 unlinked, 1 linked, 10 pending unlink, 11 pending link |
    | `data.[].policyAdopted` | boolean |  |  |
    | `data.[].serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

## PolicyQueue

Policy operation queues, pending changes and distributed application

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/queue/applyPending` { #post-policy-idpolicy-queue-applypending }

Enqueue application and removal for authorized pending policy agents

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `serverId` | query | integer |  | Metaconsole only: positive node ID, or 0 for its local queue. Omission aggregates list/summary, distributes create/applyPending to enabled nodes, and requires an explicit target for get/delete/clear. |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `operation` | enum: `apply`, `apply_db` |  | Application operation for active pending agents; defaults to the policy database/files state. Agents pending deletion are always enqueued individually with operation delete. |
| `priority` | integer |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "operation": "apply",
      "priority": 0
    }
    ```

**Response 200**: Created and skipped operations, optionally grouped by console

??? note "Response fields (18 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `serverId` | integer, nullable |  |  |
    | `created` | array of object |  |  |
    | `created.[].idPolicyQueue` | integer |  |  |
    | `created.[].idPolicy` | integer |  |  |
    | `created.[].idAgent` | integer |  | Zero targets all policy agents |
    | `created.[].operation` | string, nullable |  |  |
    | `created.[].progress` | integer |  | -1 means application failed or timed out and can be retried by the worker |
    | `created.[].endUtimestamp` | integer |  |  |
    | `created.[].priority` | integer |  |  |
    | `created.[].serverId` | integer, nullable |  |  |
    | `skipped` | integer |  |  |
    | `deleted` | integer |  |  |
    | `results` | array of object |  |  |
    | `results.[].serverId` | integer |  |  |
    | `results.[].success` | boolean |  |  |
    | `results.[].status` | integer |  |  |
    | `results.[].error` | string |  |  |
    | `results.[].data` | object |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `503`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/queue/clear` { #post-policy-idpolicy-queue-clear }

Clear matching waiting or completed operations on one console

Filters apply without pagination. Operations applying or timed out are never deleted.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `serverId` | query | integer |  | Metaconsole only: positive node ID, or 0 for its local queue. Omission aggregates list/summary, distributes create/applyPending to enabled nodes, and requires an explicit target for get/delete/clear. |

**Request body** (`application/json`): [`PolicyQueueFilter`](#model-policyqueuefilter)

**Response 200**: Deleted count

??? note "Response fields (2 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `deleted` | integer | yes | Number of deleted queue operations |
    | `serverId` | integer, nullable | yes | Null on a node; selected node ID or 0 for the local metaconsole queue. |


Error responses: `400`, `401`, `403`, `404`, `500`, `503`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/queue` { #post-policy-idpolicy-queue }

Enqueue a policy operation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `serverId` | query | integer |  | Metaconsole only: positive node ID, or 0 for its local queue. Omission aggregates list/summary, distributes create/applyPending to enabled nodes, and requires an explicit target for get/delete/clear. |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `operation` | enum: `apply`, `apply_db`, `delete` | yes |  |
| `idAgent` | integer |  |  |
| `priority` | integer |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "operation": "apply",
      "idAgent": 0,
      "priority": 0
    }
    ```

**Response 200**: Created operation or per-console distributed results

??? note "Response fields (14 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicyQueue` | integer |  |  |
    | `idPolicy` | integer |  |  |
    | `idAgent` | integer |  | Zero targets all policy agents |
    | `operation` | string, nullable |  |  |
    | `progress` | integer |  | -1 means application failed or timed out and can be retried by the worker |
    | `endUtimestamp` | integer |  |  |
    | `priority` | integer |  |  |
    | `serverId` | integer, nullable |  |  |
    | `results` | array of object |  |  |
    | `results.[].serverId` | integer |  |  |
    | `results.[].success` | boolean |  |  |
    | `results.[].status` | integer |  |  |
    | `results.[].error` | string |  |  |
    | `results.[].data` | object |  |  |


Error responses: `400`, `401`, `403`, `404`, `409`, `500`, `503`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/queue/{idPolicyQueue}` { #get-policy-idpolicy-queue-idpolicyqueue }

Get a queue operation and its current progress

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyQueue` | path | integer | yes |  |
| `serverId` | query | integer |  | Metaconsole only: positive node ID, or 0 for its local queue. Omission aggregates list/summary, distributes create/applyPending to enabled nodes, and requires an explicit target for get/delete/clear. |

**Response 200**: Queue operation

??? note "Response fields (8 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicyQueue` | integer |  |  |
    | `idPolicy` | integer |  |  |
    | `idAgent` | integer |  | Zero targets all policy agents |
    | `operation` | string, nullable |  |  |
    | `progress` | integer |  | -1 means application failed or timed out and can be retried by the worker |
    | `endUtimestamp` | integer |  |  |
    | `priority` | integer |  |  |
    | `serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `503`.

### <span class="api-method api-delete">DELETE</span> `/policy/{idPolicy}/queue/{idPolicyQueue}` { #delete-policy-idpolicy-queue-idpolicyqueue }

Delete a waiting or completed queue operation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `idPolicyQueue` | path | integer | yes |  |
| `serverId` | query | integer |  | Metaconsole only: positive node ID, or 0 for its local queue. Omission aggregates list/summary, distributes create/applyPending to enabled nodes, and requires an explicit target for get/delete/clear. |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `409`, `500`, `503`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/queue/list` { #get-policy-idpolicy-queue-list }

List queue operations using query filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `serverId` | query | integer |  | Metaconsole only: positive node ID, or 0 for its local queue. Omission aggregates list/summary, distributes create/applyPending to enabled nodes, and requires an explicit target for get/delete/clear. |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `idAgent` | query | integer |  |  |
| `operation` | query | string |  |  |
| `progress` | query | integer |  |  |
| `status` | query | enum: `all`, `complete`, `incomplete` |  |  |

**Response 200**: Authorized policy queue operations

??? note "Response fields (24 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyQueue` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idAgent` | integer |  | Zero targets all policy agents |
    | `data.[].operation` | string, nullable |  |  |
    | `data.[].progress` | integer |  | -1 means application failed or timed out and can be retried by the worker |
    | `data.[].endUtimestamp` | integer |  |  |
    | `data.[].priority` | integer |  |  |
    | `data.[].serverId` | integer, nullable |  |  |
    | `errors` | array of object |  |  |
    | `errors.[].serverId` | integer |  |  |
    | `errors.[].success` | boolean |  |  |
    | `errors.[].status` | integer |  |  |
    | `errors.[].error` | string |  |  |
    | `errors.[].data` | object |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/policy/{idPolicy}/queue/list` { #post-policy-idpolicy-queue-list }

List queue operations using advanced filters

Body filters override query filters; parent and ACL scope apply to both totals.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `serverId` | query | integer |  | Metaconsole only: positive node ID, or 0 for its local queue. Omission aggregates list/summary, distributes create/applyPending to enabled nodes, and requires an explicit target for get/delete/clear. |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`): [`PolicyQueueFilter`](#model-policyqueuefilter)

**Response 200**: Authorized policy queue operations

??? note "Response fields (24 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyQueue` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idAgent` | integer |  | Zero targets all policy agents |
    | `data.[].operation` | string, nullable |  |  |
    | `data.[].progress` | integer |  | -1 means application failed or timed out and can be retried by the worker |
    | `data.[].endUtimestamp` | integer |  |  |
    | `data.[].priority` | integer |  |  |
    | `data.[].serverId` | integer, nullable |  |  |
    | `errors` | array of object |  |  |
    | `errors.[].serverId` | integer |  |  |
    | `errors.[].success` | boolean |  |  |
    | `errors.[].status` | integer |  |  |
    | `errors.[].error` | string |  |  |
    | `errors.[].data` | object |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/policy/{idPolicy}/queue/summary` { #get-policy-idpolicy-queue-summary }

Get pending policy changes and authorized agent/group counters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPolicy` | path | integer | yes |  |
| `serverId` | query | integer |  | Metaconsole only: positive node ID, or 0 for its local queue. Omission aggregates list/summary, distributes create/applyPending to enabled nodes, and requires an explicit target for get/delete/clear. |

**Response 200**: Summary or per-console summaries

??? note "Response fields (63 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicy` | integer |  |  |
    | `serverId` | integer, nullable |  |  |
    | `status` | integer |  |  |
    | `agents` | object |  |  |
    | `agents.total` | integer |  |  |
    | `agents.pendingApply` | integer |  |  |
    | `agents.pendingDelete` | integer |  |  |
    | `agents.linkPending` | integer |  |  |
    | `agents.unlinkPending` | integer |  |  |
    | `groups` | object |  |  |
    | `groups.total` | integer |  |  |
    | `groups.pendingApply` | integer |  |  |
    | `groups.pendingDelete` | integer |  |  |
    | `groups.linkPending` | integer |  |  |
    | `groups.unlinkPending` | integer |  |  |
    | `modules` | object |  |  |
    | `modules.total` | integer |  |  |
    | `modules.pendingApply` | integer |  |  |
    | `modules.pendingDelete` | integer |  |  |
    | `modules.linkPending` | integer |  |  |
    | `modules.unlinkPending` | integer |  |  |
    | `inventoryModules` | object |  |  |
    | `inventoryModules.total` | integer |  |  |
    | `inventoryModules.pendingApply` | integer |  |  |
    | `inventoryModules.pendingDelete` | integer |  |  |
    | `inventoryModules.linkPending` | integer |  |  |
    | `inventoryModules.unlinkPending` | integer |  |  |
    | `alerts` | object |  |  |
    | `alerts.total` | integer |  |  |
    | `alerts.pendingApply` | integer |  |  |
    | `alerts.pendingDelete` | integer |  |  |
    | `alerts.linkPending` | integer |  |  |
    | `alerts.unlinkPending` | integer |  |  |
    | `externalAlerts` | object |  |  |
    | `externalAlerts.total` | integer |  |  |
    | `externalAlerts.pendingApply` | integer |  |  |
    | `externalAlerts.pendingDelete` | integer |  |  |
    | `externalAlerts.linkPending` | integer |  |  |
    | `externalAlerts.unlinkPending` | integer |  |  |
    | `collections` | object |  |  |
    | `collections.total` | integer |  |  |
    | `collections.pendingApply` | integer |  |  |
    | `collections.pendingDelete` | integer |  |  |
    | `collections.linkPending` | integer |  |  |
    | `collections.unlinkPending` | integer |  |  |
    | `plugins` | object |  |  |
    | `plugins.total` | integer |  |  |
    | `plugins.pendingApply` | integer |  |  |
    | `plugins.pendingDelete` | integer |  |  |
    | `plugins.linkPending` | integer |  |  |
    | `plugins.unlinkPending` | integer |  |  |
    | `logModules` | object |  |  |
    | `logModules.total` | integer |  |  |
    | `logModules.pendingApply` | integer |  |  |
    | `logModules.pendingDelete` | integer |  |  |
    | `logModules.linkPending` | integer |  |  |
    | `logModules.unlinkPending` | integer |  |  |
    | `results` | array of object |  |  |
    | `results.[].serverId` | integer |  |  |
    | `results.[].success` | boolean |  |  |
    | `results.[].status` | integer |  |  |
    | `results.[].error` | string |  |  |
    | `results.[].data` | object |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `503`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: PolicyAgent { #model-policyagent }

??? note "Fields (7 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicyAgent` | integer |  |  |
    | `idPolicy` | integer |  |  |
    | `idAgent` | integer |  |  |
    | `idNode` | integer |  |  |
    | `policyApplied` | boolean |  |  |
    | `pendingDelete` | boolean |  |  |
    | `lastApplyUtimestamp` | integer |  |  |


### Model: PolicyAlert { #model-policyalert }

??? note "Fields (11 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicyAlert` | integer |  |  |
    | `idPolicy` | integer |  |  |
    | `idPolicyModule` | integer |  |  |
    | `idAlertTemplate` | integer |  |  |
    | `nameExternModule` | string, nullable |  |  |
    | `disabled` | boolean |  |  |
    | `standby` | boolean |  |  |
    | `pendingDelete` | boolean |  |  |
    | `exactMatch` | boolean |  |  |
    | `noShowDelete` | boolean |  |  |
    | `exactMatchFixed` | boolean |  |  |


### Model: PolicyCollection { #model-policycollection }

??? note "Fields (4 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicyCollection` | integer |  |  |
    | `idPolicy` | integer |  |  |
    | `idCollection` | integer |  |  |
    | `pendingDelete` | boolean |  |  |


### Model: PolicyExternalAlert { #model-policyexternalalert }

??? note "Fields (10 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicyExternalAlert` | integer |  |  |
    | `idPolicy` | integer |  |  |
    | `idAlertTemplate` | integer |  |  |
    | `nameExternModule` | string |  |  |
    | `exactMatch` | boolean |  | True matches the literal module name; false uses a Perl regular expression. |
    | `pendingDelete` | boolean |  |  |
    | `noShowDelete` | boolean |  |  |
    | `disabled` | boolean |  |  |
    | `standby` | boolean |  |  |
    | `exactMatchFixed` | boolean |  |  |


### Model: PolicyExternalAlertActionList { #model-policyexternalalertactionlist }

??? note "Fields (16 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyExternalAlertAction` | integer |  |  |
    | `data.[].idPolicyExternalAlert` | integer |  |  |
    | `data.[].idAlertAction` | integer |  |  |
    | `data.[].firesMin` | integer |  |  |
    | `data.[].firesMax` | integer |  |  |
    | `data.[].moduleActionThreshold` | integer |  |  |


### Model: PolicyExternalAlertList { #model-policyexternalalertlist }

??? note "Fields (20 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyExternalAlert` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].idAlertTemplate` | integer |  |  |
    | `data.[].nameExternModule` | string |  |  |
    | `data.[].exactMatch` | boolean |  | True matches the literal module name; false uses a Perl regular expression. |
    | `data.[].pendingDelete` | boolean |  |  |
    | `data.[].noShowDelete` | boolean |  |  |
    | `data.[].disabled` | boolean |  |  |
    | `data.[].standby` | boolean |  |  |
    | `data.[].exactMatchFixed` | boolean |  |  |


### Model: PolicyFim { #model-policyfim }

| Field | Type | Required | Description |
|---|---|---|---|
| `idPolicyFim` | integer, nullable |  |  |
| `idPolicy` | integer |  |  |
| `applyPolicy` | boolean |  |  |
| `enabled` | boolean |  |  |
| `dirMaxDepth` | integer |  |  |
| `dirMaxFiles` | integer |  |  |
| `fileMaxSize` | string |  |  |
| `skipExtension` | string |  |  |
| `cacheTime` | integer |  |  |
| `files` | array of string |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "applyPolicy": false,
      "enabled": false,
      "dirMaxDepth": 0,
      "dirMaxFiles": 0,
      "fileMaxSize": "200MB",
      "skipExtension": "md,txt,iso,cab",
      "cacheTime": 0,
      "files": [
        "string"
      ]
    }
    ```

### Model: PolicyGroup { #model-policygroup }

??? note "Fields (6 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicyGroup` | integer |  |  |
    | `idPolicy` | integer |  |  |
    | `idGroup` | integer |  |  |
    | `policyApplied` | boolean |  |  |
    | `pendingDelete` | boolean |  |  |
    | `lastApplyUtimestamp` | integer |  |  |


### Model: PolicyLogModule { #model-policylogmodule }

??? note "Fields (13 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicyLogModule` | integer |  |  |
    | `idPolicy` | integer |  |  |
    | `moduleLogExec` | string, nullable |  |  |
    | `pendingDelete` | boolean |  |  |
    | `collectorMode` | enum: `log_file`, `windows_event` |  |  |
    | `moduleName` | string |  |  |
    | `source` | string |  |  |
    | `sourceType` | string |  |  |
    | `pattern` | string |  |  |
    | `excludePatterns` | array of string |  |  |
    | `eventType` | enum: `any`, `informational`, `warning`, `error`, `critical` |  |  |
    | `eventCode` | string |  |  |
    | `enabled` | boolean |  |  |


### Model: PolicyLogModuleList { #model-policylogmodulelist }

??? note "Fields (29 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
    | `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
    | `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
    | `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
    | `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
    | `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyLogModule` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].moduleLogExec` | string, nullable |  |  |
    | `data.[].pendingDelete` | boolean |  |  |
    | `data.[].collectorMode` | enum: `log_file`, `windows_event` |  |  |
    | `data.[].moduleName` | string |  |  |
    | `data.[].source` | string |  |  |
    | `data.[].sourceType` | string |  |  |
    | `data.[].pattern` | string |  |  |
    | `data.[].excludePatterns` | array of string |  |  |
    | `data.[].eventType` | enum: `any`, `informational`, `warning`, `error`, `critical` |  |  |
    | `data.[].eventCode` | string |  |  |
    | `data.[].enabled` | boolean |  |  |


### Model: PolicyModuleList { #model-policymodulelist }

??? note "Fields (100 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
    | `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
    | `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
    | `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
    | `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
    | `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyModule` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].moduleType` | enum: `data`, `icmp`, `tcp`, `snmp`, `wmi`, `remotecmd`, `web`, `prediction`, `plugin`, `wux`, `api_retrieve`, `api_custom`, `sat_icmp`, `sat_snmp`, `sat_ssh`, `sat_tcp`, `sat_exec`, `sat_wmi` |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].description` | string |  |  |
    | `data.[].idModule` | integer |  |  |
    | `data.[].idModuleType` | integer |  |  |
    | `data.[].configurationData` | string, nullable |  | Native configuration is normalized: each line is trimmed, empty lines are removed, line endings are normalized and non-empty text ends with a final newline. Satellite configuration is parsed and regenerated by the module manager. |
    | `data.[].unit` | string, nullable |  |  |
    | `data.[].max` | integer (int64), nullable |  |  |
    | `data.[].min` | integer (int64), nullable |  |  |
    | `data.[].moduleInterval` | integer, nullable |  |  |
    | `data.[].ipTarget` | string, nullable |  |  |
    | `data.[].tcpPort` | integer, nullable |  |  |
    | `data.[].tcpSend` | string, nullable |  |  |
    | `data.[].tcpRcv` | string, nullable |  |  |
    | `data.[].snmpOid` | string, nullable |  |  |
    | `data.[].idModuleGroup` | integer, nullable |  |  |
    | `data.[].flag` | integer |  |  |
    | `data.[].disabled` | boolean |  |  |
    | `data.[].idExport` | integer, nullable |  |  |
    | `data.[].pluginUser` | string, nullable |  |  |
    | `data.[].pluginParameter` | string, nullable |  |  |
    | `data.[].idPlugin` | integer, nullable |  |  |
    | `data.[].postProcess` | number, nullable |  |  |
    | `data.[].predictionModule` | integer, nullable |  |  |
    | `data.[].maxTimeout` | integer, nullable |  |  |
    | `data.[].maxRetries` | integer, nullable |  |  |
    | `data.[].customId` | string, nullable |  |  |
    | `data.[].historyData` | boolean, nullable |  |  |
    | `data.[].minWarning` | number, nullable |  |  |
    | `data.[].maxWarning` | number, nullable |  |  |
    | `data.[].strWarning` | string, nullable |  |  |
    | `data.[].minCritical` | number, nullable |  |  |
    | `data.[].maxCritical` | number, nullable |  |  |
    | `data.[].strCritical` | string, nullable |  |  |
    | `data.[].minFfEvent` | integer, nullable |  |  |
    | `data.[].customInteger1` | integer, nullable |  |  |
    | `data.[].customInteger2` | integer, nullable |  |  |
    | `data.[].pendingDelete` | boolean |  |  |
    | `data.[].criticalInstructions` | string, nullable |  |  |
    | `data.[].warningInstructions` | string, nullable |  |  |
    | `data.[].unknownInstructions` | string, nullable |  |  |
    | `data.[].criticalInverse` | boolean, nullable |  |  |
    | `data.[].warningInverse` | boolean, nullable |  |  |
    | `data.[].idCategory` | integer, nullable |  |  |
    | `data.[].moduleFfInterval` | integer, nullable |  |  |
    | `data.[].quiet` | boolean |  |  |
    | `data.[].cronInterval` | string, nullable |  |  |
    | `data.[].macros` | array, nullable |  |  |
    | `data.[].disabledTypesEvent` | object, nullable |  |  |
    | `data.[].moduleMacros` | object, nullable |  |  |
    | `data.[].minFfEventNormal` | integer, nullable |  |  |
    | `data.[].minFfEventWarning` | integer, nullable |  |  |
    | `data.[].minFfEventCritical` | integer, nullable |  |  |
    | `data.[].ffType` | boolean, nullable |  |  |
    | `data.[].eachFf` | boolean, nullable |  |  |
    | `data.[].ffTimeout` | integer, nullable |  |  |
    | `data.[].dynamicInterval` | integer, nullable |  |  |
    | `data.[].dynamicMax` | integer, nullable |  |  |
    | `data.[].dynamicMin` | integer, nullable |  |  |
    | `data.[].dynamicNext` | integer |  |  |
    | `data.[].dynamicTwoTailed` | boolean, nullable |  |  |
    | `data.[].predictionSampleWindow` | integer, nullable |  |  |
    | `data.[].predictionSamples` | integer, nullable |  |  |
    | `data.[].predictionThreshold` | integer, nullable |  |  |
    | `data.[].apiTimeout` | integer, nullable |  |  |
    | `data.[].apiUrl` | string, nullable |  |  |
    | `data.[].apiMethod` | string, nullable |  |  |
    | `data.[].apiIgnoreCert` | boolean |  |  |
    | `data.[].apiJsonq` | string, nullable |  |  |
    | `data.[].apiErrorCodes` | string, nullable |  |  |
    | `data.[].apiConditions` | array, nullable |  |  |
    | `data.[].cps` | boolean |  |  |
    | `data.[].percentageWarning` | boolean, nullable |  |  |
    | `data.[].percentageCritical` | boolean, nullable |  |  |
    | `data.[].warningTime` | integer, nullable |  |  |
    | `data.[].madeEnabled` | boolean, nullable |  |  |
    | `data.[].ignoreUnknown` | boolean |  |  |
    | `data.[].satelliteType` | string, nullable |  |  |
    | `data.[].parentPolicyModuleId` | integer |  |  |
    | `data.[].idDataTranslation` | integer, nullable |  |  |
    | `data.[].tags` | array of integer |  |  |
    | `data.[].predictionFormula` | array of object |  |  |


### Model: PolicyModuleResponse { #model-policymoduleresponse }

??? note "Fields (84 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicyModule` | integer |  |  |
    | `idPolicy` | integer |  |  |
    | `moduleType` | enum: `data`, `icmp`, `tcp`, `snmp`, `wmi`, `remotecmd`, `web`, `prediction`, `plugin`, `wux`, `api_retrieve`, `api_custom`, `sat_icmp`, `sat_snmp`, `sat_ssh`, `sat_tcp`, `sat_exec`, `sat_wmi` |  |  |
    | `name` | string |  |  |
    | `description` | string |  |  |
    | `idModule` | integer |  |  |
    | `idModuleType` | integer |  |  |
    | `configurationData` | string, nullable |  | Native configuration is normalized: each line is trimmed, empty lines are removed, line endings are normalized and non-empty text ends with a final newline. Satellite configuration is parsed and regenerated by the module manager. |
    | `unit` | string, nullable |  |  |
    | `max` | integer (int64), nullable |  |  |
    | `min` | integer (int64), nullable |  |  |
    | `moduleInterval` | integer, nullable |  |  |
    | `ipTarget` | string, nullable |  |  |
    | `tcpPort` | integer, nullable |  |  |
    | `tcpSend` | string, nullable |  |  |
    | `tcpRcv` | string, nullable |  |  |
    | `snmpOid` | string, nullable |  |  |
    | `idModuleGroup` | integer, nullable |  |  |
    | `flag` | integer |  |  |
    | `disabled` | boolean |  |  |
    | `idExport` | integer, nullable |  |  |
    | `pluginUser` | string, nullable |  |  |
    | `pluginParameter` | string, nullable |  |  |
    | `idPlugin` | integer, nullable |  |  |
    | `postProcess` | number, nullable |  |  |
    | `predictionModule` | integer, nullable |  |  |
    | `maxTimeout` | integer, nullable |  |  |
    | `maxRetries` | integer, nullable |  |  |
    | `customId` | string, nullable |  |  |
    | `historyData` | boolean, nullable |  |  |
    | `minWarning` | number, nullable |  |  |
    | `maxWarning` | number, nullable |  |  |
    | `strWarning` | string, nullable |  |  |
    | `minCritical` | number, nullable |  |  |
    | `maxCritical` | number, nullable |  |  |
    | `strCritical` | string, nullable |  |  |
    | `minFfEvent` | integer, nullable |  |  |
    | `customInteger1` | integer, nullable |  |  |
    | `customInteger2` | integer, nullable |  |  |
    | `pendingDelete` | boolean |  |  |
    | `criticalInstructions` | string, nullable |  |  |
    | `warningInstructions` | string, nullable |  |  |
    | `unknownInstructions` | string, nullable |  |  |
    | `criticalInverse` | boolean, nullable |  |  |
    | `warningInverse` | boolean, nullable |  |  |
    | `idCategory` | integer, nullable |  |  |
    | `moduleFfInterval` | integer, nullable |  |  |
    | `quiet` | boolean |  |  |
    | `cronInterval` | string, nullable |  |  |
    | `macros` | array, nullable |  |  |
    | `disabledTypesEvent` | object, nullable |  |  |
    | `moduleMacros` | object, nullable |  |  |
    | `minFfEventNormal` | integer, nullable |  |  |
    | `minFfEventWarning` | integer, nullable |  |  |
    | `minFfEventCritical` | integer, nullable |  |  |
    | `ffType` | boolean, nullable |  |  |
    | `eachFf` | boolean, nullable |  |  |
    | `ffTimeout` | integer, nullable |  |  |
    | `dynamicInterval` | integer, nullable |  |  |
    | `dynamicMax` | integer, nullable |  |  |
    | `dynamicMin` | integer, nullable |  |  |
    | `dynamicNext` | integer |  |  |
    | `dynamicTwoTailed` | boolean, nullable |  |  |
    | `predictionSampleWindow` | integer, nullable |  |  |
    | `predictionSamples` | integer, nullable |  |  |
    | `predictionThreshold` | integer, nullable |  |  |
    | `apiTimeout` | integer, nullable |  |  |
    | `apiUrl` | string, nullable |  |  |
    | `apiMethod` | string, nullable |  |  |
    | `apiIgnoreCert` | boolean |  |  |
    | `apiJsonq` | string, nullable |  |  |
    | `apiErrorCodes` | string, nullable |  |  |
    | `apiConditions` | array, nullable |  |  |
    | `cps` | boolean |  |  |
    | `percentageWarning` | boolean, nullable |  |  |
    | `percentageCritical` | boolean, nullable |  |  |
    | `warningTime` | integer, nullable |  |  |
    | `madeEnabled` | boolean, nullable |  |  |
    | `ignoreUnknown` | boolean |  |  |
    | `satelliteType` | string, nullable |  |  |
    | `parentPolicyModuleId` | integer |  |  |
    | `idDataTranslation` | integer, nullable |  |  |
    | `tags` | array of integer |  |  |
    | `predictionFormula` | array of object |  |  |


### Model: PolicyPlugin { #model-policyplugin }

??? note "Fields (5 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicyPlugin` | integer |  |  |
    | `idPolicy` | integer |  |  |
    | `pluginExec` | string, nullable |  |  |
    | `pendingDelete` | boolean |  |  |
    | `disabled` | boolean |  |  |


### Model: PolicyPluginBulkResult { #model-policypluginbulkresult }

??? note "Fields (13 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `successCount` | integer |  |  |
    | `errorCount` | integer |  |  |
    | `results` | array of object |  |  |
    | `results.[].idPolicyPlugin` | integer |  |  |
    | `results.[].success` | boolean |  |  |
    | `results.[].status` | integer |  |  |
    | `results.[].data` | object |  |  |
    | `results.[].data.idPolicyPlugin` | integer |  |  |
    | `results.[].data.idPolicy` | integer |  |  |
    | `results.[].data.pluginExec` | string, nullable |  |  |
    | `results.[].data.pendingDelete` | boolean |  |  |
    | `results.[].data.disabled` | boolean |  |  |
    | `results.[].error` | string |  |  |


### Model: PolicyPluginList { #model-policypluginlist }

??? note "Fields (21 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
    | `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
    | `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
    | `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
    | `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
    | `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object |  |  |
    | `data.[].idPolicyPlugin` | integer |  |  |
    | `data.[].idPolicy` | integer |  |  |
    | `data.[].pluginExec` | string, nullable |  |  |
    | `data.[].pendingDelete` | boolean |  |  |
    | `data.[].disabled` | boolean |  |  |


### Model: PolicyQueueFilter { #model-policyqueuefilter }

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idPolicyQueue` | integer |  |  |
| `idPolicy` | integer |  |  |
| `idAgent` | integer |  |  |
| `operation` | string |  |  |
| `progress` | integer |  |  |
| `endUtimestamp` | integer |  |  |
| `priority` | integer |  |  |
| `status` | enum: `all`, `complete`, `incomplete` |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `requestedFields` | array, nullable |  |  |
| `fieldConditions` | array, nullable |  |  |
| `multipleSearch` |  |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearch.field` | enum: `idPolicyQueue`, `idPolicy`, `idAgent`, `operation`, `progress`, `endUtimestamp`, `priority` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idPolicyQueue`, `idPolicy`, `idAgent`, `operation`, `progress`, `endUtimestamp`, `priority` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idPolicyQueue"
      ],
      "fieldConditions": [
        {
          "field": "idPolicyQueue",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idPolicyQueue": 0,
      "idAgent": 0,
      "operation": "string",
      "progress": 0,
      "endUtimestamp": 0,
      "priority": 0,
      "status": "all",
      "multipleSearch": {
        "field": "idPolicyQueue",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idPolicyQueue",
        "data": [
          "string"
        ]
      }
    }
    ```

### Model: PolicyResponse { #model-policyresponse }

??? note "Fields (8 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPolicy` | integer |  |  |
    | `name` | string |  |  |
    | `description` | string |  |  |
    | `idGroup` | integer |  |  |
    | `status` | integer |  |  |
    | `forceApply` | boolean |  |  |
    | `applyToSecondaryGroups` | boolean |  |  |
    | `createLinkedModules` | boolean |  |  |
