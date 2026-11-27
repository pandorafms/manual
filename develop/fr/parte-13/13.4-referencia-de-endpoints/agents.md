# Agents

Agents and the data attached to them: custom fields, extended data, collections and secondary groups.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-post">POST</span> | [`/agent`](#post-agent) | Creates an agent |
| <span class="api-method api-get">GET</span> | [`/agent/{idAgent}`](#get-agent-idagent) | Gets an agent |
| <span class="api-method api-put">PUT</span> | [`/agent/{idAgent}`](#put-agent-idagent) | Updates an agent |
| <span class="api-method api-delete">DELETE</span> | [`/agent/{idAgent}`](#delete-agent-idagent) | Deletes an agent |
| <span class="api-method api-get">GET</span> | [`/agent/summary`](#get-agent-summary) | Agent counters grouped by status |
| <span class="api-method api-get">GET</span> | [`/agent/list`](#get-agent-list) | Lists agents |
| <span class="api-method api-post">POST</span> | [`/agent/list`](#post-agent-list) | Lists agents |
| <span class="api-method api-get">GET</span> | [`/agent/{idAgent}/policy/list`](#get-agent-idagent-policy-list) | List the policies linked to an agent |
| <span class="api-method api-get">GET</span> | [`/agent/publicIp/list`](#get-agent-publicip-list) | List agents with a public IPv4 in any associated address |
| <span class="api-method api-post">POST</span> | [`/agent/publicIp/list`](#post-agent-publicip-list) | List public-IP agents with advanced filters |
| <span class="api-method api-get">GET</span> | [`/agent/{idAgent}/status`](#get-agent-idagent-status) | Gets the calculated status of an agent |
| <span class="api-method api-get">GET</span> | [`/agent/{idAgent}/customField/{idField}`](#get-agent-idagent-customfield-idfield) | Get an agent custom field value |
| <span class="api-method api-put">PUT</span> | [`/agent/{idAgent}/customField/{idField}`](#put-agent-idagent-customfield-idfield) | Create or update an agent custom field value |
| <span class="api-method api-delete">DELETE</span> | [`/agent/{idAgent}/customField/{idField}`](#delete-agent-idagent-customfield-idfield) | Clear an agent custom field value |
| <span class="api-method api-get">GET</span> | [`/agent/{idAgent}/customField/list`](#get-agent-idagent-customfield-list) | List the custom field values of an agent through query filters |
| <span class="api-method api-post">POST</span> | [`/agent/{idAgent}/customField/list`](#post-agent-idagent-customfield-list) | List the custom field values of an agent |
| <span class="api-method api-post">POST</span> | [`/agentCustomField`](#post-agentcustomfield) | Create an agent custom field |
| <span class="api-method api-get">GET</span> | [`/agentCustomField/{idField}`](#get-agentcustomfield-idfield) | Get an agent custom field |
| <span class="api-method api-put">PUT</span> | [`/agentCustomField/{idField}`](#put-agentcustomfield-idfield) | Update an agent custom field |
| <span class="api-method api-delete">DELETE</span> | [`/agentCustomField/{idField}`](#delete-agentcustomfield-idfield) | Delete an agent custom field |
| <span class="api-method api-get">GET</span> | [`/agentCustomField/list`](#get-agentcustomfield-list) | List agent custom fields through query filters |
| <span class="api-method api-post">POST</span> | [`/agentCustomField/list`](#post-agentcustomfield-list) | List agent custom fields |
| <span class="api-method api-post">POST</span> | [`/agentExtendedData`](#post-agentextendeddata) | Creates a new agent extended data |
| <span class="api-method api-get">GET</span> | [`/agentExtendedData/{id}`](#get-agentextendeddata-id) | Get agent extended data |
| <span class="api-method api-put">PUT</span> | [`/agentExtendedData/{id}`](#put-agentextendeddata-id) | Updates agent extended data |
| <span class="api-method api-delete">DELETE</span> | [`/agentExtendedData/{id}`](#delete-agentextendeddata-id) | Deletes agent extended data object. |
| <span class="api-method api-get">GET</span> | [`/agentExtendedData/list`](#get-agentextendeddata-list) | List agent extended data using query filters |
| <span class="api-method api-post">POST</span> | [`/agentExtendedData/list`](#post-agentextendeddata-list) | List agent extended data |
| <span class="api-method api-post">POST</span> | [`/agent/{idAgent}/collection/{idCollection}`](#post-agent-idagent-collection-idcollection) | Assign a collection to an agent remote configuration, without applying the collection |
| <span class="api-method api-delete">DELETE</span> | [`/agent/{idAgent}/collection/{idCollection}`](#delete-agent-idagent-collection-idcollection) | Remove a collection assignment |
| <span class="api-method api-get">GET</span> | [`/agent/{idAgent}/collection/list`](#get-agent-idagent-collection-list) | List collections assigned to an agent |
| <span class="api-method api-post">POST</span> | [`/agent/{idAgent}/collection/list`](#post-agent-idagent-collection-list) | List assigned collections with JSON options |
| <span class="api-method api-post">POST</span> | [`/agent/{idAgent}/secondaryGroup`](#post-agent-idagent-secondarygroup) | Adds one secondary group to an agent |
| <span class="api-method api-delete">DELETE</span> | [`/agent/{idAgent}/secondaryGroup/{idGroup}`](#delete-agent-idagent-secondarygroup-idgroup) | Removes one secondary group from an agent |
| <span class="api-method api-get">GET</span> | [`/agent/{idAgent}/secondaryGroup/list`](#get-agent-idagent-secondarygroup-list) | Lists the secondary groups assigned to an agent |
| <span class="api-method api-post">POST</span> | [`/agent/{idAgent}/secondaryGroup/list`](#post-agent-idagent-secondarygroup-list) | Lists the secondary groups assigned to an agent |

## Agents

API Endpoints for agents

### <span class="api-method api-post">POST</span> `/agent` { #post-agent }

Creates an agent

On a metaconsole serverId is required. The returned idAgent is the cache ID. A replication failure after the node write returns an error identifying the applied operation; do not retry creation automatically.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgentNode` | integer, nullable |  | Original agent ID on the node |
| `serverId` | integer, nullable |  | Source node ID on a metaconsole |
| `idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
| `name` | string |  | Agent name |
| `address` | string, nullable |  | Agent address |
| `comments` | string, nullable |  | Agent comments |
| `idGroup` | integer | yes | Group ID |
| `lastContact` | string |  | Last contact timestamp |
| `mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
| `interval` | integer |  | Agent interval in seconds |
| `idOs` | integer, nullable |  | Operating System ID |
| `osVersion` | string, nullable |  | Operating System version |
| `osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
| `osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
| `agentVersion` | string, nullable |  | Agent version |
| `lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
| `disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
| `remote` | integer |  | Remote agent flag |
| `idParent` | integer, nullable |  | Parent agent ID |
| `customId` | string, nullable |  | Custom agent ID |
| `serverName` | string, nullable |  | Server name |
| `cascadeProtection` | integer |  | Cascade protection flag |
| `cascadeProtectionModule` | integer |  | Cascade protection module ID |
| `timezoneOffset` | integer, nullable |  | Timezone offset in hours |
| `iconPath` | string, nullable |  | Icon path |
| `updateGisData` | integer |  | Update GIS data flag |
| `urlAddress` | string, nullable |  | URL address |
| `quiet` | integer |  | Quiet flag |
| `normalCount` | integer |  | Normal modules count |
| `warningCount` | integer |  | Warning modules count |
| `criticalCount` | integer |  | Critical modules count |
| `unknownCount` | integer |  | Unknown modules count |
| `notinitCount` | integer |  | Not init modules count |
| `totalCount` | integer |  | Total modules count |
| `firedCount` | integer |  | Fired alerts count |
| `updateModuleCount` | integer |  | Update module count flag |
| `updateAlertCount` | integer |  | Update alert count flag |
| `updateSecondaryGroups` | integer |  | Update secondary groups flag |
| `alias` | string | yes | Agent alias |
| `aliasAsName` | integer |  | Use alias as name flag |
| `safeModeModule` | integer |  | Safe mode module ID |
| `cps` | integer |  | CPS value |
| `cpsInhibit` | integer, nullable |  | CPS inhibition value |
| `satelliteServer` | integer |  | Satellite server ID |
| `fixedIp` | integer |  | Fixed IP flag |
| `disabledByDowntime` | integer |  | Disabled by downtime flag |
| `vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
| `ignoreUnknown` | integer |  | Ignore unknown flag |
| `balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
| `autoHa` | integer |  | Auto HA flag |
| `extraData` | string |  | Extra data |
| `quietByDowntime` | integer |  | Quiet by downtime flag |
| `idFimPolicy` | integer |  | FIM Policy ID |
| `name` | string |  | Internal name generated as SHA-256. Set aliasAsName to 1 to use alias instead. |
| `alias` | string | yes | Human-readable agent name |
| `aliasAsName` | enum: `0`, `1` |  | Set to 1 to use alias as the internal name; otherwise the API generates the internal name |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "address": "string",
      "comments": "string",
      "idGroup": 0,
      "mode": "learning",
      "interval": 300,
      "idOs": 0,
      "osVersion": "string",
      "agentVersion": "string",
      "disabled": 0,
      "remote": 0,
      "idParent": 0,
      "customId": "string",
      "serverName": "string",
      "cascadeProtection": 0,
      "cascadeProtectionModule": 0,
      "timezoneOffset": 0,
      "iconPath": "string",
      "updateGisData": 1,
      "urlAddress": "string",
      "quiet": 0,
      "updateModuleCount": 0,
      "updateAlertCount": 0,
      "updateSecondaryGroups": 0,
      "alias": "string",
      "aliasAsName": 0,
      "safeModeModule": 0,
      "cps": 0,
      "cpsInhibit": 0,
      "satelliteServer": 0,
      "fixedIp": 0,
      "disabledByDowntime": 0,
      "vulScanEnabled": "disabled",
      "ignoreUnknown": 0,
      "balanceType": "none",
      "autoHa": 1,
      "extraData": "string",
      "quietByDowntime": -1,
      "idFimPolicy": 0
    }
    ```

**Response 200**: Agent object

Schema: [`Agent`](#model-agent)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/agent/{idAgent}` { #get-agent-idagent }

Gets an agent

Reads the local agent table on a node and the agent cache on a metaconsole.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |

**Response 200**: Agent object

Schema: [`Agent`](#model-agent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/agent/{idAgent}` { #put-agent-idagent }

Updates an agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgentNode` | integer, nullable |  | Original agent ID on the node |
| `serverId` | integer, nullable |  | Source node ID on a metaconsole |
| `idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
| `name` | string |  | Agent name |
| `address` | string, nullable |  | Agent address |
| `comments` | string, nullable |  | Agent comments |
| `idGroup` | integer |  | Group ID |
| `lastContact` | string |  | Last contact timestamp |
| `mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
| `interval` | integer |  | Agent interval in seconds |
| `idOs` | integer, nullable |  | Operating System ID |
| `osVersion` | string, nullable |  | Operating System version |
| `agentVersion` | string, nullable |  | Agent version |
| `lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
| `disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
| `remote` | integer |  | Remote agent flag |
| `idParent` | integer, nullable |  | Parent agent ID |
| `customId` | string, nullable |  | Custom agent ID |
| `serverName` | string, nullable |  | Server name |
| `cascadeProtection` | integer |  | Cascade protection flag |
| `cascadeProtectionModule` | integer |  | Cascade protection module ID |
| `timezoneOffset` | integer, nullable |  | Timezone offset in hours |
| `iconPath` | string, nullable |  | Icon path |
| `updateGisData` | integer |  | Update GIS data flag |
| `urlAddress` | string, nullable |  | URL address |
| `quiet` | integer |  | Quiet flag |
| `normalCount` | integer |  | Normal modules count |
| `warningCount` | integer |  | Warning modules count |
| `criticalCount` | integer |  | Critical modules count |
| `unknownCount` | integer |  | Unknown modules count |
| `notinitCount` | integer |  | Not init modules count |
| `totalCount` | integer |  | Total modules count |
| `firedCount` | integer |  | Fired alerts count |
| `updateModuleCount` | integer |  | Update module count flag |
| `updateAlertCount` | integer |  | Update alert count flag |
| `updateSecondaryGroups` | integer |  | Update secondary groups flag |
| `alias` | string |  | Agent alias |
| `aliasAsName` | integer |  | Use alias as name flag |
| `safeModeModule` | integer |  | Safe mode module ID |
| `cps` | integer |  | CPS value |
| `cpsInhibit` | integer, nullable |  | CPS inhibition value |
| `satelliteServer` | integer |  | Satellite server ID |
| `fixedIp` | integer |  | Fixed IP flag |
| `disabledByDowntime` | integer |  | Disabled by downtime flag |
| `vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
| `ignoreUnknown` | integer |  | Ignore unknown flag |
| `balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
| `autoHa` | integer |  | Auto HA flag |
| `extraData` | string |  | Extra data |
| `quietByDowntime` | integer |  | Quiet by downtime flag |
| `idFimPolicy` | integer |  | FIM Policy ID |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "address": "string",
      "comments": "string",
      "idGroup": 0,
      "mode": "learning",
      "interval": 300,
      "idOs": 0,
      "osVersion": "string",
      "agentVersion": "string",
      "disabled": 0,
      "remote": 0,
      "idParent": 0,
      "customId": "string",
      "serverName": "string",
      "cascadeProtection": 0,
      "cascadeProtectionModule": 0,
      "timezoneOffset": 0,
      "iconPath": "string",
      "updateGisData": 1,
      "urlAddress": "string",
      "quiet": 0,
      "updateModuleCount": 0,
      "updateAlertCount": 0,
      "updateSecondaryGroups": 0,
      "alias": "string",
      "aliasAsName": 0,
      "safeModeModule": 0,
      "cps": 0,
      "cpsInhibit": 0,
      "satelliteServer": 0,
      "fixedIp": 0,
      "disabledByDowntime": 0,
      "vulScanEnabled": "disabled",
      "ignoreUnknown": 0,
      "balanceType": "none",
      "autoHa": 1,
      "extraData": "string",
      "quietByDowntime": -1,
      "idFimPolicy": 0
    }
    ```

**Response 200**: Agent object

Schema: [`Agent`](#model-agent)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-delete">DELETE</span> `/agent/{idAgent}` { #delete-agent-idagent }

Deletes an agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/agent/summary` { #get-agent-summary }

Agent counters grouped by status

**Response 200**: Agent summary

??? note "Response fields (6 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `total` | integer |  |  |
    | `normal` | integer |  |  |
    | `warning` | integer |  |  |
    | `critical` | integer |  |  |
    | `unknown` | integer |  |  |
    | `notInit` | integer |  |  |


Error responses: `401`, `403`, `500`.

### <span class="api-method api-get">GET</span> `/agent/list` { #get-agent-list }

Lists agents

Lists the local agent table on a node and the agent cache on a metaconsole,
without contacting nodes.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Array of Agent objects

Schema: list of [`Agent`](#model-agent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/agent/list` { #post-agent-list }

Lists agents

Lists the local agent table on a node and the agent cache on a metaconsole,
without contacting nodes.

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
| `idAgentNode` | integer, nullable |  | Original agent ID on the node |
| `serverId` | integer, nullable |  | Source node ID on a metaconsole |
| `idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
| `name` | string |  | Agent name |
| `address` | string, nullable |  | Agent address |
| `comments` | string, nullable |  | Agent comments |
| `idGroup` | integer |  | Group ID |
| `lastContact` | string |  | Last contact timestamp |
| `mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
| `interval` | integer |  | Agent interval in seconds |
| `idOs` | integer, nullable |  | Operating System ID |
| `osVersion` | string, nullable |  | Operating System version |
| `osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
| `osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
| `agentVersion` | string, nullable |  | Agent version |
| `lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
| `disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
| `remote` | integer |  | Remote agent flag |
| `idParent` | integer, nullable |  | Parent agent ID |
| `customId` | string, nullable |  | Custom agent ID |
| `serverName` | string, nullable |  | Server name |
| `cascadeProtection` | integer |  | Cascade protection flag |
| `cascadeProtectionModule` | integer |  | Cascade protection module ID |
| `timezoneOffset` | integer, nullable |  | Timezone offset in hours |
| `iconPath` | string, nullable |  | Icon path |
| `updateGisData` | integer |  | Update GIS data flag |
| `urlAddress` | string, nullable |  | URL address |
| `quiet` | integer |  | Quiet flag |
| `normalCount` | integer |  | Normal modules count |
| `warningCount` | integer |  | Warning modules count |
| `criticalCount` | integer |  | Critical modules count |
| `unknownCount` | integer |  | Unknown modules count |
| `notinitCount` | integer |  | Not init modules count |
| `totalCount` | integer |  | Total modules count |
| `firedCount` | integer |  | Fired alerts count |
| `updateModuleCount` | integer |  | Update module count flag |
| `updateAlertCount` | integer |  | Update alert count flag |
| `updateSecondaryGroups` | integer |  | Update secondary groups flag |
| `alias` | string |  | Agent alias |
| `aliasAsName` | integer |  | Use alias as name flag |
| `safeModeModule` | integer |  | Safe mode module ID |
| `cps` | integer |  | CPS value |
| `cpsInhibit` | integer, nullable |  | CPS inhibition value |
| `satelliteServer` | integer |  | Satellite server ID |
| `fixedIp` | integer |  | Fixed IP flag |
| `disabledByDowntime` | integer |  | Disabled by downtime flag |
| `vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
| `ignoreUnknown` | integer |  | Ignore unknown flag |
| `balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
| `autoHa` | integer |  | Auto HA flag |
| `extraData` | string |  | Extra data |
| `quietByDowntime` | integer |  | Quiet by downtime flag |
| `idFimPolicy` | integer |  | FIM Policy ID |
| `idAgent` |  |  |  |
| `serverId` |  |  | Filter cached agents by node; metaconsole only |
| `idAgentNode` |  |  | Filter by original node agent ID; metaconsole only |
| `freeSearch` | string, nullable |  | Find text in name, alias and address fields. |
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
| `multipleSearch.field` | enum: `idAgent`, `name`, `alias`, `address`, `idGroup`, `disabled`, `idOs`, `lastContact`, `osName`, `osImagePath`, `normalCount`, `warningCount`, `criticalCount`, `unknownCount`, `notinitCount`, `totalCount`, `firedCount` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAgent`, `name`, `alias`, `address`, `idGroup`, `disabled`, `idOs`, `lastContact`, `osName`, `osImagePath`, `normalCount`, `warningCount`, `criticalCount`, `unknownCount`, `notinitCount`, `totalCount`, `firedCount` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "address": "string",
      "comments": "string",
      "idGroup": 0,
      "mode": "learning",
      "interval": 300,
      "idOs": 0,
      "osVersion": "string",
      "agentVersion": "string",
      "disabled": 0,
      "remote": 0,
      "idParent": 0,
      "customId": "string",
      "serverName": "string",
      "cascadeProtection": 0,
      "cascadeProtectionModule": 0,
      "timezoneOffset": 0,
      "iconPath": "string",
      "updateGisData": 1,
      "urlAddress": "string",
      "quiet": 0,
      "updateModuleCount": 0,
      "updateAlertCount": 0,
      "updateSecondaryGroups": 0,
      "alias": "string",
      "aliasAsName": 0,
      "safeModeModule": 0,
      "cps": 0,
      "cpsInhibit": 0,
      "satelliteServer": 0,
      "fixedIp": 0,
      "disabledByDowntime": 0,
      "vulScanEnabled": "disabled",
      "ignoreUnknown": 0,
      "balanceType": "none",
      "autoHa": 1,
      "extraData": "string",
      "quietByDowntime": -1,
      "idFimPolicy": 0,
      "idAgent": null,
      "serverId": null,
      "idAgentNode": null,
      "freeSearch": "string",
      "requestedFields": [
        "idAgent"
      ],
      "fieldConditions": [
        {
          "field": "idAgent",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idAgent",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAgent",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Array of Agent objects

Schema: list of [`Agent`](#model-agent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/agent/{idAgent}/policy/list` { #get-agent-idagent-policy-list }

List the policies linked to an agent

Requires AR on the agent and AW policy visibility.
On a metaconsole, idAgent is the cached agent ID and its node serves the query.
Associations pending removal remain linked until removed.
Results and totals are scoped before pagination.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `page` | query | integer |  |  |
| `sizePage` | query | integer |  |  |
| `sortField` | query | enum: `idPolicy`, `name`, `description`, `idGroup`, `status`, `forceApply`, `applyToSecondaryGroups`, `createLinkedModules` |  |  |
| `sortDirection` | query | enum: `ASC`, `DESC` |  |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Visible linked policies

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


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/agent/publicIp/list` { #get-agent-publicip-list }

List agents with a public IPv4 in any associated address

Only 10/8, 172.16/12, 192.168/16 and loopback 127/8 are excluded by this contract.
All other valid IPv4 addresses are public, including special-purpose ranges. IPv6 is not classified.
Query filters are supported. On a metaconsole, enabled nodes supply their addresses
and cached agent IDs are returned.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `filters` | query | object |  |  |

**Response 200**: Agents with at least one public IPv4

??? note "Response fields (64 fields)"

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
    | `data.[].idAgentNode` | integer, nullable |  | Original agent ID on the node |
    | `data.[].serverId` | integer, nullable |  | Source node ID on a metaconsole |
    | `data.[].idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
    | `data.[].name` | string |  | Agent name |
    | `data.[].address` | string, nullable |  | Agent address |
    | `data.[].comments` | string, nullable |  | Agent comments |
    | `data.[].idGroup` | integer |  | Group ID |
    | `data.[].lastContact` | string |  | Last contact timestamp |
    | `data.[].mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
    | `data.[].interval` | integer |  | Agent interval in seconds |
    | `data.[].idOs` | integer, nullable |  | Operating System ID |
    | `data.[].osVersion` | string, nullable |  | Operating System version |
    | `data.[].osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].agentVersion` | string, nullable |  | Agent version |
    | `data.[].lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
    | `data.[].disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
    | `data.[].remote` | integer |  | Remote agent flag |
    | `data.[].idParent` | integer, nullable |  | Parent agent ID |
    | `data.[].customId` | string, nullable |  | Custom agent ID |
    | `data.[].serverName` | string, nullable |  | Server name |
    | `data.[].cascadeProtection` | integer |  | Cascade protection flag |
    | `data.[].cascadeProtectionModule` | integer |  | Cascade protection module ID |
    | `data.[].timezoneOffset` | integer, nullable |  | Timezone offset in hours |
    | `data.[].iconPath` | string, nullable |  | Icon path |
    | `data.[].updateGisData` | integer |  | Update GIS data flag |
    | `data.[].urlAddress` | string, nullable |  | URL address |
    | `data.[].quiet` | integer |  | Quiet flag |
    | `data.[].normalCount` | integer |  | Normal modules count |
    | `data.[].warningCount` | integer |  | Warning modules count |
    | `data.[].criticalCount` | integer |  | Critical modules count |
    | `data.[].unknownCount` | integer |  | Unknown modules count |
    | `data.[].notinitCount` | integer |  | Not init modules count |
    | `data.[].totalCount` | integer |  | Total modules count |
    | `data.[].firedCount` | integer |  | Fired alerts count |
    | `data.[].updateModuleCount` | integer |  | Update module count flag |
    | `data.[].updateAlertCount` | integer |  | Update alert count flag |
    | `data.[].updateSecondaryGroups` | integer |  | Update secondary groups flag |
    | `data.[].alias` | string |  | Agent alias |
    | `data.[].aliasAsName` | integer |  | Use alias as name flag |
    | `data.[].safeModeModule` | integer |  | Safe mode module ID |
    | `data.[].cps` | integer |  | CPS value |
    | `data.[].cpsInhibit` | integer, nullable |  | CPS inhibition value |
    | `data.[].satelliteServer` | integer |  | Satellite server ID |
    | `data.[].fixedIp` | integer |  | Fixed IP flag |
    | `data.[].disabledByDowntime` | integer |  | Disabled by downtime flag |
    | `data.[].vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
    | `data.[].ignoreUnknown` | integer |  | Ignore unknown flag |
    | `data.[].balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
    | `data.[].autoHa` | integer |  | Auto HA flag |
    | `data.[].extraData` | string |  | Extra data |
    | `data.[].quietByDowntime` | integer |  | Quiet by downtime flag |
    | `data.[].idFimPolicy` | integer |  | FIM Policy ID |
    | `data.[].publicIps` | array of string (ipv4) |  | Unique public IPv4 addresses from the primary and all associated addresses |


Error responses: `400`, `401`, `403`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/agent/publicIp/list` { #post-agent-publicip-list }

List public-IP agents with advanced filters

Body filters override query filters. Only RFC1918 IPv4 blocks and loopback 127/8 are excluded.
Both pagination totals count agents, not addresses. Public IPs are deduplicated.

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
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idAgent` | integer |  |  |
| `name` | string |  |  |
| `alias` | string |  |  |
| `address` | string |  | Exact primary address |
| `idGroup` | integer |  |  |
| `disabled` | enum: `0`, `1` |  |  |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `limit` | integer |  |  |
| `offset` | integer |  |  |
| `serverId` | integer |  | Cached node filter; metaconsole only |
| `idAgentNode` | integer |  | Original agent ID; metaconsole only |
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
| `multipleSearch.field` | enum: `idAgent`, `name`, `alias`, `address`, `idGroup`, `disabled` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAgent`, `name`, `alias`, `address`, `idGroup`, `disabled` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idAgent"
      ],
      "fieldConditions": [
        {
          "field": "idAgent",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idAgent": 0,
      "name": "string",
      "alias": "string",
      "address": "string",
      "idGroup": 0,
      "disabled": 0,
      "serverId": 0,
      "idAgentNode": 0,
      "freeSearch": "string",
      "multipleSearch": {
        "field": "idAgent",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAgent",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Agents with at least one public IPv4

??? note "Response fields (64 fields)"

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
    | `data.[].idAgentNode` | integer, nullable |  | Original agent ID on the node |
    | `data.[].serverId` | integer, nullable |  | Source node ID on a metaconsole |
    | `data.[].idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
    | `data.[].name` | string |  | Agent name |
    | `data.[].address` | string, nullable |  | Agent address |
    | `data.[].comments` | string, nullable |  | Agent comments |
    | `data.[].idGroup` | integer |  | Group ID |
    | `data.[].lastContact` | string |  | Last contact timestamp |
    | `data.[].mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
    | `data.[].interval` | integer |  | Agent interval in seconds |
    | `data.[].idOs` | integer, nullable |  | Operating System ID |
    | `data.[].osVersion` | string, nullable |  | Operating System version |
    | `data.[].osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `data.[].agentVersion` | string, nullable |  | Agent version |
    | `data.[].lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
    | `data.[].disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
    | `data.[].remote` | integer |  | Remote agent flag |
    | `data.[].idParent` | integer, nullable |  | Parent agent ID |
    | `data.[].customId` | string, nullable |  | Custom agent ID |
    | `data.[].serverName` | string, nullable |  | Server name |
    | `data.[].cascadeProtection` | integer |  | Cascade protection flag |
    | `data.[].cascadeProtectionModule` | integer |  | Cascade protection module ID |
    | `data.[].timezoneOffset` | integer, nullable |  | Timezone offset in hours |
    | `data.[].iconPath` | string, nullable |  | Icon path |
    | `data.[].updateGisData` | integer |  | Update GIS data flag |
    | `data.[].urlAddress` | string, nullable |  | URL address |
    | `data.[].quiet` | integer |  | Quiet flag |
    | `data.[].normalCount` | integer |  | Normal modules count |
    | `data.[].warningCount` | integer |  | Warning modules count |
    | `data.[].criticalCount` | integer |  | Critical modules count |
    | `data.[].unknownCount` | integer |  | Unknown modules count |
    | `data.[].notinitCount` | integer |  | Not init modules count |
    | `data.[].totalCount` | integer |  | Total modules count |
    | `data.[].firedCount` | integer |  | Fired alerts count |
    | `data.[].updateModuleCount` | integer |  | Update module count flag |
    | `data.[].updateAlertCount` | integer |  | Update alert count flag |
    | `data.[].updateSecondaryGroups` | integer |  | Update secondary groups flag |
    | `data.[].alias` | string |  | Agent alias |
    | `data.[].aliasAsName` | integer |  | Use alias as name flag |
    | `data.[].safeModeModule` | integer |  | Safe mode module ID |
    | `data.[].cps` | integer |  | CPS value |
    | `data.[].cpsInhibit` | integer, nullable |  | CPS inhibition value |
    | `data.[].satelliteServer` | integer |  | Satellite server ID |
    | `data.[].fixedIp` | integer |  | Fixed IP flag |
    | `data.[].disabledByDowntime` | integer |  | Disabled by downtime flag |
    | `data.[].vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
    | `data.[].ignoreUnknown` | integer |  | Ignore unknown flag |
    | `data.[].balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
    | `data.[].autoHa` | integer |  | Auto HA flag |
    | `data.[].extraData` | string |  | Extra data |
    | `data.[].quietByDowntime` | integer |  | Quiet by downtime flag |
    | `data.[].idFimPolicy` | integer |  | FIM Policy ID |
    | `data.[].publicIps` | array of string (ipv4) |  | Unique public IPv4 addresses from the primary and all associated addresses |


Error responses: `400`, `401`, `403`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/agent/{idAgent}/status` { #get-agent-idagent-status }

Gets the calculated status of an agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `withoutAlerts` | query | boolean |  |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Calculated agent status

??? note "Response fields (5 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAgent` | integer |  |  |
    | `status` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `100`, `200`, `300` |  |  |
    | `statusName` | enum: `normal`, `critical`, `warning`, `unknown`, `alert_fired`, `not_init`, `critical_alert`, `warning_alert`, `normal_alert` |  |  |
    | `withoutAlerts` | boolean |  |  |
    | `serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

## AgentCustomFields

API Endpoints for agent custom fields and their agent values

### <span class="api-method api-get">GET</span> `/agent/{idAgent}/customField/{idField}` { #get-agent-idagent-customfield-idfield }

Get an agent custom field value

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idField` | path | integer | yes | Agent custom field identifier |

**Response 200**: Agent custom field value

Schema: [`AgentCustomData`](#model-agentcustomdata)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/agent/{idAgent}/customField/{idField}` { #put-agent-idagent-customfield-idfield }

Create or update an agent custom field value

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idField` | path | integer | yes | Agent custom field identifier |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `description` | string, nullable |  | Agent custom field value. Password fields accept null to keep the stored value. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "description": "string"
    }
    ```

**Response 200**: Agent custom field value

Schema: [`AgentCustomData`](#model-agentcustomdata)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/agent/{idAgent}/customField/{idField}` { #delete-agent-idagent-customfield-idfield }

Clear an agent custom field value

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idField` | path | integer | yes | Agent custom field identifier |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/agent/{idAgent}/customField/list` { #get-agent-idagent-customfield-list }

List the custom field values of an agent through query filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Agent custom data list

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
    | `data.[].idField` | integer |  | Agent custom field identifier |
    | `data.[].idAgent` | integer |  | Agent identifier |
    | `data.[].name` | string, nullable |  | Agent custom field name |
    | `data.[].description` | string, nullable |  | Agent custom field value. Password fields are masked. |
    | `data.[].isPasswordType` | boolean, nullable |  | Whether the field value is handled as a password |
    | `data.[].displayOnFront` | boolean, nullable |  | Whether the field is shown in the agent front view |
    | `data.[].isLinkEnabled` | boolean, nullable |  | Whether the field value is a JSON [text, url] link |
    | `data.[].serverId` | integer, nullable |  | Source node identifier when the value comes from a metaconsole |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/agent/{idAgent}/customField/list` { #post-agent-idagent-customfield-list }

List the custom field values of an agent

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
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idField` | integer |  |  |
| `freeSearch` | string, nullable |  | Search text in the field name |
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
| `multipleSearch.field` | enum: `idField`, `idAgent`, `name`, `description` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idField`, `idAgent`, `name`, `description` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idField"
      ],
      "fieldConditions": [
        {
          "field": "idField",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idField": 0,
      "freeSearch": "string",
      "multipleSearch": {
        "field": "idField",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idField",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Agent custom data list

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
    | `data.[].idField` | integer |  | Agent custom field identifier |
    | `data.[].idAgent` | integer |  | Agent identifier |
    | `data.[].name` | string, nullable |  | Agent custom field name |
    | `data.[].description` | string, nullable |  | Agent custom field value. Password fields are masked. |
    | `data.[].isPasswordType` | boolean, nullable |  | Whether the field value is handled as a password |
    | `data.[].displayOnFront` | boolean, nullable |  | Whether the field is shown in the agent front view |
    | `data.[].isLinkEnabled` | boolean, nullable |  | Whether the field value is a JSON [text, url] link |
    | `data.[].serverId` | integer, nullable |  | Source node identifier when the value comes from a metaconsole |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/agentCustomField` { #post-agentcustomfield }

Create an agent custom field

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idField` | integer |  | Agent custom field identifier |
| `name` | string |  | Unique agent custom field name |
| `displayOnFront` | boolean |  | Whether the field is shown in the agent front view |
| `isPasswordType` | boolean |  | Whether the field value is handled as a password |
| `comboValues` | string, nullable |  | Comma separated values for combo fields |
| `isLinkEnabled` | boolean |  | Whether the field value is rendered as a link |
| `serverId` | integer, nullable |  | Source node identifier when the field comes from a metaconsole |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "displayOnFront": false,
      "isPasswordType": false,
      "comboValues": "string",
      "isLinkEnabled": false
    }
    ```

**Response 200**: Agent custom field

Schema: [`AgentCustomField`](#model-agentcustomfield)

Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-get">GET</span> `/agentCustomField/{idField}` { #get-agentcustomfield-idfield }

Get an agent custom field

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idField` | path | integer | yes | Agent custom field identifier |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Agent custom field

Schema: [`AgentCustomField`](#model-agentcustomfield)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/agentCustomField/{idField}` { #put-agentcustomfield-idfield }

Update an agent custom field

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idField` | path | integer | yes | Agent custom field identifier |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string |  |  |
| `displayOnFront` | boolean |  |  |
| `isPasswordType` | boolean |  |  |
| `comboValues` | string, nullable |  |  |
| `isLinkEnabled` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "displayOnFront": false,
      "isPasswordType": false,
      "comboValues": "string",
      "isLinkEnabled": false
    }
    ```

**Response 200**: Agent custom field

Schema: [`AgentCustomField`](#model-agentcustomfield)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/agentCustomField/{idField}` { #delete-agentcustomfield-idfield }

Delete an agent custom field

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idField` | path | integer | yes | Agent custom field identifier |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/agentCustomField/list` { #get-agentcustomfield-list }

List agent custom fields through query filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Agent custom field list

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
    | `data.[].idField` | integer |  | Agent custom field identifier |
    | `data.[].name` | string |  | Unique agent custom field name |
    | `data.[].displayOnFront` | boolean |  | Whether the field is shown in the agent front view |
    | `data.[].isPasswordType` | boolean |  | Whether the field value is handled as a password |
    | `data.[].comboValues` | string, nullable |  | Comma separated values for combo fields |
    | `data.[].isLinkEnabled` | boolean |  | Whether the field value is rendered as a link |
    | `data.[].serverId` | integer, nullable |  | Source node identifier when the field comes from a metaconsole |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/agentCustomField/list` { #post-agentcustomfield-list }

List agent custom fields

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
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `idField` | integer |  |  |
| `freeSearch` | string, nullable |  | Search text in the field name |
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
| `multipleSearch.field` | enum: `idField`, `name`, `displayOnFront`, `isPasswordType`, `comboValues`, `isLinkEnabled` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idField`, `name`, `displayOnFront`, `isPasswordType`, `comboValues`, `isLinkEnabled` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idField"
      ],
      "fieldConditions": [
        {
          "field": "idField",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idField": 0,
      "freeSearch": "string",
      "multipleSearch": {
        "field": "idField",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idField",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Agent custom field list

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
    | `data.[].idField` | integer |  | Agent custom field identifier |
    | `data.[].name` | string |  | Unique agent custom field name |
    | `data.[].displayOnFront` | boolean |  | Whether the field is shown in the agent front view |
    | `data.[].isPasswordType` | boolean |  | Whether the field value is handled as a password |
    | `data.[].comboValues` | string, nullable |  | Comma separated values for combo fields |
    | `data.[].isLinkEnabled` | boolean |  | Whether the field value is rendered as a link |
    | `data.[].serverId` | integer, nullable |  | Source node identifier when the field comes from a metaconsole |


Error responses: `400`, `401`, `403`, `500`.

## AgentExtendedData

API Endpoints for agent extended data

### <span class="api-method api-post">POST</span> `/agentExtendedData` { #post-agentextendeddata }

Creates a new agent extended data

Creates locally on a node. On a metaconsole, serverId is required and selects the target node.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | integer |  | Extended data ID |
| `idAgente` | integer | yes | Agent ID |
| `name` | string | yes | Name of the extended data |
| `category` | enum: `info`, `hardware`, `software` |  | Category of the extended data |
| `data` | object, nullable |  | JSON data object |
| `timestamp` | integer |  | Unix timestamp |
| `serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgente": 0,
      "name": "string",
      "category": "info",
      "data": {},
      "timestamp": 0
    }
    ```

**Response 200**: AgentExtendedData object

Schema: [`AgentExtendedData`](#model-agentextendeddata)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/agentExtendedData/{id}` { #get-agentextendeddata-id }

Get agent extended data

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | Extended data id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: AgentExtendedData object

Schema: [`AgentExtendedData`](#model-agentextendeddata)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/agentExtendedData/{id}` { #put-agentextendeddata-id }

Updates agent extended data

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | Extended data id |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | integer |  | Extended data ID |
| `idAgente` | integer |  | Agent ID |
| `name` | string |  | Name of the extended data |
| `category` | enum: `info`, `hardware`, `software` |  | Category of the extended data |
| `data` | object, nullable |  | JSON data object |
| `timestamp` | integer |  | Unix timestamp |
| `serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgente": 0,
      "name": "string",
      "category": "info",
      "data": {},
      "timestamp": 0
    }
    ```

**Response 200**: AgentExtendedData object

Schema: [`AgentExtendedData`](#model-agentextendeddata)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/agentExtendedData/{id}` { #delete-agentextendeddata-id }

Deletes agent extended data object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | Extended data id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/agentExtendedData/list` { #get-agentextendeddata-list }

List agent extended data using query filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: List of agent extended data

Error responses: `400`, `401`, `403`.

### <span class="api-method api-post">POST</span> `/agentExtendedData/list` { #post-agentextendeddata-list }

List agent extended data

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | integer |  | Extended data ID |
| `idAgente` | integer |  | Agent ID |
| `name` | string |  | Name of the extended data |
| `category` | enum: `info`, `hardware`, `software` |  | Category of the extended data |
| `data` | object, nullable |  | JSON data object |
| `timestamp` | integer |  | Unix timestamp |
| `serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |
| `serverId` | integer, nullable |  | Node identifier. Required when listing from a metaconsole |
| `id` |  |  |  |
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
| `multipleSearch.field` | enum: `id`, `idAgente`, `name`, `category`, `timestamp` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `id`, `idAgente`, `name`, `category`, `timestamp` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgente": 0,
      "name": "string",
      "category": "info",
      "data": {},
      "timestamp": 0,
      "serverId": 0,
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

**Response 200**: List of agent extended data

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
    | `data.[].id` | integer |  | Extended data ID |
    | `data.[].idAgente` | integer |  | Agent ID |
    | `data.[].name` | string |  | Name of the extended data |
    | `data.[].category` | enum: `info`, `hardware`, `software` |  | Category of the extended data |
    | `data.[].data` | object, nullable |  | JSON data object |
    | `data.[].timestamp` | integer |  | Unix timestamp |
    | `data.[].serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |


Error responses: `400`, `401`, `403`, `404`, `500`.

## AgentCollections

Collections assigned to agent remote configurations

### <span class="api-method api-post">POST</span> `/agent/{idAgent}/collection/{idCollection}` { #post-agent-idagent-collection-idcollection }

Assign a collection to an agent remote configuration, without applying the collection

Idempotent. On a metaconsole idAgent is the cache ID and idCollection belongs to its node.
The agent's remote configuration .conf and .md5 files must already exist on the console that owns it.
Setting remote=1 alone does not guarantee availability. Missing configuration returns HTTP 400:
Agent remote configuration is unavailable.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idCollection` | path | integer | yes |  |

**Request body** (`application/json`)


**Response 200**: Assigned collection and target metadata

??? note "Response fields (11 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idCollection` | integer |  |  |
    | `name` | string |  |  |
    | `shortName` | string |  | Immutable after creation. Empty or omitted generates fc_<timestamp>. |
    | `idGroup` | integer |  |  |
    | `description` | string, nullable |  |  |
    | `status` | enum: `0`, `1` |  | Persisted status: 0 pending apply, 1 applied. Updating metadata sets 1 as in the console. |
    | `idAgent` | integer |  |  |
    | `idAgentNode` | integer, nullable |  |  |
    | `serverId` | integer, nullable |  |  |
    | `assigned` | boolean |  |  |
    | `changed` | boolean | yes | Assignment result only. False if already assigned; absent from list items. |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-delete">DELETE</span> `/agent/{idAgent}/collection/{idCollection}` { #delete-agent-idagent-collection-idcollection }

Remove a collection assignment

Idempotent. Does not delete the collection, its files or its package.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idCollection` | path | integer | yes |  |

**Response 200**: Assignment removed or already absent

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/agent/{idAgent}/collection/list` { #get-agent-idagent-collection-list }

List collections assigned to an agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `page` | query | integer |  |  |
| `sizePage` | query | integer |  |  |
| `freeSearch` | query | string |  |  |
| `sortField` | query | enum: `name`, `shortName`, `idCollection` |  |  |
| `sortDirection` | query | enum: `ASC`, `DESC` |  |  |

**Response 200**: Collections assigned in the remote configuration

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
    | `data` | array of AgentCollection |  |  |
    | `data.[].idCollection` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].shortName` | string |  | Immutable after creation. Empty or omitted generates fc_<timestamp>. |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].status` | enum: `0`, `1` |  | Persisted status: 0 pending apply, 1 applied. Updating metadata sets 1 as in the console. |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].idAgentNode` | integer, nullable |  |  |
    | `data.[].serverId` | integer, nullable |  |  |
    | `data.[].assigned` | boolean |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/agent/{idAgent}/collection/list` { #post-agent-idagent-collection-list }

List assigned collections with JSON options

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `freeSearch` | string |  |  |
| `sortField` | enum: `name`, `shortName`, `idCollection` |  |  |
| `sortDirection` | enum: `ASC`, `DESC` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "page": 0,
      "sizePage": 50,
      "freeSearch": "string",
      "sortField": "name",
      "sortDirection": "ASC"
    }
    ```

**Response 200**: Collections assigned in the remote configuration

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
    | `data` | array of AgentCollection |  |  |
    | `data.[].idCollection` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].shortName` | string |  | Immutable after creation. Empty or omitted generates fc_<timestamp>. |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].status` | enum: `0`, `1` |  | Persisted status: 0 pending apply, 1 applied. Updating metadata sets 1 as in the console. |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].idAgentNode` | integer, nullable |  |  |
    | `data.[].serverId` | integer, nullable |  |  |
    | `data.[].assigned` | boolean |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

## AgentSecondaryGroups

API Endpoints for secondary groups assigned to agents

### <span class="api-method api-post">POST</span> `/agent/{idAgent}/secondaryGroup` { #post-agent-idagent-secondarygroup }

Adds one secondary group to an agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |

**Request body** (`application/json`): [`AgentSecondaryGroup`](#model-agentsecondarygroup)

**Response 200**: Agent secondary group

Schema: [`AgentSecondaryGroup`](#model-agentsecondarygroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/agent/{idAgent}/secondaryGroup/{idGroup}` { #delete-agent-idagent-secondarygroup-idgroup }

Removes one secondary group from an agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `idGroup` | path | integer | yes | Secondary group id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/agent/{idAgent}/secondaryGroup/list` { #get-agent-idagent-secondarygroup-list }

Lists the secondary groups assigned to an agent

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Response 200**: Agent secondary groups list

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
    | `data.[].idAgent` | integer |  |  |
    | `data.[].idGroup` | integer | yes |  |
    | `data.[].idAgentNode` | integer, nullable |  |  |
    | `data.[].serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/agent/{idAgent}/secondaryGroup/list` { #post-agent-idagent-secondarygroup-list }

Lists the secondary groups assigned to an agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgent` | integer |  |  |
| `idGroup` | integer | yes |  |
| `idAgentNode` | integer, nullable |  |  |
| `serverId` | integer, nullable |  |  |
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
| `multipleSearch.field` | enum: `idAgent`, `idGroup` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAgent`, `idGroup` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroup": 0,
      "requestedFields": [
        "idAgent"
      ],
      "fieldConditions": [
        {
          "field": "idAgent",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idAgent",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAgent",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Agent secondary groups list

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
    | `data.[].idAgent` | integer |  |  |
    | `data.[].idGroup` | integer | yes |  |
    | `data.[].idAgentNode` | integer, nullable |  |  |
    | `data.[].serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: Agent { #model-agent }

??? note "Fields (53 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAgentNode` | integer, nullable |  | Original agent ID on the node |
    | `serverId` | integer, nullable |  | Source node ID on a metaconsole |
    | `idAgent` | integer |  | Agent ID in the current console; cache ID on a metaconsole |
    | `name` | string |  | Agent name |
    | `address` | string, nullable |  | Agent address |
    | `comments` | string, nullable |  | Agent comments |
    | `idGroup` | integer |  | Group ID |
    | `lastContact` | string |  | Last contact timestamp |
    | `mode` | enum: `learning`, `normal`, `autodisable` |  | Agent mode: learning, normal, autodisable |
    | `interval` | integer |  | Agent interval in seconds |
    | `idOs` | integer, nullable |  | Operating System ID |
    | `osVersion` | string, nullable |  | Operating System version |
    | `osName` | string, nullable |  | Operating system display name from tconfig_os. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `osImagePath` | string, nullable |  | Console-relative path of the operating system icon, for example images/os_icons/so_linux.png. Only resolved when the field is listed in requestedFields; null otherwise. |
    | `agentVersion` | string, nullable |  | Agent version |
    | `lastRemoteContact` | string, nullable |  | Last remote contact timestamp |
    | `disabled` | integer |  | Agent disabled flag (0=enabled, 1=disabled) |
    | `remote` | integer |  | Remote agent flag |
    | `idParent` | integer, nullable |  | Parent agent ID |
    | `customId` | string, nullable |  | Custom agent ID |
    | `serverName` | string, nullable |  | Server name |
    | `cascadeProtection` | integer |  | Cascade protection flag |
    | `cascadeProtectionModule` | integer |  | Cascade protection module ID |
    | `timezoneOffset` | integer, nullable |  | Timezone offset in hours |
    | `iconPath` | string, nullable |  | Icon path |
    | `updateGisData` | integer |  | Update GIS data flag |
    | `urlAddress` | string, nullable |  | URL address |
    | `quiet` | integer |  | Quiet flag |
    | `normalCount` | integer |  | Normal modules count |
    | `warningCount` | integer |  | Warning modules count |
    | `criticalCount` | integer |  | Critical modules count |
    | `unknownCount` | integer |  | Unknown modules count |
    | `notinitCount` | integer |  | Not init modules count |
    | `totalCount` | integer |  | Total modules count |
    | `firedCount` | integer |  | Fired alerts count |
    | `updateModuleCount` | integer |  | Update module count flag |
    | `updateAlertCount` | integer |  | Update alert count flag |
    | `updateSecondaryGroups` | integer |  | Update secondary groups flag |
    | `alias` | string |  | Agent alias |
    | `aliasAsName` | integer |  | Use alias as name flag |
    | `safeModeModule` | integer |  | Safe mode module ID |
    | `cps` | integer |  | CPS value |
    | `cpsInhibit` | integer, nullable |  | CPS inhibition value |
    | `satelliteServer` | integer |  | Satellite server ID |
    | `fixedIp` | integer |  | Fixed IP flag |
    | `disabledByDowntime` | integer |  | Disabled by downtime flag |
    | `vulScanEnabled` | enum: `disabled`, `enabled`, `default` |  | Vulnerability scan enabled: disabled, enabled, default |
    | `ignoreUnknown` | integer |  | Ignore unknown flag |
    | `balanceType` | enum: `none`, `round_robin`, `balanced` |  | Balance type: none, round_robin, balanced |
    | `autoHa` | integer |  | Auto HA flag |
    | `extraData` | string |  | Extra data |
    | `quietByDowntime` | integer |  | Quiet by downtime flag |
    | `idFimPolicy` | integer |  | FIM Policy ID |


### Model: AgentCustomData { #model-agentcustomdata }

??? note "Fields (8 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idField` | integer |  | Agent custom field identifier |
    | `idAgent` | integer |  | Agent identifier |
    | `name` | string, nullable |  | Agent custom field name |
    | `description` | string, nullable |  | Agent custom field value. Password fields are masked. |
    | `isPasswordType` | boolean, nullable |  | Whether the field value is handled as a password |
    | `displayOnFront` | boolean, nullable |  | Whether the field is shown in the agent front view |
    | `isLinkEnabled` | boolean, nullable |  | Whether the field value is a JSON [text, url] link |
    | `serverId` | integer, nullable |  | Source node identifier when the value comes from a metaconsole |


### Model: AgentCustomField { #model-agentcustomfield }

??? note "Fields (7 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idField` | integer |  | Agent custom field identifier |
    | `name` | string |  | Unique agent custom field name |
    | `displayOnFront` | boolean |  | Whether the field is shown in the agent front view |
    | `isPasswordType` | boolean |  | Whether the field value is handled as a password |
    | `comboValues` | string, nullable |  | Comma separated values for combo fields |
    | `isLinkEnabled` | boolean |  | Whether the field value is rendered as a link |
    | `serverId` | integer, nullable |  | Source node identifier when the field comes from a metaconsole |


### Model: AgentExtendedData { #model-agentextendeddata }

??? note "Fields (7 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `id` | integer |  | Extended data ID |
    | `idAgente` | integer |  | Agent ID |
    | `name` | string |  | Name of the extended data |
    | `category` | enum: `info`, `hardware`, `software` |  | Category of the extended data |
    | `data` | object, nullable |  | JSON data object |
    | `timestamp` | integer |  | Unix timestamp |
    | `serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |


### Model: AgentSecondaryGroup { #model-agentsecondarygroup }

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgent` | integer |  |  |
| `idGroup` | integer | yes |  |
| `idAgentNode` | integer, nullable |  |  |
| `serverId` | integer, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroup": 0
    }
    ```
