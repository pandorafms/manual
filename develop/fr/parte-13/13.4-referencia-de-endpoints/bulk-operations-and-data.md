# Bulk operations and data

Bulk drafts and queue, logs, servers and system information.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-delete">DELETE</span> | [`/bulkDraft/user`](#delete-bulkdraft-user) | Deletes all bulk drafts for the current user. |
| <span class="api-method api-get">GET</span> | [`/bulkDraft/{idBulkDraft}`](#get-bulkdraft-idbulkdraft) | Show bulk draft |
| <span class="api-method api-delete">DELETE</span> | [`/bulkDraft/{idBulkDraft}`](#delete-bulkdraft-idbulkdraft) | Deletes a bulk draft object. |
| <span class="api-method api-get">GET</span> | [`/bulkDraft/list`](#get-bulkdraft-list) | List bulk drafts |
| <span class="api-method api-post">POST</span> | [`/bulkDraft/list`](#post-bulkdraft-list) | List bulk drafts |
| <span class="api-method api-get">GET</span> | [`/bulkQueue/{idBulkQueue}`](#get-bulkqueue-idbulkqueue) | Show bulk queue item |
| <span class="api-method api-delete">DELETE</span> | [`/bulkQueue/{idBulkQueue}`](#delete-bulkqueue-idbulkqueue) | Deletes a bulk queue item. |
| <span class="api-method api-get">GET</span> | [`/bulkQueue/list`](#get-bulkqueue-list) | List bulk queue items |
| <span class="api-method api-post">POST</span> | [`/bulkQueue/list`](#post-bulkqueue-list) | List bulk queue items |
| <span class="api-method api-get">GET</span> | [`/log/agent/list`](#get-log-agent-list) | List agents with retained log entries |
| <span class="api-method api-post">POST</span> | [`/log/agent/list`](#post-log-agent-list) | List agents with retained log entries using object filters |
| <span class="api-method api-get">GET</span> | [`/log/agent/{idAgent}/entry/list`](#get-log-agent-idagent-entry-list) | Read retained log entries of an authorized agent |
| <span class="api-method api-post">POST</span> | [`/log/agent/{idAgent}/entry/list`](#post-log-agent-idagent-entry-list) | Read retained log entries using object filters |
| <span class="api-method api-get">GET</span> | [`/log/agent/{idAgent}/source/list`](#get-log-agent-idagent-source-list) | List retained log sources of an authorized agent |
| <span class="api-method api-post">POST</span> | [`/log/agent/{idAgent}/source/list`](#post-log-agent-idagent-source-list) | List retained log sources using object filters |
| <span class="api-method api-get">GET</span> | [`/server/{idServer}`](#get-server-idserver) | Gets a server |
| <span class="api-method api-get">GET</span> | [`/server/summary`](#get-server-summary) | Server counters grouped by status |
| <span class="api-method api-get">GET</span> | [`/server/list`](#get-server-list) | Lists servers |
| <span class="api-method api-post">POST</span> | [`/server/list`](#post-server-list) | Lists servers |
| <span class="api-method api-get">GET</span> | [`/system/selfMonitoringAgentName`](#get-system-selfmonitoringagentname) | Self-monitoring agent name |
| <span class="api-method api-get">GET</span> | [`/system/timezone`](#get-system-timezone) | Console system timezone |
| <span class="api-method api-post">POST</span> | [`/monitoring`](#post-monitoring) | Add monitoring data module |

## BulkDrafts

API Endpoints for bulk operation drafts

### <span class="api-method api-delete">DELETE</span> `/bulkDraft/user` { #delete-bulkdraft-user }

Deletes all bulk drafts for the current user.

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/bulkDraft/{idBulkDraft}` { #get-bulkdraft-idbulkdraft }

Show bulk draft

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBulkDraft` | path | integer | yes | BulkDraft id |

**Response 200**: BulkDraft object

??? note "Response fields (7 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idBulkDraft` | integer |  | Id BulkDraft |
    | `operationType` | string |  | Operation type |
    | `userId` | string |  | User id |
    | `target` | object |  | Target data |
    | `data` | object |  | Draft data |
    | `createdAt` | integer |  | Creation timestamp |
    | `updatedAt` | integer |  | Update timestamp |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/bulkDraft/{idBulkDraft}` { #delete-bulkdraft-idbulkdraft }

Deletes a bulk draft object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBulkDraft` | path | integer | yes | BulkDraft id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/bulkDraft/list` { #get-bulkdraft-list }

List bulk drafts

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List BulkDraft objects

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
    | `data.[].idBulkDraft` | integer |  | Id BulkDraft |
    | `data.[].operationType` | string |  | Operation type |
    | `data.[].userId` | string |  | User id |
    | `data.[].target` | object |  | Target data |
    | `data.[].data` | object |  | Draft data |
    | `data.[].createdAt` | integer |  | Creation timestamp |
    | `data.[].updatedAt` | integer |  | Update timestamp |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/bulkDraft/list` { #post-bulkdraft-list }

List bulk drafts

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idBulkDraft` | integer |  | Id BulkDraft |
| `operationType` | string |  | Operation type |
| `userId` | string |  | User id |
| `target` | object |  | Target data |
| `data` | object |  | Draft data |
| `createdAt` | integer |  | Creation timestamp |
| `updatedAt` | integer |  | Update timestamp |
| `idBulkDraft` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in operation_type or user_id fields. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "operationType": "string",
      "userId": "string",
      "target": {},
      "data": {},
      "createdAt": 0,
      "updatedAt": 0,
      "idBulkDraft": null,
      "freeSearch": "string",
      "requestedFields": [
        "string"
      ],
      "fieldConditions": [
        {
          "field": "name",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0
    }
    ```

**Response 200**: List BulkDraft objects

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
    | `data.[].idBulkDraft` | integer |  | Id BulkDraft |
    | `data.[].operationType` | string |  | Operation type |
    | `data.[].userId` | string |  | User id |
    | `data.[].target` | object |  | Target data |
    | `data.[].data` | object |  | Draft data |
    | `data.[].createdAt` | integer |  | Creation timestamp |
    | `data.[].updatedAt` | integer |  | Update timestamp |


Error responses: `400`, `401`, `403`, `404`, `500`.

## BulkQueue

API Endpoints for the bulk operation queue

### <span class="api-method api-get">GET</span> `/bulkQueue/{idBulkQueue}` { #get-bulkqueue-idbulkqueue }

Show bulk queue item

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBulkQueue` | path | integer | yes | BulkQueue id |

**Response 200**: BulkQueue object

??? note "Response fields (9 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idBulkQueue` | integer |  | Id BulkQueue |
    | `operationType` | string |  | Operation type |
    | `userId` | string |  | User id |
    | `target` | object |  | Target data |
    | `data` | object |  | Queue data |
    | `status` | enum: `pending`, `failed` |  | Queue item status |
    | `errorMessage` | string, nullable |  | Error message if status is failed |
    | `createdAt` | integer |  | Creation timestamp |
    | `updatedAt` | integer |  | Update timestamp |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/bulkQueue/{idBulkQueue}` { #delete-bulkqueue-idbulkqueue }

Deletes a bulk queue item.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBulkQueue` | path | integer | yes | BulkQueue id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/bulkQueue/list` { #get-bulkqueue-list }

List bulk queue items

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List BulkQueue objects

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
    | `data.[].idBulkQueue` | integer |  | Id BulkQueue |
    | `data.[].operationType` | string |  | Operation type |
    | `data.[].userId` | string |  | User id |
    | `data.[].target` | object |  | Target data |
    | `data.[].data` | object |  | Queue data |
    | `data.[].status` | enum: `pending`, `failed` |  | Queue item status |
    | `data.[].errorMessage` | string, nullable |  | Error message if status is failed |
    | `data.[].createdAt` | integer |  | Creation timestamp |
    | `data.[].updatedAt` | integer |  | Update timestamp |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/bulkQueue/list` { #post-bulkqueue-list }

List bulk queue items

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idBulkQueue` | integer |  | Id BulkQueue |
| `operationType` | string |  | Operation type |
| `userId` | string |  | User id |
| `target` | object |  | Target data |
| `data` | object |  | Queue data |
| `status` | enum: `pending`, `failed` |  | Queue item status |
| `errorMessage` | string, nullable |  | Error message if status is failed |
| `createdAt` | integer |  | Creation timestamp |
| `updatedAt` | integer |  | Update timestamp |
| `idBulkQueue` |  |  | Filter for listing BulkQueue entries. |
| `freeSearch` | string, nullable |  | Find word in operation_type or user_id fields. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "operationType": "string",
      "userId": "string",
      "target": {},
      "data": {},
      "status": "pending",
      "errorMessage": "string",
      "createdAt": 0,
      "updatedAt": 0,
      "idBulkQueue": null,
      "freeSearch": "string",
      "requestedFields": [
        "string"
      ],
      "fieldConditions": [
        {
          "field": "name",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0
    }
    ```

**Response 200**: List BulkQueue objects

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
    | `data.[].idBulkQueue` | integer |  | Id BulkQueue |
    | `data.[].operationType` | string |  | Operation type |
    | `data.[].userId` | string |  | User id |
    | `data.[].target` | object |  | Target data |
    | `data.[].data` | object |  | Queue data |
    | `data.[].status` | enum: `pending`, `failed` |  | Queue item status |
    | `data.[].errorMessage` | string, nullable |  | Error message if status is failed |
    | `data.[].createdAt` | integer |  | Creation timestamp |
    | `data.[].updatedAt` | integer |  | Update timestamp |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Logs

Read retained log activity through nodes and metaconsole federation

### <span class="api-method api-get">GET</span> `/log/agent/list` { #get-log-agent-list }

List agents with retained log entries

Defaults to the last 24 hours. Uses event dates, not collection status. On a metaconsole,
delegates to nodes. Continue in blocks using the same filters and returned cursor; no numbered pages,
exact totals or immutable snapshot. Retention limits history.
Query/body filters merge with body precedence.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `period` | query | string |  | Default last 24h; examples: 12h, 15d, all. Do not combine with from/to. |
| `from` | query | string (date-time) |  | Inclusive UTC-normalized event date; requires to, timezone and second precision |
| `to` | query | string (date-time) |  | Exclusive event date; requires from |
| `sizePage` | query | integer |  |  |
| `cursor` | query | string |  | Continuation preserving original dates, filters and sizePage |
| `idAgents` | query | array of integer |  | Optional narrowing filter; query syntax: idAgents[]=1&idAgents[]=2 |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Authorized agents, interval and cursor

Schema: [`LogAgentList`](#model-logagentlist)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`, `502`, `503`, `504`.

### <span class="api-method api-post">POST</span> `/log/agent/list` { #post-log-agent-list }

List agents with retained log entries using object filters

Same query, authorization and cursor contract as GET. Optional object body takes precedence
over query parameters. Period and explicit dates are mutually exclusive. No SQL advanced filters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `period` | query | string |  | Default last 24h; examples: 12h, 15d, all. Do not combine with from/to. |
| `from` | query | string (date-time) |  | Inclusive UTC-normalized event date; requires to, timezone and second precision |
| `to` | query | string (date-time) |  | Exclusive event date; requires from |
| `sizePage` | query | integer |  |  |
| `cursor` | query | string |  | Continuation preserving original dates, filters and sizePage |
| `idAgents` | query | array of integer |  | Optional narrowing filter; query syntax: idAgents[]=1&idAgents[]=2 |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `period` | string |  | Rolling hours/days or all retained history; incompatible with from/to |
| `from` | string (date-time) |  | Inclusive event-date bound |
| `to` | string (date-time) |  | Exclusive event-date bound |
| `sizePage` | integer |  |  |
| `cursor` | string |  |  |
| `serverId` | integer |  | Metaconsole target; omitted means all |
| `idAgents` | array of integer |  | Optional narrowing filter using agent IDs of the receiving console; never grants access |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "period": "1d",
      "from": "string",
      "to": "string",
      "sizePage": 100,
      "cursor": "string",
      "serverId": 0,
      "idAgents": [
        0
      ]
    }
    ```

**Response 200**: Authorized agents, interval and cursor

Schema: [`LogAgentList`](#model-logagentlist)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`, `502`, `503`, `504`.

### <span class="api-method api-get">GET</span> `/log/agent/{idAgent}/entry/list` { #get-log-agent-idagent-entry-list }

Read retained log entries of an authorized agent

Defaults to last 24h by event date. Optional source is an exact literal match.
Newest events first; backend index and document ID break equal-date ties. Cursor blocks, no
numbered pages, exact totals or immutable snapshot. Repeat original filters and sizePage.
The metaconsole delegates to the cached parent's node. Content is literal text, not safe HTML.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Local agent ID on a node; cached agent ID returned by log/agent/list on a metaconsole |
| `serverId` | query | integer |  | Optional metaconsole guard; must match the cached agent's node |
| `source` | query | string |  | Exact case-sensitive literal source name; not a regular expression or wildcard |
| `period` | query | string |  | Default last 24h; examples: 12h, 15d, all. Do not combine with from/to. |
| `from` | query | string (date-time) |  | Inclusive UTC-normalized event date; requires to, timezone and second precision |
| `to` | query | string (date-time) |  | Exclusive event date; requires from |
| `sizePage` | query | integer |  |  |
| `cursor` | query | string |  | Continuation preserving original dates, filters and sizePage |

**Response 200**: Literal entries, parent identity, interval and continuation

Schema: [`LogEntryList`](#model-logentrylist)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`, `503`, `504`.

### <span class="api-method api-post">POST</span> `/log/agent/{idAgent}/entry/list` { #post-log-agent-idagent-entry-list }

Read retained log entries using object filters

Same ACL, ordering and cursor contract as GET. Optional object body takes precedence
over query parameters. Parent identity comes only from the URL. No raw queries or SIEM fields.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Local agent ID on a node; cached agent ID returned by log/agent/list on a metaconsole |
| `serverId` | query | integer |  | Optional metaconsole guard; must match the cached agent's node |
| `source` | query | string |  | Exact case-sensitive literal source name; not a regular expression or wildcard |
| `period` | query | string |  | Default last 24h; examples: 12h, 15d, all. Do not combine with from/to. |
| `from` | query | string (date-time) |  | Inclusive UTC-normalized event date; requires to, timezone and second precision |
| `to` | query | string (date-time) |  | Exclusive event date; requires from |
| `sizePage` | query | integer |  |  |
| `cursor` | query | string |  | Continuation preserving original dates, filters and sizePage |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `source` | string |  | Optional exact source name; omission reads all sources of the path agent |
| `period` | string |  |  |
| `from` | string (date-time) |  |  |
| `to` | string (date-time) |  |  |
| `sizePage` | integer |  |  |
| `cursor` | string |  |  |
| `serverId` | integer |  | Optional metaconsole guard against the cached parent's node |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "source": "string",
      "period": "1d",
      "from": "string",
      "to": "string",
      "sizePage": 100,
      "cursor": "string",
      "serverId": 0
    }
    ```

**Response 200**: Literal entries, parent identity, interval and continuation

Schema: [`LogEntryList`](#model-logentrylist)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`, `503`, `504`.

### <span class="api-method api-get">GET</span> `/log/agent/{idAgent}/source/list` { #get-log-agent-idagent-source-list }

List retained log sources of an authorized agent

Defaults to last 24h by event date. Exact source names, ascending order, cursor blocks,
no numbered pages or exact totals. Repeat filters and sizePage on continuation. No immutable snapshot.
On a metaconsole the cached parent selects its node; no direct backend access. Hidden parents return
404. Missing AR returns 403. Query and optional object filters merge with body precedence.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Local agent ID on a node; cached agent ID returned by log/agent/list on a metaconsole |
| `serverId` | query | integer |  | Optional metaconsole guard; must match the cached agent's node |
| `period` | query | string |  | Default last 24h; examples: 12h, 15d, all. Do not combine with from/to. |
| `from` | query | string (date-time) |  | Inclusive UTC-normalized event date; requires to, timezone and second precision |
| `to` | query | string (date-time) |  | Exclusive event date; requires from |
| `sizePage` | query | integer |  |  |
| `cursor` | query | string |  | Continuation preserving original dates, filters and sizePage |

**Response 200**: Sources, parent identity, interval and continuation

Schema: [`LogSourceList`](#model-logsourcelist)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`, `503`, `504`.

### <span class="api-method api-post">POST</span> `/log/agent/{idAgent}/source/list` { #post-log-agent-idagent-source-list }

List retained log sources using object filters

Same authorization, ordering and cursor contract as GET. Body takes precedence over query.
Parent identity comes only from the URL. Do not combine period and explicit from/to.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Local agent ID on a node; cached agent ID returned by log/agent/list on a metaconsole |
| `serverId` | query | integer |  | Optional metaconsole guard; must match the cached agent's node |
| `period` | query | string |  | Default last 24h; examples: 12h, 15d, all. Do not combine with from/to. |
| `from` | query | string (date-time) |  | Inclusive UTC-normalized event date; requires to, timezone and second precision |
| `to` | query | string (date-time) |  | Exclusive event date; requires from |
| `sizePage` | query | integer |  |  |
| `cursor` | query | string |  | Continuation preserving original dates, filters and sizePage |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `period` | string |  |  |
| `from` | string (date-time) |  |  |
| `to` | string (date-time) |  |  |
| `sizePage` | integer |  |  |
| `cursor` | string |  |  |
| `serverId` | integer |  | Optional metaconsole guard; must match the cached agent's node |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "period": "1d",
      "from": "string",
      "to": "string",
      "sizePage": 100,
      "cursor": "string",
      "serverId": 0
    }
    ```

**Response 200**: Sources, parent identity, interval and continuation

Schema: [`LogSourceList`](#model-logsourcelist)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`, `503`, `504`.

## Servers

API Endpoints for servers

### <span class="api-method api-get">GET</span> `/server/{idServer}` { #get-server-idserver }

Gets a server

Reads the server locally on a node. On a metaconsole, serverId identifies the node that owns it.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idServer` | path | integer | yes | Server id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Server object

??? note "Response fields (34 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idServer` | integer, nullable |  | Server identifier |
    | `name` | string |  | Server name |
    | `idGroup` | integer, nullable |  | Group the server belongs to. Null means not assigned |
    | `ipAddress` | string, nullable |  | Server address |
    | `status` | integer, nullable |  | Server status: 0 down, 1 up |
    | `laststart` | string, nullable |  | Last server start date |
    | `keepalive` | string, nullable |  | Last server keepalive date |
    | `master` | boolean, nullable |  | Whether the server is the master of its type |
    | `description` | string, nullable |  | Server description |
    | `version` | string, nullable |  | Server version |
    | `serverType` | integer, nullable |  | Server type identifier (SERVER_TYPE_* constant) |
    | `queuedModules` | integer, nullable |  | Modules currently queued by the server |
    | `threads` | integer, nullable |  | Server worker threads |
    | `lagTime` | integer, nullable |  | Server lag time in seconds |
    | `lagModules` | integer, nullable |  | Number of delayed modules |
    | `totalModulesRunning` | integer, nullable |  | Total modules running on the server |
    | `myModules` | integer, nullable |  | Modules assigned to the server |
    | `serverKeepalive` | integer, nullable |  | Keepalive threshold in seconds |
    | `statUtimestamp` | integer, nullable |  | Last statistics timestamp |
    | `execProxy` | boolean, nullable |  | Whether the server executes the proxy |
    | `port` | integer, nullable |  | Server port |
    | `serverKeepaliveUtimestamp` | integer, nullable |  | Last keepalive timestamp |
    | `disabled` | boolean, nullable |  | Whether the server is disabled |
    | `serverId` | integer, nullable |  | Node identifier for metaconsole operations |
    | `enableReverseSsh` | boolean, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `reverseSshHost` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `reverseSshUser` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `reverseSshPort` | integer, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `reverseSshReady` | boolean, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `reverseSshAuthKey` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `reverseSshHostKey` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `reverseSshHostUser` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `reverseSshForceReload` | boolean, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `reverseSshRemotePort` | integer, nullable |  | Reserved for future updates. Never returned by read endpoints |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/server/summary` { #get-server-summary }

Server counters grouped by status

**Response 200**: Server summary

??? note "Response fields (2 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `total` | integer |  |  |
    | `status` | object |  |  |


Error responses: `401`, `403`, `500`.

### <span class="api-method api-get">GET</span> `/server/list` { #get-server-list }

Lists servers

On a metaconsole the list aggregates the local console and every node unless the filter serverId selects specific nodes. Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Server object

??? note "Response fields (44 fields)"

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
    | `data.[].idServer` | integer, nullable |  | Server identifier |
    | `data.[].name` | string |  | Server name |
    | `data.[].idGroup` | integer, nullable |  | Group the server belongs to. Null means not assigned |
    | `data.[].ipAddress` | string, nullable |  | Server address |
    | `data.[].status` | integer, nullable |  | Server status: 0 down, 1 up |
    | `data.[].laststart` | string, nullable |  | Last server start date |
    | `data.[].keepalive` | string, nullable |  | Last server keepalive date |
    | `data.[].master` | boolean, nullable |  | Whether the server is the master of its type |
    | `data.[].description` | string, nullable |  | Server description |
    | `data.[].version` | string, nullable |  | Server version |
    | `data.[].serverType` | integer, nullable |  | Server type identifier (SERVER_TYPE_* constant) |
    | `data.[].queuedModules` | integer, nullable |  | Modules currently queued by the server |
    | `data.[].threads` | integer, nullable |  | Server worker threads |
    | `data.[].lagTime` | integer, nullable |  | Server lag time in seconds |
    | `data.[].lagModules` | integer, nullable |  | Number of delayed modules |
    | `data.[].totalModulesRunning` | integer, nullable |  | Total modules running on the server |
    | `data.[].myModules` | integer, nullable |  | Modules assigned to the server |
    | `data.[].serverKeepalive` | integer, nullable |  | Keepalive threshold in seconds |
    | `data.[].statUtimestamp` | integer, nullable |  | Last statistics timestamp |
    | `data.[].execProxy` | boolean, nullable |  | Whether the server executes the proxy |
    | `data.[].port` | integer, nullable |  | Server port |
    | `data.[].serverKeepaliveUtimestamp` | integer, nullable |  | Last keepalive timestamp |
    | `data.[].disabled` | boolean, nullable |  | Whether the server is disabled |
    | `data.[].serverId` | integer, nullable |  | Node identifier for metaconsole operations |
    | `data.[].enableReverseSsh` | boolean, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshHost` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshUser` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshPort` | integer, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshReady` | boolean, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshAuthKey` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshHostKey` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshHostUser` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshForceReload` | boolean, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshRemotePort` | integer, nullable |  | Reserved for future updates. Never returned by read endpoints |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/server/list` { #post-server-list }

Lists servers

On a metaconsole the list aggregates the local console and every node unless the filter serverId selects specific nodes.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idServer` | integer, nullable |  | Server identifier |
| `name` | string |  | Server name |
| `idGroup` | integer, nullable |  | Group the server belongs to. Null means not assigned |
| `ipAddress` | string, nullable |  | Server address |
| `status` | integer, nullable |  | Server status: 0 down, 1 up |
| `laststart` | string, nullable |  | Last server start date |
| `keepalive` | string, nullable |  | Last server keepalive date |
| `master` | boolean, nullable |  | Whether the server is the master of its type |
| `description` | string, nullable |  | Server description |
| `version` | string, nullable |  | Server version |
| `serverType` | integer, nullable |  | Server type identifier (SERVER_TYPE_* constant) |
| `queuedModules` | integer, nullable |  | Modules currently queued by the server |
| `threads` | integer, nullable |  | Server worker threads |
| `lagTime` | integer, nullable |  | Server lag time in seconds |
| `lagModules` | integer, nullable |  | Number of delayed modules |
| `totalModulesRunning` | integer, nullable |  | Total modules running on the server |
| `myModules` | integer, nullable |  | Modules assigned to the server |
| `serverKeepalive` | integer, nullable |  | Keepalive threshold in seconds |
| `statUtimestamp` | integer, nullable |  | Last statistics timestamp |
| `execProxy` | boolean, nullable |  | Whether the server executes the proxy |
| `port` | integer, nullable |  | Server port |
| `serverKeepaliveUtimestamp` | integer, nullable |  | Last keepalive timestamp |
| `disabled` | boolean, nullable |  | Whether the server is disabled |
| `serverId` | integer, nullable |  | Node identifier for metaconsole operations |
| `enableReverseSsh` | boolean, nullable |  | Reserved for future updates. Never returned by read endpoints |
| `reverseSshHost` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
| `reverseSshUser` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
| `reverseSshPort` | integer, nullable |  | Reserved for future updates. Never returned by read endpoints |
| `reverseSshReady` | boolean, nullable |  | Reserved for future updates. Never returned by read endpoints |
| `reverseSshAuthKey` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
| `reverseSshHostKey` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
| `reverseSshHostUser` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
| `reverseSshForceReload` | boolean, nullable |  | Reserved for future updates. Never returned by read endpoints |
| `reverseSshRemotePort` | integer, nullable |  | Reserved for future updates. Never returned by read endpoints |
| `idServer` |  |  |  |
| `freeSearch` | string, nullable |  | Find text in server name and version fields |
| `serverId` | array, nullable |  | Node identifiers to aggregate on a metaconsole. Empty means every node plus the local console. Zero selects the local console |
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
| `multipleSearch.field` | enum: `idServer`, `name`, `idGroup`, `ipAddress`, `status`, `laststart`, `keepalive`, `master`, `description`, `version`, `serverType`, `queuedModules`, `threads`, `lagTime`, `lagModules`, `totalModulesRunning`, `myModules`, `serverKeepalive`, `statUtimestamp`, `execProxy`, `port`, `serverKeepaliveUtimestamp`, `disabled` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idServer`, `name`, `idGroup`, `ipAddress`, `status`, `laststart`, `keepalive`, `master`, `description`, `version`, `serverType`, `queuedModules`, `threads`, `lagTime`, `lagModules`, `totalModulesRunning`, `myModules`, `serverKeepalive`, `statUtimestamp`, `execProxy`, `port`, `serverKeepaliveUtimestamp`, `disabled` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idGroup": 0,
      "ipAddress": "string",
      "description": "string",
      "execProxy": false,
      "port": 0,
      "enableReverseSsh": false,
      "reverseSshHost": "string",
      "reverseSshUser": "string",
      "reverseSshPort": 0,
      "reverseSshReady": false,
      "reverseSshAuthKey": "string",
      "reverseSshHostKey": "string",
      "reverseSshHostUser": "string",
      "reverseSshForceReload": false,
      "reverseSshRemotePort": 0,
      "idServer": null,
      "freeSearch": "string",
      "serverId": [
        0
      ],
      "requestedFields": [
        "idServer"
      ],
      "fieldConditions": [
        {
          "field": "idServer",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idServer",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idServer",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List Server object

??? note "Response fields (44 fields)"

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
    | `data.[].idServer` | integer, nullable |  | Server identifier |
    | `data.[].name` | string |  | Server name |
    | `data.[].idGroup` | integer, nullable |  | Group the server belongs to. Null means not assigned |
    | `data.[].ipAddress` | string, nullable |  | Server address |
    | `data.[].status` | integer, nullable |  | Server status: 0 down, 1 up |
    | `data.[].laststart` | string, nullable |  | Last server start date |
    | `data.[].keepalive` | string, nullable |  | Last server keepalive date |
    | `data.[].master` | boolean, nullable |  | Whether the server is the master of its type |
    | `data.[].description` | string, nullable |  | Server description |
    | `data.[].version` | string, nullable |  | Server version |
    | `data.[].serverType` | integer, nullable |  | Server type identifier (SERVER_TYPE_* constant) |
    | `data.[].queuedModules` | integer, nullable |  | Modules currently queued by the server |
    | `data.[].threads` | integer, nullable |  | Server worker threads |
    | `data.[].lagTime` | integer, nullable |  | Server lag time in seconds |
    | `data.[].lagModules` | integer, nullable |  | Number of delayed modules |
    | `data.[].totalModulesRunning` | integer, nullable |  | Total modules running on the server |
    | `data.[].myModules` | integer, nullable |  | Modules assigned to the server |
    | `data.[].serverKeepalive` | integer, nullable |  | Keepalive threshold in seconds |
    | `data.[].statUtimestamp` | integer, nullable |  | Last statistics timestamp |
    | `data.[].execProxy` | boolean, nullable |  | Whether the server executes the proxy |
    | `data.[].port` | integer, nullable |  | Server port |
    | `data.[].serverKeepaliveUtimestamp` | integer, nullable |  | Last keepalive timestamp |
    | `data.[].disabled` | boolean, nullable |  | Whether the server is disabled |
    | `data.[].serverId` | integer, nullable |  | Node identifier for metaconsole operations |
    | `data.[].enableReverseSsh` | boolean, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshHost` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshUser` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshPort` | integer, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshReady` | boolean, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshAuthKey` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshHostKey` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshHostUser` | string, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshForceReload` | boolean, nullable |  | Reserved for future updates. Never returned by read endpoints |
    | `data.[].reverseSshRemotePort` | integer, nullable |  | Reserved for future updates. Never returned by read endpoints |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

## System

### <span class="api-method api-get">GET</span> `/system/selfMonitoringAgentName` { #get-system-selfmonitoringagentname }

Self-monitoring agent name

Agent used by the console system boxes for CPU, memory, database and IO metrics.

**Response 200**: System settings

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `selfMonitoringAgentName` | string |  |  |


Error responses: `401`, `500`.

### <span class="api-method api-get">GET</span> `/system/timezone` { #get-system-timezone }

Console system timezone

Timezone used as fallback when the user has no configured timezone.

**Response 200**: System timezone

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `timezone` | string |  |  |


Error responses: `401`, `500`.

## Monitoring

API Endpoints for monitoring

### <span class="api-method api-post">POST</span> `/monitoring` { #post-monitoring }

Add monitoring data module

Asynchronous local queue ingestion. The entire batch is validated and authorized before writes. Existing agents require AW on real groups; new agents without a group require explicit AW on All. Samples within api_interval_module update an existing queue row. Supply non-null data or a nonempty datalist. Omitted timestamps use request time; positive Unix timestamps and date strings are supported. Query parameters are ignored. Database failures do not guarantee transactional rollback.

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `[].agent_data` | object | yes |  |
| `[].agent_data.agent_name` | string | yes | Agent name |
| `[].agent_data.address` | string | yes | Agent address |
| `[].agent_data.interval` | integer | yes | Agent interval in seconds |
| `[].agent_data.id_group` | integer, nullable |  | Creation group; omission/null/zero requires AW on All. Existing agents use real groups. |
| `[].module_data` | array of object | yes |  |
| `[].module_data.[].name` | string | yes | Module name |
| `[].module_data.[].type` | string | yes | Module type |
| `[].module_data.[].data` |  |  |  |
| `[].module_data.[].timestamp` |  |  |  |
| `[].module_data.[].datalist` | array, nullable |  |  |
| `[].events` |  |  | Event list: base64 strings or objects (encoded). |
| `[].events.event` | array of string | yes |  |
| `[].inventory_data` |  |  | Inventory objects, or an inventory wrapper |
| `[].inventory_data.inventory` | array of object | yes |  |
| `[].log_data` |  |  | Log objects, or a log_module wrapper |
| `[].log_data.log_module` | array of object | yes |  |
| `[].trap_data` |  |  | SNMP trap: base64 string or object (encoded). |
| `[].trap_data.data` |  | yes |  |
| `[].discovery_data` |  |  | Discovery: base64 string or object (encoded). |
| `[].discovery_data.discovery` |  | yes |  |
| `[].cmd_data` |  |  | Command report objects, or a cmd_report wrapper |
| `[].cmd_data.cmd_report` | array of object | yes |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    [
      {
        "agent_data": {
          "agent_name": "string",
          "address": "string",
          "interval": 0,
          "id_group": 0
        },
        "module_data": [
          {
            "name": "string",
            "type": "string",
            "data": "string",
            "timestamp": "string",
            "datalist": []
          }
        ],
        "events": [
          "string"
        ],
        "inventory_data": [
          {}
        ],
        "log_data": [
          {}
        ],
        "trap_data": "string",
        "discovery_data": "string",
        "cmd_data": [
          {}
        ]
      }
    ]
    ```

**Response 200**: Data added successfully

??? note "Response fields (7 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `[].id` | integer |  | Monitoring data ID |
    | `[].uniqueMd5` | string |  | Internal queue grouping hash |
    | `[].nameAgent` | string |  | Agent name |
    | `[].nameModule` | string |  | Module name |
    | `[].utimestamp` | integer |  | Timestamp |
    | `[].monitoringData` | object |  | Monitoring data (JSON) |
    | `[].agentData` | object |  | Agent data (JSON) |


Error responses: `400`, `401`, `403`, `500`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: LogAgentList { #model-logagentlist }

??? note "Fields (14 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `data` | array of object |  |  |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].alias` | string |  |  |
    | `data.[].address` | string, nullable |  |  |
    | `data.[].entries` | integer |  | Number of retained log entries inside the selected interval |
    | `data.[].lastEventUtimestamp` | integer |  | Latest event timestamp in seconds inside the interval, not reception time |
    | `data.[].idAgentNode` | integer, nullable |  |  |
    | `data.[].serverId` | integer, nullable |  |  |
    | `from` | string (date-time), nullable |  |  |
    | `to` | string (date-time) |  |  |
    | `paginationData` | object |  |  |
    | `paginationData.sizePage` | integer |  |  |
    | `paginationData.hasMore` | boolean |  |  |
    | `paginationData.nextCursor` | string, nullable |  |  |


### Model: LogEntryList { #model-logentrylist }

??? note "Fields (13 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAgent` | integer |  |  |
    | `idAgentNode` | integer, nullable |  |  |
    | `serverId` | integer, nullable |  |  |
    | `from` | string (date-time), nullable |  |  |
    | `to` | string (date-time) |  |  |
    | `data` | array of object |  |  |
    | `data.[].source` | string |  |  |
    | `data.[].content` | string |  | Literal log content; consumers must escape it before rendering HTML |
    | `data.[].eventUtimestamp` | integer |  | Event timestamp in seconds; internal ordering retains millisecond precision |
    | `paginationData` | object |  |  |
    | `paginationData.sizePage` | integer |  |  |
    | `paginationData.hasMore` | boolean |  |  |
    | `paginationData.nextCursor` | string, nullable |  |  |


### Model: LogSourceList { #model-logsourcelist }

??? note "Fields (13 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAgent` | integer |  |  |
    | `idAgentNode` | integer, nullable |  |  |
    | `serverId` | integer, nullable |  |  |
    | `from` | string (date-time), nullable |  |  |
    | `to` | string (date-time) |  |  |
    | `data` | array of object |  |  |
    | `data.[].source` | string |  | Exact retained source name |
    | `data.[].entries` | integer |  |  |
    | `data.[].lastEventUtimestamp` | integer |  | Latest event timestamp in seconds within the selected interval |
    | `paginationData` | object |  |  |
    | `paginationData.sizePage` | integer |  |  |
    | `paginationData.hasMore` | boolean |  |  |
    | `paginationData.nextCursor` | string, nullable |  |  |
