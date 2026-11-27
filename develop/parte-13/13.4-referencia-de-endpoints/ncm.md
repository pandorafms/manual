# Network Configuration Manager

Network configuration management (NCM).

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-post">POST</span> | [`/ncm/agent/{idAgent}/script`](#post-ncm-agent-idagent-script) | Creates a per agent script override |
| <span class="api-method api-get">GET</span> | [`/ncm/agent/{idAgent}/script/{idAgentScript}`](#get-ncm-agent-idagent-script-idagentscript) | Show a per agent script override |
| <span class="api-method api-put">PUT</span> | [`/ncm/agent/{idAgent}/script/{idAgentScript}`](#put-ncm-agent-idagent-script-idagentscript) | Updates a per agent script override |
| <span class="api-method api-delete">DELETE</span> | [`/ncm/agent/{idAgent}/script/{idAgentScript}`](#delete-ncm-agent-idagent-script-idagentscript) | Deletes a per agent script override. |
| <span class="api-method api-get">GET</span> | [`/ncm/agent/{idAgent}/script/list`](#get-ncm-agent-idagent-script-list) | List per agent script overrides |
| <span class="api-method api-post">POST</span> | [`/ncm/agent/{idAgent}/script/list`](#post-ncm-agent-idagent-script-list) | List per agent script overrides |
| <span class="api-method api-get">GET</span> | [`/ncm/agent/{idAgent}/backup/{idBackup}`](#get-ncm-agent-idagent-backup-idbackup) | Show an NCM agent configuration backup |
| <span class="api-method api-delete">DELETE</span> | [`/ncm/agent/{idAgent}/backup/{idBackup}`](#delete-ncm-agent-idagent-backup-idbackup) | Deletes an NCM agent configuration backup |
| <span class="api-method api-get">GET</span> | [`/ncm/agent/{idAgent}/backup/{idBackup}/download`](#get-ncm-agent-idagent-backup-idbackup-download) | Download the raw data of an NCM agent configuration backup |
| <span class="api-method api-get">GET</span> | [`/ncm/agent/{idAgent}/backup/list`](#get-ncm-agent-idagent-backup-list) | List NCM agent configuration backups |
| <span class="api-method api-post">POST</span> | [`/ncm/agent/{idAgent}/backup/list`](#post-ncm-agent-idagent-backup-list) | List NCM agent configuration backups with a body filter |
| <span class="api-method api-post">POST</span> | [`/ncm/agent/{idAgent}/backup/mark`](#post-ncm-agent-idagent-backup-mark) | Mark the most recent configuration backup as current |
| <span class="api-method api-post">POST</span> | [`/ncm/agent/{idAgent}/backup/{idBackup}/restore`](#post-ncm-agent-idagent-backup-idbackup-restore) | Restore an NCM agent configuration backup |
| <span class="api-method api-post">POST</span> | [`/ncm/agent/bulk`](#post-ncm-agent-bulk) | Applies the same NCM configuration to several agents |
| <span class="api-method api-post">POST</span> | [`/ncm/agent`](#post-ncm-agent) | Enables NCM management for an agent |
| <span class="api-method api-get">GET</span> | [`/ncm/agent/{idAgent}`](#get-ncm-agent-idagent) | Show NCM agent |
| <span class="api-method api-put">PUT</span> | [`/ncm/agent/{idAgent}`](#put-ncm-agent-idagent) | Updates the NCM configuration of an agent |
| <span class="api-method api-delete">DELETE</span> | [`/ncm/agent/{idAgent}`](#delete-ncm-agent-idagent) | Disables NCM management for an agent. |
| <span class="api-method api-get">GET</span> | [`/ncm/agent/list`](#get-ncm-agent-list) | List NCM agents |
| <span class="api-method api-post">POST</span> | [`/ncm/agent/list`](#post-ncm-agent-list) | List NCM agents |
| <span class="api-method api-post">POST</span> | [`/ncm/agent/{idAgent}/queue`](#post-ncm-agent-idagent-queue) | Queues a task for an NCM agent |
| <span class="api-method api-delete">DELETE</span> | [`/ncm/agent/{idAgent}/queue`](#delete-ncm-agent-idagent-queue) | Clears all queued tasks of an NCM agent |
| <span class="api-method api-delete">DELETE</span> | [`/ncm/agent/{idAgent}/queue/{idQueue}`](#delete-ncm-agent-idagent-queue-idqueue) | Deletes a queued NCM agent task |
| <span class="api-method api-get">GET</span> | [`/ncm/agent/{idAgent}/queue/list`](#get-ncm-agent-idagent-queue-list) | List queued NCM agent tasks |
| <span class="api-method api-post">POST</span> | [`/ncm/agent/{idAgent}/queue/list`](#post-ncm-agent-idagent-queue-list) | List queued NCM agent tasks with a body filter |
| <span class="api-method api-post">POST</span> | [`/ncm/firmware`](#post-ncm-firmware) | Creates a new NCM firmware |
| <span class="api-method api-get">GET</span> | [`/ncm/firmware/{idFirmware}`](#get-ncm-firmware-idfirmware) | Show NCM firmware |
| <span class="api-method api-put">PUT</span> | [`/ncm/firmware/{idFirmware}`](#put-ncm-firmware-idfirmware) | Updates a NCM firmware |
| <span class="api-method api-delete">DELETE</span> | [`/ncm/firmware/{idFirmware}`](#delete-ncm-firmware-idfirmware) | Deletes a NCM firmware. |
| <span class="api-method api-get">GET</span> | [`/ncm/firmware/list`](#get-ncm-firmware-list) | List NCM firmwares |
| <span class="api-method api-post">POST</span> | [`/ncm/firmware/list`](#post-ncm-firmware-list) | List NCM firmwares |
| <span class="api-method api-post">POST</span> | [`/ncm/script`](#post-ncm-script) | Creates a new NCM script |
| <span class="api-method api-get">GET</span> | [`/ncm/script/{idScript}`](#get-ncm-script-idscript) | Show NCM script |
| <span class="api-method api-put">PUT</span> | [`/ncm/script/{idScript}`](#put-ncm-script-idscript) | Updates a NCM script |
| <span class="api-method api-delete">DELETE</span> | [`/ncm/script/{idScript}`](#delete-ncm-script-idscript) | Deletes a NCM script. |
| <span class="api-method api-get">GET</span> | [`/ncm/script/list`](#get-ncm-script-list) | List NCM scripts |
| <span class="api-method api-post">POST</span> | [`/ncm/script/list`](#post-ncm-script-list) | List NCM scripts |
| <span class="api-method api-post">POST</span> | [`/ncm/template`](#post-ncm-template) | Creates a new NCM template |
| <span class="api-method api-get">GET</span> | [`/ncm/template/{idTemplate}`](#get-ncm-template-idtemplate) | Show NCM template |
| <span class="api-method api-put">PUT</span> | [`/ncm/template/{idTemplate}`](#put-ncm-template-idtemplate) | Updates a NCM template |
| <span class="api-method api-delete">DELETE</span> | [`/ncm/template/{idTemplate}`](#delete-ncm-template-idtemplate) | Deletes a NCM template. |
| <span class="api-method api-get">GET</span> | [`/ncm/template/list`](#get-ncm-template-list) | List NCM templates |
| <span class="api-method api-post">POST</span> | [`/ncm/template/list`](#post-ncm-template-list) | List NCM templates |
| <span class="api-method api-post">POST</span> | [`/ncm/template/{idTemplate}/script`](#post-ncm-template-idtemplate-script) | Creates a new NCM template script |
| <span class="api-method api-get">GET</span> | [`/ncm/template/{idTemplate}/script/{idTemplateScript}`](#get-ncm-template-idtemplate-script-idtemplatescript) | Show NCM template script |
| <span class="api-method api-put">PUT</span> | [`/ncm/template/{idTemplate}/script/{idTemplateScript}`](#put-ncm-template-idtemplate-script-idtemplatescript) | Updates a NCM template script |
| <span class="api-method api-delete">DELETE</span> | [`/ncm/template/{idTemplate}/script/{idTemplateScript}`](#delete-ncm-template-idtemplate-script-idtemplatescript) | Deletes a NCM template script. |
| <span class="api-method api-get">GET</span> | [`/ncm/template/{idTemplate}/script/list`](#get-ncm-template-idtemplate-script-list) | List NCM template scripts |
| <span class="api-method api-post">POST</span> | [`/ncm/template/{idTemplate}/script/list`](#post-ncm-template-idtemplate-script-list) | List NCM template scripts |
| <span class="api-method api-post">POST</span> | [`/ncm/vendor`](#post-ncm-vendor) | Creates a new NCM vendor |
| <span class="api-method api-get">GET</span> | [`/ncm/vendor/{idVendor}`](#get-ncm-vendor-idvendor) | Show NCM vendor |
| <span class="api-method api-put">PUT</span> | [`/ncm/vendor/{idVendor}`](#put-ncm-vendor-idvendor) | Updates a NCM vendor |
| <span class="api-method api-delete">DELETE</span> | [`/ncm/vendor/{idVendor}`](#delete-ncm-vendor-idvendor) | Deletes a NCM vendor. |
| <span class="api-method api-get">GET</span> | [`/ncm/vendor/list`](#get-ncm-vendor-list) | List NCM vendors |
| <span class="api-method api-post">POST</span> | [`/ncm/vendor/list`](#post-ncm-vendor-list) | List NCM vendors |
| <span class="api-method api-post">POST</span> | [`/ncm/vendor/{idVendor}/model`](#post-ncm-vendor-idvendor-model) | Creates a new NCM model |
| <span class="api-method api-get">GET</span> | [`/ncm/vendor/{idVendor}/model/{idModel}`](#get-ncm-vendor-idvendor-model-idmodel) | Show NCM model |
| <span class="api-method api-put">PUT</span> | [`/ncm/vendor/{idVendor}/model/{idModel}`](#put-ncm-vendor-idvendor-model-idmodel) | Updates a NCM model |
| <span class="api-method api-delete">DELETE</span> | [`/ncm/vendor/{idVendor}/model/{idModel}`](#delete-ncm-vendor-idvendor-model-idmodel) | Deletes a NCM model. |
| <span class="api-method api-get">GET</span> | [`/ncm/vendor/{idVendor}/model/list`](#get-ncm-vendor-idvendor-model-list) | List NCM models |
| <span class="api-method api-post">POST</span> | [`/ncm/vendor/{idVendor}/model/list`](#post-ncm-vendor-idvendor-model-list) | List NCM models |

## NCM

API Endpoints for Network Configuration Manager

### <span class="api-method api-post">POST</span> `/ncm/agent/{idAgent}/script` { #post-ncm-agent-idagent-script }

Creates a per agent script override

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |

**Request body** (`application/json`): [`NcmAgentScript`](#model-ncmagentscript)

**Response 200**: NCM agent script object

Schema: [`NcmAgentScript`](#model-ncmagentscript)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/agent/{idAgent}/script/{idAgentScript}` { #get-ncm-agent-idagent-script-idagentscript }

Show a per agent script override

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idAgentScript` | path | integer | yes | NCM agent script override id |

**Response 200**: NCM agent script object

Schema: [`NcmAgentScript`](#model-ncmagentscript)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/ncm/agent/{idAgent}/script/{idAgentScript}` { #put-ncm-agent-idagent-script-idagentscript }

Updates a per agent script override

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idAgentScript` | path | integer | yes | NCM agent script override id |

**Request body** (`application/json`): [`NcmAgentScript`](#model-ncmagentscript)

**Response 200**: NCM agent script object

Schema: [`NcmAgentScript`](#model-ncmagentscript)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/ncm/agent/{idAgent}/script/{idAgentScript}` { #delete-ncm-agent-idagent-script-idagentscript }

Deletes a per agent script override.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idAgentScript` | path | integer | yes | NCM agent script override id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/agent/{idAgent}/script/list` { #get-ncm-agent-idagent-script-list }

List per agent script overrides

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List NCM agent script object

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
    | `data.[].idAgentScript` | integer |  | Id of the per agent script override |
    | `data.[].idAgent` | integer |  | Id of the NCM agent the override belongs to |
    | `data.[].type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  | Slot type the override applies to |
    | `data.[].idScript` | integer, nullable |  | Script that overrides the slot. Null inherits the template script |
    | `data.[].eventOnChange` | boolean, nullable |  | Raise an event when the data changes. Null inherits the template value |
    | `data.[].schedule` | string, nullable |  | Cron expression of the slot. Null inherits the template value |
    | `data.[].updatedAt` | integer, nullable |  | Last update timestamp |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/agent/{idAgent}/script/list` { #post-ncm-agent-idagent-script-list }

List per agent script overrides

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgentScript` | integer |  | Id of the per agent script override |
| `idAgent` | integer |  | Id of the NCM agent the override belongs to |
| `type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  | Slot type the override applies to |
| `idScript` | integer, nullable |  | Script that overrides the slot. Null inherits the template script |
| `eventOnChange` | boolean, nullable |  | Raise an event when the data changes. Null inherits the template value |
| `schedule` | string, nullable |  | Cron expression of the slot. Null inherits the template value |
| `updatedAt` | integer, nullable |  | Last update timestamp |
| `idAgentScript` |  |  |  |
| `idAgent` | integer, nullable |  |  |
| `type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  |  |
| `idScript` | integer, nullable |  |  |
| `eventOnChange` | boolean, nullable |  |  |
| `schedule` | string, nullable |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "type": "TEST",
      "idScript": 0,
      "eventOnChange": false,
      "schedule": "string",
      "idAgentScript": null,
      "idAgent": 0,
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

**Response 200**: List NCM agent script object

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
    | `data.[].idAgentScript` | integer |  | Id of the per agent script override |
    | `data.[].idAgent` | integer |  | Id of the NCM agent the override belongs to |
    | `data.[].type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  | Slot type the override applies to |
    | `data.[].idScript` | integer, nullable |  | Script that overrides the slot. Null inherits the template script |
    | `data.[].eventOnChange` | boolean, nullable |  | Raise an event when the data changes. Null inherits the template value |
    | `data.[].schedule` | string, nullable |  | Cron expression of the slot. Null inherits the template value |
    | `data.[].updatedAt` | integer, nullable |  | Last update timestamp |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/agent/{idAgent}/backup/{idBackup}` { #get-ncm-agent-idagent-backup-idbackup }

Show an NCM agent configuration backup

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idBackup` | path | integer | yes | NCM agent backup id |

**Response 200**: NCM agent backup object

Schema: [`NcmAgentBackup`](#model-ncmagentbackup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/ncm/agent/{idAgent}/backup/{idBackup}` { #delete-ncm-agent-idagent-backup-idbackup }

Deletes an NCM agent configuration backup

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idBackup` | path | integer | yes | NCM agent backup id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/agent/{idAgent}/backup/{idBackup}/download` { #get-ncm-agent-idagent-backup-idbackup-download }

Download the raw data of an NCM agent configuration backup

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idBackup` | path | integer | yes | NCM agent backup id |

**Response 200**: Raw configuration backup data

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/agent/{idAgent}/backup/list` { #get-ncm-agent-idagent-backup-list }

List NCM agent configuration backups

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List NCM agent backup object

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
    | `data.[].idBackup` | integer |  | Id of the stored configuration backup |
    | `data.[].idAgent` | integer |  | Id of the NCM agent the backup belongs to |
    | `data.[].scriptType` | integer |  | Slot type that produced the captured data |
    | `data.[].idAgentData` | integer |  | Related agent data id |
    | `data.[].data` | string, nullable |  | Raw captured configuration data |
    | `data.[].script` | string, nullable |  | Executed snippet content (snippet executions only) |
    | `data.[].status` | integer, nullable |  | Status of the captured data |
    | `data.[].updatedAt` | integer, nullable |  | Capture timestamp |
    | `data.[].current` | boolean |  | Whether this backup is the current one for the agent |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/agent/{idAgent}/backup/list` { #post-ncm-agent-idagent-backup-list }

List NCM agent configuration backups with a body filter

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idBackup` | integer |  | Id of the stored configuration backup |
| `idAgent` | integer |  | Id of the NCM agent the backup belongs to |
| `scriptType` | integer |  | Slot type that produced the captured data |
| `idAgentData` | integer |  | Related agent data id |
| `data` | string, nullable |  | Raw captured configuration data |
| `script` | string, nullable |  | Executed snippet content (snippet executions only) |
| `status` | integer, nullable |  | Status of the captured data |
| `updatedAt` | integer, nullable |  | Capture timestamp |
| `current` | boolean |  | Whether this backup is the current one for the agent |
| `idBackup` |  |  |  |
| `idAgent` | integer, nullable |  |  |
| `scriptType` | integer, nullable |  |  |
| `idAgentData` | integer, nullable |  |  |
| `status` | integer, nullable |  |  |
| `updatedAt` | integer, nullable |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idBackup": null,
      "idAgent": 0,
      "scriptType": 0,
      "idAgentData": 0,
      "status": 0,
      "updatedAt": 0,
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

**Response 200**: List NCM agent backup object

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
    | `data.[].idBackup` | integer |  | Id of the stored configuration backup |
    | `data.[].idAgent` | integer |  | Id of the NCM agent the backup belongs to |
    | `data.[].scriptType` | integer |  | Slot type that produced the captured data |
    | `data.[].idAgentData` | integer |  | Related agent data id |
    | `data.[].data` | string, nullable |  | Raw captured configuration data |
    | `data.[].script` | string, nullable |  | Executed snippet content (snippet executions only) |
    | `data.[].status` | integer, nullable |  | Status of the captured data |
    | `data.[].updatedAt` | integer, nullable |  | Capture timestamp |
    | `data.[].current` | boolean |  | Whether this backup is the current one for the agent |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/agent/{idAgent}/backup/mark` { #post-ncm-agent-idagent-backup-mark }

Mark the most recent configuration backup as current

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |

**Response 200**: NCM agent backup object

Schema: [`NcmAgentBackup`](#model-ncmagentbackup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/agent/{idAgent}/backup/{idBackup}/restore` { #post-ncm-agent-idagent-backup-idbackup-restore }

Restore an NCM agent configuration backup

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idBackup` | path | integer | yes | NCM agent backup id |

**Response 200**: NCM agent backup object

Schema: [`NcmAgentBackup`](#model-ncmagentbackup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/agent/bulk` { #post-ncm-agent-bulk }

Applies the same NCM configuration to several agents

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgents` | array of integer |  | Agent ids to configure |
| `idVendor` | integer, nullable |  |  |
| `idModel` | integer, nullable |  |  |
| `protocol` | integer, nullable |  |  |
| `credKey` | string, nullable |  |  |
| `advKey` | string, nullable |  |  |
| `port` | integer, nullable |  |  |
| `idTemplate` | integer, nullable |  |  |
| `cronInterval` | string, nullable |  |  |
| `eventOnChange` | boolean, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgents": [
        0
      ],
      "idVendor": 0,
      "idModel": 0,
      "protocol": 0,
      "credKey": "string",
      "advKey": "string",
      "port": 0,
      "idTemplate": 0,
      "cronInterval": "string",
      "eventOnChange": false
    }
    ```

**Response 200**: Per agent result

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/agent` { #post-ncm-agent }

Enables NCM management for an agent

**Request body** (`application/json`): [`NcmAgent`](#model-ncmagent)

**Response 200**: NCM agent object

Schema: [`NcmAgent`](#model-ncmagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/agent/{idAgent}` { #get-ncm-agent-idagent }

Show NCM agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |

**Response 200**: NCM agent object

Schema: [`NcmAgent`](#model-ncmagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/ncm/agent/{idAgent}` { #put-ncm-agent-idagent }

Updates the NCM configuration of an agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |

**Request body** (`application/json`): [`NcmAgent`](#model-ncmagent)

**Response 200**: NCM agent object

Schema: [`NcmAgent`](#model-ncmagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/ncm/agent/{idAgent}` { #delete-ncm-agent-idagent }

Disables NCM management for an agent.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/agent/list` { #get-ncm-agent-list }

List NCM agents

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List NCM agent object

??? note "Response fields (33 fields)"

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
    | `data.[].idAgent` | integer |  | Agent id the NCM configuration belongs to |
    | `data.[].idVendor` | integer, nullable |  | Vendor id of the device |
    | `data.[].idModel` | integer, nullable |  | Model id of the device |
    | `data.[].protocol` | enum: `0`, `1` |  | Connection protocol: 0 SSH, 1 Telnet |
    | `data.[].credKey` | string, nullable |  | Credential key identifier used to connect to the device |
    | `data.[].advKey` | string, nullable |  | Advanced credential key of the device |
    | `data.[].port` | integer, nullable |  | Connection port |
    | `data.[].idTemplate` | integer, nullable |  | Template id assigned to the device |
    | `data.[].cronInterval` | string, nullable |  | Cron interval for the configuration backup, empty means no schedule |
    | `data.[].eventOnChange` | boolean, nullable |  | Fire an event when the configuration changes |
    | `data.[].status` | integer, nullable |  | Last task status |
    | `data.[].executeType` | integer, nullable |  | Type of the last queued task |
    | `data.[].execute` | integer, nullable |  | Pending task flag |
    | `data.[].configBackupId` | integer, nullable |  | Id of the stored configuration backup |
    | `data.[].updatedAt` | integer, nullable |  | Last update timestamp |
    | `data.[].lastError` | string, nullable |  | Last execution error |
    | `data.[].agentAlias` | string, nullable |  | Alias of the agent |
    | `data.[].agentName` | string, nullable |  | Name of the agent |
    | `data.[].agentAddress` | string, nullable |  | Address of the agent |
    | `data.[].agentDescription` | string, nullable |  | Description of the agent |
    | `data.[].idGroup` | integer, nullable |  | Group id of the agent |
    | `data.[].vendorName` | string, nullable |  | Name of the device vendor |
    | `data.[].modelName` | string, nullable |  | Name of the device model |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/agent/list` { #post-ncm-agent-list }

List NCM agents

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
| `idAgent` | integer |  | Agent id the NCM configuration belongs to |
| `idVendor` | integer, nullable |  | Vendor id of the device |
| `idModel` | integer, nullable |  | Model id of the device |
| `protocol` | enum: `0`, `1` |  | Connection protocol: 0 SSH, 1 Telnet |
| `credKey` | string, nullable |  | Credential key identifier used to connect to the device |
| `advKey` | string, nullable |  | Advanced credential key of the device |
| `port` | integer, nullable |  | Connection port |
| `idTemplate` | integer, nullable |  | Template id assigned to the device |
| `cronInterval` | string, nullable |  | Cron interval for the configuration backup, empty means no schedule |
| `eventOnChange` | boolean, nullable |  | Fire an event when the configuration changes |
| `status` | integer, nullable |  | Last task status |
| `executeType` | integer, nullable |  | Type of the last queued task |
| `execute` | integer, nullable |  | Pending task flag |
| `configBackupId` | integer, nullable |  | Id of the stored configuration backup |
| `updatedAt` | integer, nullable |  | Last update timestamp |
| `lastError` | string, nullable |  | Last execution error |
| `agentAlias` | string, nullable |  | Alias of the agent |
| `agentName` | string, nullable |  | Name of the agent |
| `agentAddress` | string, nullable |  | Address of the agent |
| `agentDescription` | string, nullable |  | Description of the agent |
| `idGroup` | integer, nullable |  | Group id of the agent |
| `vendorName` | string, nullable |  | Name of the device vendor |
| `modelName` | string, nullable |  | Name of the device model |
| `idAgent` |  |  |  |
| `idVendor` | integer, nullable |  |  |
| `idModel` | integer, nullable |  |  |
| `idTemplate` | integer, nullable |  |  |
| `protocol` | integer, nullable |  |  |
| `status` | integer, nullable |  |  |
| `idGroup` | integer, nullable |  |  |
| `freeSearch` | string, nullable |  | Find word in the agent alias, name, address and description. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": null,
      "idVendor": 0,
      "idModel": 0,
      "protocol": 0,
      "credKey": "string",
      "advKey": "string",
      "port": 22,
      "idTemplate": 0,
      "cronInterval": "string",
      "eventOnChange": false,
      "status": 0,
      "idGroup": 0,
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

**Response 200**: List NCM agent object

??? note "Response fields (33 fields)"

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
    | `data.[].idAgent` | integer |  | Agent id the NCM configuration belongs to |
    | `data.[].idVendor` | integer, nullable |  | Vendor id of the device |
    | `data.[].idModel` | integer, nullable |  | Model id of the device |
    | `data.[].protocol` | enum: `0`, `1` |  | Connection protocol: 0 SSH, 1 Telnet |
    | `data.[].credKey` | string, nullable |  | Credential key identifier used to connect to the device |
    | `data.[].advKey` | string, nullable |  | Advanced credential key of the device |
    | `data.[].port` | integer, nullable |  | Connection port |
    | `data.[].idTemplate` | integer, nullable |  | Template id assigned to the device |
    | `data.[].cronInterval` | string, nullable |  | Cron interval for the configuration backup, empty means no schedule |
    | `data.[].eventOnChange` | boolean, nullable |  | Fire an event when the configuration changes |
    | `data.[].status` | integer, nullable |  | Last task status |
    | `data.[].executeType` | integer, nullable |  | Type of the last queued task |
    | `data.[].execute` | integer, nullable |  | Pending task flag |
    | `data.[].configBackupId` | integer, nullable |  | Id of the stored configuration backup |
    | `data.[].updatedAt` | integer, nullable |  | Last update timestamp |
    | `data.[].lastError` | string, nullable |  | Last execution error |
    | `data.[].agentAlias` | string, nullable |  | Alias of the agent |
    | `data.[].agentName` | string, nullable |  | Name of the agent |
    | `data.[].agentAddress` | string, nullable |  | Address of the agent |
    | `data.[].agentDescription` | string, nullable |  | Description of the agent |
    | `data.[].idGroup` | integer, nullable |  | Group id of the agent |
    | `data.[].vendorName` | string, nullable |  | Name of the device vendor |
    | `data.[].modelName` | string, nullable |  | Name of the device model |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/agent/{idAgent}/queue` { #post-ncm-agent-idagent-queue }

Queues a task for an NCM agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |

**Request body** (`application/json`): [`NcmAgentQueue`](#model-ncmagentqueue)

**Response 200**: NCM agent queue object

Schema: [`NcmAgentQueue`](#model-ncmagentqueue)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/ncm/agent/{idAgent}/queue` { #delete-ncm-agent-idagent-queue }

Clears all queued tasks of an NCM agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/ncm/agent/{idAgent}/queue/{idQueue}` { #delete-ncm-agent-idagent-queue-idqueue }

Deletes a queued NCM agent task

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idQueue` | path | integer | yes | NCM agent queue id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/agent/{idAgent}/queue/list` { #get-ncm-agent-idagent-queue-list }

List queued NCM agent tasks

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List NCM agent queue object

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
    | `data.[].idQueue` | integer |  | Id Queue |
    | `data.[].idAgent` | integer |  | Id of the NCM agent the queued task belongs to |
    | `data.[].idScript` | integer |  | Id of the script to run |
    | `data.[].idAgentData` | integer, nullable |  | Related agent data id, zero when not applicable |
    | `data.[].idFirmware` | integer, nullable |  | Firmware to apply on a SET_FIRMWARE task, zero to use the server auto-pick |
    | `data.[].utimestamp` | integer, nullable |  | Queue timestamp |
    | `data.[].scheduled` | integer, nullable |  | Scheduled execution timestamp, null for immediate execution |
    | `data.[].snippet` | string, nullable |  | Optional snippet sent to the script |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/agent/{idAgent}/queue/list` { #post-ncm-agent-idagent-queue-list }

List queued NCM agent tasks with a body filter

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idQueue` | integer |  | Id Queue |
| `idAgent` | integer |  | Id of the NCM agent the queued task belongs to |
| `idScript` | integer |  | Id of the script to run |
| `idAgentData` | integer, nullable |  | Related agent data id, zero when not applicable |
| `idFirmware` | integer, nullable |  | Firmware to apply on a SET_FIRMWARE task, zero to use the server auto-pick |
| `utimestamp` | integer, nullable |  | Queue timestamp |
| `scheduled` | integer, nullable |  | Scheduled execution timestamp, null for immediate execution |
| `snippet` | string, nullable |  | Optional snippet sent to the script |
| `idQueue` |  |  |  |
| `idAgent` | integer, nullable |  |  |
| `idScript` | integer, nullable |  |  |
| `idAgentData` | integer, nullable |  |  |
| `utimestamp` | integer, nullable |  |  |
| `scheduled` | integer, nullable |  |  |
| `snippet` | string, nullable |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idScript": 0,
      "idAgentData": 0,
      "idFirmware": 0,
      "snippet": "string",
      "idQueue": null,
      "idAgent": 0,
      "utimestamp": 0,
      "scheduled": 0,
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

**Response 200**: List NCM agent queue object

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
    | `data.[].idQueue` | integer |  | Id Queue |
    | `data.[].idAgent` | integer |  | Id of the NCM agent the queued task belongs to |
    | `data.[].idScript` | integer |  | Id of the script to run |
    | `data.[].idAgentData` | integer, nullable |  | Related agent data id, zero when not applicable |
    | `data.[].idFirmware` | integer, nullable |  | Firmware to apply on a SET_FIRMWARE task, zero to use the server auto-pick |
    | `data.[].utimestamp` | integer, nullable |  | Queue timestamp |
    | `data.[].scheduled` | integer, nullable |  | Scheduled execution timestamp, null for immediate execution |
    | `data.[].snippet` | string, nullable |  | Optional snippet sent to the script |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/firmware` { #post-ncm-firmware }

Creates a new NCM firmware

**Request body** (`application/json`): [`NcmFirmware`](#model-ncmfirmware)

**Response 200**: NCM firmware object

Schema: [`NcmFirmware`](#model-ncmfirmware)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/firmware/{idFirmware}` { #get-ncm-firmware-idfirmware }

Show NCM firmware

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idFirmware` | path | integer | yes | Firmware id |

**Response 200**: NCM firmware object

Schema: [`NcmFirmware`](#model-ncmfirmware)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/ncm/firmware/{idFirmware}` { #put-ncm-firmware-idfirmware }

Updates a NCM firmware

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idFirmware` | path | integer | yes | Firmware id |

**Request body** (`application/json`): [`NcmFirmware`](#model-ncmfirmware)

**Response 200**: NCM firmware object

Schema: [`NcmFirmware`](#model-ncmfirmware)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/ncm/firmware/{idFirmware}` { #delete-ncm-firmware-idfirmware }

Deletes a NCM firmware.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idFirmware` | path | integer | yes | Firmware id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/firmware/list` { #get-ncm-firmware-list }

List NCM firmwares

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List NCM firmware object

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
    | `data.[].idFirmware` | integer |  | Id Firmware |
    | `data.[].name` | string |  | Name of the firmware |
    | `data.[].shortname` | string, nullable |  | Short unique name of the firmware, derived from vendor and name when omitted |
    | `data.[].vendor` | integer, nullable |  | Id of the vendor the firmware belongs to |
    | `data.[].models` | array, nullable |  | Ids of the models the firmware applies to |
    | `data.[].path` | string, nullable |  | Absolute path of the uploaded firmware binary |
    | `data.[].createdDate` | integer, nullable |  | Creation timestamp of the firmware |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/firmware/list` { #post-ncm-firmware-list }

List NCM firmwares

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
| `idFirmware` | integer |  | Id Firmware |
| `name` | string |  | Name of the firmware |
| `shortname` | string, nullable |  | Short unique name of the firmware, derived from vendor and name when omitted |
| `vendor` | integer, nullable |  | Id of the vendor the firmware belongs to |
| `models` | array, nullable |  | Ids of the models the firmware applies to |
| `path` | string, nullable |  | Absolute path of the uploaded firmware binary |
| `createdDate` | integer, nullable |  | Creation timestamp of the firmware |
| `idFirmware` |  |  |  |
| `name` | string, nullable |  |  |
| `shortname` | string, nullable |  |  |
| `vendor` | integer, nullable |  |  |
| `freeSearch` | string, nullable |  | Find word in name and shortname fields. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "shortname": "string",
      "vendor": 0,
      "models": [
        0
      ],
      "idFirmware": null,
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

**Response 200**: List NCM firmware object

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
    | `data.[].idFirmware` | integer |  | Id Firmware |
    | `data.[].name` | string |  | Name of the firmware |
    | `data.[].shortname` | string, nullable |  | Short unique name of the firmware, derived from vendor and name when omitted |
    | `data.[].vendor` | integer, nullable |  | Id of the vendor the firmware belongs to |
    | `data.[].models` | array, nullable |  | Ids of the models the firmware applies to |
    | `data.[].path` | string, nullable |  | Absolute path of the uploaded firmware binary |
    | `data.[].createdDate` | integer, nullable |  | Creation timestamp of the firmware |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/script` { #post-ncm-script }

Creates a new NCM script

**Request body** (`application/json`): [`Script`](#model-script)

**Response 200**: Script object

Schema: [`Script`](#model-script)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/script/{idScript}` { #get-ncm-script-idscript }

Show NCM script

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScript` | path | integer | yes | Script id |

**Response 200**: Script object

Schema: [`Script`](#model-script)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/ncm/script/{idScript}` { #put-ncm-script-idscript }

Updates a NCM script

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScript` | path | integer | yes | Script id |

**Request body** (`application/json`): [`Script`](#model-script)

**Response 200**: Script object

Schema: [`Script`](#model-script)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/ncm/script/{idScript}` { #delete-ncm-script-idscript }

Deletes a NCM script.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScript` | path | integer | yes | Script id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/script/list` { #get-ncm-script-list }

List NCM scripts

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List NCM script object

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
    | `data.[].idScript` | integer |  | Id Script |
    | `data.[].name` | string |  | Name of the script |
    | `data.[].description` | string, nullable |  | Description of the script |
    | `data.[].idGroup` | integer |  | Group id of the script |
    | `data.[].type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  | Type of the script |
    | `data.[].content` | string, nullable |  | Executable content of the script |
    | `data.[].regexp` | array, nullable |  | Parse output: list of [regex, boolean] pairs. |
    | `data.[].createdAt` | number |  | Creation timestamp of the script |
    | `data.[].updatedAt` | number |  | Last update timestamp of the script |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/script/list` { #post-ncm-script-list }

List NCM scripts

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
| `idScript` | integer |  | Id Script |
| `name` | string |  | Name of the script |
| `description` | string, nullable |  | Description of the script |
| `idGroup` | integer |  | Group id of the script |
| `type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  | Type of the script |
| `content` | string, nullable |  | Executable content of the script |
| `regexp` | array, nullable |  | Parse output: list of [regex, boolean] pairs. |
| `createdAt` | number |  | Creation timestamp of the script |
| `updatedAt` | number |  | Last update timestamp of the script |
| `idScript` |  |  |  |
| `name` | string, nullable |  |  |
| `description` | string, nullable |  |  |
| `idGroup` | integer, nullable |  |  |
| `type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  |  |
| `content` | string, nullable |  |  |
| `regexp` | array, nullable |  |  |
| `freeSearch` | string, nullable |  | Find word in name and description fields. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "type": "TEST",
      "content": "string",
      "regexp": [],
      "idScript": null,
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

**Response 200**: List NCM script object

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
    | `data.[].idScript` | integer |  | Id Script |
    | `data.[].name` | string |  | Name of the script |
    | `data.[].description` | string, nullable |  | Description of the script |
    | `data.[].idGroup` | integer |  | Group id of the script |
    | `data.[].type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  | Type of the script |
    | `data.[].content` | string, nullable |  | Executable content of the script |
    | `data.[].regexp` | array, nullable |  | Parse output: list of [regex, boolean] pairs. |
    | `data.[].createdAt` | number |  | Creation timestamp of the script |
    | `data.[].updatedAt` | number |  | Last update timestamp of the script |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/template` { #post-ncm-template }

Creates a new NCM template

**Request body** (`application/json`): [`Template`](#model-template)

**Response 200**: Template object

Schema: [`Template`](#model-template)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/template/{idTemplate}` { #get-ncm-template-idtemplate }

Show NCM template

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idTemplate` | path | integer | yes | Template id |

**Response 200**: Template object

Schema: [`Template`](#model-template)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/ncm/template/{idTemplate}` { #put-ncm-template-idtemplate }

Updates a NCM template

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idTemplate` | path | integer | yes | Template id |

**Request body** (`application/json`): [`Template`](#model-template)

**Response 200**: Template object

Schema: [`Template`](#model-template)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/ncm/template/{idTemplate}` { #delete-ncm-template-idtemplate }

Deletes a NCM template.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idTemplate` | path | integer | yes | Template id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/template/list` { #get-ncm-template-list }

List NCM templates

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List NCM template object

??? note "Response fields (15 fields)"

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
    | `data.[].idTemplate` | integer |  | Id Template |
    | `data.[].name` | string |  | Name of the template |
    | `data.[].idGroup` | integer |  | Group id of the template |
    | `data.[].vendors` | array, nullable |  | List of vendor ids compatible with the template |
    | `data.[].models` | array, nullable |  | List of model ids compatible with the template |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/template/list` { #post-ncm-template-list }

List NCM templates

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
| `idTemplate` | integer |  | Id Template |
| `name` | string |  | Name of the template |
| `idGroup` | integer |  | Group id of the template |
| `vendors` | array, nullable |  | List of vendor ids compatible with the template |
| `models` | array, nullable |  | List of model ids compatible with the template |
| `idTemplate` |  |  |  |
| `name` | string, nullable |  |  |
| `idGroup` | integer, nullable |  |  |
| `vendors` | array, nullable |  |  |
| `models` | array, nullable |  |  |
| `freeSearch` | string, nullable |  | Find word in name field. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idGroup": 0,
      "vendors": [],
      "models": [],
      "idTemplate": null,
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

**Response 200**: List NCM template object

??? note "Response fields (15 fields)"

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
    | `data.[].idTemplate` | integer |  | Id Template |
    | `data.[].name` | string |  | Name of the template |
    | `data.[].idGroup` | integer |  | Group id of the template |
    | `data.[].vendors` | array, nullable |  | List of vendor ids compatible with the template |
    | `data.[].models` | array, nullable |  | List of model ids compatible with the template |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/template/{idTemplate}/script` { #post-ncm-template-idtemplate-script }

Creates a new NCM template script

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idTemplate` | path | integer | yes | Template id |

**Request body** (`application/json`): [`TemplateScript`](#model-templatescript)

**Response 200**: Template script object

Schema: [`TemplateScript`](#model-templatescript)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/template/{idTemplate}/script/{idTemplateScript}` { #get-ncm-template-idtemplate-script-idtemplatescript }

Show NCM template script

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idTemplate` | path | integer | yes | Template id |
| `idTemplateScript` | path | integer | yes | Template script id |

**Response 200**: Template script object

Schema: [`TemplateScript`](#model-templatescript)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/ncm/template/{idTemplate}/script/{idTemplateScript}` { #put-ncm-template-idtemplate-script-idtemplatescript }

Updates a NCM template script

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idTemplate` | path | integer | yes | Template id |
| `idTemplateScript` | path | integer | yes | Template script id |

**Request body** (`application/json`): [`TemplateScript`](#model-templatescript)

**Response 200**: Template script object

Schema: [`TemplateScript`](#model-templatescript)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/ncm/template/{idTemplate}/script/{idTemplateScript}` { #delete-ncm-template-idtemplate-script-idtemplatescript }

Deletes a NCM template script.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idTemplate` | path | integer | yes | Template id |
| `idTemplateScript` | path | integer | yes | Template script id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/template/{idTemplate}/script/list` { #get-ncm-template-idtemplate-script-list }

List NCM template scripts

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idTemplate` | path | integer | yes | Template id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List NCM template script object

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
    | `data.[].idTemplateScript` | integer |  | Id TemplateScript |
    | `data.[].idTemplate` | integer |  | Id of the template the script belongs to |
    | `data.[].idScript` | integer |  | Id of the script assigned to the slot |
    | `data.[].type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  | Slot type, derived from the assigned script |
    | `data.[].eventOnChange` | boolean |  | Raise an event when the captured data changes |
    | `data.[].schedule` | string |  | Cron expression used to schedule the slot. Empty means no schedule |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/template/{idTemplate}/script/list` { #post-ncm-template-idtemplate-script-list }

List NCM template scripts

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idTemplate` | path | integer | yes | Template id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idTemplateScript` | integer |  | Id TemplateScript |
| `idTemplate` | integer |  | Id of the template the script belongs to |
| `idScript` | integer |  | Id of the script assigned to the slot |
| `type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  | Slot type, derived from the assigned script |
| `eventOnChange` | boolean |  | Raise an event when the captured data changes |
| `schedule` | string |  | Cron expression used to schedule the slot. Empty means no schedule |
| `idTemplateScript` |  |  |  |
| `idTemplate` | integer, nullable |  |  |
| `idScript` | integer, nullable |  |  |
| `type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  |  |
| `eventOnChange` | boolean, nullable |  |  |
| `schedule` | string, nullable |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idScript": 0,
      "eventOnChange": false,
      "schedule": "string",
      "idTemplateScript": null,
      "idTemplate": 0,
      "type": "TEST",
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

**Response 200**: List NCM template script object

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
    | `data.[].idTemplateScript` | integer |  | Id TemplateScript |
    | `data.[].idTemplate` | integer |  | Id of the template the script belongs to |
    | `data.[].idScript` | integer |  | Id of the script assigned to the slot |
    | `data.[].type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  | Slot type, derived from the assigned script |
    | `data.[].eventOnChange` | boolean |  | Raise an event when the captured data changes |
    | `data.[].schedule` | string |  | Cron expression used to schedule the slot. Empty means no schedule |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/vendor` { #post-ncm-vendor }

Creates a new NCM vendor

**Request body** (`application/json`): [`Vendor`](#model-vendor)

**Response 200**: Vendor object

Schema: [`Vendor`](#model-vendor)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/vendor/{idVendor}` { #get-ncm-vendor-idvendor }

Show NCM vendor

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idVendor` | path | integer | yes | Vendor id |

**Response 200**: Vendor object

Schema: [`Vendor`](#model-vendor)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/ncm/vendor/{idVendor}` { #put-ncm-vendor-idvendor }

Updates a NCM vendor

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idVendor` | path | integer | yes | Vendor id |

**Request body** (`application/json`): [`Vendor`](#model-vendor)

**Response 200**: Vendor object

Schema: [`Vendor`](#model-vendor)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/ncm/vendor/{idVendor}` { #delete-ncm-vendor-idvendor }

Deletes a NCM vendor.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idVendor` | path | integer | yes | Vendor id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/vendor/list` { #get-ncm-vendor-list }

List NCM vendors

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List NCM vendor object

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
    | `data.[].idVendor` | integer |  | Id Vendor |
    | `data.[].name` | string |  | Name of the vendor |
    | `data.[].description` | string, nullable |  | Description of the vendor |
    | `data.[].icon` | string |  | Relative path of the vendor icon |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/vendor/list` { #post-ncm-vendor-list }

List NCM vendors

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
| `idVendor` | integer |  | Id Vendor |
| `name` | string |  | Name of the vendor |
| `description` | string, nullable |  | Description of the vendor |
| `icon` | string |  | Relative path of the vendor icon |
| `idVendor` |  |  |  |
| `name` | string, nullable |  |  |
| `description` | string, nullable |  |  |
| `icon` | string, nullable |  |  |
| `freeSearch` | string, nullable |  | Find word in name and description fields. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "icon": "string",
      "idVendor": null,
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

**Response 200**: List NCM vendor object

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
    | `data.[].idVendor` | integer |  | Id Vendor |
    | `data.[].name` | string |  | Name of the vendor |
    | `data.[].description` | string, nullable |  | Description of the vendor |
    | `data.[].icon` | string |  | Relative path of the vendor icon |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/vendor/{idVendor}/model` { #post-ncm-vendor-idvendor-model }

Creates a new NCM model

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idVendor` | path | integer | yes | Vendor id |

**Request body** (`application/json`): [`Model`](#model-model)

**Response 200**: Model object

Schema: [`Model`](#model-model)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/vendor/{idVendor}/model/{idModel}` { #get-ncm-vendor-idvendor-model-idmodel }

Show NCM model

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idVendor` | path | integer | yes | Vendor id |
| `idModel` | path | integer | yes | Model id |

**Response 200**: Model object

Schema: [`Model`](#model-model)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/ncm/vendor/{idVendor}/model/{idModel}` { #put-ncm-vendor-idvendor-model-idmodel }

Updates a NCM model

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idVendor` | path | integer | yes | Vendor id |
| `idModel` | path | integer | yes | Model id |

**Request body** (`application/json`): [`Model`](#model-model)

**Response 200**: Model object

Schema: [`Model`](#model-model)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/ncm/vendor/{idVendor}/model/{idModel}` { #delete-ncm-vendor-idvendor-model-idmodel }

Deletes a NCM model.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idVendor` | path | integer | yes | Vendor id |
| `idModel` | path | integer | yes | Model id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/ncm/vendor/{idVendor}/model/list` { #get-ncm-vendor-idvendor-model-list }

List NCM models

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idVendor` | path | integer | yes | Vendor id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List NCM model object

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
    | `data.[].idModel` | integer |  | Id Model |
    | `data.[].idVendor` | integer |  | Id of the vendor the model belongs to |
    | `data.[].name` | string |  | Name of the model |
    | `data.[].description` | string, nullable |  | Description of the model |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/ncm/vendor/{idVendor}/model/list` { #post-ncm-vendor-idvendor-model-list }

List NCM models

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idVendor` | path | integer | yes | Vendor id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idModel` | integer |  | Id Model |
| `idVendor` | integer |  | Id of the vendor the model belongs to |
| `name` | string |  | Name of the model |
| `description` | string, nullable |  | Description of the model |
| `idModel` |  |  |  |
| `idVendor` | integer, nullable |  |  |
| `name` | string, nullable |  |  |
| `description` | string, nullable |  |  |
| `freeSearch` | string, nullable |  | Find word in name and description fields. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idModel": null,
      "idVendor": 0,
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

**Response 200**: List NCM model object

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
    | `data.[].idModel` | integer |  | Id Model |
    | `data.[].idVendor` | integer |  | Id of the vendor the model belongs to |
    | `data.[].name` | string |  | Name of the model |
    | `data.[].description` | string, nullable |  | Description of the model |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: Model { #model-model }

| Field | Type | Required | Description |
|---|---|---|---|
| `idModel` | integer |  | Id Model |
| `idVendor` | integer |  | Id of the vendor the model belongs to |
| `name` | string |  | Name of the model |
| `description` | string, nullable |  | Description of the model |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string"
    }
    ```

### Model: NcmAgent { #model-ncmagent }

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgent` | integer |  | Agent id the NCM configuration belongs to |
| `idVendor` | integer, nullable |  | Vendor id of the device |
| `idModel` | integer, nullable |  | Model id of the device |
| `protocol` | enum: `0`, `1` |  | Connection protocol: 0 SSH, 1 Telnet |
| `credKey` | string, nullable |  | Credential key identifier used to connect to the device |
| `advKey` | string, nullable |  | Advanced credential key of the device |
| `port` | integer, nullable |  | Connection port |
| `idTemplate` | integer, nullable |  | Template id assigned to the device |
| `cronInterval` | string, nullable |  | Cron interval for the configuration backup, empty means no schedule |
| `eventOnChange` | boolean, nullable |  | Fire an event when the configuration changes |
| `status` | integer, nullable |  | Last task status |
| `executeType` | integer, nullable |  | Type of the last queued task |
| `execute` | integer, nullable |  | Pending task flag |
| `configBackupId` | integer, nullable |  | Id of the stored configuration backup |
| `updatedAt` | integer, nullable |  | Last update timestamp |
| `lastError` | string, nullable |  | Last execution error |
| `agentAlias` | string, nullable |  | Alias of the agent |
| `agentName` | string, nullable |  | Name of the agent |
| `agentAddress` | string, nullable |  | Address of the agent |
| `agentDescription` | string, nullable |  | Description of the agent |
| `idGroup` | integer, nullable |  | Group id of the agent |
| `vendorName` | string, nullable |  | Name of the device vendor |
| `modelName` | string, nullable |  | Name of the device model |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": 0,
      "idVendor": 0,
      "idModel": 0,
      "protocol": 0,
      "credKey": "string",
      "advKey": "string",
      "port": 22,
      "idTemplate": 0,
      "cronInterval": "string",
      "eventOnChange": false
    }
    ```

### Model: NcmAgentBackup { #model-ncmagentbackup }

??? note "Fields (9 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idBackup` | integer |  | Id of the stored configuration backup |
    | `idAgent` | integer |  | Id of the NCM agent the backup belongs to |
    | `scriptType` | integer |  | Slot type that produced the captured data |
    | `idAgentData` | integer |  | Related agent data id |
    | `data` | string, nullable |  | Raw captured configuration data |
    | `script` | string, nullable |  | Executed snippet content (snippet executions only) |
    | `status` | integer, nullable |  | Status of the captured data |
    | `updatedAt` | integer, nullable |  | Capture timestamp |
    | `current` | boolean |  | Whether this backup is the current one for the agent |


### Model: NcmAgentQueue { #model-ncmagentqueue }

| Field | Type | Required | Description |
|---|---|---|---|
| `idQueue` | integer |  | Id Queue |
| `idAgent` | integer |  | Id of the NCM agent the queued task belongs to |
| `idScript` | integer |  | Id of the script to run |
| `idAgentData` | integer, nullable |  | Related agent data id, zero when not applicable |
| `idFirmware` | integer, nullable |  | Firmware to apply on a SET_FIRMWARE task, zero to use the server auto-pick |
| `utimestamp` | integer, nullable |  | Queue timestamp |
| `scheduled` | integer, nullable |  | Scheduled execution timestamp, null for immediate execution |
| `snippet` | string, nullable |  | Optional snippet sent to the script |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idScript": 0,
      "idAgentData": 0,
      "idFirmware": 0,
      "snippet": "string"
    }
    ```

### Model: NcmAgentScript { #model-ncmagentscript }

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgentScript` | integer |  | Id of the per agent script override |
| `idAgent` | integer |  | Id of the NCM agent the override belongs to |
| `type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  | Slot type the override applies to |
| `idScript` | integer, nullable |  | Script that overrides the slot. Null inherits the template script |
| `eventOnChange` | boolean, nullable |  | Raise an event when the data changes. Null inherits the template value |
| `schedule` | string, nullable |  | Cron expression of the slot. Null inherits the template value |
| `updatedAt` | integer, nullable |  | Last update timestamp |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "type": "TEST",
      "idScript": 0,
      "eventOnChange": false,
      "schedule": "string"
    }
    ```

### Model: NcmFirmware { #model-ncmfirmware }

| Field | Type | Required | Description |
|---|---|---|---|
| `idFirmware` | integer |  | Id Firmware |
| `name` | string |  | Name of the firmware |
| `shortname` | string, nullable |  | Short unique name of the firmware, derived from vendor and name when omitted |
| `vendor` | integer, nullable |  | Id of the vendor the firmware belongs to |
| `models` | array, nullable |  | Ids of the models the firmware applies to |
| `path` | string, nullable |  | Absolute path of the uploaded firmware binary |
| `createdDate` | integer, nullable |  | Creation timestamp of the firmware |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "shortname": "string",
      "vendor": 0,
      "models": [
        0
      ]
    }
    ```

### Model: Script { #model-script }

| Field | Type | Required | Description |
|---|---|---|---|
| `idScript` | integer |  | Id Script |
| `name` | string |  | Name of the script |
| `description` | string, nullable |  | Description of the script |
| `idGroup` | integer |  | Group id of the script |
| `type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  | Type of the script |
| `content` | string, nullable |  | Executable content of the script |
| `regexp` | array, nullable |  | Parse output: list of [regex, boolean] pairs. |
| `createdAt` | number |  | Creation timestamp of the script |
| `updatedAt` | number |  | Last update timestamp of the script |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "type": "TEST",
      "content": "string",
      "regexp": [
        [
          "^.*$",
          true
        ]
      ]
    }
    ```

### Model: Template { #model-template }

| Field | Type | Required | Description |
|---|---|---|---|
| `idTemplate` | integer |  | Id Template |
| `name` | string |  | Name of the template |
| `idGroup` | integer |  | Group id of the template |
| `vendors` | array, nullable |  | List of vendor ids compatible with the template |
| `models` | array, nullable |  | List of model ids compatible with the template |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idGroup": 0,
      "vendors": [
        0
      ],
      "models": [
        0
      ]
    }
    ```

### Model: TemplateScript { #model-templatescript }

| Field | Type | Required | Description |
|---|---|---|---|
| `idTemplateScript` | integer |  | Id TemplateScript |
| `idTemplate` | integer |  | Id of the template the script belongs to |
| `idScript` | integer |  | Id of the script assigned to the slot |
| `type` | enum: `TEST`, `GET_CONFIGURATION`, `SET_CONFIGURATION`, `GET_FIRMWARE`, `SET_FIRMWARE`, `CUSTOM_TASK`, `SNIPPET`, `GET_OS_VERSION` |  | Slot type, derived from the assigned script |
| `eventOnChange` | boolean |  | Raise an event when the captured data changes |
| `schedule` | string |  | Cron expression used to schedule the slot. Empty means no schedule |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idScript": 0,
      "eventOnChange": false,
      "schedule": "string"
    }
    ```

### Model: Vendor { #model-vendor }

| Field | Type | Required | Description |
|---|---|---|---|
| `idVendor` | integer |  | Id Vendor |
| `name` | string |  | Name of the vendor |
| `description` | string, nullable |  | Description of the vendor |
| `icon` | string |  | Relative path of the vendor icon |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "icon": "string"
    }
    ```
