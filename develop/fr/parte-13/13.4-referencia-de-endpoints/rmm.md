# RMM

Remote monitoring and management (RMM).

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-get">GET</span> | [`/rmm/agent/{idAgentRmm}`](#get-rmm-agent-idagentrmm) | Show RMM agent |
| <span class="api-method api-put">PUT</span> | [`/rmm/agent/{idAgentRmm}`](#put-rmm-agent-idagentrmm) | Updates an RMM agent |
| <span class="api-method api-delete">DELETE</span> | [`/rmm/agent/{idAgentRmm}`](#delete-rmm-agent-idagentrmm) | Deletes an RMM agent object. |
| <span class="api-method api-get">GET</span> | [`/rmm/agent/list`](#get-rmm-agent-list) | List RMM agents |
| <span class="api-method api-post">POST</span> | [`/rmm/agent/list`](#post-rmm-agent-list) | List RMM agents |
| <span class="api-method api-post">POST</span> | [`/rmm/batch/{idBatchJob}/agent`](#post-rmm-batch-idbatchjob-agent) | Creates a new RMM batch agent relation |
| <span class="api-method api-get">GET</span> | [`/rmm/batch/{idBatchJob}/agent/{idBatchAgent}`](#get-rmm-batch-idbatchjob-agent-idbatchagent) | Show RMM batch agent relation |
| <span class="api-method api-delete">DELETE</span> | [`/rmm/batch/{idBatchJob}/agent/{idBatchAgent}`](#delete-rmm-batch-idbatchjob-agent-idbatchagent) | Deletes an RMM batch agent relation |
| <span class="api-method api-get">GET</span> | [`/rmm/batch/{idBatchJob}/agent/list`](#get-rmm-batch-idbatchjob-agent-list) | List RMM batch agent relations |
| <span class="api-method api-post">POST</span> | [`/rmm/batch/{idBatchJob}/agent/list`](#post-rmm-batch-idbatchjob-agent-list) | List RMM batch agent relations |
| <span class="api-method api-post">POST</span> | [`/rmm/batch`](#post-rmm-batch) | Creates a new RMM batch job |
| <span class="api-method api-get">GET</span> | [`/rmm/batch/{idBatchJob}`](#get-rmm-batch-idbatchjob) | Show RMM batch job |
| <span class="api-method api-put">PUT</span> | [`/rmm/batch/{idBatchJob}`](#put-rmm-batch-idbatchjob) | Updates an RMM batch job |
| <span class="api-method api-delete">DELETE</span> | [`/rmm/batch/{idBatchJob}`](#delete-rmm-batch-idbatchjob) | Deletes an RMM batch job |
| <span class="api-method api-get">GET</span> | [`/rmm/batch/list`](#get-rmm-batch-list) | List RMM batch jobs |
| <span class="api-method api-post">POST</span> | [`/rmm/batch/list`](#post-rmm-batch-list) | List RMM batch jobs |
| <span class="api-method api-post">POST</span> | [`/rmm/batch/{idBatchJob}/queue`](#post-rmm-batch-idbatchjob-queue) | Creates a new RMM batch queue entry |
| <span class="api-method api-get">GET</span> | [`/rmm/batch/{idBatchJob}/queue/{idBatchQueue}`](#get-rmm-batch-idbatchjob-queue-idbatchqueue) | Show RMM batch queue entry |
| <span class="api-method api-put">PUT</span> | [`/rmm/batch/{idBatchJob}/queue/{idBatchQueue}`](#put-rmm-batch-idbatchjob-queue-idbatchqueue) | Updates an RMM batch queue entry |
| <span class="api-method api-delete">DELETE</span> | [`/rmm/batch/{idBatchJob}/queue/{idBatchQueue}`](#delete-rmm-batch-idbatchjob-queue-idbatchqueue) | Deletes an RMM batch queue entry |
| <span class="api-method api-post">POST</span> | [`/rmm/batch/{idBatchJob}/queue/{idBatchQueue}/execute`](#post-rmm-batch-idbatchjob-queue-idbatchqueue-execute) | Executes an RMM batch queue entry over the batch job agents |
| <span class="api-method api-get">GET</span> | [`/rmm/batch/{idBatchJob}/queue/list`](#get-rmm-batch-idbatchjob-queue-list) | List RMM batch queue entries |
| <span class="api-method api-post">POST</span> | [`/rmm/batch/{idBatchJob}/queue/list`](#post-rmm-batch-idbatchjob-queue-list) | List RMM batch queue entries |
| <span class="api-method api-post">POST</span> | [`/rmm/batch/{idBatchJob}/rule`](#post-rmm-batch-idbatchjob-rule) | Creates a new RMM batch rule |
| <span class="api-method api-get">GET</span> | [`/rmm/batch/{idBatchJob}/rule/{idBatchRule}`](#get-rmm-batch-idbatchjob-rule-idbatchrule) | Show RMM batch rule |
| <span class="api-method api-put">PUT</span> | [`/rmm/batch/{idBatchJob}/rule/{idBatchRule}`](#put-rmm-batch-idbatchjob-rule-idbatchrule) | Updates an RMM batch rule |
| <span class="api-method api-delete">DELETE</span> | [`/rmm/batch/{idBatchJob}/rule/{idBatchRule}`](#delete-rmm-batch-idbatchjob-rule-idbatchrule) | Deletes an RMM batch rule |
| <span class="api-method api-get">GET</span> | [`/rmm/batch/{idBatchJob}/rule/list`](#get-rmm-batch-idbatchjob-rule-list) | List RMM batch rules |
| <span class="api-method api-post">POST</span> | [`/rmm/batch/{idBatchJob}/rule/list`](#post-rmm-batch-idbatchjob-rule-list) | List RMM batch rules |
| <span class="api-method api-post">POST</span> | [`/rmm/pendingSoftware/agentsWithPending/list`](#post-rmm-pendingsoftware-agentswithpending-list) | List RMM agents that have pending software updates |
| <span class="api-method api-get">GET</span> | [`/rmm/pendingSoftware/list`](#get-rmm-pendingsoftware-list) | List pending software updates of the RMM agents |
| <span class="api-method api-post">POST</span> | [`/rmm/pendingSoftware/list`](#post-rmm-pendingsoftware-list) | List pending software updates of the RMM agents |
| <span class="api-method api-get">GET</span> | [`/rmm/queue/{id}`](#get-rmm-queue-id) | Show RMM queue |
| <span class="api-method api-delete">DELETE</span> | [`/rmm/queue/{id}`](#delete-rmm-queue-id) | Deletes an RMM queue object. |
| <span class="api-method api-get">GET</span> | [`/rmm/queue/list`](#get-rmm-queue-list) | List RMM queues |
| <span class="api-method api-post">POST</span> | [`/rmm/queue/list`](#post-rmm-queue-list) | List RMM queues |
| <span class="api-method api-post">POST</span> | [`/rmm/resource`](#post-rmm-resource) | Creates a new RMM resource |
| <span class="api-method api-get">GET</span> | [`/rmm/resource/{idResource}`](#get-rmm-resource-idresource) | Show RMM resource |
| <span class="api-method api-delete">DELETE</span> | [`/rmm/resource/{idResource}`](#delete-rmm-resource-idresource) | Deletes an RMM resource object. |
| <span class="api-method api-get">GET</span> | [`/rmm/resource/exist/{shortName}`](#get-rmm-resource-exist-shortname) | Checks if an RMM resource short name exists |
| <span class="api-method api-get">GET</span> | [`/rmm/resource/list`](#get-rmm-resource-list) | List RMM resources |
| <span class="api-method api-post">POST</span> | [`/rmm/resource/list`](#post-rmm-resource-list) | List RMM resources |
| <span class="api-method api-post">POST</span> | [`/rmm/resource/{idResource}/version`](#post-rmm-resource-idresource-version) | Creates a new version of an RMM resource |
| <span class="api-method api-get">GET</span> | [`/rmm/resource/{idResource}/version/{version}`](#get-rmm-resource-idresource-version-version) | Show RMM resource version |
| <span class="api-method api-put">PUT</span> | [`/rmm/resource/{idResource}/version/{version}`](#put-rmm-resource-idresource-version-version) | Updates an RMM resource version (only name and current) |
| <span class="api-method api-delete">DELETE</span> | [`/rmm/resource/{idResource}/version/{version}`](#delete-rmm-resource-idresource-version-version) | Deletes an RMM resource version object. |
| <span class="api-method api-get">GET</span> | [`/rmm/resource/{idResource}/version/{version}/download`](#get-rmm-resource-idresource-version-version-download) | Download RMM resource version file |
| <span class="api-method api-get">GET</span> | [`/rmm/resource/{idResource}/version/list`](#get-rmm-resource-idresource-version-list) | List RMM resource versions |
| <span class="api-method api-post">POST</span> | [`/rmm/resource/{idResource}/version/list`](#post-rmm-resource-idresource-version-list) | List RMM resource versions |
| <span class="api-method api-post">POST</span> | [`/rmm/routine/{idRoutine}/agent`](#post-rmm-routine-idroutine-agent) | Creates a new RMM routine agent relation |
| <span class="api-method api-get">GET</span> | [`/rmm/routine/{idRoutine}/agent/{idRoutineAgent}`](#get-rmm-routine-idroutine-agent-idroutineagent) | Show RMM routine agent relation |
| <span class="api-method api-put">PUT</span> | [`/rmm/routine/{idRoutine}/agent/{idRoutineAgent}`](#put-rmm-routine-idroutine-agent-idroutineagent) | Updates an RMM routine agent relation |
| <span class="api-method api-get">GET</span> | [`/rmm/routine/{idRoutine}/agent/list`](#get-rmm-routine-idroutine-agent-list) | List RMM routine agent relations |
| <span class="api-method api-post">POST</span> | [`/rmm/routine/{idRoutine}/agent/list`](#post-rmm-routine-idroutine-agent-list) | List RMM routine agent relations |
| <span class="api-method api-post">POST</span> | [`/rmm/routine`](#post-rmm-routine) | Creates a new RMM routine |
| <span class="api-method api-get">GET</span> | [`/rmm/routine/{idRoutine}`](#get-rmm-routine-idroutine) | Show RMM routine |
| <span class="api-method api-put">PUT</span> | [`/rmm/routine/{idRoutine}`](#put-rmm-routine-idroutine) | Updates an RMM routine |
| <span class="api-method api-delete">DELETE</span> | [`/rmm/routine/{idRoutine}`](#delete-rmm-routine-idroutine) | Deletes an RMM routine object. |
| <span class="api-method api-get">GET</span> | [`/rmm/routine/list`](#get-rmm-routine-list) | List RMM routines |
| <span class="api-method api-post">POST</span> | [`/rmm/routine/list`](#post-rmm-routine-list) | List RMM routines |
| <span class="api-method api-post">POST</span> | [`/rmm/routine/{idRoutine}/queue`](#post-rmm-routine-idroutine-queue) | Creates a new RMM routine queue |
| <span class="api-method api-get">GET</span> | [`/rmm/routine/{idRoutine}/queue/{idRoutineQueue}`](#get-rmm-routine-idroutine-queue-idroutinequeue) | Show RMM routine queue |
| <span class="api-method api-put">PUT</span> | [`/rmm/routine/{idRoutine}/queue/{idRoutineQueue}`](#put-rmm-routine-idroutine-queue-idroutinequeue) | Updates an RMM routine queue |
| <span class="api-method api-delete">DELETE</span> | [`/rmm/routine/{idRoutine}/queue/{idRoutineQueue}`](#delete-rmm-routine-idroutine-queue-idroutinequeue) | Deletes an RMM routine queue object. |
| <span class="api-method api-post">POST</span> | [`/rmm/routine/{idRoutine}/queue/{idRoutineQueue}/execute`](#post-rmm-routine-idroutine-queue-idroutinequeue-execute) | Executes an RMM routine queue entry |
| <span class="api-method api-get">GET</span> | [`/rmm/routine/{idRoutine}/queue/list`](#get-rmm-routine-idroutine-queue-list) | List RMM routine queues |
| <span class="api-method api-post">POST</span> | [`/rmm/routine/{idRoutine}/queue/list`](#post-rmm-routine-idroutine-queue-list) | List RMM routine queues |
| <span class="api-method api-post">POST</span> | [`/rmm/routine/{idRoutine}/schedule`](#post-rmm-routine-idroutine-schedule) | Creates a new RMM routine schedule |
| <span class="api-method api-get">GET</span> | [`/rmm/routine/{idRoutine}/schedule/{idRoutineSchedule}`](#get-rmm-routine-idroutine-schedule-idroutineschedule) | Show RMM routine schedule |
| <span class="api-method api-put">PUT</span> | [`/rmm/routine/{idRoutine}/schedule/{idRoutineSchedule}`](#put-rmm-routine-idroutine-schedule-idroutineschedule) | Updates an RMM routine schedule |
| <span class="api-method api-get">GET</span> | [`/rmm/routine/{idRoutine}/schedule/list`](#get-rmm-routine-idroutine-schedule-list) | List RMM routine schedules |
| <span class="api-method api-post">POST</span> | [`/rmm/routine/{idRoutine}/schedule/list`](#post-rmm-routine-idroutine-schedule-list) | List RMM routine schedules |
| <span class="api-method api-post">POST</span> | [`/rmm/rule/execute`](#post-rmm-rule-execute) | Executes an RMM rule on a set of agents |
| <span class="api-method api-post">POST</span> | [`/rmm/schedule`](#post-rmm-schedule) | Creates a new RMM schedule |
| <span class="api-method api-get">GET</span> | [`/rmm/schedule/{id}`](#get-rmm-schedule-id) | Show RMM schedule |
| <span class="api-method api-put">PUT</span> | [`/rmm/schedule/{id}`](#put-rmm-schedule-id) | Updates an RMM schedule |
| <span class="api-method api-delete">DELETE</span> | [`/rmm/schedule/{id}`](#delete-rmm-schedule-id) | Deletes an RMM schedule object. |
| <span class="api-method api-get">GET</span> | [`/rmm/schedule/list`](#get-rmm-schedule-list) | List RMM schedules |
| <span class="api-method api-post">POST</span> | [`/rmm/schedule/list`](#post-rmm-schedule-list) | List RMM schedules |
| <span class="api-method api-post">POST</span> | [`/rmm/script`](#post-rmm-script) | Creates a new RMM script |
| <span class="api-method api-get">GET</span> | [`/rmm/script/{idScriptRmm}`](#get-rmm-script-idscriptrmm) | Show RMM script |
| <span class="api-method api-put">PUT</span> | [`/rmm/script/{idScriptRmm}`](#put-rmm-script-idscriptrmm) | Updates an RMM script |
| <span class="api-method api-delete">DELETE</span> | [`/rmm/script/{idScriptRmm}`](#delete-rmm-script-idscriptrmm) | Deletes an RMM script object. |
| <span class="api-method api-get">GET</span> | [`/rmm/script/list`](#get-rmm-script-list) | List RMM scripts |
| <span class="api-method api-post">POST</span> | [`/rmm/script/list`](#post-rmm-script-list) | List RMM scripts |
| <span class="api-method api-post">POST</span> | [`/rmm/settings`](#post-rmm-settings) | Create a RMM settings object |
| <span class="api-method api-get">GET</span> | [`/rmm/settings/{id}`](#get-rmm-settings-id) | Get a RMM settings object |
| <span class="api-method api-put">PUT</span> | [`/rmm/settings/{id}`](#put-rmm-settings-id) | Update a RMM settings object |
| <span class="api-method api-get">GET</span> | [`/rmm/settings/list`](#get-rmm-settings-list) | List RMM settings |
| <span class="api-method api-post">POST</span> | [`/rmm/settings/list`](#post-rmm-settings-list) | List RMM settings |

## RMM

API Endpoints of RMM

### <span class="api-method api-get">GET</span> `/rmm/agent/{idAgentRmm}` { #get-rmm-agent-idagentrmm }

Show RMM agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentRmm` | path | integer | yes | RMM agent id |

**Response 200**: RMM agent object

Schema: [`RmmAgent`](#model-rmmagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/rmm/agent/{idAgentRmm}` { #put-rmm-agent-idagentrmm }

Updates an RMM agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentRmm` | path | integer | yes | RMM agent id |

**Request body** (`application/json`): [`RmmAgent`](#model-rmmagent)

**Response 200**: RMM agent object

Schema: [`RmmAgent`](#model-rmmagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/rmm/agent/{idAgentRmm}` { #delete-rmm-agent-idagentrmm }

Deletes an RMM agent object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentRmm` | path | integer | yes | RMM agent id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/agent/list` { #get-rmm-agent-list }

List RMM agents

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM agent object

??? note "Response fields (70 fields)"

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
    | `data.[].idAgentRmm` | integer |  | Id RMM agent |
    | `data.[].agentName` | string |  | Name of the RMM agent |
    | `data.[].lastContact` | integer, nullable |  | RMM agent last contact utimestamp |
    | `data.[].interval` | integer, nullable |  | RMM agent contact interval |
    | `data.[].enabled` | boolean, nullable |  | Whether the RMM agent is enabled |
    | `data.[].status` | integer, nullable |  | RMM agent status |
    | `data.[].Agent` |  |  | Embedded normal agent |
    | `data.[].Agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
    | `data.[].Agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
    | `data.[].Agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
    | `data.[].Agent.name` | string |  | Agent name |
    | `data.[].Agent.address` | string, nullable |  | Agent address |
    | `data.[].Agent.comments` | string, nullable |  | Agent comments |
    | `data.[].Agent.idGroup` | integer |  | Group ID |
    | `data.[].Agent.lastContact` | string |  | Last contact timestamp |
    | `data.[].Agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
    | `data.[].Agent.interval` | integer |  | Agent interval in seconds |
    | `data.[].Agent.idOs` | integer, nullable |  | Operating System ID |
    | `data.[].Agent.osVersion` | string, nullable |  | Operating System version |
    | `data.[].Agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].Agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].Agent.agentVersion` | string, nullable |  | Agent version |
    | `data.[].Agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
    | `data.[].Agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
    | `data.[].Agent.remote` | integer |  | Remote agent flag |
    | `data.[].Agent.idParent` | integer, nullable |  | Parent agent ID |
    | `data.[].Agent.customId` | string, nullable |  | Custom agent ID |
    | `data.[].Agent.serverName` | string, nullable |  | Server name |
    | `data.[].Agent.cascadeProtection` | integer |  | Cascade protection flag |
    | `data.[].Agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
    | `data.[].Agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
    | `data.[].Agent.iconPath` | string, nullable |  | Icon path |
    | `data.[].Agent.updateGisData` | integer |  | Update GIS data flag |
    | `data.[].Agent.urlAddress` | string, nullable |  | URL address |
    | `data.[].Agent.quiet` | integer |  | Quiet flag |
    | `data.[].Agent.normalCount` | integer |  | Normal modules count |
    | `data.[].Agent.warningCount` | integer |  | Warning modules count |
    | `data.[].Agent.criticalCount` | integer |  | Critical modules count |
    | `data.[].Agent.unknownCount` | integer |  | Unknown modules count |
    | `data.[].Agent.notinitCount` | integer |  | Not init modules count |
    | `data.[].Agent.totalCount` | integer |  | Total modules count |
    | `data.[].Agent.firedCount` | integer |  | Fired alerts count |
    | `data.[].Agent.updateModuleCount` | integer |  | Update module count flag |
    | `data.[].Agent.updateAlertCount` | integer |  | Update alert count flag |
    | `data.[].Agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
    | `data.[].Agent.alias` | string |  | Agent alias |
    | `data.[].Agent.aliasAsName` | integer |  | Use alias as name flag |
    | `data.[].Agent.safeModeModule` | integer |  | Safe mode module ID |
    | `data.[].Agent.cps` | integer |  | CPS value |
    | `data.[].Agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
    | `data.[].Agent.satelliteServer` | integer |  | Satellite server ID |
    | `data.[].Agent.fixedIp` | integer |  | Fixed IP flag |
    | `data.[].Agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
    | `data.[].Agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
    | `data.[].Agent.ignoreUnknown` | integer |  | Ignore unknown flag |
    | `data.[].Agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
    | `data.[].Agent.autoHa` | integer |  | Auto HA flag |
    | `data.[].Agent.extraData` | string |  | Extra data |
    | `data.[].Agent.quietByDowntime` | integer |  | Quiet by downtime flag |
    | `data.[].Agent.idFimPolicy` | integer |  | FIM Policy ID |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/agent/list` { #post-rmm-agent-list }

List RMM agents

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
| `idAgentRmm` | integer |  | Id RMM agent |
| `agentName` | string |  | Name of the RMM agent |
| `lastContact` | integer, nullable |  | RMM agent last contact utimestamp |
| `interval` | integer, nullable |  | RMM agent contact interval |
| `enabled` | boolean, nullable |  | Whether the RMM agent is enabled |
| `status` | integer, nullable |  | RMM agent status |
| `Agent` |  |  | Embedded normal agent |
| `Agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
| `Agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
| `Agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
| `Agent.name` | string |  | Agent name |
| `Agent.address` | string, nullable |  | Agent address |
| `Agent.comments` | string, nullable |  | Agent comments |
| `Agent.idGroup` | integer |  | Group ID |
| `Agent.lastContact` | string |  | Last contact timestamp |
| `Agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
| `Agent.interval` | integer |  | Agent interval in seconds |
| `Agent.idOs` | integer, nullable |  | Operating System ID |
| `Agent.osVersion` | string, nullable |  | Operating System version |
| `Agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
| `Agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
| `Agent.agentVersion` | string, nullable |  | Agent version |
| `Agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
| `Agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
| `Agent.remote` | integer |  | Remote agent flag |
| `Agent.idParent` | integer, nullable |  | Parent agent ID |
| `Agent.customId` | string, nullable |  | Custom agent ID |
| `Agent.serverName` | string, nullable |  | Server name |
| `Agent.cascadeProtection` | integer |  | Cascade protection flag |
| `Agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
| `Agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
| `Agent.iconPath` | string, nullable |  | Icon path |
| `Agent.updateGisData` | integer |  | Update GIS data flag |
| `Agent.urlAddress` | string, nullable |  | URL address |
| `Agent.quiet` | integer |  | Quiet flag |
| `Agent.normalCount` | integer |  | Normal modules count |
| `Agent.warningCount` | integer |  | Warning modules count |
| `Agent.criticalCount` | integer |  | Critical modules count |
| `Agent.unknownCount` | integer |  | Unknown modules count |
| `Agent.notinitCount` | integer |  | Not init modules count |
| `Agent.totalCount` | integer |  | Total modules count |
| `Agent.firedCount` | integer |  | Fired alerts count |
| `Agent.updateModuleCount` | integer |  | Update module count flag |
| `Agent.updateAlertCount` | integer |  | Update alert count flag |
| `Agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
| `Agent.alias` | string |  | Agent alias |
| `Agent.aliasAsName` | integer |  | Use alias as name flag |
| `Agent.safeModeModule` | integer |  | Safe mode module ID |
| `Agent.cps` | integer |  | CPS value |
| `Agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
| `Agent.satelliteServer` | integer |  | Satellite server ID |
| `Agent.fixedIp` | integer |  | Fixed IP flag |
| `Agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
| `Agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
| `Agent.ignoreUnknown` | integer |  | Ignore unknown flag |
| `Agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
| `Agent.autoHa` | integer |  | Auto HA flag |
| `Agent.extraData` | string |  | Extra data |
| `Agent.quietByDowntime` | integer |  | Quiet by downtime flag |
| `Agent.idFimPolicy` | integer |  | FIM Policy ID |
| `idAgentRmm` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in agent name field. |
| `status` | integer, nullable |  | Filter by RMM agent status (RMM_OK, RMM_ERROR, RMM_NO_STATUS). |
| `connection` | integer, nullable |  | Filter by connection: 0 connected, 1 disconnected. |
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
| `multipleSearch.field` | enum: `idAgentRmm`, `agentName`, `lastContact`, `interval`, `enabled`, `direccion`, `os`, `osVersion`, `comentarios` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAgentRmm`, `agentName`, `lastContact`, `interval`, `enabled`, `direccion`, `os`, `osVersion`, `comentarios` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "agentName": "string",
      "lastContact": 0,
      "interval": 30,
      "enabled": true,
      "idAgentRmm": null,
      "freeSearch": "string",
      "status": 0,
      "connection": 0,
      "requestedFields": [
        "idAgentRmm"
      ],
      "fieldConditions": [
        {
          "field": "idAgentRmm",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idAgentRmm",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAgentRmm",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM agent object

??? note "Response fields (70 fields)"

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
    | `data.[].idAgentRmm` | integer |  | Id RMM agent |
    | `data.[].agentName` | string |  | Name of the RMM agent |
    | `data.[].lastContact` | integer, nullable |  | RMM agent last contact utimestamp |
    | `data.[].interval` | integer, nullable |  | RMM agent contact interval |
    | `data.[].enabled` | boolean, nullable |  | Whether the RMM agent is enabled |
    | `data.[].status` | integer, nullable |  | RMM agent status |
    | `data.[].Agent` |  |  | Embedded normal agent |
    | `data.[].Agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
    | `data.[].Agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
    | `data.[].Agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
    | `data.[].Agent.name` | string |  | Agent name |
    | `data.[].Agent.address` | string, nullable |  | Agent address |
    | `data.[].Agent.comments` | string, nullable |  | Agent comments |
    | `data.[].Agent.idGroup` | integer |  | Group ID |
    | `data.[].Agent.lastContact` | string |  | Last contact timestamp |
    | `data.[].Agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
    | `data.[].Agent.interval` | integer |  | Agent interval in seconds |
    | `data.[].Agent.idOs` | integer, nullable |  | Operating System ID |
    | `data.[].Agent.osVersion` | string, nullable |  | Operating System version |
    | `data.[].Agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].Agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].Agent.agentVersion` | string, nullable |  | Agent version |
    | `data.[].Agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
    | `data.[].Agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
    | `data.[].Agent.remote` | integer |  | Remote agent flag |
    | `data.[].Agent.idParent` | integer, nullable |  | Parent agent ID |
    | `data.[].Agent.customId` | string, nullable |  | Custom agent ID |
    | `data.[].Agent.serverName` | string, nullable |  | Server name |
    | `data.[].Agent.cascadeProtection` | integer |  | Cascade protection flag |
    | `data.[].Agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
    | `data.[].Agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
    | `data.[].Agent.iconPath` | string, nullable |  | Icon path |
    | `data.[].Agent.updateGisData` | integer |  | Update GIS data flag |
    | `data.[].Agent.urlAddress` | string, nullable |  | URL address |
    | `data.[].Agent.quiet` | integer |  | Quiet flag |
    | `data.[].Agent.normalCount` | integer |  | Normal modules count |
    | `data.[].Agent.warningCount` | integer |  | Warning modules count |
    | `data.[].Agent.criticalCount` | integer |  | Critical modules count |
    | `data.[].Agent.unknownCount` | integer |  | Unknown modules count |
    | `data.[].Agent.notinitCount` | integer |  | Not init modules count |
    | `data.[].Agent.totalCount` | integer |  | Total modules count |
    | `data.[].Agent.firedCount` | integer |  | Fired alerts count |
    | `data.[].Agent.updateModuleCount` | integer |  | Update module count flag |
    | `data.[].Agent.updateAlertCount` | integer |  | Update alert count flag |
    | `data.[].Agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
    | `data.[].Agent.alias` | string |  | Agent alias |
    | `data.[].Agent.aliasAsName` | integer |  | Use alias as name flag |
    | `data.[].Agent.safeModeModule` | integer |  | Safe mode module ID |
    | `data.[].Agent.cps` | integer |  | CPS value |
    | `data.[].Agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
    | `data.[].Agent.satelliteServer` | integer |  | Satellite server ID |
    | `data.[].Agent.fixedIp` | integer |  | Fixed IP flag |
    | `data.[].Agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
    | `data.[].Agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
    | `data.[].Agent.ignoreUnknown` | integer |  | Ignore unknown flag |
    | `data.[].Agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
    | `data.[].Agent.autoHa` | integer |  | Auto HA flag |
    | `data.[].Agent.extraData` | string |  | Extra data |
    | `data.[].Agent.quietByDowntime` | integer |  | Quiet by downtime flag |
    | `data.[].Agent.idFimPolicy` | integer |  | FIM Policy ID |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/batch/{idBatchJob}/agent` { #post-rmm-batch-idbatchjob-agent }

Creates a new RMM batch agent relation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idBatchAgent` | integer |  | Id RMM batch agent |
| `idBatchJob` | integer |  | Id of the RMM batch job |
| `idAgentRmm` | integer | yes | Id of the RMM agent |
| `agent` | object |  | Normal agent linked to the RMM batch agent |
| `agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
| `agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
| `agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
| `agent.name` | string |  | Agent name |
| `agent.address` | string, nullable |  | Agent address |
| `agent.comments` | string, nullable |  | Agent comments |
| `agent.idGroup` | integer |  | Group ID |
| `agent.lastContact` | string |  | Last contact timestamp |
| `agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
| `agent.interval` | integer |  | Agent interval in seconds |
| `agent.idOs` | integer, nullable |  | Operating System ID |
| `agent.osVersion` | string, nullable |  | Operating System version |
| `agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
| `agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
| `agent.agentVersion` | string, nullable |  | Agent version |
| `agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
| `agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
| `agent.remote` | integer |  | Remote agent flag |
| `agent.idParent` | integer, nullable |  | Parent agent ID |
| `agent.customId` | string, nullable |  | Custom agent ID |
| `agent.serverName` | string, nullable |  | Server name |
| `agent.cascadeProtection` | integer |  | Cascade protection flag |
| `agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
| `agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
| `agent.iconPath` | string, nullable |  | Icon path |
| `agent.updateGisData` | integer |  | Update GIS data flag |
| `agent.urlAddress` | string, nullable |  | URL address |
| `agent.quiet` | integer |  | Quiet flag |
| `agent.normalCount` | integer |  | Normal modules count |
| `agent.warningCount` | integer |  | Warning modules count |
| `agent.criticalCount` | integer |  | Critical modules count |
| `agent.unknownCount` | integer |  | Unknown modules count |
| `agent.notinitCount` | integer |  | Not init modules count |
| `agent.totalCount` | integer |  | Total modules count |
| `agent.firedCount` | integer |  | Fired alerts count |
| `agent.updateModuleCount` | integer |  | Update module count flag |
| `agent.updateAlertCount` | integer |  | Update alert count flag |
| `agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
| `agent.alias` | string |  | Agent alias |
| `agent.aliasAsName` | integer |  | Use alias as name flag |
| `agent.safeModeModule` | integer |  | Safe mode module ID |
| `agent.cps` | integer |  | CPS value |
| `agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
| `agent.satelliteServer` | integer |  | Satellite server ID |
| `agent.fixedIp` | integer |  | Fixed IP flag |
| `agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
| `agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
| `agent.ignoreUnknown` | integer |  | Ignore unknown flag |
| `agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
| `agent.autoHa` | integer |  | Auto HA flag |
| `agent.extraData` | string |  | Extra data |
| `agent.quietByDowntime` | integer |  | Quiet by downtime flag |
| `agent.idFimPolicy` | integer |  | FIM Policy ID |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idBatchJob": 0,
      "idAgentRmm": 0
    }
    ```

**Response 200**: RMM batch agent object

Schema: [`RmmBatchAgent`](#model-rmmbatchagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/batch/{idBatchJob}/agent/{idBatchAgent}` { #get-rmm-batch-idbatchjob-agent-idbatchagent }

Show RMM batch agent relation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `idBatchAgent` | path | integer | yes | RMM batch agent id |

**Response 200**: RMM batch agent object

Schema: [`RmmBatchAgent`](#model-rmmbatchagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/rmm/batch/{idBatchJob}/agent/{idBatchAgent}` { #delete-rmm-batch-idbatchjob-agent-idbatchagent }

Deletes an RMM batch agent relation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `idBatchAgent` | path | integer | yes | RMM batch agent id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/batch/{idBatchJob}/agent/list` { #get-rmm-batch-idbatchjob-agent-list }

List RMM batch agent relations

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM batch agent object

??? note "Response fields (67 fields)"

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
    | `data.[].idBatchAgent` | integer |  | Id RMM batch agent |
    | `data.[].idBatchJob` | integer |  | Id of the RMM batch job |
    | `data.[].idAgentRmm` | integer |  | Id of the RMM agent |
    | `data.[].agent` | object |  | Normal agent linked to the RMM batch agent |
    | `data.[].agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
    | `data.[].agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
    | `data.[].agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
    | `data.[].agent.name` | string |  | Agent name |
    | `data.[].agent.address` | string, nullable |  | Agent address |
    | `data.[].agent.comments` | string, nullable |  | Agent comments |
    | `data.[].agent.idGroup` | integer |  | Group ID |
    | `data.[].agent.lastContact` | string |  | Last contact timestamp |
    | `data.[].agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
    | `data.[].agent.interval` | integer |  | Agent interval in seconds |
    | `data.[].agent.idOs` | integer, nullable |  | Operating System ID |
    | `data.[].agent.osVersion` | string, nullable |  | Operating System version |
    | `data.[].agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].agent.agentVersion` | string, nullable |  | Agent version |
    | `data.[].agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
    | `data.[].agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
    | `data.[].agent.remote` | integer |  | Remote agent flag |
    | `data.[].agent.idParent` | integer, nullable |  | Parent agent ID |
    | `data.[].agent.customId` | string, nullable |  | Custom agent ID |
    | `data.[].agent.serverName` | string, nullable |  | Server name |
    | `data.[].agent.cascadeProtection` | integer |  | Cascade protection flag |
    | `data.[].agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
    | `data.[].agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
    | `data.[].agent.iconPath` | string, nullable |  | Icon path |
    | `data.[].agent.updateGisData` | integer |  | Update GIS data flag |
    | `data.[].agent.urlAddress` | string, nullable |  | URL address |
    | `data.[].agent.quiet` | integer |  | Quiet flag |
    | `data.[].agent.normalCount` | integer |  | Normal modules count |
    | `data.[].agent.warningCount` | integer |  | Warning modules count |
    | `data.[].agent.criticalCount` | integer |  | Critical modules count |
    | `data.[].agent.unknownCount` | integer |  | Unknown modules count |
    | `data.[].agent.notinitCount` | integer |  | Not init modules count |
    | `data.[].agent.totalCount` | integer |  | Total modules count |
    | `data.[].agent.firedCount` | integer |  | Fired alerts count |
    | `data.[].agent.updateModuleCount` | integer |  | Update module count flag |
    | `data.[].agent.updateAlertCount` | integer |  | Update alert count flag |
    | `data.[].agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
    | `data.[].agent.alias` | string |  | Agent alias |
    | `data.[].agent.aliasAsName` | integer |  | Use alias as name flag |
    | `data.[].agent.safeModeModule` | integer |  | Safe mode module ID |
    | `data.[].agent.cps` | integer |  | CPS value |
    | `data.[].agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
    | `data.[].agent.satelliteServer` | integer |  | Satellite server ID |
    | `data.[].agent.fixedIp` | integer |  | Fixed IP flag |
    | `data.[].agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
    | `data.[].agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
    | `data.[].agent.ignoreUnknown` | integer |  | Ignore unknown flag |
    | `data.[].agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
    | `data.[].agent.autoHa` | integer |  | Auto HA flag |
    | `data.[].agent.extraData` | string |  | Extra data |
    | `data.[].agent.quietByDowntime` | integer |  | Quiet by downtime flag |
    | `data.[].agent.idFimPolicy` | integer |  | FIM Policy ID |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/batch/{idBatchJob}/agent/list` { #post-rmm-batch-idbatchjob-agent-list }

List RMM batch agent relations

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idBatchAgent` | integer |  | Id RMM batch agent |
| `idBatchJob` | integer |  | Id of the RMM batch job |
| `idAgentRmm` | integer |  | Id of the RMM agent |
| `agent` | object |  | Normal agent linked to the RMM batch agent |
| `agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
| `agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
| `agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
| `agent.name` | string |  | Agent name |
| `agent.address` | string, nullable |  | Agent address |
| `agent.comments` | string, nullable |  | Agent comments |
| `agent.idGroup` | integer |  | Group ID |
| `agent.lastContact` | string |  | Last contact timestamp |
| `agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
| `agent.interval` | integer |  | Agent interval in seconds |
| `agent.idOs` | integer, nullable |  | Operating System ID |
| `agent.osVersion` | string, nullable |  | Operating System version |
| `agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
| `agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
| `agent.agentVersion` | string, nullable |  | Agent version |
| `agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
| `agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
| `agent.remote` | integer |  | Remote agent flag |
| `agent.idParent` | integer, nullable |  | Parent agent ID |
| `agent.customId` | string, nullable |  | Custom agent ID |
| `agent.serverName` | string, nullable |  | Server name |
| `agent.cascadeProtection` | integer |  | Cascade protection flag |
| `agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
| `agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
| `agent.iconPath` | string, nullable |  | Icon path |
| `agent.updateGisData` | integer |  | Update GIS data flag |
| `agent.urlAddress` | string, nullable |  | URL address |
| `agent.quiet` | integer |  | Quiet flag |
| `agent.normalCount` | integer |  | Normal modules count |
| `agent.warningCount` | integer |  | Warning modules count |
| `agent.criticalCount` | integer |  | Critical modules count |
| `agent.unknownCount` | integer |  | Unknown modules count |
| `agent.notinitCount` | integer |  | Not init modules count |
| `agent.totalCount` | integer |  | Total modules count |
| `agent.firedCount` | integer |  | Fired alerts count |
| `agent.updateModuleCount` | integer |  | Update module count flag |
| `agent.updateAlertCount` | integer |  | Update alert count flag |
| `agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
| `agent.alias` | string |  | Agent alias |
| `agent.aliasAsName` | integer |  | Use alias as name flag |
| `agent.safeModeModule` | integer |  | Safe mode module ID |
| `agent.cps` | integer |  | CPS value |
| `agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
| `agent.satelliteServer` | integer |  | Satellite server ID |
| `agent.fixedIp` | integer |  | Fixed IP flag |
| `agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
| `agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
| `agent.ignoreUnknown` | integer |  | Ignore unknown flag |
| `agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
| `agent.autoHa` | integer |  | Auto HA flag |
| `agent.extraData` | string |  | Extra data |
| `agent.quietByDowntime` | integer |  | Quiet by downtime flag |
| `agent.idFimPolicy` | integer |  | FIM Policy ID |
| `idBatchAgent` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in agent name field. |
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
| `multipleSearch.field` | enum: `id`, `idBatchAgent`, `idBatchJob`, `idAgentRmm` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `idBatchAgent`, `idBatchJob`, `idAgentRmm` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idBatchJob": 0,
      "idAgentRmm": 0,
      "idBatchAgent": null,
      "freeSearch": "string",
      "requestedFields": [
        "id"
      ],
      "fieldConditions": [
        {
          "field": "id",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "id",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "id",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM batch agent object

??? note "Response fields (67 fields)"

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
    | `data.[].idBatchAgent` | integer |  | Id RMM batch agent |
    | `data.[].idBatchJob` | integer |  | Id of the RMM batch job |
    | `data.[].idAgentRmm` | integer |  | Id of the RMM agent |
    | `data.[].agent` | object |  | Normal agent linked to the RMM batch agent |
    | `data.[].agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
    | `data.[].agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
    | `data.[].agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
    | `data.[].agent.name` | string |  | Agent name |
    | `data.[].agent.address` | string, nullable |  | Agent address |
    | `data.[].agent.comments` | string, nullable |  | Agent comments |
    | `data.[].agent.idGroup` | integer |  | Group ID |
    | `data.[].agent.lastContact` | string |  | Last contact timestamp |
    | `data.[].agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
    | `data.[].agent.interval` | integer |  | Agent interval in seconds |
    | `data.[].agent.idOs` | integer, nullable |  | Operating System ID |
    | `data.[].agent.osVersion` | string, nullable |  | Operating System version |
    | `data.[].agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].agent.agentVersion` | string, nullable |  | Agent version |
    | `data.[].agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
    | `data.[].agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
    | `data.[].agent.remote` | integer |  | Remote agent flag |
    | `data.[].agent.idParent` | integer, nullable |  | Parent agent ID |
    | `data.[].agent.customId` | string, nullable |  | Custom agent ID |
    | `data.[].agent.serverName` | string, nullable |  | Server name |
    | `data.[].agent.cascadeProtection` | integer |  | Cascade protection flag |
    | `data.[].agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
    | `data.[].agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
    | `data.[].agent.iconPath` | string, nullable |  | Icon path |
    | `data.[].agent.updateGisData` | integer |  | Update GIS data flag |
    | `data.[].agent.urlAddress` | string, nullable |  | URL address |
    | `data.[].agent.quiet` | integer |  | Quiet flag |
    | `data.[].agent.normalCount` | integer |  | Normal modules count |
    | `data.[].agent.warningCount` | integer |  | Warning modules count |
    | `data.[].agent.criticalCount` | integer |  | Critical modules count |
    | `data.[].agent.unknownCount` | integer |  | Unknown modules count |
    | `data.[].agent.notinitCount` | integer |  | Not init modules count |
    | `data.[].agent.totalCount` | integer |  | Total modules count |
    | `data.[].agent.firedCount` | integer |  | Fired alerts count |
    | `data.[].agent.updateModuleCount` | integer |  | Update module count flag |
    | `data.[].agent.updateAlertCount` | integer |  | Update alert count flag |
    | `data.[].agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
    | `data.[].agent.alias` | string |  | Agent alias |
    | `data.[].agent.aliasAsName` | integer |  | Use alias as name flag |
    | `data.[].agent.safeModeModule` | integer |  | Safe mode module ID |
    | `data.[].agent.cps` | integer |  | CPS value |
    | `data.[].agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
    | `data.[].agent.satelliteServer` | integer |  | Satellite server ID |
    | `data.[].agent.fixedIp` | integer |  | Fixed IP flag |
    | `data.[].agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
    | `data.[].agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
    | `data.[].agent.ignoreUnknown` | integer |  | Ignore unknown flag |
    | `data.[].agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
    | `data.[].agent.autoHa` | integer |  | Auto HA flag |
    | `data.[].agent.extraData` | string |  | Extra data |
    | `data.[].agent.quietByDowntime` | integer |  | Quiet by downtime flag |
    | `data.[].agent.idFimPolicy` | integer |  | FIM Policy ID |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/batch` { #post-rmm-batch }

Creates a new RMM batch job

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idBatchJob` | integer |  | Id RMM batch job |
| `name` | string | yes | Name of the RMM batch job |
| `description` | string, nullable |  | Description of the RMM batch job |
| `idGroup` | integer, nullable |  | Group id of the RMM batch job |
| `lastExecutionUtimestamp` | integer, nullable |  | Timestamp of the last execution of the RMM batch job |
| `numAgents` | integer, nullable |  | Total number of RMM agents associated to the RMM batch job |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0
    }
    ```

**Response 200**: RMM batch job object

Schema: [`RmmBatchJob`](#model-rmmbatchjob)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/batch/{idBatchJob}` { #get-rmm-batch-idbatchjob }

Show RMM batch job

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |

**Response 200**: RMM batch job object

Schema: [`RmmBatchJob`](#model-rmmbatchjob)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/rmm/batch/{idBatchJob}` { #put-rmm-batch-idbatchjob }

Updates an RMM batch job

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |

**Request body** (`application/json`): [`RmmBatchJob`](#model-rmmbatchjob)

**Response 200**: RMM batch job object

Schema: [`RmmBatchJob`](#model-rmmbatchjob)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/rmm/batch/{idBatchJob}` { #delete-rmm-batch-idbatchjob }

Deletes an RMM batch job

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/batch/list` { #get-rmm-batch-list }

List RMM batch jobs

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM batch job object

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
    | `data.[].idBatchJob` | integer |  | Id RMM batch job |
    | `data.[].name` | string |  | Name of the RMM batch job |
    | `data.[].description` | string, nullable |  | Description of the RMM batch job |
    | `data.[].idGroup` | integer, nullable |  | Group id of the RMM batch job |
    | `data.[].lastExecutionUtimestamp` | integer, nullable |  | Timestamp of the last execution of the RMM batch job |
    | `data.[].numAgents` | integer, nullable |  | Total number of RMM agents associated to the RMM batch job |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/batch/list` { #post-rmm-batch-list }

List RMM batch jobs

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
| `idBatchJob` | integer |  | Id RMM batch job |
| `name` | string |  | Name of the RMM batch job |
| `description` | string, nullable |  | Description of the RMM batch job |
| `idGroup` | integer, nullable |  | Group id of the RMM batch job |
| `lastExecutionUtimestamp` | integer, nullable |  | Timestamp of the last execution of the RMM batch job |
| `numAgents` | integer, nullable |  | Total number of RMM agents associated to the RMM batch job |
| `idBatchJob` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in name and description fields. |
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
| `multipleSearch.field` | enum: `id`, `idBatchJob`, `name`, `description`, `idGroup`, `lastExecutionUtimestamp` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `idBatchJob`, `name`, `description`, `idGroup`, `lastExecutionUtimestamp` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "idBatchJob": null,
      "freeSearch": "string",
      "requestedFields": [
        "id"
      ],
      "fieldConditions": [
        {
          "field": "id",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "id",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "id",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM batch job object

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
    | `data.[].idBatchJob` | integer |  | Id RMM batch job |
    | `data.[].name` | string |  | Name of the RMM batch job |
    | `data.[].description` | string, nullable |  | Description of the RMM batch job |
    | `data.[].idGroup` | integer, nullable |  | Group id of the RMM batch job |
    | `data.[].lastExecutionUtimestamp` | integer, nullable |  | Timestamp of the last execution of the RMM batch job |
    | `data.[].numAgents` | integer, nullable |  | Total number of RMM agents associated to the RMM batch job |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/batch/{idBatchJob}/queue` { #post-rmm-batch-idbatchjob-queue }

Creates a new RMM batch queue entry

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |

**Request body** (`application/json`): [`RmmBatchQueue`](#model-rmmbatchqueue)

**Response 200**: RMM batch queue object

Schema: [`RmmBatchQueue`](#model-rmmbatchqueue)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/batch/{idBatchJob}/queue/{idBatchQueue}` { #get-rmm-batch-idbatchjob-queue-idbatchqueue }

Show RMM batch queue entry

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `idBatchQueue` | path | integer | yes | RMM batch queue id |

**Response 200**: RMM batch queue object

Schema: [`RmmBatchQueue`](#model-rmmbatchqueue)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/rmm/batch/{idBatchJob}/queue/{idBatchQueue}` { #put-rmm-batch-idbatchjob-queue-idbatchqueue }

Updates an RMM batch queue entry

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `idBatchQueue` | path | integer | yes | RMM batch queue id |

**Request body** (`application/json`): [`RmmBatchQueue`](#model-rmmbatchqueue)

**Response 200**: RMM batch queue object

Schema: [`RmmBatchQueue`](#model-rmmbatchqueue)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/rmm/batch/{idBatchJob}/queue/{idBatchQueue}` { #delete-rmm-batch-idbatchjob-queue-idbatchqueue }

Deletes an RMM batch queue entry

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `idBatchQueue` | path | integer | yes | RMM batch queue id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/batch/{idBatchJob}/queue/{idBatchQueue}/execute` { #post-rmm-batch-idbatchjob-queue-idbatchqueue-execute }

Executes an RMM batch queue entry over the batch job agents

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `idBatchQueue` | path | integer | yes | RMM batch queue id |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `id_agents_rmm` | array of integer |  | Optional list of RMM agent ids to execute. If empty, the agents assigned to the batch job are used. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "id_agents_rmm": [
        0
      ]
    }
    ```

**Response 200**: RMM batch job execution started

??? note "Response fields (2 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `success` | boolean |  |  |
    | `message` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/batch/{idBatchJob}/queue/list` { #get-rmm-batch-idbatchjob-queue-list }

List RMM batch queue entries

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM batch queue object

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
    | `data.[].idBatchQueue` | integer |  | Id RMM batch queue |
    | `data.[].idBatchJob` | integer |  | Id of the RMM batch job |
    | `data.[].progress` | array, nullable |  | Progress of the RMM batch queue |
    | `data.[].error` | string, nullable |  | Error message of the RMM batch queue |
    | `data.[].status` | enum: `pending`, `running`, `failed` |  | Status of the RMM batch queue |
    | `data.[].queueUtimestamp` | integer, nullable |  | Timestamp when the RMM batch queue was created |
    | `data.[].dataUtimestamp` | integer, nullable |  | Timestamp when the RMM batch queue was last updated |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/batch/{idBatchJob}/queue/list` { #post-rmm-batch-idbatchjob-queue-list }

List RMM batch queue entries

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idBatchQueue` | integer |  | Id RMM batch queue |
| `idBatchJob` | integer |  | Id of the RMM batch job |
| `progress` | array, nullable |  | Progress of the RMM batch queue |
| `error` | string, nullable |  | Error message of the RMM batch queue |
| `status` | enum: `pending`, `running`, `failed` |  | Status of the RMM batch queue |
| `queueUtimestamp` | integer, nullable |  | Timestamp when the RMM batch queue was created |
| `dataUtimestamp` | integer, nullable |  | Timestamp when the RMM batch queue was last updated |
| `idBatchQueue` |  |  |  |
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
| `multipleSearch.field` | enum: `id`, `idBatchQueue`, `idBatchJob`, `progress`, `error`, `status`, `queueUtimestamp`, `dataUtimestamp` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `idBatchQueue`, `idBatchJob`, `progress`, `error`, `status`, `queueUtimestamp`, `dataUtimestamp` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idBatchJob": 0,
      "progress": [],
      "error": "string",
      "queueUtimestamp": 0,
      "dataUtimestamp": 0,
      "idBatchQueue": null,
      "requestedFields": [
        "id"
      ],
      "fieldConditions": [
        {
          "field": "id",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "id",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "id",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM batch queue object

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
    | `data.[].idBatchQueue` | integer |  | Id RMM batch queue |
    | `data.[].idBatchJob` | integer |  | Id of the RMM batch job |
    | `data.[].progress` | array, nullable |  | Progress of the RMM batch queue |
    | `data.[].error` | string, nullable |  | Error message of the RMM batch queue |
    | `data.[].status` | enum: `pending`, `running`, `failed` |  | Status of the RMM batch queue |
    | `data.[].queueUtimestamp` | integer, nullable |  | Timestamp when the RMM batch queue was created |
    | `data.[].dataUtimestamp` | integer, nullable |  | Timestamp when the RMM batch queue was last updated |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/batch/{idBatchJob}/rule` { #post-rmm-batch-idbatchjob-rule }

Creates a new RMM batch rule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idBatchRule` | integer |  | Id RMM batch rule |
| `idBatchJob` | integer |  | Id of the RMM batch job |
| `idScriptRmm` | integer | yes | Id of the RMM script |
| `name` | string | yes | Name of the RMM batch rule |
| `inputs` | array, nullable |  | Inputs of the RMM batch rule |
| `script` | string, nullable |  | Name of the RMM script |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idBatchJob": 0,
      "idScriptRmm": 0,
      "name": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "tip": "string",
          "value": "string",
          "file_name": "string"
        }
      ]
    }
    ```

**Response 200**: RMM batch rule object

Schema: [`RmmBatchRule`](#model-rmmbatchrule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/batch/{idBatchJob}/rule/{idBatchRule}` { #get-rmm-batch-idbatchjob-rule-idbatchrule }

Show RMM batch rule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `idBatchRule` | path | integer | yes | RMM batch rule id |

**Response 200**: RMM batch rule object

Schema: [`RmmBatchRule`](#model-rmmbatchrule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/rmm/batch/{idBatchJob}/rule/{idBatchRule}` { #put-rmm-batch-idbatchjob-rule-idbatchrule }

Updates an RMM batch rule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `idBatchRule` | path | integer | yes | RMM batch rule id |

**Request body** (`application/json`): [`RmmBatchRule`](#model-rmmbatchrule)

**Response 200**: RMM batch rule object

Schema: [`RmmBatchRule`](#model-rmmbatchrule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/rmm/batch/{idBatchJob}/rule/{idBatchRule}` { #delete-rmm-batch-idbatchjob-rule-idbatchrule }

Deletes an RMM batch rule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `idBatchRule` | path | integer | yes | RMM batch rule id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/batch/{idBatchJob}/rule/list` { #get-rmm-batch-idbatchjob-rule-list }

List RMM batch rules

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM batch rule object

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
    | `data.[].idBatchRule` | integer |  | Id RMM batch rule |
    | `data.[].idBatchJob` | integer |  | Id of the RMM batch job |
    | `data.[].idScriptRmm` | integer |  | Id of the RMM script |
    | `data.[].name` | string |  | Name of the RMM batch rule |
    | `data.[].inputs` | array, nullable |  | Inputs of the RMM batch rule |
    | `data.[].script` | string, nullable |  | Name of the RMM script |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/batch/{idBatchJob}/rule/list` { #post-rmm-batch-idbatchjob-rule-list }

List RMM batch rules

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idBatchJob` | path | integer | yes | RMM batch job id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idBatchRule` | integer |  | Id RMM batch rule |
| `idBatchJob` | integer |  | Id of the RMM batch job |
| `idScriptRmm` | integer |  | Id of the RMM script |
| `name` | string |  | Name of the RMM batch rule |
| `inputs` | array, nullable |  | Inputs of the RMM batch rule |
| `script` | string, nullable |  | Name of the RMM script |
| `idBatchRule` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in name field. |
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
| `multipleSearch.field` | enum: `id`, `idBatchRule`, `idBatchJob`, `idScriptRmm`, `name`, `inputs`, `script` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `idBatchRule`, `idBatchJob`, `idScriptRmm`, `name`, `inputs`, `script` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idBatchJob": 0,
      "idScriptRmm": 0,
      "name": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "tip": "string",
          "value": "string",
          "file_name": "string"
        }
      ],
      "idBatchRule": null,
      "freeSearch": "string",
      "requestedFields": [
        "id"
      ],
      "fieldConditions": [
        {
          "field": "id",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "id",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "id",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM batch rule object

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
    | `data.[].idBatchRule` | integer |  | Id RMM batch rule |
    | `data.[].idBatchJob` | integer |  | Id of the RMM batch job |
    | `data.[].idScriptRmm` | integer |  | Id of the RMM script |
    | `data.[].name` | string |  | Name of the RMM batch rule |
    | `data.[].inputs` | array, nullable |  | Inputs of the RMM batch rule |
    | `data.[].script` | string, nullable |  | Name of the RMM script |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/pendingSoftware/agentsWithPending/list` { #post-rmm-pendingsoftware-agentswithpending-list }

List RMM agents that have pending software updates

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`): [`RmmPendingSoftwareFilter`](#model-rmmpendingsoftwarefilter)

**Response 200**: List of RMM agents with pending software

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
    | `data.[].idAgente` | integer, nullable |  | Represents one tagent_extended_data row of category "software" joined with its RMM agent. The "data" JSON is decoded into the "packages" array. |
    | `data.[].idAgentRmm` | integer, nullable |  |  |
    | `data.[].agentName` | string, nullable |  |  |
    | `data.[].agentAlias` | string, nullable |  |  |
    | `data.[].idGroup` | integer, nullable |  |  |
    | `data.[].idOs` | integer, nullable |  |  |
    | `data.[].timestamp` | integer, nullable |  |  |
    | `data.[].packages` | array, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/pendingSoftware/list` { #get-rmm-pendingsoftware-list }

List pending software updates of the RMM agents

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List pending software objects

??? note "Response fields (22 fields)"

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
    | `data.[].idAgente` | integer, nullable |  | One pending software update of an RMM agent. |
    | `data.[].idAgentRmm` | integer, nullable |  |  |
    | `data.[].agentName` | string, nullable |  |  |
    | `data.[].idGroup` | integer, nullable |  |  |
    | `data.[].idOs` | integer, nullable |  |  |
    | `data.[].name` | string, nullable |  |  |
    | `data.[].currentVersion` | string, nullable |  |  |
    | `data.[].availableVersion` | string, nullable |  |  |
    | `data.[].manager` | string, nullable |  |  |
    | `data.[].uniqueId` | string, nullable |  |  |
    | `data.[].timestamp` | integer, nullable |  |  |
    | `data.[].isUpdatable` | boolean, nullable |  | Whether the allow/deny policy allows updating this package |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/pendingSoftware/list` { #post-rmm-pendingsoftware-list }

List pending software updates of the RMM agents

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`): [`RmmPendingSoftwareFilter`](#model-rmmpendingsoftwarefilter)

**Response 200**: List pending software objects

??? note "Response fields (22 fields)"

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
    | `data.[].idAgente` | integer, nullable |  | One pending software update of an RMM agent. |
    | `data.[].idAgentRmm` | integer, nullable |  |  |
    | `data.[].agentName` | string, nullable |  |  |
    | `data.[].idGroup` | integer, nullable |  |  |
    | `data.[].idOs` | integer, nullable |  |  |
    | `data.[].name` | string, nullable |  |  |
    | `data.[].currentVersion` | string, nullable |  |  |
    | `data.[].availableVersion` | string, nullable |  |  |
    | `data.[].manager` | string, nullable |  |  |
    | `data.[].uniqueId` | string, nullable |  |  |
    | `data.[].timestamp` | integer, nullable |  |  |
    | `data.[].isUpdatable` | boolean, nullable |  | Whether the allow/deny policy allows updating this package |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/queue/{id}` { #get-rmm-queue-id }

Show RMM queue

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | RMM queue id |

**Response 200**: RMM queue object

Schema: [`RmmQueue`](#model-rmmqueue)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/rmm/queue/{id}` { #delete-rmm-queue-id }

Deletes an RMM queue object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | RMM queue id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/queue/list` { #get-rmm-queue-list }

List RMM queues

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM queue object

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
    | `data.[].id` | integer |  | Id RMM queue |
    | `data.[].idAgentRmm` | integer, nullable |  | Id RMM agent |
    | `data.[].idScriptRmm` | integer, nullable |  | Id RMM script |
    | `data.[].name` | string |  | Name of the RMM queue |
    | `data.[].step` | string, nullable |  | Step of the RMM queue |
    | `data.[].status` | integer, nullable |  | Status of the RMM queue |
    | `data.[].output` | string, nullable |  | Output of the RMM queue |
    | `data.[].error` | string, nullable |  | Error of the RMM queue |
    | `data.[].queueUtimestamp` | integer, nullable |  | Queue utimestamp |
    | `data.[].dataUtimestamp` | integer, nullable |  | Data utimestamp |
    | `data.[].valuesInputs` | array, nullable |  | Values inputs of the RMM queue |
    | `data.[].script` | string, nullable |  | Script name (trmm_scripts.name) |
    | `data.[].alias` | string, nullable |  | Agent alias (tagente.alias) — legacy nombre |
    | `data.[].agentName` | string, nullable |  | Agent name (trmm_agents.agent_name) — legacy nombre_rmm |
    | `data.[].nombre` | string, nullable |  | Alias of the linked agent (legacy alias of tagente.alias) |
    | `data.[].nombre_rmm` | string, nullable |  | RMM agent name (legacy alias of trmm_agents.agent_name) |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/queue/list` { #post-rmm-queue-list }

List RMM queues

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
| `id` | integer |  | Id RMM queue |
| `idAgentRmm` | integer, nullable |  | Id RMM agent |
| `idScriptRmm` | integer, nullable |  | Id RMM script |
| `name` | string |  | Name of the RMM queue |
| `step` | string, nullable |  | Step of the RMM queue |
| `status` | integer, nullable |  | Status of the RMM queue |
| `output` | string, nullable |  | Output of the RMM queue |
| `error` | string, nullable |  | Error of the RMM queue |
| `queueUtimestamp` | integer, nullable |  | Queue utimestamp |
| `dataUtimestamp` | integer, nullable |  | Data utimestamp |
| `valuesInputs` | array, nullable |  | Values inputs of the RMM queue |
| `script` | string, nullable |  | Script name (trmm_scripts.name) |
| `alias` | string, nullable |  | Agent alias (tagente.alias) — legacy nombre |
| `agentName` | string, nullable |  | Agent name (trmm_agents.agent_name) — legacy nombre_rmm |
| `nombre` | string, nullable |  | Alias of the linked agent (legacy alias of tagente.alias) |
| `nombre_rmm` | string, nullable |  | RMM agent name (legacy alias of trmm_agents.agent_name) |
| `id` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in name, step, output and error fields. |
| `groupIds` | string, nullable |  | Comma separated group ids to filter by agent group. |
| `dateInit` | integer, nullable |  | Minimum queue utimestamp. |
| `dateEnd` | integer, nullable |  | Maximum queue utimestamp. |
| `dateInitExec` | integer, nullable |  | Minimum data (execution) utimestamp. |
| `dateEndExec` | integer, nullable |  | Maximum data (execution) utimestamp. |
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
| `multipleSearch.field` | enum: `id`, `idAgentRmm`, `id_agent_rmm`, `idScriptRmm`, `id_script_rmm`, `name`, `queue_name`, `step`, `status`, `output`, `error`, `queueUtimestamp`, `queue_utimestamp`, `dataUtimestamp`, `data_utimestamp`, `valuesInputs`, `script`, `alias`, `nombre`, `agentName`, `nombre_rmm`, `agent_name` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `idAgentRmm`, `id_agent_rmm`, `idScriptRmm`, `id_script_rmm`, `name`, `queue_name`, `step`, `status`, `output`, `error`, `queueUtimestamp`, `queue_utimestamp`, `dataUtimestamp`, `data_utimestamp`, `valuesInputs`, `script`, `alias`, `nombre`, `agentName`, `nombre_rmm`, `agent_name` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgentRmm": 0,
      "idScriptRmm": 0,
      "name": "string",
      "step": "string",
      "status": 0,
      "output": "string",
      "error": "string",
      "queueUtimestamp": 0,
      "dataUtimestamp": 0,
      "valuesInputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "value": "string",
          "file_name": "string"
        }
      ],
      "id": null,
      "freeSearch": "string",
      "groupIds": "string",
      "dateInit": 0,
      "dateEnd": 0,
      "dateInitExec": 0,
      "dateEndExec": 0,
      "requestedFields": [
        "id"
      ],
      "fieldConditions": [
        {
          "field": "id",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "id",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "id",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM queue object

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
    | `data.[].id` | integer |  | Id RMM queue |
    | `data.[].idAgentRmm` | integer, nullable |  | Id RMM agent |
    | `data.[].idScriptRmm` | integer, nullable |  | Id RMM script |
    | `data.[].name` | string |  | Name of the RMM queue |
    | `data.[].step` | string, nullable |  | Step of the RMM queue |
    | `data.[].status` | integer, nullable |  | Status of the RMM queue |
    | `data.[].output` | string, nullable |  | Output of the RMM queue |
    | `data.[].error` | string, nullable |  | Error of the RMM queue |
    | `data.[].queueUtimestamp` | integer, nullable |  | Queue utimestamp |
    | `data.[].dataUtimestamp` | integer, nullable |  | Data utimestamp |
    | `data.[].valuesInputs` | array, nullable |  | Values inputs of the RMM queue |
    | `data.[].script` | string, nullable |  | Script name (trmm_scripts.name) |
    | `data.[].alias` | string, nullable |  | Agent alias (tagente.alias) — legacy nombre |
    | `data.[].agentName` | string, nullable |  | Agent name (trmm_agents.agent_name) — legacy nombre_rmm |
    | `data.[].nombre` | string, nullable |  | Alias of the linked agent (legacy alias of tagente.alias) |
    | `data.[].nombre_rmm` | string, nullable |  | RMM agent name (legacy alias of trmm_agents.agent_name) |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/resource` { #post-rmm-resource }

Creates a new RMM resource

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `shortName` | query | string | yes | Alphanumeric short name of the resource |

**Request body** (`multipart/form-data`)

| Field | Type | Required | Description |
|---|---|---|---|
| `file` | string (binary) | yes | Resource file |
| `name` | string | yes | Version label |

**Response 200**: RMM resource object

Schema: [`RmmResource`](#model-rmmresource)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/resource/{idResource}` { #get-rmm-resource-idresource }

Show RMM resource

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idResource` | path | integer | yes | RMM resource id |

**Response 200**: RMM resource object

Schema: [`RmmResource`](#model-rmmresource)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/rmm/resource/{idResource}` { #delete-rmm-resource-idresource }

Deletes an RMM resource object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idResource` | path | integer | yes | RMM resource id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/resource/exist/{shortName}` { #get-rmm-resource-exist-shortname }

Checks if an RMM resource short name exists

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `shortName` | path | string | yes | RMM resource short name |

**Response 200**: Exist result

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `exist` | boolean |  | True if the short name exists |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/resource/list` { #get-rmm-resource-list }

List RMM resources

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM resource object

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
    | `data.[].idResource` | integer |  | Id RMM resource |
    | `data.[].shortName` | string |  | Short name of the RMM resource |
    | `data.[].realName` | string |  | Real name of the RMM resource |
    | `data.[].createdDate` | integer |  | Creation date of the RMM resource |
    | `data.[].version` | integer |  | Latest version number of the RMM resource |
    | `data.[].versionsCount` | integer |  | Total number of versions of the RMM resource |
    | `data.[].versionName` | string |  | User friendly label of the latest RMM resource version |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/resource/list` { #post-rmm-resource-list }

List RMM resources

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
| `idResource` | integer |  | Id RMM resource |
| `shortName` | string |  | Short name of the RMM resource |
| `realName` | string |  | Real name of the RMM resource |
| `createdDate` | integer |  | Creation date of the RMM resource |
| `version` | integer |  | Latest version number of the RMM resource |
| `versionsCount` | integer |  | Total number of versions of the RMM resource |
| `versionName` | string |  | User friendly label of the latest RMM resource version |
| `idResource` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in short name and real name fields. |
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
| `multipleSearch.field` | enum: `idResource`, `shortName`, `realName`, `createdDate` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idResource`, `shortName`, `realName`, `createdDate` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "shortName": "string",
      "realName": "string",
      "idResource": null,
      "freeSearch": "string",
      "requestedFields": [
        "idResource"
      ],
      "fieldConditions": [
        {
          "field": "idResource",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idResource",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idResource",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM resource object

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
    | `data.[].idResource` | integer |  | Id RMM resource |
    | `data.[].shortName` | string |  | Short name of the RMM resource |
    | `data.[].realName` | string |  | Real name of the RMM resource |
    | `data.[].createdDate` | integer |  | Creation date of the RMM resource |
    | `data.[].version` | integer |  | Latest version number of the RMM resource |
    | `data.[].versionsCount` | integer |  | Total number of versions of the RMM resource |
    | `data.[].versionName` | string |  | User friendly label of the latest RMM resource version |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/resource/{idResource}/version` { #post-rmm-resource-idresource-version }

Creates a new version of an RMM resource

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idResource` | path | integer | yes | RMM resource id |

**Request body** (`multipart/form-data`)

| Field | Type | Required | Description |
|---|---|---|---|
| `file` | string (binary) | yes | Resource version file |
| `name` | string | yes | Version label |

**Response 200**: RMM resource version object

Schema: [`RmmResourceVersion`](#model-rmmresourceversion)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/resource/{idResource}/version/{version}` { #get-rmm-resource-idresource-version-version }

Show RMM resource version

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idResource` | path | integer | yes | RMM resource id |
| `version` | path | integer | yes | RMM resource version number |

**Response 200**: RMM resource version object

Schema: [`RmmResourceVersion`](#model-rmmresourceversion)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/rmm/resource/{idResource}/version/{version}` { #put-rmm-resource-idresource-version-version }

Updates an RMM resource version (only name and current)

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idResource` | path | integer | yes | RMM resource id |
| `version` | path | integer | yes | RMM resource version number |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string, nullable |  | Label of the version |
| `current` | boolean, nullable |  | Whether this version is the current one |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "current": false
    }
    ```

**Response 200**: RMM resource version updated

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/rmm/resource/{idResource}/version/{version}` { #delete-rmm-resource-idresource-version-version }

Deletes an RMM resource version object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idResource` | path | integer | yes | RMM resource id |
| `version` | path | integer | yes | RMM resource version number |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/resource/{idResource}/version/{version}/download` { #get-rmm-resource-idresource-version-version-download }

Download RMM resource version file

Downloads the binary file of an RMM resource version

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idResource` | path | integer | yes | RMM resource id |
| `version` | path | integer | yes | RMM resource version number |

**Response 200**: RMM resource version file

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/resource/{idResource}/version/list` { #get-rmm-resource-idresource-version-list }

List RMM resource versions

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idResource` | path | integer | yes | RMM resource id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM resource version object

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
    | `data.[].id` | integer |  | Id of the RMM resource version |
    | `data.[].idResource` | integer |  | Id RMM resource |
    | `data.[].version` | integer |  | Version number of the RMM resource |
    | `data.[].name` | string |  | User friendly label of the RMM resource version |
    | `data.[].realName` | string |  | Real name of the RMM resource version |
    | `data.[].current` | boolean |  | Whether this version is the default selected in the resource version selectors |
    | `data.[].createdDate` | integer |  | Creation date of the RMM resource version |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/resource/{idResource}/version/list` { #post-rmm-resource-idresource-version-list }

List RMM resource versions

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idResource` | path | integer | yes | RMM resource id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | integer |  | Id of the RMM resource version |
| `idResource` | integer |  | Id RMM resource |
| `version` | integer |  | Version number of the RMM resource |
| `name` | string |  | User friendly label of the RMM resource version |
| `realName` | string |  | Real name of the RMM resource version |
| `current` | boolean |  | Whether this version is the default selected in the resource version selectors |
| `createdDate` | integer |  | Creation date of the RMM resource version |
| `idResource` |  |  |  |
| `version` |  |  |  |
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
| `multipleSearch.field` | enum: `id`, `idResource`, `version`, `name`, `realName`, `current`, `createdDate` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `idResource`, `version`, `name`, `realName`, `current`, `createdDate` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "realName": "string",
      "current": false,
      "idResource": null,
      "version": null,
      "requestedFields": [
        "id"
      ],
      "fieldConditions": [
        {
          "field": "id",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "id",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "id",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM resource version object

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
    | `data.[].id` | integer |  | Id of the RMM resource version |
    | `data.[].idResource` | integer |  | Id RMM resource |
    | `data.[].version` | integer |  | Version number of the RMM resource |
    | `data.[].name` | string |  | User friendly label of the RMM resource version |
    | `data.[].realName` | string |  | Real name of the RMM resource version |
    | `data.[].current` | boolean |  | Whether this version is the default selected in the resource version selectors |
    | `data.[].createdDate` | integer |  | Creation date of the RMM resource version |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/routine/{idRoutine}/agent` { #post-rmm-routine-idroutine-agent }

Creates a new RMM routine agent relation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idRoutineAgent` | integer |  | Id RMM routine agent relation |
| `idRoutine` | integer |  | Id RMM routine |
| `idAgentRmm` | integer | yes | Id RMM agent |
| `routineApplied` | boolean, nullable |  | Whether the routine has been applied to the RMM agent |
| `pendingDelete` | boolean, nullable |  | Whether the routine-agent relation is pending to be deleted |
| `lastApplyUtimestamp` | integer, nullable |  | Last time the routine was applied to the RMM agent |
| `agent` |  |  | Embedded normal agent |
| `agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
| `agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
| `agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
| `agent.name` | string |  | Agent name |
| `agent.address` | string, nullable |  | Agent address |
| `agent.comments` | string, nullable |  | Agent comments |
| `agent.idGroup` | integer |  | Group ID |
| `agent.lastContact` | string |  | Last contact timestamp |
| `agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
| `agent.interval` | integer |  | Agent interval in seconds |
| `agent.idOs` | integer, nullable |  | Operating System ID |
| `agent.osVersion` | string, nullable |  | Operating System version |
| `agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
| `agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
| `agent.agentVersion` | string, nullable |  | Agent version |
| `agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
| `agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
| `agent.remote` | integer |  | Remote agent flag |
| `agent.idParent` | integer, nullable |  | Parent agent ID |
| `agent.customId` | string, nullable |  | Custom agent ID |
| `agent.serverName` | string, nullable |  | Server name |
| `agent.cascadeProtection` | integer |  | Cascade protection flag |
| `agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
| `agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
| `agent.iconPath` | string, nullable |  | Icon path |
| `agent.updateGisData` | integer |  | Update GIS data flag |
| `agent.urlAddress` | string, nullable |  | URL address |
| `agent.quiet` | integer |  | Quiet flag |
| `agent.normalCount` | integer |  | Normal modules count |
| `agent.warningCount` | integer |  | Warning modules count |
| `agent.criticalCount` | integer |  | Critical modules count |
| `agent.unknownCount` | integer |  | Unknown modules count |
| `agent.notinitCount` | integer |  | Not init modules count |
| `agent.totalCount` | integer |  | Total modules count |
| `agent.firedCount` | integer |  | Fired alerts count |
| `agent.updateModuleCount` | integer |  | Update module count flag |
| `agent.updateAlertCount` | integer |  | Update alert count flag |
| `agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
| `agent.alias` | string |  | Agent alias |
| `agent.aliasAsName` | integer |  | Use alias as name flag |
| `agent.safeModeModule` | integer |  | Safe mode module ID |
| `agent.cps` | integer |  | CPS value |
| `agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
| `agent.satelliteServer` | integer |  | Satellite server ID |
| `agent.fixedIp` | integer |  | Fixed IP flag |
| `agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
| `agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
| `agent.ignoreUnknown` | integer |  | Ignore unknown flag |
| `agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
| `agent.autoHa` | integer |  | Auto HA flag |
| `agent.extraData` | string |  | Extra data |
| `agent.quietByDowntime` | integer |  | Quiet by downtime flag |
| `agent.idFimPolicy` | integer |  | FIM Policy ID |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgentRmm": 0,
      "pendingDelete": false
    }
    ```

**Response 200**: RMM routine agent relation object

Schema: [`RmmRoutineAgent`](#model-rmmroutineagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/routine/{idRoutine}/agent/{idRoutineAgent}` { #get-rmm-routine-idroutine-agent-idroutineagent }

Show RMM routine agent relation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `idRoutineAgent` | path | integer | yes | RMM routine agent relation id |

**Response 200**: RMM routine agent relation object

Schema: [`RmmRoutineAgent`](#model-rmmroutineagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/rmm/routine/{idRoutine}/agent/{idRoutineAgent}` { #put-rmm-routine-idroutine-agent-idroutineagent }

Updates an RMM routine agent relation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `idRoutineAgent` | path | integer | yes | RMM routine agent relation id |

**Request body** (`application/json`): [`RmmRoutineAgent`](#model-rmmroutineagent)

**Response 200**: RMM routine agent relation object

Schema: [`RmmRoutineAgent`](#model-rmmroutineagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/routine/{idRoutine}/agent/list` { #get-rmm-routine-idroutine-agent-list }

List RMM routine agent relations

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM routine agent relation object

??? note "Response fields (70 fields)"

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
    | `data.[].idRoutineAgent` | integer |  | Id RMM routine agent relation |
    | `data.[].idRoutine` | integer |  | Id RMM routine |
    | `data.[].idAgentRmm` | integer |  | Id RMM agent |
    | `data.[].routineApplied` | boolean, nullable |  | Whether the routine has been applied to the RMM agent |
    | `data.[].pendingDelete` | boolean, nullable |  | Whether the routine-agent relation is pending to be deleted |
    | `data.[].lastApplyUtimestamp` | integer, nullable |  | Last time the routine was applied to the RMM agent |
    | `data.[].agent` |  |  | Embedded normal agent |
    | `data.[].agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
    | `data.[].agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
    | `data.[].agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
    | `data.[].agent.name` | string |  | Agent name |
    | `data.[].agent.address` | string, nullable |  | Agent address |
    | `data.[].agent.comments` | string, nullable |  | Agent comments |
    | `data.[].agent.idGroup` | integer |  | Group ID |
    | `data.[].agent.lastContact` | string |  | Last contact timestamp |
    | `data.[].agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
    | `data.[].agent.interval` | integer |  | Agent interval in seconds |
    | `data.[].agent.idOs` | integer, nullable |  | Operating System ID |
    | `data.[].agent.osVersion` | string, nullable |  | Operating System version |
    | `data.[].agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].agent.agentVersion` | string, nullable |  | Agent version |
    | `data.[].agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
    | `data.[].agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
    | `data.[].agent.remote` | integer |  | Remote agent flag |
    | `data.[].agent.idParent` | integer, nullable |  | Parent agent ID |
    | `data.[].agent.customId` | string, nullable |  | Custom agent ID |
    | `data.[].agent.serverName` | string, nullable |  | Server name |
    | `data.[].agent.cascadeProtection` | integer |  | Cascade protection flag |
    | `data.[].agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
    | `data.[].agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
    | `data.[].agent.iconPath` | string, nullable |  | Icon path |
    | `data.[].agent.updateGisData` | integer |  | Update GIS data flag |
    | `data.[].agent.urlAddress` | string, nullable |  | URL address |
    | `data.[].agent.quiet` | integer |  | Quiet flag |
    | `data.[].agent.normalCount` | integer |  | Normal modules count |
    | `data.[].agent.warningCount` | integer |  | Warning modules count |
    | `data.[].agent.criticalCount` | integer |  | Critical modules count |
    | `data.[].agent.unknownCount` | integer |  | Unknown modules count |
    | `data.[].agent.notinitCount` | integer |  | Not init modules count |
    | `data.[].agent.totalCount` | integer |  | Total modules count |
    | `data.[].agent.firedCount` | integer |  | Fired alerts count |
    | `data.[].agent.updateModuleCount` | integer |  | Update module count flag |
    | `data.[].agent.updateAlertCount` | integer |  | Update alert count flag |
    | `data.[].agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
    | `data.[].agent.alias` | string |  | Agent alias |
    | `data.[].agent.aliasAsName` | integer |  | Use alias as name flag |
    | `data.[].agent.safeModeModule` | integer |  | Safe mode module ID |
    | `data.[].agent.cps` | integer |  | CPS value |
    | `data.[].agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
    | `data.[].agent.satelliteServer` | integer |  | Satellite server ID |
    | `data.[].agent.fixedIp` | integer |  | Fixed IP flag |
    | `data.[].agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
    | `data.[].agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
    | `data.[].agent.ignoreUnknown` | integer |  | Ignore unknown flag |
    | `data.[].agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
    | `data.[].agent.autoHa` | integer |  | Auto HA flag |
    | `data.[].agent.extraData` | string |  | Extra data |
    | `data.[].agent.quietByDowntime` | integer |  | Quiet by downtime flag |
    | `data.[].agent.idFimPolicy` | integer |  | FIM Policy ID |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/routine/{idRoutine}/agent/list` { #post-rmm-routine-idroutine-agent-list }

List RMM routine agent relations

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idRoutineAgent` | integer |  | Id RMM routine agent relation |
| `idRoutine` | integer |  | Id RMM routine |
| `idAgentRmm` | integer |  | Id RMM agent |
| `routineApplied` | boolean, nullable |  | Whether the routine has been applied to the RMM agent |
| `pendingDelete` | boolean, nullable |  | Whether the routine-agent relation is pending to be deleted |
| `lastApplyUtimestamp` | integer, nullable |  | Last time the routine was applied to the RMM agent |
| `agent` |  |  | Embedded normal agent |
| `agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
| `agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
| `agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
| `agent.name` | string |  | Agent name |
| `agent.address` | string, nullable |  | Agent address |
| `agent.comments` | string, nullable |  | Agent comments |
| `agent.idGroup` | integer |  | Group ID |
| `agent.lastContact` | string |  | Last contact timestamp |
| `agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
| `agent.interval` | integer |  | Agent interval in seconds |
| `agent.idOs` | integer, nullable |  | Operating System ID |
| `agent.osVersion` | string, nullable |  | Operating System version |
| `agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
| `agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
| `agent.agentVersion` | string, nullable |  | Agent version |
| `agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
| `agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
| `agent.remote` | integer |  | Remote agent flag |
| `agent.idParent` | integer, nullable |  | Parent agent ID |
| `agent.customId` | string, nullable |  | Custom agent ID |
| `agent.serverName` | string, nullable |  | Server name |
| `agent.cascadeProtection` | integer |  | Cascade protection flag |
| `agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
| `agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
| `agent.iconPath` | string, nullable |  | Icon path |
| `agent.updateGisData` | integer |  | Update GIS data flag |
| `agent.urlAddress` | string, nullable |  | URL address |
| `agent.quiet` | integer |  | Quiet flag |
| `agent.normalCount` | integer |  | Normal modules count |
| `agent.warningCount` | integer |  | Warning modules count |
| `agent.criticalCount` | integer |  | Critical modules count |
| `agent.unknownCount` | integer |  | Unknown modules count |
| `agent.notinitCount` | integer |  | Not init modules count |
| `agent.totalCount` | integer |  | Total modules count |
| `agent.firedCount` | integer |  | Fired alerts count |
| `agent.updateModuleCount` | integer |  | Update module count flag |
| `agent.updateAlertCount` | integer |  | Update alert count flag |
| `agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
| `agent.alias` | string |  | Agent alias |
| `agent.aliasAsName` | integer |  | Use alias as name flag |
| `agent.safeModeModule` | integer |  | Safe mode module ID |
| `agent.cps` | integer |  | CPS value |
| `agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
| `agent.satelliteServer` | integer |  | Satellite server ID |
| `agent.fixedIp` | integer |  | Fixed IP flag |
| `agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
| `agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
| `agent.ignoreUnknown` | integer |  | Ignore unknown flag |
| `agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
| `agent.autoHa` | integer |  | Auto HA flag |
| `agent.extraData` | string |  | Extra data |
| `agent.quietByDowntime` | integer |  | Quiet by downtime flag |
| `agent.idFimPolicy` | integer |  | FIM Policy ID |
| `idRoutineAgent` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in agent name field. |
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
| `multipleSearch.field` | enum: `id`, `idRoutineAgent`, `idRoutine`, `idAgentRmm`, `routineApplied`, `pendingDelete`, `lastApplyUtimestamp` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `idRoutineAgent`, `idRoutine`, `idAgentRmm`, `routineApplied`, `pendingDelete`, `lastApplyUtimestamp` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgentRmm": 0,
      "pendingDelete": false,
      "idRoutineAgent": null,
      "freeSearch": "string",
      "requestedFields": [
        "id"
      ],
      "fieldConditions": [
        {
          "field": "id",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "id",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "id",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM routine agent relation object

??? note "Response fields (70 fields)"

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
    | `data.[].idRoutineAgent` | integer |  | Id RMM routine agent relation |
    | `data.[].idRoutine` | integer |  | Id RMM routine |
    | `data.[].idAgentRmm` | integer |  | Id RMM agent |
    | `data.[].routineApplied` | boolean, nullable |  | Whether the routine has been applied to the RMM agent |
    | `data.[].pendingDelete` | boolean, nullable |  | Whether the routine-agent relation is pending to be deleted |
    | `data.[].lastApplyUtimestamp` | integer, nullable |  | Last time the routine was applied to the RMM agent |
    | `data.[].agent` |  |  | Embedded normal agent |
    | `data.[].agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
    | `data.[].agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
    | `data.[].agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
    | `data.[].agent.name` | string |  | Agent name |
    | `data.[].agent.address` | string, nullable |  | Agent address |
    | `data.[].agent.comments` | string, nullable |  | Agent comments |
    | `data.[].agent.idGroup` | integer |  | Group ID |
    | `data.[].agent.lastContact` | string |  | Last contact timestamp |
    | `data.[].agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
    | `data.[].agent.interval` | integer |  | Agent interval in seconds |
    | `data.[].agent.idOs` | integer, nullable |  | Operating System ID |
    | `data.[].agent.osVersion` | string, nullable |  | Operating System version |
    | `data.[].agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].agent.agentVersion` | string, nullable |  | Agent version |
    | `data.[].agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
    | `data.[].agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
    | `data.[].agent.remote` | integer |  | Remote agent flag |
    | `data.[].agent.idParent` | integer, nullable |  | Parent agent ID |
    | `data.[].agent.customId` | string, nullable |  | Custom agent ID |
    | `data.[].agent.serverName` | string, nullable |  | Server name |
    | `data.[].agent.cascadeProtection` | integer |  | Cascade protection flag |
    | `data.[].agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
    | `data.[].agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
    | `data.[].agent.iconPath` | string, nullable |  | Icon path |
    | `data.[].agent.updateGisData` | integer |  | Update GIS data flag |
    | `data.[].agent.urlAddress` | string, nullable |  | URL address |
    | `data.[].agent.quiet` | integer |  | Quiet flag |
    | `data.[].agent.normalCount` | integer |  | Normal modules count |
    | `data.[].agent.warningCount` | integer |  | Warning modules count |
    | `data.[].agent.criticalCount` | integer |  | Critical modules count |
    | `data.[].agent.unknownCount` | integer |  | Unknown modules count |
    | `data.[].agent.notinitCount` | integer |  | Not init modules count |
    | `data.[].agent.totalCount` | integer |  | Total modules count |
    | `data.[].agent.firedCount` | integer |  | Fired alerts count |
    | `data.[].agent.updateModuleCount` | integer |  | Update module count flag |
    | `data.[].agent.updateAlertCount` | integer |  | Update alert count flag |
    | `data.[].agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
    | `data.[].agent.alias` | string |  | Agent alias |
    | `data.[].agent.aliasAsName` | integer |  | Use alias as name flag |
    | `data.[].agent.safeModeModule` | integer |  | Safe mode module ID |
    | `data.[].agent.cps` | integer |  | CPS value |
    | `data.[].agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
    | `data.[].agent.satelliteServer` | integer |  | Satellite server ID |
    | `data.[].agent.fixedIp` | integer |  | Fixed IP flag |
    | `data.[].agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
    | `data.[].agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
    | `data.[].agent.ignoreUnknown` | integer |  | Ignore unknown flag |
    | `data.[].agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
    | `data.[].agent.autoHa` | integer |  | Auto HA flag |
    | `data.[].agent.extraData` | string |  | Extra data |
    | `data.[].agent.quietByDowntime` | integer |  | Quiet by downtime flag |
    | `data.[].agent.idFimPolicy` | integer |  | FIM Policy ID |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/routine` { #post-rmm-routine }

Creates a new RMM routine

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idRoutine` | integer |  | Id RMM routine |
| `name` | string | yes | Name of the RMM routine |
| `description` | string, nullable |  | Description of the RMM routine |
| `idGroup` | integer, nullable |  | Group id of the RMM routine |
| `applied` | boolean, nullable |  | Whether the RMM routine is applied to the RMM agents |
| `numAgents` | integer, nullable |  | Total number of RMM agents assigned to the RMM routine |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "applied": true
    }
    ```

**Response 200**: RMM routine object

Schema: [`RmmRoutine`](#model-rmmroutine)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/routine/{idRoutine}` { #get-rmm-routine-idroutine }

Show RMM routine

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |

**Response 200**: RMM routine object

Schema: [`RmmRoutine`](#model-rmmroutine)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/rmm/routine/{idRoutine}` { #put-rmm-routine-idroutine }

Updates an RMM routine

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |

**Request body** (`application/json`): [`RmmRoutine`](#model-rmmroutine)

**Response 200**: RMM routine object

Schema: [`RmmRoutine`](#model-rmmroutine)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/rmm/routine/{idRoutine}` { #delete-rmm-routine-idroutine }

Deletes an RMM routine object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/routine/list` { #get-rmm-routine-list }

List RMM routines

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM routine object

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
    | `data.[].idRoutine` | integer |  | Id RMM routine |
    | `data.[].name` | string |  | Name of the RMM routine |
    | `data.[].description` | string, nullable |  | Description of the RMM routine |
    | `data.[].idGroup` | integer, nullable |  | Group id of the RMM routine |
    | `data.[].applied` | boolean, nullable |  | Whether the RMM routine is applied to the RMM agents |
    | `data.[].numAgents` | integer, nullable |  | Total number of RMM agents assigned to the RMM routine |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/routine/list` { #post-rmm-routine-list }

List RMM routines

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
| `idRoutine` | integer |  | Id RMM routine |
| `name` | string |  | Name of the RMM routine |
| `description` | string, nullable |  | Description of the RMM routine |
| `idGroup` | integer, nullable |  | Group id of the RMM routine |
| `applied` | boolean, nullable |  | Whether the RMM routine is applied to the RMM agents |
| `numAgents` | integer, nullable |  | Total number of RMM agents assigned to the RMM routine |
| `idRoutine` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in name and description fields. |
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
| `multipleSearch.field` | enum: `id`, `idRoutine`, `name`, `description`, `idGroup`, `applied` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `idRoutine`, `name`, `description`, `idGroup`, `applied` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "applied": true,
      "idRoutine": null,
      "freeSearch": "string",
      "requestedFields": [
        "id"
      ],
      "fieldConditions": [
        {
          "field": "id",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "id",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "id",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM routine object

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
    | `data.[].idRoutine` | integer |  | Id RMM routine |
    | `data.[].name` | string |  | Name of the RMM routine |
    | `data.[].description` | string, nullable |  | Description of the RMM routine |
    | `data.[].idGroup` | integer, nullable |  | Group id of the RMM routine |
    | `data.[].applied` | boolean, nullable |  | Whether the RMM routine is applied to the RMM agents |
    | `data.[].numAgents` | integer, nullable |  | Total number of RMM agents assigned to the RMM routine |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/routine/{idRoutine}/queue` { #post-rmm-routine-idroutine-queue }

Creates a new RMM routine queue

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |

**Request body** (`application/json`): [`RmmRoutineQueue`](#model-rmmroutinequeue)

**Response 200**: RMM routine queue object

Schema: [`RmmRoutineQueue`](#model-rmmroutinequeue)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/routine/{idRoutine}/queue/{idRoutineQueue}` { #get-rmm-routine-idroutine-queue-idroutinequeue }

Show RMM routine queue

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `idRoutineQueue` | path | integer | yes | RMM routine queue id |

**Response 200**: RMM routine queue object

Schema: [`RmmRoutineQueue`](#model-rmmroutinequeue)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/rmm/routine/{idRoutine}/queue/{idRoutineQueue}` { #put-rmm-routine-idroutine-queue-idroutinequeue }

Updates an RMM routine queue

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `idRoutineQueue` | path | integer | yes | RMM routine queue id |

**Request body** (`application/json`): [`RmmRoutineQueue`](#model-rmmroutinequeue)

**Response 200**: RMM routine queue object

Schema: [`RmmRoutineQueue`](#model-rmmroutinequeue)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/rmm/routine/{idRoutine}/queue/{idRoutineQueue}` { #delete-rmm-routine-idroutine-queue-idroutinequeue }

Deletes an RMM routine queue object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `idRoutineQueue` | path | integer | yes | RMM routine queue id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/routine/{idRoutine}/queue/{idRoutineQueue}/execute` { #post-rmm-routine-idroutine-queue-idroutinequeue-execute }

Executes an RMM routine queue entry

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `idRoutineQueue` | path | integer | yes | RMM routine queue id |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `force_all_agents` | boolean, nullable |  | When true, applies the routine to all its agents regardless of their current apply state |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "force_all_agents": false
    }
    ```

**Response 200**: RMM routine execution started

??? note "Response fields (2 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `success` | boolean |  |  |
    | `message` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/routine/{idRoutine}/queue/list` { #get-rmm-routine-idroutine-queue-list }

List RMM routine queues

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM routine queue object

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
    | `data.[].idRoutineQueue` | integer |  | Id RMM routine queue |
    | `data.[].idRoutine` | integer |  | Id RMM routine |
    | `data.[].progress` | array, nullable |  | Progress of the RMM routine queue |
    | `data.[].error` | string, nullable |  | Error of the RMM routine queue |
    | `data.[].status` | enum: `pending`, `running`, `failed` |  | Status of the RMM routine queue |
    | `data.[].queueUtimestamp` | integer, nullable |  | Queue creation utimestamp |
    | `data.[].dataUtimestamp` | integer, nullable |  | Last data update utimestamp |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/routine/{idRoutine}/queue/list` { #post-rmm-routine-idroutine-queue-list }

List RMM routine queues

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idRoutineQueue` | integer |  | Id RMM routine queue |
| `idRoutine` | integer |  | Id RMM routine |
| `progress` | array, nullable |  | Progress of the RMM routine queue |
| `error` | string, nullable |  | Error of the RMM routine queue |
| `status` | enum: `pending`, `running`, `failed` |  | Status of the RMM routine queue |
| `queueUtimestamp` | integer, nullable |  | Queue creation utimestamp |
| `dataUtimestamp` | integer, nullable |  | Last data update utimestamp |
| `idRoutineQueue` |  |  |  |
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
| `multipleSearch.field` | enum: `id`, `idRoutineQueue`, `idRoutine`, `progress`, `error`, `status`, `queueUtimestamp`, `dataUtimestamp` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `idRoutineQueue`, `idRoutine`, `progress`, `error`, `status`, `queueUtimestamp`, `dataUtimestamp` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "progress": [
        {}
      ],
      "error": "string",
      "status": "pending",
      "queueUtimestamp": 0,
      "dataUtimestamp": 0,
      "idRoutineQueue": null,
      "requestedFields": [
        "id"
      ],
      "fieldConditions": [
        {
          "field": "id",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "id",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "id",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM routine queue object

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
    | `data.[].idRoutineQueue` | integer |  | Id RMM routine queue |
    | `data.[].idRoutine` | integer |  | Id RMM routine |
    | `data.[].progress` | array, nullable |  | Progress of the RMM routine queue |
    | `data.[].error` | string, nullable |  | Error of the RMM routine queue |
    | `data.[].status` | enum: `pending`, `running`, `failed` |  | Status of the RMM routine queue |
    | `data.[].queueUtimestamp` | integer, nullable |  | Queue creation utimestamp |
    | `data.[].dataUtimestamp` | integer, nullable |  | Last data update utimestamp |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/routine/{idRoutine}/schedule` { #post-rmm-routine-idroutine-schedule }

Creates a new RMM routine schedule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idRoutineSchedule` | integer |  | Id RMM routine schedule |
| `idRoutine` | integer |  | Id RMM routine |
| `idScriptRmm` | integer | yes | Id RMM script |
| `name` | string | yes | Name of the RMM routine schedule |
| `inputs` | array, nullable |  | Inputs of the RMM routine schedule |
| `schedule` | string, nullable |  | Cron expression: minute hour day-of-month month day-of-week |
| `enabled` | boolean, nullable |  | Whether the RMM routine schedule is enabled |
| `pendingDelete` | boolean, nullable |  | Whether the routine schedule is pending to be deleted |
| `script` | string, nullable |  | Name of the linked RMM script (trmm_scripts.name) |
| `description` | string, nullable |  | Description of the linked RMM script (trmm_scripts.description) |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idScriptRmm": 0,
      "name": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "tip": "string",
          "value": "string",
          "file_name": "string"
        }
      ],
      "schedule": "* * * * *",
      "enabled": true,
      "pendingDelete": false
    }
    ```

**Response 200**: RMM routine schedule object

Schema: [`RmmRoutineSchedule`](#model-rmmroutineschedule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/routine/{idRoutine}/schedule/{idRoutineSchedule}` { #get-rmm-routine-idroutine-schedule-idroutineschedule }

Show RMM routine schedule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `idRoutineSchedule` | path | integer | yes | RMM routine schedule id |

**Response 200**: RMM routine schedule object

Schema: [`RmmRoutineSchedule`](#model-rmmroutineschedule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/rmm/routine/{idRoutine}/schedule/{idRoutineSchedule}` { #put-rmm-routine-idroutine-schedule-idroutineschedule }

Updates an RMM routine schedule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `idRoutineSchedule` | path | integer | yes | RMM routine schedule id |

**Request body** (`application/json`): [`RmmRoutineSchedule`](#model-rmmroutineschedule)

**Response 200**: RMM routine schedule object

Schema: [`RmmRoutineSchedule`](#model-rmmroutineschedule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/routine/{idRoutine}/schedule/list` { #get-rmm-routine-idroutine-schedule-list }

List RMM routine schedules

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM routine schedule object

??? note "Response fields (20 fields)"

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
    | `data.[].idRoutineSchedule` | integer |  | Id RMM routine schedule |
    | `data.[].idRoutine` | integer |  | Id RMM routine |
    | `data.[].idScriptRmm` | integer |  | Id RMM script |
    | `data.[].name` | string |  | Name of the RMM routine schedule |
    | `data.[].inputs` | array, nullable |  | Inputs of the RMM routine schedule |
    | `data.[].schedule` | string, nullable |  | Cron expression: minute hour day-of-month month day-of-week |
    | `data.[].enabled` | boolean, nullable |  | Whether the RMM routine schedule is enabled |
    | `data.[].pendingDelete` | boolean, nullable |  | Whether the routine schedule is pending to be deleted |
    | `data.[].script` | string, nullable |  | Name of the linked RMM script (trmm_scripts.name) |
    | `data.[].description` | string, nullable |  | Description of the linked RMM script (trmm_scripts.description) |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/routine/{idRoutine}/schedule/list` { #post-rmm-routine-idroutine-schedule-list }

List RMM routine schedules

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRoutine` | path | integer | yes | RMM routine id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idRoutineSchedule` | integer |  | Id RMM routine schedule |
| `idRoutine` | integer |  | Id RMM routine |
| `idScriptRmm` | integer |  | Id RMM script |
| `name` | string |  | Name of the RMM routine schedule |
| `inputs` | array, nullable |  | Inputs of the RMM routine schedule |
| `schedule` | string, nullable |  | Cron expression: minute hour day-of-month month day-of-week |
| `enabled` | boolean, nullable |  | Whether the RMM routine schedule is enabled |
| `pendingDelete` | boolean, nullable |  | Whether the routine schedule is pending to be deleted |
| `script` | string, nullable |  | Name of the linked RMM script (trmm_scripts.name) |
| `description` | string, nullable |  | Description of the linked RMM script (trmm_scripts.description) |
| `idRoutineSchedule` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in name and schedule fields. |
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
| `multipleSearch.field` | enum: `id`, `idRoutineSchedule`, `idRoutine`, `idScriptRmm`, `name`, `inputs`, `schedule`, `enabled`, `pendingDelete`, `script`, `description` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `idRoutineSchedule`, `idRoutine`, `idScriptRmm`, `name`, `inputs`, `schedule`, `enabled`, `pendingDelete`, `script`, `description` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idScriptRmm": 0,
      "name": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "tip": "string",
          "value": "string",
          "file_name": "string"
        }
      ],
      "schedule": "* * * * *",
      "enabled": true,
      "pendingDelete": false,
      "idRoutineSchedule": null,
      "freeSearch": "string",
      "requestedFields": [
        "id"
      ],
      "fieldConditions": [
        {
          "field": "id",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "id",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "id",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM routine schedule object

??? note "Response fields (20 fields)"

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
    | `data.[].idRoutineSchedule` | integer |  | Id RMM routine schedule |
    | `data.[].idRoutine` | integer |  | Id RMM routine |
    | `data.[].idScriptRmm` | integer |  | Id RMM script |
    | `data.[].name` | string |  | Name of the RMM routine schedule |
    | `data.[].inputs` | array, nullable |  | Inputs of the RMM routine schedule |
    | `data.[].schedule` | string, nullable |  | Cron expression: minute hour day-of-month month day-of-week |
    | `data.[].enabled` | boolean, nullable |  | Whether the RMM routine schedule is enabled |
    | `data.[].pendingDelete` | boolean, nullable |  | Whether the routine schedule is pending to be deleted |
    | `data.[].script` | string, nullable |  | Name of the linked RMM script (trmm_scripts.name) |
    | `data.[].description` | string, nullable |  | Description of the linked RMM script (trmm_scripts.description) |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/rule/execute` { #post-rmm-rule-execute }

Executes an RMM rule on a set of agents

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idScriptRmm` | integer | yes | Id RMM script to execute |
| `idAgentsRmm` | array of integer | yes | RMM agents ids |
| `name` | string | yes | Name of the task |
| `inputs` | array, nullable |  | Input values |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idScriptRmm": 0,
      "idAgentsRmm": [
        0
      ],
      "name": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "value": "string"
        }
      ]
    }
    ```

**Response 200**: RMM queue object

Schema: [`RmmQueue`](#model-rmmqueue)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/schedule` { #post-rmm-schedule }

Creates a new RMM schedule

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | integer |  | Id RMM schedule |
| `idAgentRmm` | integer | yes | Id RMM agent |
| `idScriptRmm` | integer | yes | Id RMM script |
| `name` | string | yes | Name of the RMM schedule |
| `inputs` | array, nullable |  | Inputs of the RMM schedule |
| `schedule` | string, nullable |  | Cron expression: minute hour day-of-month month day-of-week |
| `enabled` | boolean, nullable |  | Whether the RMM schedule is enabled |
| `idScheduleRoutine` | integer, nullable |  | Id of the linked schedule routine |
| `routineLinked` | boolean, nullable |  | Whether the schedule is linked to a routine |
| `script` | string, nullable |  | Name of the linked RMM script (trmm_scripts.name) |
| `description` | string, nullable |  | Description of the linked RMM script (trmm_scripts.description) |
| `agentName` | string, nullable |  | Agent name from trmm_agents.agent_name |
| `agentAlias` | string, nullable |  | Agent alias from tagente.alias |
| `agentRmmId` | integer, nullable |  | RMM agent id from trmm_agents (corrected alias of id_agent_emm) |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgentRmm": 0,
      "idScriptRmm": 0,
      "name": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "tip": "string",
          "value": "string",
          "file_name": "string"
        }
      ],
      "schedule": "* * * * *",
      "enabled": true,
      "idScheduleRoutine": 0,
      "routineLinked": false
    }
    ```

**Response 200**: RMM schedule object

Schema: [`RmmSchedule`](#model-rmmschedule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/schedule/{id}` { #get-rmm-schedule-id }

Show RMM schedule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | RMM schedule id |

**Response 200**: RMM schedule object

Schema: [`RmmSchedule`](#model-rmmschedule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/rmm/schedule/{id}` { #put-rmm-schedule-id }

Updates an RMM schedule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | RMM schedule id |

**Request body** (`application/json`): [`RmmSchedule`](#model-rmmschedule)

**Response 200**: RMM schedule object

Schema: [`RmmSchedule`](#model-rmmschedule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/rmm/schedule/{id}` { #delete-rmm-schedule-id }

Deletes an RMM schedule object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | RMM schedule id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/schedule/list` { #get-rmm-schedule-list }

List RMM schedules

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM schedule object

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
    | `data.[].id` | integer |  | Id RMM schedule |
    | `data.[].idAgentRmm` | integer |  | Id RMM agent |
    | `data.[].idScriptRmm` | integer |  | Id RMM script |
    | `data.[].name` | string |  | Name of the RMM schedule |
    | `data.[].inputs` | array, nullable |  | Inputs of the RMM schedule |
    | `data.[].schedule` | string, nullable |  | Cron expression: minute hour day-of-month month day-of-week |
    | `data.[].enabled` | boolean, nullable |  | Whether the RMM schedule is enabled |
    | `data.[].idScheduleRoutine` | integer, nullable |  | Id of the linked schedule routine |
    | `data.[].routineLinked` | boolean, nullable |  | Whether the schedule is linked to a routine |
    | `data.[].script` | string, nullable |  | Name of the linked RMM script (trmm_scripts.name) |
    | `data.[].description` | string, nullable |  | Description of the linked RMM script (trmm_scripts.description) |
    | `data.[].agentName` | string, nullable |  | Agent name from trmm_agents.agent_name |
    | `data.[].agentAlias` | string, nullable |  | Agent alias from tagente.alias |
    | `data.[].agentRmmId` | integer, nullable |  | RMM agent id from trmm_agents (corrected alias of id_agent_emm) |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/schedule/list` { #post-rmm-schedule-list }

List RMM schedules

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
| `id` | integer |  | Id RMM schedule |
| `idAgentRmm` | integer |  | Id RMM agent |
| `idScriptRmm` | integer |  | Id RMM script |
| `name` | string |  | Name of the RMM schedule |
| `inputs` | array, nullable |  | Inputs of the RMM schedule |
| `schedule` | string, nullable |  | Cron expression: minute hour day-of-month month day-of-week |
| `enabled` | boolean, nullable |  | Whether the RMM schedule is enabled |
| `idScheduleRoutine` | integer, nullable |  | Id of the linked schedule routine |
| `routineLinked` | boolean, nullable |  | Whether the schedule is linked to a routine |
| `script` | string, nullable |  | Name of the linked RMM script (trmm_scripts.name) |
| `description` | string, nullable |  | Description of the linked RMM script (trmm_scripts.description) |
| `agentName` | string, nullable |  | Agent name from trmm_agents.agent_name |
| `agentAlias` | string, nullable |  | Agent alias from tagente.alias |
| `agentRmmId` | integer, nullable |  | RMM agent id from trmm_agents (corrected alias of id_agent_emm) |
| `id` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in name and schedule fields. |
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
| `multipleSearch.field` | enum: `id`, `id_agent_rmm`, `idAgentRmm`, `id_script_rmm`, `idScriptRmm`, `name`, `inputs`, `schedule`, `enabled`, `idScheduleRoutine`, `routineLinked`, `script`, `description`, `agent_name`, `agentName`, `alias_agent`, `aliasAgent`, `agentAlias`, `agent_rmm_id`, `agentRmmId`, `id_agent_emm` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `id_agent_rmm`, `idAgentRmm`, `id_script_rmm`, `idScriptRmm`, `name`, `inputs`, `schedule`, `enabled`, `idScheduleRoutine`, `routineLinked`, `script`, `description`, `agent_name`, `agentName`, `alias_agent`, `aliasAgent`, `agentAlias`, `agent_rmm_id`, `agentRmmId`, `id_agent_emm` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgentRmm": 0,
      "idScriptRmm": 0,
      "name": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "tip": "string",
          "value": "string",
          "file_name": "string"
        }
      ],
      "schedule": "* * * * *",
      "enabled": true,
      "idScheduleRoutine": 0,
      "routineLinked": false,
      "id": null,
      "freeSearch": "string",
      "requestedFields": [
        "id"
      ],
      "fieldConditions": [
        {
          "field": "id",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "id",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "id",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM schedule object

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
    | `data.[].id` | integer |  | Id RMM schedule |
    | `data.[].idAgentRmm` | integer |  | Id RMM agent |
    | `data.[].idScriptRmm` | integer |  | Id RMM script |
    | `data.[].name` | string |  | Name of the RMM schedule |
    | `data.[].inputs` | array, nullable |  | Inputs of the RMM schedule |
    | `data.[].schedule` | string, nullable |  | Cron expression: minute hour day-of-month month day-of-week |
    | `data.[].enabled` | boolean, nullable |  | Whether the RMM schedule is enabled |
    | `data.[].idScheduleRoutine` | integer, nullable |  | Id of the linked schedule routine |
    | `data.[].routineLinked` | boolean, nullable |  | Whether the schedule is linked to a routine |
    | `data.[].script` | string, nullable |  | Name of the linked RMM script (trmm_scripts.name) |
    | `data.[].description` | string, nullable |  | Description of the linked RMM script (trmm_scripts.description) |
    | `data.[].agentName` | string, nullable |  | Agent name from trmm_agents.agent_name |
    | `data.[].agentAlias` | string, nullable |  | Agent alias from tagente.alias |
    | `data.[].agentRmmId` | integer, nullable |  | RMM agent id from trmm_agents (corrected alias of id_agent_emm) |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/script` { #post-rmm-script }

Creates a new RMM script

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idScriptRmm` | integer |  | Id RMM script |
| `idGroup` | integer |  | Id group of the RMM script |
| `name` | string | yes | Name of the RMM script |
| `description` | string, nullable |  | Description of the RMM script |
| `idOs` | integer, nullable |  | Id OS of the RMM script |
| `osVersion` | string |  | OS version of the RMM script |
| `inputs` | array, nullable |  | Inputs of the RMM script |
| `notifyBeforeRun` | boolean, nullable |  | Notify before run |
| `eventResponse` | boolean, nullable |  | Whether the script can be used in event responses |
| `preconditionEnabled` | boolean, nullable |  | Precondition enabled |
| `preconditionParameters` | string, nullable |  | Precondition parameters |
| `preconditionInterpreter` | string, nullable |  | Precondition interpreter |
| `preconditionExtension` | string, nullable |  | Precondition extension |
| `preconditionCode` | string, nullable |  | Precondition code |
| `scriptParameters` | string, nullable |  | Script parameters |
| `scriptInterpreter` | string, nullable |  | Script interpreter |
| `scriptExtension` | string, nullable |  | Script extension |
| `scriptCode` | string, nullable |  | Script code |
| `postconditionEnabled` | boolean, nullable |  | Postcondition enabled |
| `postconditionParameters` | string, nullable |  | Postcondition parameters |
| `postconditionInterpreter` | string, nullable |  | Postcondition interpreter |
| `postconditionExtension` | string, nullable |  | Postcondition extension |
| `postconditionCode` | string, nullable |  | Postcondition code |
| `nameOs` | string, nullable |  | Name of the OS of the last execution |
| `idInternal` | string, nullable |  | Internal script identifier. When set the script cannot be modified or deleted. |
| `Queue` |  |  | Embedded last RMM queue |
| `Queue.id` | integer |  | Id RMM queue |
| `Queue.idAgentRmm` | integer, nullable |  | Id RMM agent |
| `Queue.idScriptRmm` | integer, nullable |  | Id RMM script |
| `Queue.name` | string |  | Name of the RMM queue |
| `Queue.step` | string, nullable |  | Step of the RMM queue |
| `Queue.status` | integer, nullable |  | Status of the RMM queue |
| `Queue.output` | string, nullable |  | Output of the RMM queue |
| `Queue.error` | string, nullable |  | Error of the RMM queue |
| `Queue.queueUtimestamp` | integer, nullable |  | Queue utimestamp |
| `Queue.dataUtimestamp` | integer, nullable |  | Data utimestamp |
| `Queue.valuesInputs` | array, nullable |  | Values inputs of the RMM queue |
| `Queue.script` | string, nullable |  | Script name (trmm_scripts.name) |
| `Queue.alias` | string, nullable |  | Agent alias (tagente.alias) — legacy nombre |
| `Queue.agentName` | string, nullable |  | Agent name (trmm_agents.agent_name) — legacy nombre_rmm |
| `Queue.nombre` | string, nullable |  | Alias of the linked agent (legacy alias of tagente.alias) |
| `Queue.nombre_rmm` | string, nullable |  | RMM agent name (legacy alias of trmm_agents.agent_name) |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroup": 0,
      "name": "string",
      "description": "string",
      "idOs": 0,
      "osVersion": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "tip": "string",
          "value": "string",
          "file_name": "string"
        }
      ],
      "notifyBeforeRun": false,
      "eventResponse": false,
      "preconditionEnabled": false,
      "preconditionParameters": "string",
      "preconditionInterpreter": "string",
      "preconditionExtension": "string",
      "preconditionCode": "string",
      "scriptParameters": "string",
      "scriptInterpreter": "string",
      "scriptExtension": "string",
      "scriptCode": "string",
      "postconditionEnabled": false,
      "postconditionParameters": "string",
      "postconditionInterpreter": "string",
      "postconditionExtension": "string",
      "postconditionCode": "string"
    }
    ```

**Response 200**: RMM script object

Schema: [`RmmScript`](#model-rmmscript)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/script/{idScriptRmm}` { #get-rmm-script-idscriptrmm }

Show RMM script

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScriptRmm` | path | integer | yes | RMM script id |

**Response 200**: RMM script object

Schema: [`RmmScript`](#model-rmmscript)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/rmm/script/{idScriptRmm}` { #put-rmm-script-idscriptrmm }

Updates an RMM script

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScriptRmm` | path | integer | yes | RMM script id |

**Request body** (`application/json`): [`RmmScript`](#model-rmmscript)

**Response 200**: RMM script object

Schema: [`RmmScript`](#model-rmmscript)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/rmm/script/{idScriptRmm}` { #delete-rmm-script-idscriptrmm }

Deletes an RMM script object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScriptRmm` | path | integer | yes | RMM script id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/script/list` { #get-rmm-script-list }

List RMM scripts

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List RMM script object

??? note "Response fields (52 fields)"

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
    | `data.[].idScriptRmm` | integer |  | Id RMM script |
    | `data.[].idGroup` | integer |  | Id group of the RMM script |
    | `data.[].name` | string |  | Name of the RMM script |
    | `data.[].description` | string, nullable |  | Description of the RMM script |
    | `data.[].idOs` | integer, nullable |  | Id OS of the RMM script |
    | `data.[].osVersion` | string |  | OS version of the RMM script |
    | `data.[].inputs` | array, nullable |  | Inputs of the RMM script |
    | `data.[].notifyBeforeRun` | boolean, nullable |  | Notify before run |
    | `data.[].eventResponse` | boolean, nullable |  | Whether the script can be used in event responses |
    | `data.[].preconditionEnabled` | boolean, nullable |  | Precondition enabled |
    | `data.[].preconditionParameters` | string, nullable |  | Precondition parameters |
    | `data.[].preconditionInterpreter` | string, nullable |  | Precondition interpreter |
    | `data.[].preconditionExtension` | string, nullable |  | Precondition extension |
    | `data.[].preconditionCode` | string, nullable |  | Precondition code |
    | `data.[].scriptParameters` | string, nullable |  | Script parameters |
    | `data.[].scriptInterpreter` | string, nullable |  | Script interpreter |
    | `data.[].scriptExtension` | string, nullable |  | Script extension |
    | `data.[].scriptCode` | string, nullable |  | Script code |
    | `data.[].postconditionEnabled` | boolean, nullable |  | Postcondition enabled |
    | `data.[].postconditionParameters` | string, nullable |  | Postcondition parameters |
    | `data.[].postconditionInterpreter` | string, nullable |  | Postcondition interpreter |
    | `data.[].postconditionExtension` | string, nullable |  | Postcondition extension |
    | `data.[].postconditionCode` | string, nullable |  | Postcondition code |
    | `data.[].nameOs` | string, nullable |  | Name of the OS of the last execution |
    | `data.[].idInternal` | string, nullable |  | Internal script identifier. When set the script cannot be modified or deleted. |
    | `data.[].Queue` |  |  | Embedded last RMM queue |
    | `data.[].Queue.id` | integer |  | Id RMM queue |
    | `data.[].Queue.idAgentRmm` | integer, nullable |  | Id RMM agent |
    | `data.[].Queue.idScriptRmm` | integer, nullable |  | Id RMM script |
    | `data.[].Queue.name` | string |  | Name of the RMM queue |
    | `data.[].Queue.step` | string, nullable |  | Step of the RMM queue |
    | `data.[].Queue.status` | integer, nullable |  | Status of the RMM queue |
    | `data.[].Queue.output` | string, nullable |  | Output of the RMM queue |
    | `data.[].Queue.error` | string, nullable |  | Error of the RMM queue |
    | `data.[].Queue.queueUtimestamp` | integer, nullable |  | Queue utimestamp |
    | `data.[].Queue.dataUtimestamp` | integer, nullable |  | Data utimestamp |
    | `data.[].Queue.valuesInputs` | array, nullable |  | Values inputs of the RMM queue |
    | `data.[].Queue.script` | string, nullable |  | Script name (trmm_scripts.name) |
    | `data.[].Queue.alias` | string, nullable |  | Agent alias (tagente.alias) — legacy nombre |
    | `data.[].Queue.agentName` | string, nullable |  | Agent name (trmm_agents.agent_name) — legacy nombre_rmm |
    | `data.[].Queue.nombre` | string, nullable |  | Alias of the linked agent (legacy alias of tagente.alias) |
    | `data.[].Queue.nombre_rmm` | string, nullable |  | RMM agent name (legacy alias of trmm_agents.agent_name) |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/script/list` { #post-rmm-script-list }

List RMM scripts

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
| `idScriptRmm` | integer |  | Id RMM script |
| `idGroup` | integer |  | Id group of the RMM script |
| `name` | string |  | Name of the RMM script |
| `description` | string, nullable |  | Description of the RMM script |
| `idOs` | integer, nullable |  | Id OS of the RMM script |
| `osVersion` | string |  | OS version of the RMM script |
| `inputs` | array, nullable |  | Inputs of the RMM script |
| `notifyBeforeRun` | boolean, nullable |  | Notify before run |
| `eventResponse` | boolean, nullable |  | Whether the script can be used in event responses |
| `preconditionEnabled` | boolean, nullable |  | Precondition enabled |
| `preconditionParameters` | string, nullable |  | Precondition parameters |
| `preconditionInterpreter` | string, nullable |  | Precondition interpreter |
| `preconditionExtension` | string, nullable |  | Precondition extension |
| `preconditionCode` | string, nullable |  | Precondition code |
| `scriptParameters` | string, nullable |  | Script parameters |
| `scriptInterpreter` | string, nullable |  | Script interpreter |
| `scriptExtension` | string, nullable |  | Script extension |
| `scriptCode` | string, nullable |  | Script code |
| `postconditionEnabled` | boolean, nullable |  | Postcondition enabled |
| `postconditionParameters` | string, nullable |  | Postcondition parameters |
| `postconditionInterpreter` | string, nullable |  | Postcondition interpreter |
| `postconditionExtension` | string, nullable |  | Postcondition extension |
| `postconditionCode` | string, nullable |  | Postcondition code |
| `nameOs` | string, nullable |  | Name of the OS of the last execution |
| `idInternal` | string, nullable |  | Internal script identifier. When set the script cannot be modified or deleted. |
| `Queue` |  |  | Embedded last RMM queue |
| `Queue.id` | integer |  | Id RMM queue |
| `Queue.idAgentRmm` | integer, nullable |  | Id RMM agent |
| `Queue.idScriptRmm` | integer, nullable |  | Id RMM script |
| `Queue.name` | string |  | Name of the RMM queue |
| `Queue.step` | string, nullable |  | Step of the RMM queue |
| `Queue.status` | integer, nullable |  | Status of the RMM queue |
| `Queue.output` | string, nullable |  | Output of the RMM queue |
| `Queue.error` | string, nullable |  | Error of the RMM queue |
| `Queue.queueUtimestamp` | integer, nullable |  | Queue utimestamp |
| `Queue.dataUtimestamp` | integer, nullable |  | Data utimestamp |
| `Queue.valuesInputs` | array, nullable |  | Values inputs of the RMM queue |
| `Queue.script` | string, nullable |  | Script name (trmm_scripts.name) |
| `Queue.alias` | string, nullable |  | Agent alias (tagente.alias) — legacy nombre |
| `Queue.agentName` | string, nullable |  | Agent name (trmm_agents.agent_name) — legacy nombre_rmm |
| `Queue.nombre` | string, nullable |  | Alias of the linked agent (legacy alias of tagente.alias) |
| `Queue.nombre_rmm` | string, nullable |  | RMM agent name (legacy alias of trmm_agents.agent_name) |
| `idScriptRmm` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in name, description and os version fields. |
| `status` | integer, nullable |  | Filter by last queue status (RMM_OK, RMM_ERROR, RMM_NO_STATUS). |
| `idAgentRmm` | integer, nullable |  | Filter by RMM agent id. |
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
| `multipleSearch.field` | enum: `idScriptRmm`, `idGroup`, `name`, `description`, `os`, `osVersion`, `inputs`, `notifyBeforeRun`, `preconditionEnabled`, `preconditionParameters`, `preconditionInterpreter`, `preconditionExtension`, `preconditionCode`, `scriptParameters`, `scriptInterpreter`, `scriptExtension`, `scriptCode`, `postconditionEnabled`, `postconditionParameters`, `postconditionInterpreter`, `postconditionExtension`, `postconditionCode`, `nameOs`, `idInternal`, `status`, `output`, `error`, `step`, `lastUtimestamp`, `dataUtimestamp`, `valuesInputs`, `idQueue`, `queueName` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idScriptRmm`, `idGroup`, `name`, `description`, `os`, `osVersion`, `inputs`, `notifyBeforeRun`, `preconditionEnabled`, `preconditionParameters`, `preconditionInterpreter`, `preconditionExtension`, `preconditionCode`, `scriptParameters`, `scriptInterpreter`, `scriptExtension`, `scriptCode`, `postconditionEnabled`, `postconditionParameters`, `postconditionInterpreter`, `postconditionExtension`, `postconditionCode`, `nameOs`, `idInternal`, `status`, `output`, `error`, `step`, `lastUtimestamp`, `dataUtimestamp`, `valuesInputs`, `idQueue`, `queueName` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroup": 0,
      "name": "string",
      "description": "string",
      "idOs": 0,
      "osVersion": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "tip": "string",
          "value": "string",
          "file_name": "string"
        }
      ],
      "notifyBeforeRun": false,
      "eventResponse": false,
      "preconditionEnabled": false,
      "preconditionParameters": "string",
      "preconditionInterpreter": "string",
      "preconditionExtension": "string",
      "preconditionCode": "string",
      "scriptParameters": "string",
      "scriptInterpreter": "string",
      "scriptExtension": "string",
      "scriptCode": "string",
      "postconditionEnabled": false,
      "postconditionParameters": "string",
      "postconditionInterpreter": "string",
      "postconditionExtension": "string",
      "postconditionCode": "string",
      "idScriptRmm": null,
      "freeSearch": "string",
      "status": 0,
      "idAgentRmm": 0,
      "requestedFields": [
        "idScriptRmm"
      ],
      "fieldConditions": [
        {
          "field": "idScriptRmm",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idScriptRmm",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idScriptRmm",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM script object

??? note "Response fields (52 fields)"

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
    | `data.[].idScriptRmm` | integer |  | Id RMM script |
    | `data.[].idGroup` | integer |  | Id group of the RMM script |
    | `data.[].name` | string |  | Name of the RMM script |
    | `data.[].description` | string, nullable |  | Description of the RMM script |
    | `data.[].idOs` | integer, nullable |  | Id OS of the RMM script |
    | `data.[].osVersion` | string |  | OS version of the RMM script |
    | `data.[].inputs` | array, nullable |  | Inputs of the RMM script |
    | `data.[].notifyBeforeRun` | boolean, nullable |  | Notify before run |
    | `data.[].eventResponse` | boolean, nullable |  | Whether the script can be used in event responses |
    | `data.[].preconditionEnabled` | boolean, nullable |  | Precondition enabled |
    | `data.[].preconditionParameters` | string, nullable |  | Precondition parameters |
    | `data.[].preconditionInterpreter` | string, nullable |  | Precondition interpreter |
    | `data.[].preconditionExtension` | string, nullable |  | Precondition extension |
    | `data.[].preconditionCode` | string, nullable |  | Precondition code |
    | `data.[].scriptParameters` | string, nullable |  | Script parameters |
    | `data.[].scriptInterpreter` | string, nullable |  | Script interpreter |
    | `data.[].scriptExtension` | string, nullable |  | Script extension |
    | `data.[].scriptCode` | string, nullable |  | Script code |
    | `data.[].postconditionEnabled` | boolean, nullable |  | Postcondition enabled |
    | `data.[].postconditionParameters` | string, nullable |  | Postcondition parameters |
    | `data.[].postconditionInterpreter` | string, nullable |  | Postcondition interpreter |
    | `data.[].postconditionExtension` | string, nullable |  | Postcondition extension |
    | `data.[].postconditionCode` | string, nullable |  | Postcondition code |
    | `data.[].nameOs` | string, nullable |  | Name of the OS of the last execution |
    | `data.[].idInternal` | string, nullable |  | Internal script identifier. When set the script cannot be modified or deleted. |
    | `data.[].Queue` |  |  | Embedded last RMM queue |
    | `data.[].Queue.id` | integer |  | Id RMM queue |
    | `data.[].Queue.idAgentRmm` | integer, nullable |  | Id RMM agent |
    | `data.[].Queue.idScriptRmm` | integer, nullable |  | Id RMM script |
    | `data.[].Queue.name` | string |  | Name of the RMM queue |
    | `data.[].Queue.step` | string, nullable |  | Step of the RMM queue |
    | `data.[].Queue.status` | integer, nullable |  | Status of the RMM queue |
    | `data.[].Queue.output` | string, nullable |  | Output of the RMM queue |
    | `data.[].Queue.error` | string, nullable |  | Error of the RMM queue |
    | `data.[].Queue.queueUtimestamp` | integer, nullable |  | Queue utimestamp |
    | `data.[].Queue.dataUtimestamp` | integer, nullable |  | Data utimestamp |
    | `data.[].Queue.valuesInputs` | array, nullable |  | Values inputs of the RMM queue |
    | `data.[].Queue.script` | string, nullable |  | Script name (trmm_scripts.name) |
    | `data.[].Queue.alias` | string, nullable |  | Agent alias (tagente.alias) — legacy nombre |
    | `data.[].Queue.agentName` | string, nullable |  | Agent name (trmm_agents.agent_name) — legacy nombre_rmm |
    | `data.[].Queue.nombre` | string, nullable |  | Alias of the linked agent (legacy alias of tagente.alias) |
    | `data.[].Queue.nombre_rmm` | string, nullable |  | RMM agent name (legacy alias of trmm_agents.agent_name) |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/settings` { #post-rmm-settings }

Create a RMM settings object

**Request body** (`application/json`): [`RmmSettings`](#model-rmmsettings)

**Response 200**: RMM settings object

Schema: [`RmmSettings`](#model-rmmsettings)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/settings/{id}` { #get-rmm-settings-id }

Get a RMM settings object

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | RMM settings id |

**Response 200**: RMM settings object

Schema: [`RmmSettings`](#model-rmmsettings)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/rmm/settings/{id}` { #put-rmm-settings-id }

Update a RMM settings object

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | RMM settings id |

**Request body** (`application/json`): [`RmmSettings`](#model-rmmsettings)

**Response 200**: RMM settings object

Schema: [`RmmSettings`](#model-rmmsettings)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/rmm/settings/list` { #get-rmm-settings-list }

List RMM settings

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Response 200**: List RMM settings objects

??? note "Response fields (13 fields)"

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
    | `data.[].id` | integer, nullable |  | RMM settings id |
    | `data.[].allowList` | string, nullable |  | Packages allowed to be updated, one per line |
    | `data.[].denyList` | string, nullable |  | Packages not allowed to be updated, one per line |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/rmm/settings/list` { #post-rmm-settings-list }

List RMM settings

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | integer, nullable |  | RMM settings id |
| `allowList` | string, nullable |  | Packages allowed to be updated, one per line |
| `denyList` | string, nullable |  | Packages not allowed to be updated, one per line |
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
| `multipleSearch.field` | enum: `id`, `allowList`, `denyList` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `allowList`, `denyList` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "allowList": "string",
      "denyList": "string",
      "requestedFields": [
        "id"
      ],
      "fieldConditions": [
        {
          "field": "id",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "id",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "id",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List RMM settings objects

??? note "Response fields (13 fields)"

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
    | `data.[].id` | integer, nullable |  | RMM settings id |
    | `data.[].allowList` | string, nullable |  | Packages allowed to be updated, one per line |
    | `data.[].denyList` | string, nullable |  | Packages not allowed to be updated, one per line |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: RmmAgent { #model-rmmagent }

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgentRmm` | integer |  | Id RMM agent |
| `agentName` | string |  | Name of the RMM agent |
| `lastContact` | integer, nullable |  | RMM agent last contact utimestamp |
| `interval` | integer, nullable |  | RMM agent contact interval |
| `enabled` | boolean, nullable |  | Whether the RMM agent is enabled |
| `status` | integer, nullable |  | RMM agent status |
| `Agent` |  |  | Embedded normal agent |
| `Agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
| `Agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
| `Agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
| `Agent.name` | string |  | Agent name |
| `Agent.address` | string, nullable |  | Agent address |
| `Agent.comments` | string, nullable |  | Agent comments |
| `Agent.idGroup` | integer |  | Group ID |
| `Agent.lastContact` | string |  | Last contact timestamp |
| `Agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
| `Agent.interval` | integer |  | Agent interval in seconds |
| `Agent.idOs` | integer, nullable |  | Operating System ID |
| `Agent.osVersion` | string, nullable |  | Operating System version |
| `Agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
| `Agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
| `Agent.agentVersion` | string, nullable |  | Agent version |
| `Agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
| `Agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
| `Agent.remote` | integer |  | Remote agent flag |
| `Agent.idParent` | integer, nullable |  | Parent agent ID |
| `Agent.customId` | string, nullable |  | Custom agent ID |
| `Agent.serverName` | string, nullable |  | Server name |
| `Agent.cascadeProtection` | integer |  | Cascade protection flag |
| `Agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
| `Agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
| `Agent.iconPath` | string, nullable |  | Icon path |
| `Agent.updateGisData` | integer |  | Update GIS data flag |
| `Agent.urlAddress` | string, nullable |  | URL address |
| `Agent.quiet` | integer |  | Quiet flag |
| `Agent.normalCount` | integer |  | Normal modules count |
| `Agent.warningCount` | integer |  | Warning modules count |
| `Agent.criticalCount` | integer |  | Critical modules count |
| `Agent.unknownCount` | integer |  | Unknown modules count |
| `Agent.notinitCount` | integer |  | Not init modules count |
| `Agent.totalCount` | integer |  | Total modules count |
| `Agent.firedCount` | integer |  | Fired alerts count |
| `Agent.updateModuleCount` | integer |  | Update module count flag |
| `Agent.updateAlertCount` | integer |  | Update alert count flag |
| `Agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
| `Agent.alias` | string |  | Agent alias |
| `Agent.aliasAsName` | integer |  | Use alias as name flag |
| `Agent.safeModeModule` | integer |  | Safe mode module ID |
| `Agent.cps` | integer |  | CPS value |
| `Agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
| `Agent.satelliteServer` | integer |  | Satellite server ID |
| `Agent.fixedIp` | integer |  | Fixed IP flag |
| `Agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
| `Agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
| `Agent.ignoreUnknown` | integer |  | Ignore unknown flag |
| `Agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
| `Agent.autoHa` | integer |  | Auto HA flag |
| `Agent.extraData` | string |  | Extra data |
| `Agent.quietByDowntime` | integer |  | Quiet by downtime flag |
| `Agent.idFimPolicy` | integer |  | FIM Policy ID |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "agentName": "string",
      "lastContact": 0,
      "interval": 30,
      "enabled": true
    }
    ```

### Model: RmmBatchAgent { #model-rmmbatchagent }

??? note "Fields (57 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idBatchAgent` | integer |  | Id RMM batch agent |
    | `idBatchJob` | integer |  | Id of the RMM batch job |
    | `idAgentRmm` | integer |  | Id of the RMM agent |
    | `agent` | object |  | Normal agent linked to the RMM batch agent |
    | `agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
    | `agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
    | `agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
    | `agent.name` | string |  | Agent name |
    | `agent.address` | string, nullable |  | Agent address |
    | `agent.comments` | string, nullable |  | Agent comments |
    | `agent.idGroup` | integer |  | Group ID |
    | `agent.lastContact` | string |  | Last contact timestamp |
    | `agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
    | `agent.interval` | integer |  | Agent interval in seconds |
    | `agent.idOs` | integer, nullable |  | Operating System ID |
    | `agent.osVersion` | string, nullable |  | Operating System version |
    | `agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `agent.agentVersion` | string, nullable |  | Agent version |
    | `agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
    | `agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
    | `agent.remote` | integer |  | Remote agent flag |
    | `agent.idParent` | integer, nullable |  | Parent agent ID |
    | `agent.customId` | string, nullable |  | Custom agent ID |
    | `agent.serverName` | string, nullable |  | Server name |
    | `agent.cascadeProtection` | integer |  | Cascade protection flag |
    | `agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
    | `agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
    | `agent.iconPath` | string, nullable |  | Icon path |
    | `agent.updateGisData` | integer |  | Update GIS data flag |
    | `agent.urlAddress` | string, nullable |  | URL address |
    | `agent.quiet` | integer |  | Quiet flag |
    | `agent.normalCount` | integer |  | Normal modules count |
    | `agent.warningCount` | integer |  | Warning modules count |
    | `agent.criticalCount` | integer |  | Critical modules count |
    | `agent.unknownCount` | integer |  | Unknown modules count |
    | `agent.notinitCount` | integer |  | Not init modules count |
    | `agent.totalCount` | integer |  | Total modules count |
    | `agent.firedCount` | integer |  | Fired alerts count |
    | `agent.updateModuleCount` | integer |  | Update module count flag |
    | `agent.updateAlertCount` | integer |  | Update alert count flag |
    | `agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
    | `agent.alias` | string |  | Agent alias |
    | `agent.aliasAsName` | integer |  | Use alias as name flag |
    | `agent.safeModeModule` | integer |  | Safe mode module ID |
    | `agent.cps` | integer |  | CPS value |
    | `agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
    | `agent.satelliteServer` | integer |  | Satellite server ID |
    | `agent.fixedIp` | integer |  | Fixed IP flag |
    | `agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
    | `agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
    | `agent.ignoreUnknown` | integer |  | Ignore unknown flag |
    | `agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
    | `agent.autoHa` | integer |  | Auto HA flag |
    | `agent.extraData` | string |  | Extra data |
    | `agent.quietByDowntime` | integer |  | Quiet by downtime flag |
    | `agent.idFimPolicy` | integer |  | FIM Policy ID |


### Model: RmmBatchJob { #model-rmmbatchjob }

| Field | Type | Required | Description |
|---|---|---|---|
| `idBatchJob` | integer |  | Id RMM batch job |
| `name` | string |  | Name of the RMM batch job |
| `description` | string, nullable |  | Description of the RMM batch job |
| `idGroup` | integer, nullable |  | Group id of the RMM batch job |
| `lastExecutionUtimestamp` | integer, nullable |  | Timestamp of the last execution of the RMM batch job |
| `numAgents` | integer, nullable |  | Total number of RMM agents associated to the RMM batch job |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0
    }
    ```

### Model: RmmBatchQueue { #model-rmmbatchqueue }

| Field | Type | Required | Description |
|---|---|---|---|
| `idBatchQueue` | integer |  | Id RMM batch queue |
| `idBatchJob` | integer |  | Id of the RMM batch job |
| `progress` | array, nullable |  | Progress of the RMM batch queue |
| `error` | string, nullable |  | Error message of the RMM batch queue |
| `status` | enum: `pending`, `running`, `failed` |  | Status of the RMM batch queue |
| `queueUtimestamp` | integer, nullable |  | Timestamp when the RMM batch queue was created |
| `dataUtimestamp` | integer, nullable |  | Timestamp when the RMM batch queue was last updated |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idBatchJob": 0,
      "progress": [],
      "error": "string",
      "queueUtimestamp": 0,
      "dataUtimestamp": 0
    }
    ```

### Model: RmmBatchRule { #model-rmmbatchrule }

| Field | Type | Required | Description |
|---|---|---|---|
| `idBatchRule` | integer |  | Id RMM batch rule |
| `idBatchJob` | integer |  | Id of the RMM batch job |
| `idScriptRmm` | integer |  | Id of the RMM script |
| `name` | string |  | Name of the RMM batch rule |
| `inputs` | array, nullable |  | Inputs of the RMM batch rule |
| `script` | string, nullable |  | Name of the RMM script |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idBatchJob": 0,
      "idScriptRmm": 0,
      "name": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "tip": "string",
          "value": "string",
          "file_name": "string"
        }
      ]
    }
    ```

### Model: RmmPendingSoftwareFilter { #model-rmmpendingsoftwarefilter }

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgente` | integer, nullable |  | One pending software update of an RMM agent. |
| `idAgentRmm` | integer, nullable |  |  |
| `agentName` | string, nullable |  |  |
| `idGroup` | integer, nullable |  |  |
| `idOs` | integer, nullable |  |  |
| `name` | string, nullable |  |  |
| `currentVersion` | string, nullable |  |  |
| `availableVersion` | string, nullable |  |  |
| `manager` | string, nullable |  |  |
| `uniqueId` | string, nullable |  |  |
| `timestamp` | integer, nullable |  |  |
| `isUpdatable` | boolean, nullable |  | Whether the allow/deny policy allows updating this package |
| `freeSearch` | string, nullable |  | Find word in agent name, package, manager or version. |
| `idGroup` | integer, nullable |  | Filter by agent group id. |
| `idOs` | integer, nullable |  | Filter by agent OS id. |
| `updatable` | boolean, nullable |  | Filter by whether the allow/deny policy allows updating the package (true) or not (false). |
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
| `multipleSearch.field` | enum: `idAgente`, `idAgentRmm`, `agent`, `agentName`, `agentAlias`, `idGroup`, `idOs`, `category`, `name`, `currentVersion`, `availableVersion`, `manager`, `uniqueId`, `timestamp` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAgente`, `idAgentRmm`, `agent`, `agentName`, `agentAlias`, `idGroup`, `idOs`, `category`, `name`, `currentVersion`, `availableVersion`, `manager`, `uniqueId`, `timestamp` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgente": 0,
      "idAgentRmm": 0,
      "agentName": "string",
      "idGroup": 0,
      "idOs": 0,
      "name": "string",
      "currentVersion": "string",
      "availableVersion": "string",
      "manager": "string",
      "uniqueId": "string",
      "timestamp": 0,
      "isUpdatable": false,
      "freeSearch": "string",
      "updatable": false,
      "requestedFields": [
        "idAgente"
      ],
      "fieldConditions": [
        {
          "field": "idAgente",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idAgente",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAgente",
        "data": [
          "string"
        ]
      }
    }
    ```

### Model: RmmQueue { #model-rmmqueue }

??? note "Fields (16 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `id` | integer |  | Id RMM queue |
    | `idAgentRmm` | integer, nullable |  | Id RMM agent |
    | `idScriptRmm` | integer, nullable |  | Id RMM script |
    | `name` | string |  | Name of the RMM queue |
    | `step` | string, nullable |  | Step of the RMM queue |
    | `status` | integer, nullable |  | Status of the RMM queue |
    | `output` | string, nullable |  | Output of the RMM queue |
    | `error` | string, nullable |  | Error of the RMM queue |
    | `queueUtimestamp` | integer, nullable |  | Queue utimestamp |
    | `dataUtimestamp` | integer, nullable |  | Data utimestamp |
    | `valuesInputs` | array, nullable |  | Values inputs of the RMM queue |
    | `script` | string, nullable |  | Script name (trmm_scripts.name) |
    | `alias` | string, nullable |  | Agent alias (tagente.alias) — legacy nombre |
    | `agentName` | string, nullable |  | Agent name (trmm_agents.agent_name) — legacy nombre_rmm |
    | `nombre` | string, nullable |  | Alias of the linked agent (legacy alias of tagente.alias) |
    | `nombre_rmm` | string, nullable |  | RMM agent name (legacy alias of trmm_agents.agent_name) |


### Model: RmmResource { #model-rmmresource }

??? note "Fields (7 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idResource` | integer |  | Id RMM resource |
    | `shortName` | string |  | Short name of the RMM resource |
    | `realName` | string |  | Real name of the RMM resource |
    | `createdDate` | integer |  | Creation date of the RMM resource |
    | `version` | integer |  | Latest version number of the RMM resource |
    | `versionsCount` | integer |  | Total number of versions of the RMM resource |
    | `versionName` | string |  | User friendly label of the latest RMM resource version |


### Model: RmmResourceVersion { #model-rmmresourceversion }

??? note "Fields (7 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `id` | integer |  | Id of the RMM resource version |
    | `idResource` | integer |  | Id RMM resource |
    | `version` | integer |  | Version number of the RMM resource |
    | `name` | string |  | User friendly label of the RMM resource version |
    | `realName` | string |  | Real name of the RMM resource version |
    | `current` | boolean |  | Whether this version is the default selected in the resource version selectors |
    | `createdDate` | integer |  | Creation date of the RMM resource version |


### Model: RmmRoutine { #model-rmmroutine }

| Field | Type | Required | Description |
|---|---|---|---|
| `idRoutine` | integer |  | Id RMM routine |
| `name` | string |  | Name of the RMM routine |
| `description` | string, nullable |  | Description of the RMM routine |
| `idGroup` | integer, nullable |  | Group id of the RMM routine |
| `applied` | boolean, nullable |  | Whether the RMM routine is applied to the RMM agents |
| `numAgents` | integer, nullable |  | Total number of RMM agents assigned to the RMM routine |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "applied": true
    }
    ```

### Model: RmmRoutineAgent { #model-rmmroutineagent }

| Field | Type | Required | Description |
|---|---|---|---|
| `idRoutineAgent` | integer |  | Id RMM routine agent relation |
| `idRoutine` | integer |  | Id RMM routine |
| `idAgentRmm` | integer |  | Id RMM agent |
| `routineApplied` | boolean, nullable |  | Whether the routine has been applied to the RMM agent |
| `pendingDelete` | boolean, nullable |  | Whether the routine-agent relation is pending to be deleted |
| `lastApplyUtimestamp` | integer, nullable |  | Last time the routine was applied to the RMM agent |
| `agent` |  |  | Embedded normal agent |
| `agent.idAgentNode` | integer, nullable |  | Original agent ID on the node |
| `agent.serverId` | integer, nullable |  | Source node ID on a metaconsole |
| `agent.idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
| `agent.name` | string |  | Agent name |
| `agent.address` | string, nullable |  | Agent address |
| `agent.comments` | string, nullable |  | Agent comments |
| `agent.idGroup` | integer |  | Group ID |
| `agent.lastContact` | string |  | Last contact timestamp |
| `agent.mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
| `agent.interval` | integer |  | Agent interval in seconds |
| `agent.idOs` | integer, nullable |  | Operating System ID |
| `agent.osVersion` | string, nullable |  | Operating System version |
| `agent.osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
| `agent.osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
| `agent.agentVersion` | string, nullable |  | Agent version |
| `agent.lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
| `agent.disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
| `agent.remote` | integer |  | Remote agent flag |
| `agent.idParent` | integer, nullable |  | Parent agent ID |
| `agent.customId` | string, nullable |  | Custom agent ID |
| `agent.serverName` | string, nullable |  | Server name |
| `agent.cascadeProtection` | integer |  | Cascade protection flag |
| `agent.cascadeProtectionModule` | integer |  | Cascade protection module ID |
| `agent.timezoneOffset` | integer, nullable |  | Timezone offset in hours |
| `agent.iconPath` | string, nullable |  | Icon path |
| `agent.updateGisData` | integer |  | Update GIS data flag |
| `agent.urlAddress` | string, nullable |  | URL address |
| `agent.quiet` | integer |  | Quiet flag |
| `agent.normalCount` | integer |  | Normal modules count |
| `agent.warningCount` | integer |  | Warning modules count |
| `agent.criticalCount` | integer |  | Critical modules count |
| `agent.unknownCount` | integer |  | Unknown modules count |
| `agent.notinitCount` | integer |  | Not init modules count |
| `agent.totalCount` | integer |  | Total modules count |
| `agent.firedCount` | integer |  | Fired alerts count |
| `agent.updateModuleCount` | integer |  | Update module count flag |
| `agent.updateAlertCount` | integer |  | Update alert count flag |
| `agent.updateSecondaryGroups` | integer |  | Update secondary groups flag |
| `agent.alias` | string |  | Agent alias |
| `agent.aliasAsName` | integer |  | Use alias as name flag |
| `agent.safeModeModule` | integer |  | Safe mode module ID |
| `agent.cps` | integer |  | CPS value |
| `agent.cpsInhibit` | integer, nullable |  | CPS inhibition value |
| `agent.satelliteServer` | integer |  | Satellite server ID |
| `agent.fixedIp` | integer |  | Fixed IP flag |
| `agent.disabledByDowntime` | integer |  | Disabled by downtime flag |
| `agent.vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
| `agent.ignoreUnknown` | integer |  | Ignore unknown flag |
| `agent.balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
| `agent.autoHa` | integer |  | Auto HA flag |
| `agent.extraData` | string |  | Extra data |
| `agent.quietByDowntime` | integer |  | Quiet by downtime flag |
| `agent.idFimPolicy` | integer |  | FIM Policy ID |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgentRmm": 0,
      "pendingDelete": false
    }
    ```

### Model: RmmRoutineQueue { #model-rmmroutinequeue }

| Field | Type | Required | Description |
|---|---|---|---|
| `idRoutineQueue` | integer |  | Id RMM routine queue |
| `idRoutine` | integer |  | Id RMM routine |
| `progress` | array, nullable |  | Progress of the RMM routine queue |
| `error` | string, nullable |  | Error of the RMM routine queue |
| `status` | enum: `pending`, `running`, `failed` |  | Status of the RMM routine queue |
| `queueUtimestamp` | integer, nullable |  | Queue creation utimestamp |
| `dataUtimestamp` | integer, nullable |  | Last data update utimestamp |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "progress": [
        {}
      ],
      "error": "string",
      "status": "pending",
      "queueUtimestamp": 0,
      "dataUtimestamp": 0
    }
    ```

### Model: RmmRoutineSchedule { #model-rmmroutineschedule }

| Field | Type | Required | Description |
|---|---|---|---|
| `idRoutineSchedule` | integer |  | Id RMM routine schedule |
| `idRoutine` | integer |  | Id RMM routine |
| `idScriptRmm` | integer |  | Id RMM script |
| `name` | string |  | Name of the RMM routine schedule |
| `inputs` | array, nullable |  | Inputs of the RMM routine schedule |
| `schedule` | string, nullable |  | Cron expression: minute hour day-of-month month day-of-week |
| `enabled` | boolean, nullable |  | Whether the RMM routine schedule is enabled |
| `pendingDelete` | boolean, nullable |  | Whether the routine schedule is pending to be deleted |
| `script` | string, nullable |  | Name of the linked RMM script (trmm_scripts.name) |
| `description` | string, nullable |  | Description of the linked RMM script (trmm_scripts.description) |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idScriptRmm": 0,
      "name": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "tip": "string",
          "value": "string",
          "file_name": "string"
        }
      ],
      "schedule": "* * * * *",
      "enabled": true,
      "pendingDelete": false
    }
    ```

### Model: RmmSchedule { #model-rmmschedule }

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | integer |  | Id RMM schedule |
| `idAgentRmm` | integer |  | Id RMM agent |
| `idScriptRmm` | integer |  | Id RMM script |
| `name` | string |  | Name of the RMM schedule |
| `inputs` | array, nullable |  | Inputs of the RMM schedule |
| `schedule` | string, nullable |  | Cron expression: minute hour day-of-month month day-of-week |
| `enabled` | boolean, nullable |  | Whether the RMM schedule is enabled |
| `idScheduleRoutine` | integer, nullable |  | Id of the linked schedule routine |
| `routineLinked` | boolean, nullable |  | Whether the schedule is linked to a routine |
| `script` | string, nullable |  | Name of the linked RMM script (trmm_scripts.name) |
| `description` | string, nullable |  | Description of the linked RMM script (trmm_scripts.description) |
| `agentName` | string, nullable |  | Agent name from trmm_agents.agent_name |
| `agentAlias` | string, nullable |  | Agent alias from tagente.alias |
| `agentRmmId` | integer, nullable |  | RMM agent id from trmm_agents (corrected alias of id_agent_emm) |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgentRmm": 0,
      "idScriptRmm": 0,
      "name": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "tip": "string",
          "value": "string",
          "file_name": "string"
        }
      ],
      "schedule": "* * * * *",
      "enabled": true,
      "idScheduleRoutine": 0,
      "routineLinked": false
    }
    ```

### Model: RmmScript { #model-rmmscript }

| Field | Type | Required | Description |
|---|---|---|---|
| `idScriptRmm` | integer |  | Id RMM script |
| `idGroup` | integer |  | Id group of the RMM script |
| `name` | string |  | Name of the RMM script |
| `description` | string, nullable |  | Description of the RMM script |
| `idOs` | integer, nullable |  | Id OS of the RMM script |
| `osVersion` | string |  | OS version of the RMM script |
| `inputs` | array, nullable |  | Inputs of the RMM script |
| `notifyBeforeRun` | boolean, nullable |  | Notify before run |
| `eventResponse` | boolean, nullable |  | Whether the script can be used in event responses |
| `preconditionEnabled` | boolean, nullable |  | Precondition enabled |
| `preconditionParameters` | string, nullable |  | Precondition parameters |
| `preconditionInterpreter` | string, nullable |  | Precondition interpreter |
| `preconditionExtension` | string, nullable |  | Precondition extension |
| `preconditionCode` | string, nullable |  | Precondition code |
| `scriptParameters` | string, nullable |  | Script parameters |
| `scriptInterpreter` | string, nullable |  | Script interpreter |
| `scriptExtension` | string, nullable |  | Script extension |
| `scriptCode` | string, nullable |  | Script code |
| `postconditionEnabled` | boolean, nullable |  | Postcondition enabled |
| `postconditionParameters` | string, nullable |  | Postcondition parameters |
| `postconditionInterpreter` | string, nullable |  | Postcondition interpreter |
| `postconditionExtension` | string, nullable |  | Postcondition extension |
| `postconditionCode` | string, nullable |  | Postcondition code |
| `nameOs` | string, nullable |  | Name of the OS of the last execution |
| `idInternal` | string, nullable |  | Internal script identifier. When set the script cannot be modified or deleted. |
| `Queue` |  |  | Embedded last RMM queue |
| `Queue.id` | integer |  | Id RMM queue |
| `Queue.idAgentRmm` | integer, nullable |  | Id RMM agent |
| `Queue.idScriptRmm` | integer, nullable |  | Id RMM script |
| `Queue.name` | string |  | Name of the RMM queue |
| `Queue.step` | string, nullable |  | Step of the RMM queue |
| `Queue.status` | integer, nullable |  | Status of the RMM queue |
| `Queue.output` | string, nullable |  | Output of the RMM queue |
| `Queue.error` | string, nullable |  | Error of the RMM queue |
| `Queue.queueUtimestamp` | integer, nullable |  | Queue utimestamp |
| `Queue.dataUtimestamp` | integer, nullable |  | Data utimestamp |
| `Queue.valuesInputs` | array, nullable |  | Values inputs of the RMM queue |
| `Queue.script` | string, nullable |  | Script name (trmm_scripts.name) |
| `Queue.alias` | string, nullable |  | Agent alias (tagente.alias) — legacy nombre |
| `Queue.agentName` | string, nullable |  | Agent name (trmm_agents.agent_name) — legacy nombre_rmm |
| `Queue.nombre` | string, nullable |  | Alias of the linked agent (legacy alias of tagente.alias) |
| `Queue.nombre_rmm` | string, nullable |  | RMM agent name (legacy alias of trmm_agents.agent_name) |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroup": 0,
      "name": "string",
      "description": "string",
      "idOs": 0,
      "osVersion": "string",
      "inputs": [
        {
          "name": "string",
          "type": "string",
          "macro": "string",
          "tip": "string",
          "value": "string",
          "file_name": "string"
        }
      ],
      "notifyBeforeRun": false,
      "eventResponse": false,
      "preconditionEnabled": false,
      "preconditionParameters": "string",
      "preconditionInterpreter": "string",
      "preconditionExtension": "string",
      "preconditionCode": "string",
      "scriptParameters": "string",
      "scriptInterpreter": "string",
      "scriptExtension": "string",
      "scriptCode": "string",
      "postconditionEnabled": false,
      "postconditionParameters": "string",
      "postconditionInterpreter": "string",
      "postconditionExtension": "string",
      "postconditionCode": "string"
    }
    ```

### Model: RmmSettings { #model-rmmsettings }

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | integer, nullable |  | RMM settings id |
| `allowList` | string, nullable |  | Packages allowed to be updated, one per line |
| `denyList` | string, nullable |  | Packages not allowed to be updated, one per line |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "allowList": "string",
      "denyList": "string"
    }
    ```
