# Pandora AI and ITSM

Pandora AI audit, notifications and scheduled tasks, and the Pandora ITSM integration.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-get">GET</span> | [`/pandora_ai/audit/session/{userId}/{sessionId}`](#get-pandora-ai-audit-session-userid-sessionid) | Show one Pandora AI audited session |
| <span class="api-method api-get">GET</span> | [`/pandora_ai/audit/message/list`](#get-pandora-ai-audit-message-list) | Search the messages of the Pandora AI audit |
| <span class="api-method api-post">POST</span> | [`/pandora_ai/audit/message/list`](#post-pandora-ai-audit-message-list) | Search the messages of the Pandora AI audit |
| <span class="api-method api-get">GET</span> | [`/pandora_ai/audit/session/list`](#get-pandora-ai-audit-session-list) | List the Pandora AI sessions of a user |
| <span class="api-method api-post">POST</span> | [`/pandora_ai/audit/session/list`](#post-pandora-ai-audit-session-list) | List the Pandora AI sessions of a user |
| <span class="api-method api-get">GET</span> | [`/pandora_ai/audit/user/list`](#get-pandora-ai-audit-user-list) | List Pandora AI audit users |
| <span class="api-method api-post">POST</span> | [`/pandora_ai/audit/user/list`](#post-pandora-ai-audit-user-list) | List Pandora AI audit users |
| <span class="api-method api-post">POST</span> | [`/pandora_ai/notify`](#post-pandora-ai-notify) | Notify the owner of a Pandora AI scheduled task |
| <span class="api-method api-post">POST</span> | [`/pandora_ai/scheduled_task`](#post-pandora-ai-scheduled-task) | Create a Pandora AI scheduled task |
| <span class="api-method api-get">GET</span> | [`/pandora_ai/scheduled_task/{idScheduledTask}`](#get-pandora-ai-scheduled-task-idscheduledtask) | Get one Pandora AI scheduled task |
| <span class="api-method api-put">PUT</span> | [`/pandora_ai/scheduled_task/{idScheduledTask}`](#put-pandora-ai-scheduled-task-idscheduledtask) | Update a Pandora AI scheduled task |
| <span class="api-method api-delete">DELETE</span> | [`/pandora_ai/scheduled_task/{idScheduledTask}`](#delete-pandora-ai-scheduled-task-idscheduledtask) | Delete a Pandora AI scheduled task |
| <span class="api-method api-post">POST</span> | [`/pandora_ai/scheduled_task/{idScheduledTask}/enabled`](#post-pandora-ai-scheduled-task-idscheduledtask-enabled) | Enable or disable a Pandora AI scheduled task |
| <span class="api-method api-get">GET</span> | [`/pandora_ai/scheduled_task/list`](#get-pandora-ai-scheduled-task-list) | List Pandora AI scheduled tasks |
| <span class="api-method api-post">POST</span> | [`/pandora_ai/scheduled_task/list`](#post-pandora-ai-scheduled-task-list) | List Pandora AI scheduled tasks |
| <span class="api-method api-post">POST</span> | [`/pandora_ai/scheduled_task/{idScheduledTask}/run`](#post-pandora-ai-scheduled-task-idscheduledtask-run) | Queue a Pandora AI scheduled task to run on the next cron tick |
| <span class="api-method api-get">GET</span> | [`/pandoraITSM/inventory/{idPandoraITSMInventory}`](#get-pandoraitsm-inventory-idpandoraitsminventory) | Show pandoraITSMInventory |
| <span class="api-method api-get">GET</span> | [`/pandoraITSM/inventory/list`](#get-pandoraitsm-inventory-list) | List pandoraITSMInventories |
| <span class="api-method api-post">POST</span> | [`/pandoraITSM/inventory/list`](#post-pandoraitsm-inventory-list) | List pandoraITSMInventories |

## PandoraAiAudit

Read-only endpoints of the Pandora AI audit

### <span class="api-method api-get">GET</span> `/pandora_ai/audit/session/{userId}/{sessionId}` { #get-pandora-ai-audit-session-userid-sessionid }

Show one Pandora AI audited session

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `userId` | path | string | yes | Console user id |
| `sessionId` | path | string | yes | Pandora AI session id |

**Response 200**: Pandora AI audited session

??? note "Response fields (18 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `userId` | string, nullable |  |  |
    | `sessionId` | string, nullable |  |  |
    | `messages` | array of object |  |  |
    | `messages.[].id` | integer, nullable |  |  |
    | `messages.[].userId` | string, nullable |  |  |
    | `messages.[].sessionId` | string, nullable |  |  |
    | `messages.[].name` | string, nullable |  | Session display name |
    | `messages.[].role` | string, nullable |  | user or assistant |
    | `messages.[].content` | string, nullable |  |  |
    | `messages.[].provider` | string, nullable |  |  |
    | `messages.[].model` | string, nullable |  |  |
    | `messages.[].createdAt` | string, nullable |  |  |
    | `messages.[].tokens` | integer, nullable |  | Tokens used by this message |
    | `messages.[].cost` | number (float), nullable |  | Cost of this message in USD |
    | `messages.[].sessionTokens` | integer, nullable |  | Accumulated tokens of the whole session |
    | `messages.[].sessionCost` | number (float), nullable |  | Accumulated cost of the whole session in USD |
    | `events` | array of object |  |  |
    | `compactions` | array of object |  |  |


Error responses: `400`, `401`, `403`, `404`, `503`, `500`.

### <span class="api-method api-get">GET</span> `/pandora_ai/audit/message/list` { #get-pandora-ai-audit-message-list }

Search the messages of the Pandora AI audit

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Pandora AI audit messages

??? note "Response fields (23 fields)"

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
    | `data.[].id` | integer, nullable |  |  |
    | `data.[].userId` | string, nullable |  |  |
    | `data.[].sessionId` | string, nullable |  |  |
    | `data.[].name` | string, nullable |  | Session display name |
    | `data.[].role` | string, nullable |  | user or assistant |
    | `data.[].content` | string, nullable |  |  |
    | `data.[].provider` | string, nullable |  |  |
    | `data.[].model` | string, nullable |  |  |
    | `data.[].createdAt` | string, nullable |  |  |
    | `data.[].tokens` | integer, nullable |  | Tokens used by this message |
    | `data.[].cost` | number (float), nullable |  | Cost of this message in USD |
    | `data.[].sessionTokens` | integer, nullable |  | Accumulated tokens of the whole session |
    | `data.[].sessionCost` | number (float), nullable |  | Accumulated cost of the whole session in USD |


Error responses: `400`, `401`, `403`, `404`, `503`, `500`.

### <span class="api-method api-post">POST</span> `/pandora_ai/audit/message/list` { #post-pandora-ai-audit-message-list }

Search the messages of the Pandora AI audit

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`): [`PandoraAiAuditMessageFilter`](#model-pandoraaiauditmessagefilter)

**Response 200**: List Pandora AI audit messages

??? note "Response fields (23 fields)"

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
    | `data.[].id` | integer, nullable |  |  |
    | `data.[].userId` | string, nullable |  |  |
    | `data.[].sessionId` | string, nullable |  |  |
    | `data.[].name` | string, nullable |  | Session display name |
    | `data.[].role` | string, nullable |  | user or assistant |
    | `data.[].content` | string, nullable |  |  |
    | `data.[].provider` | string, nullable |  |  |
    | `data.[].model` | string, nullable |  |  |
    | `data.[].createdAt` | string, nullable |  |  |
    | `data.[].tokens` | integer, nullable |  | Tokens used by this message |
    | `data.[].cost` | number (float), nullable |  | Cost of this message in USD |
    | `data.[].sessionTokens` | integer, nullable |  | Accumulated tokens of the whole session |
    | `data.[].sessionCost` | number (float), nullable |  | Accumulated cost of the whole session in USD |


Error responses: `400`, `401`, `403`, `404`, `503`, `500`.

### <span class="api-method api-get">GET</span> `/pandora_ai/audit/session/list` { #get-pandora-ai-audit-session-list }

List the Pandora AI sessions of a user

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Pandora AI audit sessions

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
    | `data.[].sessionId` | string, nullable |  |  |
    | `data.[].provider` | string, nullable |  |  |
    | `data.[].model` | string, nullable |  |  |
    | `data.[].name` | string, nullable |  |  |
    | `data.[].startedAt` | string, nullable |  |  |
    | `data.[].lastMessageAt` | string, nullable |  |  |
    | `data.[].messages` | integer, nullable |  |  |
    | `data.[].tokensTotal` | integer, nullable |  |  |
    | `data.[].cost` | number (float), nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `503`, `500`.

### <span class="api-method api-post">POST</span> `/pandora_ai/audit/session/list` { #post-pandora-ai-audit-session-list }

List the Pandora AI sessions of a user

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`): [`PandoraAiAuditMessageFilter`](#model-pandoraaiauditmessagefilter)

**Response 200**: List Pandora AI audit sessions

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
    | `data.[].sessionId` | string, nullable |  |  |
    | `data.[].provider` | string, nullable |  |  |
    | `data.[].model` | string, nullable |  |  |
    | `data.[].name` | string, nullable |  |  |
    | `data.[].startedAt` | string, nullable |  |  |
    | `data.[].lastMessageAt` | string, nullable |  |  |
    | `data.[].messages` | integer, nullable |  |  |
    | `data.[].tokensTotal` | integer, nullable |  |  |
    | `data.[].cost` | number (float), nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `503`, `500`.

### <span class="api-method api-get">GET</span> `/pandora_ai/audit/user/list` { #get-pandora-ai-audit-user-list }

List Pandora AI audit users

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Pandora AI audit users

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
    | `data.[].userId` | string, nullable |  |  |
    | `data.[].lastMessageAt` | string, nullable |  |  |
    | `data.[].sessions` | integer, nullable |  |  |
    | `data.[].messages` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `503`, `500`.

### <span class="api-method api-post">POST</span> `/pandora_ai/audit/user/list` { #post-pandora-ai-audit-user-list }

List Pandora AI audit users

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`): [`PandoraAiAuditMessageFilter`](#model-pandoraaiauditmessagefilter)

**Response 200**: List Pandora AI audit users

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
    | `data.[].userId` | string, nullable |  |  |
    | `data.[].lastMessageAt` | string, nullable |  |  |
    | `data.[].sessions` | integer, nullable |  |  |
    | `data.[].messages` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `503`, `500`.

## PandoraAiNotifications

Pandora AI notification delivery

### <span class="api-method api-post">POST</span> `/pandora_ai/notify` { #post-pandora-ai-notify }

Notify the owner of a Pandora AI scheduled task

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idScheduledTask` | integer | yes |  |
| `event` | enum: `success`, `error` | yes |  |
| `subject` | string | yes |  |
| `message` | string | yes |  |
| `url` | string, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idScheduledTask": 0,
      "event": "success",
      "subject": "string",
      "message": "string",
      "url": "string"
    }
    ```

**Response 200**: Delivery result

??? note "Response fields (3 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `notification` | boolean |  |  |
    | `email` | boolean |  |  |
    | `reason` | string, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

## PandoraAiScheduledTasks

Pandora AI scheduled tasks

### <span class="api-method api-post">POST</span> `/pandora_ai/scheduled_task` { #post-pandora-ai-scheduled-task }

Create a Pandora AI scheduled task

**Request body** (`application/json`): [`PandoraAiScheduledTask`](#model-pandoraaischeduledtask)

**Response 200**: Pandora AI scheduled task object

Schema: [`PandoraAiScheduledTask`](#model-pandoraaischeduledtask)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/pandora_ai/scheduled_task/{idScheduledTask}` { #get-pandora-ai-scheduled-task-idscheduledtask }

Get one Pandora AI scheduled task

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledTask` | path | integer | yes | Pandora AI scheduled task id |

**Response 200**: Pandora AI scheduled task object

Schema: [`PandoraAiScheduledTask`](#model-pandoraaischeduledtask)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/pandora_ai/scheduled_task/{idScheduledTask}` { #put-pandora-ai-scheduled-task-idscheduledtask }

Update a Pandora AI scheduled task

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledTask` | path | integer | yes | Pandora AI scheduled task id |

**Request body** (`application/json`): [`PandoraAiScheduledTask`](#model-pandoraaischeduledtask)

**Response 200**: Pandora AI scheduled task object

Schema: [`PandoraAiScheduledTask`](#model-pandoraaischeduledtask)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/pandora_ai/scheduled_task/{idScheduledTask}` { #delete-pandora-ai-scheduled-task-idscheduledtask }

Delete a Pandora AI scheduled task

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledTask` | path | integer | yes | Pandora AI scheduled task id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/pandora_ai/scheduled_task/{idScheduledTask}/enabled` { #post-pandora-ai-scheduled-task-idscheduledtask-enabled }

Enable or disable a Pandora AI scheduled task

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledTask` | path | integer | yes | Pandora AI scheduled task id |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `enabled` | boolean | yes |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "enabled": false
    }
    ```

**Response 200**: Pandora AI scheduled task object

Schema: [`PandoraAiScheduledTask`](#model-pandoraaischeduledtask)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/pandora_ai/scheduled_task/list` { #get-pandora-ai-scheduled-task-list }

List Pandora AI scheduled tasks

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List of Pandora AI scheduled tasks

??? note "Response fields (26 fields)"

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
    | `data.[].idScheduledTask` | integer |  |  |
    | `data.[].idUser` | string |  |  |
    | `data.[].name` | string | yes |  |
    | `data.[].model` | string, nullable |  |  |
    | `data.[].prompt` | string | yes |  |
    | `data.[].periodicity` | enum: `hourly`, `daily`, `weekly`, `monthly`, `yearly` | yes |  |
    | `data.[].firstRun` | integer | yes |  |
    | `data.[].nextRun` | integer |  |  |
    | `data.[].lastRun` | integer, nullable |  |  |
    | `data.[].lastStatus` | string, nullable |  |  |
    | `data.[].lastError` | string, nullable |  |  |
    | `data.[].enabled` | boolean |  |  |
    | `data.[].notifySuccess` | enum: `never`, `on_request`, `always` |  |  |
    | `data.[].notifyError` | enum: `never`, `on_request`, `always` |  |  |
    | `data.[].createdAt` | integer |  |  |
    | `data.[].updatedAt` | integer |  |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/pandora_ai/scheduled_task/list` { #post-pandora-ai-scheduled-task-list }

List Pandora AI scheduled tasks

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
| `idScheduledTask` | integer |  |  |
| `idUser` | string |  |  |
| `name` | string | yes |  |
| `model` | string, nullable |  |  |
| `prompt` | string | yes |  |
| `periodicity` | enum: `hourly`, `daily`, `weekly`, `monthly`, `yearly` | yes |  |
| `firstRun` | integer | yes |  |
| `nextRun` | integer |  |  |
| `lastRun` | integer, nullable |  |  |
| `lastStatus` | string, nullable |  |  |
| `lastError` | string, nullable |  |  |
| `enabled` | boolean |  |  |
| `notifySuccess` | enum: `never`, `on_request`, `always` |  |  |
| `notifyError` | enum: `never`, `on_request`, `always` |  |  |
| `createdAt` | integer |  |  |
| `updatedAt` | integer |  |  |
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
| `multipleSearch.field` | enum: `idScheduledTask`, `idUser`, `name`, `model`, `periodicity`, `firstRun`, `nextRun`, `lastRun`, `lastStatus`, `enabled`, `notifySuccess`, `notifyError`, `createdAt`, `updatedAt` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idScheduledTask`, `idUser`, `name`, `model`, `periodicity`, `firstRun`, `nextRun`, `lastRun`, `lastStatus`, `enabled`, `notifySuccess`, `notifyError`, `createdAt`, `updatedAt` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idUser": "string",
      "name": "string",
      "model": "string",
      "prompt": "string",
      "periodicity": "hourly",
      "firstRun": 0,
      "enabled": false,
      "notifySuccess": "never",
      "notifyError": "never",
      "freeSearch": "string",
      "requestedFields": [
        "idScheduledTask"
      ],
      "fieldConditions": [
        {
          "field": "idScheduledTask",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idScheduledTask",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idScheduledTask",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List of Pandora AI scheduled tasks

??? note "Response fields (26 fields)"

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
    | `data.[].idScheduledTask` | integer |  |  |
    | `data.[].idUser` | string |  |  |
    | `data.[].name` | string | yes |  |
    | `data.[].model` | string, nullable |  |  |
    | `data.[].prompt` | string | yes |  |
    | `data.[].periodicity` | enum: `hourly`, `daily`, `weekly`, `monthly`, `yearly` | yes |  |
    | `data.[].firstRun` | integer | yes |  |
    | `data.[].nextRun` | integer |  |  |
    | `data.[].lastRun` | integer, nullable |  |  |
    | `data.[].lastStatus` | string, nullable |  |  |
    | `data.[].lastError` | string, nullable |  |  |
    | `data.[].enabled` | boolean |  |  |
    | `data.[].notifySuccess` | enum: `never`, `on_request`, `always` |  |  |
    | `data.[].notifyError` | enum: `never`, `on_request`, `always` |  |  |
    | `data.[].createdAt` | integer |  |  |
    | `data.[].updatedAt` | integer |  |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/pandora_ai/scheduled_task/{idScheduledTask}/run` { #post-pandora-ai-scheduled-task-idscheduledtask-run }

Queue a Pandora AI scheduled task to run on the next cron tick

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledTask` | path | integer | yes | Pandora AI scheduled task id |

**Response 200**: Pandora AI scheduled task object

Schema: [`PandoraAiScheduledTask`](#model-pandoraaischeduledtask)

Error responses: `400`, `401`, `403`, `404`, `500`.

## PandoraITSM

API Endpoints of integration pandoraITSM

### <span class="api-method api-get">GET</span> `/pandoraITSM/inventory/{idPandoraITSMInventory}` { #get-pandoraitsm-inventory-idpandoraitsminventory }

Show pandoraITSMInventory

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idPandoraITSMInventory` | path | integer | yes | PandoraITSMInventory id |

**Response 200**: PandoraITSMInventory object

??? note "Response fields (9 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idPandoraITSMInventory` | integer |  | Id Agent pandoraITSMInventory |
    | `agentAlias` | string, nullable |  | Agent Name pandoraITSMInventory |
    | `osVersion` | string, nullable |  | Agent os version pandoraITSMInventory |
    | `agentAddress` | string, nullable |  | Agent address pandoraITSMInventory |
    | `agentUrlAddress` | string, nullable |  | Agent url address pandoraITSMInventory |
    | `agentDisabled` | boolean, nullable |  | Agent disable pandoraITSMInventory |
    | `groupName` | string, nullable |  | Agent group name pandoraITSMInventory |
    | `groupId` | integer, nullable |  | Agent group id pandoraITSMInventory |
    | `osName` | string, nullable |  | Agent OS name pandoraITSMInventory |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/pandoraITSM/inventory/list` { #get-pandoraitsm-inventory-list }

List pandoraITSMInventories

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List PandoraITSM Inventories Object

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
    | `data.[].idPandoraITSMInventory` | integer |  | Id Agent pandoraITSMInventory |
    | `data.[].agentAlias` | string, nullable |  | Agent Name pandoraITSMInventory |
    | `data.[].osVersion` | string, nullable |  | Agent os version pandoraITSMInventory |
    | `data.[].agentAddress` | string, nullable |  | Agent address pandoraITSMInventory |
    | `data.[].agentUrlAddress` | string, nullable |  | Agent url address pandoraITSMInventory |
    | `data.[].agentDisabled` | boolean, nullable |  | Agent disable pandoraITSMInventory |
    | `data.[].groupName` | string, nullable |  | Agent group name pandoraITSMInventory |
    | `data.[].groupId` | integer, nullable |  | Agent group id pandoraITSMInventory |
    | `data.[].osName` | string, nullable |  | Agent OS name pandoraITSMInventory |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/pandoraITSM/inventory/list` { #post-pandoraitsm-inventory-list }

List pandoraITSMInventories

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
| `idPandoraITSMInventory` | integer |  | Id Agent pandoraITSMInventory |
| `agentAlias` | string, nullable |  | Agent Name pandoraITSMInventory |
| `osVersion` | string, nullable |  | Agent os version pandoraITSMInventory |
| `agentAddress` | string, nullable |  | Agent address pandoraITSMInventory |
| `agentUrlAddress` | string, nullable |  | Agent url address pandoraITSMInventory |
| `agentDisabled` | boolean, nullable |  | Agent disable pandoraITSMInventory |
| `groupName` | string, nullable |  | Agent group name pandoraITSMInventory |
| `groupId` | integer, nullable |  | Agent group id pandoraITSMInventory |
| `osName` | string, nullable |  | Agent OS name pandoraITSMInventory |
| `idPandoraITSMInventory` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in name field. |
| `multipleSearch` | object |  |  |
| `multipleSearch.field` | string, nullable |  | Field to search of query |
| `multipleSearch.data` | array, nullable |  | Values to search of query IN() |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "agentAlias": "string",
      "osVersion": "string",
      "agentAddress": "string",
      "agentUrlAddress": "string",
      "agentDisabled": false,
      "groupName": "string",
      "groupId": 0,
      "osName": "string",
      "idPandoraITSMInventory": null,
      "freeSearch": "string",
      "multipleSearch": {
        "field": "string",
        "data": [
          0
        ]
      },
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

**Response 200**: List PandoraITSM Inventories Object

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
    | `data.[].idPandoraITSMInventory` | integer |  | Id Agent pandoraITSMInventory |
    | `data.[].agentAlias` | string, nullable |  | Agent Name pandoraITSMInventory |
    | `data.[].osVersion` | string, nullable |  | Agent os version pandoraITSMInventory |
    | `data.[].agentAddress` | string, nullable |  | Agent address pandoraITSMInventory |
    | `data.[].agentUrlAddress` | string, nullable |  | Agent url address pandoraITSMInventory |
    | `data.[].agentDisabled` | boolean, nullable |  | Agent disable pandoraITSMInventory |
    | `data.[].groupName` | string, nullable |  | Agent group name pandoraITSMInventory |
    | `data.[].groupId` | integer, nullable |  | Agent group id pandoraITSMInventory |
    | `data.[].osName` | string, nullable |  | Agent OS name pandoraITSMInventory |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: PandoraAiAuditMessageFilter { #model-pandoraaiauditmessagefilter }

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `freeSearch` | string, nullable |  | Full-text search over the conversation messages |
| `userId` | string, nullable |  | Only messages of this console user |
| `sessionId` | string, nullable |  | Only messages of this Pandora AI session |
| `role` | string, nullable |  | Only messages with this role (user, assistant...) |
| `model` | string, nullable |  | Only messages whose model contains this text |
| `dateFrom` | string, nullable |  | Start date (YYYY-MM-DD or RFC3339) |
| `dateTo` | string, nullable |  | End date (YYYY-MM-DD or RFC3339) |
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
| `multipleSearch.field` | enum: `freeSearch`, `userId`, `sessionId`, `role`, `model`, `dateFrom`, `dateTo` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `freeSearch`, `userId`, `sessionId`, `role`, `model`, `dateFrom`, `dateTo` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "freeSearch"
      ],
      "fieldConditions": [
        {
          "field": "freeSearch",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "freeSearch": "string",
      "userId": "string",
      "sessionId": "string",
      "role": "string",
      "model": "string",
      "dateFrom": "string",
      "dateTo": "string",
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "freeSearch",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "freeSearch",
        "data": [
          "string"
        ]
      }
    }
    ```

### Model: PandoraAiScheduledTask { #model-pandoraaischeduledtask }

| Field | Type | Required | Description |
|---|---|---|---|
| `idScheduledTask` | integer |  |  |
| `idUser` | string |  |  |
| `name` | string | yes |  |
| `model` | string, nullable |  |  |
| `prompt` | string | yes |  |
| `periodicity` | enum: `hourly`, `daily`, `weekly`, `monthly`, `yearly` | yes |  |
| `firstRun` | integer | yes |  |
| `nextRun` | integer |  |  |
| `lastRun` | integer, nullable |  |  |
| `lastStatus` | string, nullable |  |  |
| `lastError` | string, nullable |  |  |
| `enabled` | boolean |  |  |
| `notifySuccess` | enum: `never`, `on_request`, `always` |  |  |
| `notifyError` | enum: `never`, `on_request`, `always` |  |  |
| `createdAt` | integer |  |  |
| `updatedAt` | integer |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idUser": "string",
      "name": "string",
      "model": "string",
      "prompt": "string",
      "periodicity": "hourly",
      "firstRun": 0,
      "enabled": false,
      "notifySuccess": "never",
      "notifyError": "never"
    }
    ```
