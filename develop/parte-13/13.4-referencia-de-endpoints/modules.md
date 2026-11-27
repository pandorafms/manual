# Modules

Agent modules, their data, states and tags, plus module groups, types, components and data translations.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-post">POST</span> | [`/agentModule`](#post-agentmodule) | Creates an agent module |
| <span class="api-method api-get">GET</span> | [`/agentModule/{idAgentModule}`](#get-agentmodule-idagentmodule) | Gets an agent module |
| <span class="api-method api-put">PUT</span> | [`/agentModule/{idAgentModule}`](#put-agentmodule-idagentmodule) | Updates an agent module |
| <span class="api-method api-delete">DELETE</span> | [`/agentModule/{idAgentModule}`](#delete-agentmodule-idagentmodule) | Deletes an agent module |
| <span class="api-method api-post">POST</span> | [`/agentModule/{idAgentModule}/forceCheck`](#post-agentmodule-idagentmodule-forcecheck) | Requests an immediate check of a remote agent module |
| <span class="api-method api-get">GET</span> | [`/agentModule/summary`](#get-agentmodule-summary) | Module counters grouped by status |
| <span class="api-method api-get">GET</span> | [`/agentModule/list`](#get-agentmodule-list) | Lists agent modules |
| <span class="api-method api-post">POST</span> | [`/agentModule/list`](#post-agentmodule-list) | Lists agent modules |
| <span class="api-method api-post">POST</span> | [`/agentModule/{idAgentModule}/graph`](#post-agentmodule-idagentmodule-graph) | Render a module graph as a base64 image |
| <span class="api-method api-get">GET</span> | [`/agentModule/{idAgentModule}/agentModuleData/{utimestamp}`](#get-agentmodule-idagentmodule-agentmoduledata-utimestamp) | Gets historical agent module data |
| <span class="api-method api-post">POST</span> | [`/agentModule/{idAgentModule}/agentModuleData/list`](#post-agentmodule-idagentmodule-agentmoduledata-list) | Lists historical agent module data |
| <span class="api-method api-get">GET</span> | [`/agentModule/{idAgentModule}/agentModuleData/uncompressed/list`](#get-agentmodule-idagentmodule-agentmoduledata-uncompressed-list) | Lists uncompressed historical agent module data |
| <span class="api-method api-post">POST</span> | [`/agentModule/{idAgentModule}/agentModuleData/uncompressed/list`](#post-agentmodule-idagentmodule-agentmoduledata-uncompressed-list) | Lists uncompressed historical agent module data |
| <span class="api-method api-get">GET</span> | [`/agentModule/{idAgentModule}/agentModuleState`](#get-agentmodule-idagentmodule-agentmodulestate) | Gets the current state of an agent module |
| <span class="api-method api-get">GET</span> | [`/agentModuleState/list`](#get-agentmodulestate-list) | Lists current agent module states |
| <span class="api-method api-post">POST</span> | [`/agentModuleState/list`](#post-agentmodulestate-list) | Lists current agent module states |
| <span class="api-method api-post">POST</span> | [`/agentModule/{idAgentModule}/tag`](#post-agentmodule-idagentmodule-tag) | Associates a tag with an agent module |
| <span class="api-method api-get">GET</span> | [`/agentModule/{idAgentModule}/tag/{idTag}`](#get-agentmodule-idagentmodule-tag-idtag) | Gets an agent module tag association |
| <span class="api-method api-delete">DELETE</span> | [`/agentModule/{idAgentModule}/tag/{idTag}`](#delete-agentmodule-idagentmodule-tag-idtag) | Removes a manual tag association from an agent module |
| <span class="api-method api-get">GET</span> | [`/agentModule/{idAgentModule}/tag/list`](#get-agentmodule-idagentmodule-tag-list) | Lists tags associated with an agent module |
| <span class="api-method api-post">POST</span> | [`/agentModule/{idAgentModule}/tag/list`](#post-agentmodule-idagentmodule-tag-list) | Lists tags associated with an agent module |
| <span class="api-method api-post">POST</span> | [`/agentModule/{idAgentModule}/policy/link`](#post-agentmodule-idagentmodule-policy-link) | Relink a module to its source policy |
| <span class="api-method api-post">POST</span> | [`/agentModule/{idAgentModule}/policy/unlink`](#post-agentmodule-idagentmodule-policy-unlink) | Unlink a module from its source policy |
| <span class="api-method api-post">POST</span> | [`/moduleGroup`](#post-modulegroup) | Creates a new module groups |
| <span class="api-method api-get">GET</span> | [`/moduleGroup/{idModuleGroup}`](#get-modulegroup-idmodulegroup) | Show module group |
| <span class="api-method api-put">PUT</span> | [`/moduleGroup/{idModuleGroup}`](#put-modulegroup-idmodulegroup) | Updates an moduleGroup |
| <span class="api-method api-delete">DELETE</span> | [`/moduleGroup/{idModuleGroup}`](#delete-modulegroup-idmodulegroup) | Deletes an module group object. |
| <span class="api-method api-get">GET</span> | [`/moduleGroup/list`](#get-modulegroup-list) | List module groups |
| <span class="api-method api-post">POST</span> | [`/moduleGroup/list`](#post-modulegroup-list) | List module groups |
| <span class="api-method api-get">GET</span> | [`/moduleType/{idModuleType}`](#get-moduletype-idmoduletype) | Get a module type |
| <span class="api-method api-get">GET</span> | [`/moduleType/list`](#get-moduletype-list) | List module types |
| <span class="api-method api-post">POST</span> | [`/moduleType/list`](#post-moduletype-list) | List and filter module types |
| <span class="api-method api-post">POST</span> | [`/localComponent`](#post-localcomponent) | Creates a new local component |
| <span class="api-method api-get">GET</span> | [`/localComponent/{idLocalComponent}`](#get-localcomponent-idlocalcomponent) | Show a local component |
| <span class="api-method api-put">PUT</span> | [`/localComponent/{idLocalComponent}`](#put-localcomponent-idlocalcomponent) | Updates a local component |
| <span class="api-method api-delete">DELETE</span> | [`/localComponent/{idLocalComponent}`](#delete-localcomponent-idlocalcomponent) | Deletes a local component |
| <span class="api-method api-get">GET</span> | [`/localComponent/list`](#get-localcomponent-list) | List local components using query filters |
| <span class="api-method api-post">POST</span> | [`/localComponent/list`](#post-localcomponent-list) | List local components using advanced filters |
| <span class="api-method api-post">POST</span> | [`/networkComponent`](#post-networkcomponent) | Creates a new network component |
| <span class="api-method api-get">GET</span> | [`/networkComponent/{idNetworkComponent}`](#get-networkcomponent-idnetworkcomponent) | Show a network component |
| <span class="api-method api-put">PUT</span> | [`/networkComponent/{idNetworkComponent}`](#put-networkcomponent-idnetworkcomponent) | Updates a network component |
| <span class="api-method api-delete">DELETE</span> | [`/networkComponent/{idNetworkComponent}`](#delete-networkcomponent-idnetworkcomponent) | Deletes a network component |
| <span class="api-method api-get">GET</span> | [`/networkComponent/list`](#get-networkcomponent-list) | List network components using query filters |
| <span class="api-method api-post">POST</span> | [`/networkComponent/list`](#post-networkcomponent-list) | List network components using advanced filters |
| <span class="api-method api-post">POST</span> | [`/networkComponentGroup`](#post-networkcomponentgroup) | Creates a new network component group |
| <span class="api-method api-get">GET</span> | [`/networkComponentGroup/{idNetworkComponentGroup}`](#get-networkcomponentgroup-idnetworkcomponentgroup) | Show a network component group |
| <span class="api-method api-put">PUT</span> | [`/networkComponentGroup/{idNetworkComponentGroup}`](#put-networkcomponentgroup-idnetworkcomponentgroup) | Updates a network component group |
| <span class="api-method api-delete">DELETE</span> | [`/networkComponentGroup/{idNetworkComponentGroup}`](#delete-networkcomponentgroup-idnetworkcomponentgroup) | Deletes a network component group |
| <span class="api-method api-get">GET</span> | [`/networkComponentGroup/list`](#get-networkcomponentgroup-list) | List network component groups using query filters |
| <span class="api-method api-post">POST</span> | [`/networkComponentGroup/list`](#post-networkcomponentgroup-list) | List network component groups using advanced filters |
| <span class="api-method api-post">POST</span> | [`/dataTranslation`](#post-datatranslation) | Creates a new data translation |
| <span class="api-method api-get">GET</span> | [`/dataTranslation/{idDataTranslation}`](#get-datatranslation-iddatatranslation) | Show data translation |
| <span class="api-method api-put">PUT</span> | [`/dataTranslation/{idDataTranslation}`](#put-datatranslation-iddatatranslation) | Updates a data translation |
| <span class="api-method api-delete">DELETE</span> | [`/dataTranslation/{idDataTranslation}`](#delete-datatranslation-iddatatranslation) | Deletes a data translation object. |
| <span class="api-method api-get">GET</span> | [`/dataTranslation/list`](#get-datatranslation-list) | List data translations |
| <span class="api-method api-post">POST</span> | [`/dataTranslation/list`](#post-datatranslation-list) | List data translations |

## AgentModules

API Endpoints for agent modules

### <span class="api-method api-post">POST</span> `/agentModule` { #post-agentmodule }

Creates an agent module

Creates the module locally on a node. On a metaconsole, serverId is required and the operation is delegated to that node.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgentModule` | integer, nullable |  | Agent module identifier |
| `idAgent` | integer | yes | Identifier of the agent that owns the module |
| `idModuleType` | integer | yes | Module data type identifier |
| `description` | string, nullable |  | Module description |
| `extendedInfo` | string, nullable |  | Additional module information |
| `name` | string | yes | Module name |
| `unit` | string, nullable |  | Value unit |
| `idPolicyModule` | integer, nullable |  | Source policy module identifier |
| `max` | integer (int64), nullable |  | Maximum accepted value |
| `min` | integer (int64), nullable |  | Minimum accepted value |
| `moduleInterval` | integer, nullable |  | Module execution interval in seconds |
| `cronInterval` | string, nullable |  | Cron expression used as the module interval |
| `moduleFfInterval` | integer, nullable |  | Flip-flop execution interval |
| `tcpPort` | integer, nullable |  | Target TCP port |
| `tcpSend` | string, nullable |  | Payload sent to the TCP target |
| `tcpRcv` | string, nullable |  | Expected TCP response |
| `snmpCommunity` | string, nullable |  | SNMP community |
| `snmpOid` | string, nullable |  | SNMP object identifier |
| `ipTarget` | string, nullable |  | Module target address |
| `idModuleGroup` | integer, nullable |  | Module group identifier |
| `flag` | integer, nullable |  | Module state flag |
| `idModule` | integer | yes | Module server type identifier |
| `disabled` | boolean, nullable |  | Whether the module is disabled |
| `disabledBySafeMode` | boolean, nullable |  | Whether safe mode disabled the module |
| `idExport` | integer, nullable |  | Export server identifier |
| `pluginUser` | string, nullable |  | Plugin authentication user |
| `pluginPass` | string, nullable |  | Plugin authentication password |
| `pluginParameter` | string, nullable |  | Plugin parameters |
| `idPlugin` | integer, nullable |  | Plugin identifier |
| `postProcess` | number (double), nullable |  | Post-processing multiplier |
| `predictionModule` | integer (int64), nullable |  | Prediction source module or mode |
| `maxTimeout` | integer, nullable |  | Maximum execution timeout |
| `maxRetries` | integer, nullable |  | Maximum execution retries |
| `customId` | string, nullable |  | External module identifier |
| `historyData` | boolean, nullable |  | Whether historical data is stored |
| `minWarning` | number (double), nullable |  | Warning threshold lower bound |
| `maxWarning` | number (double), nullable |  | Warning threshold upper bound |
| `strWarning` | string, nullable |  | Warning string condition |
| `minCritical` | number (double), nullable |  | Critical threshold lower bound |
| `maxCritical` | number (double), nullable |  | Critical threshold upper bound |
| `strCritical` | string, nullable |  | Critical string condition |
| `minFfEvent` | integer, nullable |  | Event flip-flop threshold |
| `deletePending` | boolean, nullable |  | Whether the module is pending deletion |
| `policyLinked` | integer, nullable |  | Policy link state |
| `policyAdopted` | boolean, nullable |  | Whether the module was adopted from a policy |
| `customString1` | string, nullable |  | First custom string value |
| `customString2` | string, nullable |  | Second custom string value |
| `customString3` | string, nullable |  | Third custom string value |
| `customInteger1` | integer, nullable |  | First custom integer value |
| `customInteger2` | integer, nullable |  | Second custom integer value |
| `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  | Wizard visibility level |
| `macros` | string, nullable |  | Serialized module macros |
| `criticalInstructions` | string, nullable |  | Instructions for critical status |
| `warningInstructions` | string, nullable |  | Instructions for warning status |
| `unknownInstructions` | string, nullable |  | Instructions for unknown status |
| `quiet` | boolean, nullable |  | Whether event generation is silenced |
| `criticalInverse` | boolean, nullable |  | Whether the critical threshold is inverted |
| `warningInverse` | boolean, nullable |  | Whether the warning threshold is inverted |
| `idCategory` | integer, nullable |  | Module category identifier |
| `disabledTypesEvent` | string, nullable |  | Serialized disabled event types |
| `moduleMacros` | string, nullable |  | Serialized module macro definitions |
| `minFfEventNormal` | integer, nullable |  | Normal status flip-flop threshold |
| `minFfEventWarning` | integer, nullable |  | Warning status flip-flop threshold |
| `minFfEventCritical` | integer, nullable |  | Critical status flip-flop threshold |
| `ffType` | integer, nullable |  | Flip-flop calculation type |
| `eachFf` | boolean, nullable |  | Whether each status has an independent flip-flop threshold |
| `ffTimeout` | integer, nullable |  | Flip-flop timeout |
| `dynamicInterval` | integer, nullable |  | Dynamic interval value |
| `dynamicMax` | integer, nullable |  | Dynamic interval upper bound |
| `dynamicMin` | integer, nullable |  | Dynamic interval lower bound |
| `dynamicNext` | integer (int64), nullable |  | Next calculated dynamic execution time |
| `dynamicTwoTailed` | boolean, nullable |  | Whether dynamic thresholds are two-tailed |
| `predictionSampleWindow` | integer, nullable |  | Prediction sample window |
| `predictionSamples` | integer, nullable |  | Number of prediction samples |
| `predictionThreshold` | integer, nullable |  | Prediction threshold |
| `apiTimeout` | integer, nullable |  | API request timeout |
| `apiUrl` | string, nullable |  | API request URL |
| `apiMethod` | string, nullable |  | API HTTP method |
| `apiIgnoreCert` | boolean, nullable |  | Whether API certificate validation is disabled |
| `apiJsonq` | string, nullable |  | JSON query used to extract the API result |
| `apiBody` | string, nullable |  | API request body |
| `apiHeaders` | object, nullable |  | API request headers |
| `apiErrorCodes` | string, nullable |  | API error code configuration |
| `apiConditions` | object, nullable |  | API response conditions |
| `parentModuleId` | integer, nullable |  | Parent module identifier |
| `cps` | boolean, nullable |  | Whether change-per-second calculation is enabled |
| `cpsInhibit` | integer, nullable |  | Change-per-second inhibition interval |
| `debugContent` | string, nullable |  | Last module debug content |
| `percentageCritical` | boolean, nullable |  | Whether critical thresholds are percentages |
| `percentageWarning` | boolean, nullable |  | Whether warning thresholds are percentages |
| `warningTime` | integer, nullable |  | Minimum warning duration |
| `quietByDowntime` | boolean, nullable |  | Whether downtime silenced the module |
| `disabledByDowntime` | boolean, nullable |  | Whether downtime disabled the module |
| `madeEnabled` | boolean, nullable |  | Whether downtime enabled the module |
| `ignoreUnknown` | boolean, nullable |  | Whether unknown status is ignored |
| `extraData` | string, nullable |  | Additional serialized module data |
| `idDataTranslation` | integer, nullable |  | Data translation identifier |
| `serverId` | integer, nullable |  | Node identifier for metaconsole operations |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": 0,
      "idModuleType": 0,
      "description": "string",
      "extendedInfo": "string",
      "name": "string",
      "unit": "string",
      "idPolicyModule": 0,
      "max": 0,
      "min": 0,
      "moduleInterval": 0,
      "cronInterval": "string",
      "moduleFfInterval": 0,
      "tcpPort": 0,
      "tcpSend": "string",
      "tcpRcv": "string",
      "snmpCommunity": "string",
      "snmpOid": "string",
      "ipTarget": "string",
      "idModuleGroup": 0,
      "flag": 0,
      "idModule": 0,
      "disabled": false,
      "disabledBySafeMode": false,
      "idExport": 0,
      "pluginUser": "string",
      "pluginPass": "string",
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
      "customString1": "string",
      "customString2": "string",
      "customString3": "string",
      "customInteger1": 0,
      "customInteger2": 0,
      "wizardLevel": "basic",
      "macros": "string",
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "quiet": false,
      "criticalInverse": false,
      "warningInverse": false,
      "idCategory": 0,
      "disabledTypesEvent": "string",
      "moduleMacros": "string",
      "minFfEventNormal": 0,
      "minFfEventWarning": 0,
      "minFfEventCritical": 0,
      "ffType": 0,
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
      "apiBody": "string",
      "apiHeaders": {},
      "apiErrorCodes": "string",
      "apiConditions": {},
      "parentModuleId": 0,
      "cps": false,
      "cpsInhibit": 0,
      "debugContent": "string",
      "percentageCritical": false,
      "percentageWarning": false,
      "warningTime": 0,
      "quietByDowntime": false,
      "disabledByDowntime": false,
      "madeEnabled": false,
      "ignoreUnknown": false,
      "extraData": "string",
      "idDataTranslation": 0
    }
    ```

**Response 200**: Agent module created

Schema: [`AgentModule`](#model-agentmodule)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/agentModule/{idAgentModule}` { #get-agentmodule-idagentmodule }

Gets an agent module

Reads the module locally on a node. On a metaconsole, serverId identifies the node that owns the module.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes | Agent module identifier |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Agent module

Schema: [`AgentModule`](#model-agentmodule)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-put">PUT</span> `/agentModule/{idAgentModule}` { #put-agentmodule-idagentmodule }

Updates an agent module

Updates the module locally on a node. On a metaconsole, serverId identifies the node that owns the module.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes | Agent module identifier |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`AgentModule`](#model-agentmodule)

**Response 200**: Agent module updated

Schema: [`AgentModule`](#model-agentmodule)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-delete">DELETE</span> `/agentModule/{idAgentModule}` { #delete-agentmodule-idagentmodule }

Deletes an agent module

Deletes the module locally on a node. On a metaconsole, serverId identifies the node that owns the module.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes | Agent module identifier |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/agentModule/{idAgentModule}/forceCheck` { #post-agentmodule-idagentmodule-forcecheck }

Requests an immediate check of a remote agent module

Marks the module for an immediate asynchronous check. On a metaconsole, serverId identifies the node that owns the module.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes | Agent module identifier |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 202**: Immediate check request accepted

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/agentModule/summary` { #get-agentmodule-summary }

Module counters grouped by status

**Response 200**: Agent module summary

??? note "Response fields (8 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `total` | integer |  |  |
    | `normal` | integer |  |  |
    | `warning` | integer |  |  |
    | `critical` | integer |  |  |
    | `unknown` | integer |  |  |
    | `notInit` | integer |  |  |
    | `alerts` | integer |  |  |
    | `alertsFired` | integer |  |  |


Error responses: `401`, `403`, `500`.

### <span class="api-method api-get">GET</span> `/agentModule/list` { #get-agentmodule-list }

Lists agent modules

Lists modules locally on a node. On a metaconsole, serverId is required and selects the node to query. Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Agent module list

??? note "Response fields (108 fields)"

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
    | `data.[].idAgentModule` | integer, nullable |  | Agent module identifier |
    | `data.[].idAgent` | integer |  | Identifier of the agent that owns the module |
    | `data.[].idModuleType` | integer |  | Module data type identifier |
    | `data.[].description` | string, nullable |  | Module description |
    | `data.[].extendedInfo` | string, nullable |  | Additional module information |
    | `data.[].name` | string |  | Module name |
    | `data.[].unit` | string, nullable |  | Value unit |
    | `data.[].idPolicyModule` | integer, nullable |  | Source policy module identifier |
    | `data.[].max` | integer (int64), nullable |  | Maximum accepted value |
    | `data.[].min` | integer (int64), nullable |  | Minimum accepted value |
    | `data.[].moduleInterval` | integer, nullable |  | Module execution interval in seconds |
    | `data.[].cronInterval` | string, nullable |  | Cron expression used as the module interval |
    | `data.[].moduleFfInterval` | integer, nullable |  | Flip-flop execution interval |
    | `data.[].tcpPort` | integer, nullable |  | Target TCP port |
    | `data.[].tcpSend` | string, nullable |  | Payload sent to the TCP target |
    | `data.[].tcpRcv` | string, nullable |  | Expected TCP response |
    | `data.[].snmpCommunity` | string, nullable |  | SNMP community |
    | `data.[].snmpOid` | string, nullable |  | SNMP object identifier |
    | `data.[].ipTarget` | string, nullable |  | Module target address |
    | `data.[].idModuleGroup` | integer, nullable |  | Module group identifier |
    | `data.[].flag` | integer, nullable |  | Module state flag |
    | `data.[].idModule` | integer |  | Module server type identifier |
    | `data.[].disabled` | boolean, nullable |  | Whether the module is disabled |
    | `data.[].disabledBySafeMode` | boolean, nullable |  | Whether safe mode disabled the module |
    | `data.[].idExport` | integer, nullable |  | Export server identifier |
    | `data.[].pluginUser` | string, nullable |  | Plugin authentication user |
    | `data.[].pluginPass` | string, nullable |  | Plugin authentication password |
    | `data.[].pluginParameter` | string, nullable |  | Plugin parameters |
    | `data.[].idPlugin` | integer, nullable |  | Plugin identifier |
    | `data.[].postProcess` | number (double), nullable |  | Post-processing multiplier |
    | `data.[].predictionModule` | integer (int64), nullable |  | Prediction source module or mode |
    | `data.[].maxTimeout` | integer, nullable |  | Maximum execution timeout |
    | `data.[].maxRetries` | integer, nullable |  | Maximum execution retries |
    | `data.[].customId` | string, nullable |  | External module identifier |
    | `data.[].historyData` | boolean, nullable |  | Whether historical data is stored |
    | `data.[].minWarning` | number (double), nullable |  | Warning threshold lower bound |
    | `data.[].maxWarning` | number (double), nullable |  | Warning threshold upper bound |
    | `data.[].strWarning` | string, nullable |  | Warning string condition |
    | `data.[].minCritical` | number (double), nullable |  | Critical threshold lower bound |
    | `data.[].maxCritical` | number (double), nullable |  | Critical threshold upper bound |
    | `data.[].strCritical` | string, nullable |  | Critical string condition |
    | `data.[].minFfEvent` | integer, nullable |  | Event flip-flop threshold |
    | `data.[].deletePending` | boolean, nullable |  | Whether the module is pending deletion |
    | `data.[].policyLinked` | integer, nullable |  | Policy link state |
    | `data.[].policyAdopted` | boolean, nullable |  | Whether the module was adopted from a policy |
    | `data.[].customString1` | string, nullable |  | First custom string value |
    | `data.[].customString2` | string, nullable |  | Second custom string value |
    | `data.[].customString3` | string, nullable |  | Third custom string value |
    | `data.[].customInteger1` | integer, nullable |  | First custom integer value |
    | `data.[].customInteger2` | integer, nullable |  | Second custom integer value |
    | `data.[].wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  | Wizard visibility level |
    | `data.[].macros` | string, nullable |  | Serialized module macros |
    | `data.[].criticalInstructions` | string, nullable |  | Instructions for critical status |
    | `data.[].warningInstructions` | string, nullable |  | Instructions for warning status |
    | `data.[].unknownInstructions` | string, nullable |  | Instructions for unknown status |
    | `data.[].quiet` | boolean, nullable |  | Whether event generation is silenced |
    | `data.[].criticalInverse` | boolean, nullable |  | Whether the critical threshold is inverted |
    | `data.[].warningInverse` | boolean, nullable |  | Whether the warning threshold is inverted |
    | `data.[].idCategory` | integer, nullable |  | Module category identifier |
    | `data.[].disabledTypesEvent` | string, nullable |  | Serialized disabled event types |
    | `data.[].moduleMacros` | string, nullable |  | Serialized module macro definitions |
    | `data.[].minFfEventNormal` | integer, nullable |  | Normal status flip-flop threshold |
    | `data.[].minFfEventWarning` | integer, nullable |  | Warning status flip-flop threshold |
    | `data.[].minFfEventCritical` | integer, nullable |  | Critical status flip-flop threshold |
    | `data.[].ffType` | integer, nullable |  | Flip-flop calculation type |
    | `data.[].eachFf` | boolean, nullable |  | Whether each status has an independent flip-flop threshold |
    | `data.[].ffTimeout` | integer, nullable |  | Flip-flop timeout |
    | `data.[].dynamicInterval` | integer, nullable |  | Dynamic interval value |
    | `data.[].dynamicMax` | integer, nullable |  | Dynamic interval upper bound |
    | `data.[].dynamicMin` | integer, nullable |  | Dynamic interval lower bound |
    | `data.[].dynamicNext` | integer (int64), nullable |  | Next calculated dynamic execution time |
    | `data.[].dynamicTwoTailed` | boolean, nullable |  | Whether dynamic thresholds are two-tailed |
    | `data.[].predictionSampleWindow` | integer, nullable |  | Prediction sample window |
    | `data.[].predictionSamples` | integer, nullable |  | Number of prediction samples |
    | `data.[].predictionThreshold` | integer, nullable |  | Prediction threshold |
    | `data.[].apiTimeout` | integer, nullable |  | API request timeout |
    | `data.[].apiUrl` | string, nullable |  | API request URL |
    | `data.[].apiMethod` | string, nullable |  | API HTTP method |
    | `data.[].apiIgnoreCert` | boolean, nullable |  | Whether API certificate validation is disabled |
    | `data.[].apiJsonq` | string, nullable |  | JSON query used to extract the API result |
    | `data.[].apiBody` | string, nullable |  | API request body |
    | `data.[].apiHeaders` | object, nullable |  | API request headers |
    | `data.[].apiErrorCodes` | string, nullable |  | API error code configuration |
    | `data.[].apiConditions` | object, nullable |  | API response conditions |
    | `data.[].parentModuleId` | integer, nullable |  | Parent module identifier |
    | `data.[].cps` | boolean, nullable |  | Whether change-per-second calculation is enabled |
    | `data.[].cpsInhibit` | integer, nullable |  | Change-per-second inhibition interval |
    | `data.[].debugContent` | string, nullable |  | Last module debug content |
    | `data.[].percentageCritical` | boolean, nullable |  | Whether critical thresholds are percentages |
    | `data.[].percentageWarning` | boolean, nullable |  | Whether warning thresholds are percentages |
    | `data.[].warningTime` | integer, nullable |  | Minimum warning duration |
    | `data.[].quietByDowntime` | boolean, nullable |  | Whether downtime silenced the module |
    | `data.[].disabledByDowntime` | boolean, nullable |  | Whether downtime disabled the module |
    | `data.[].madeEnabled` | boolean, nullable |  | Whether downtime enabled the module |
    | `data.[].ignoreUnknown` | boolean, nullable |  | Whether unknown status is ignored |
    | `data.[].extraData` | string, nullable |  | Additional serialized module data |
    | `data.[].idDataTranslation` | integer, nullable |  | Data translation identifier |
    | `data.[].serverId` | integer, nullable |  | Node identifier for metaconsole operations |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/agentModule/list` { #post-agentmodule-list }

Lists agent modules

Lists modules locally on a node. On a metaconsole, serverId is required and selects the node to query.

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
| `idAgentModule` | integer, nullable |  | Agent module identifier |
| `idAgent` | integer |  | Identifier of the agent that owns the module |
| `idModuleType` | integer |  | Module data type identifier |
| `description` | string, nullable |  | Module description |
| `extendedInfo` | string, nullable |  | Additional module information |
| `name` | string |  | Module name |
| `unit` | string, nullable |  | Value unit |
| `idPolicyModule` | integer, nullable |  | Source policy module identifier |
| `max` | integer (int64), nullable |  | Maximum accepted value |
| `min` | integer (int64), nullable |  | Minimum accepted value |
| `moduleInterval` | integer, nullable |  | Module execution interval in seconds |
| `cronInterval` | string, nullable |  | Cron expression used as the module interval |
| `moduleFfInterval` | integer, nullable |  | Flip-flop execution interval |
| `tcpPort` | integer, nullable |  | Target TCP port |
| `tcpSend` | string, nullable |  | Payload sent to the TCP target |
| `tcpRcv` | string, nullable |  | Expected TCP response |
| `snmpCommunity` | string, nullable |  | SNMP community |
| `snmpOid` | string, nullable |  | SNMP object identifier |
| `ipTarget` | string, nullable |  | Module target address |
| `idModuleGroup` | integer, nullable |  | Module group identifier |
| `flag` | integer, nullable |  | Module state flag |
| `idModule` | integer |  | Module server type identifier |
| `disabled` | boolean, nullable |  | Whether the module is disabled |
| `disabledBySafeMode` | boolean, nullable |  | Whether safe mode disabled the module |
| `idExport` | integer, nullable |  | Export server identifier |
| `pluginUser` | string, nullable |  | Plugin authentication user |
| `pluginPass` | string, nullable |  | Plugin authentication password |
| `pluginParameter` | string, nullable |  | Plugin parameters |
| `idPlugin` | integer, nullable |  | Plugin identifier |
| `postProcess` | number (double), nullable |  | Post-processing multiplier |
| `predictionModule` | integer (int64), nullable |  | Prediction source module or mode |
| `maxTimeout` | integer, nullable |  | Maximum execution timeout |
| `maxRetries` | integer, nullable |  | Maximum execution retries |
| `customId` | string, nullable |  | External module identifier |
| `historyData` | boolean, nullable |  | Whether historical data is stored |
| `minWarning` | number (double), nullable |  | Warning threshold lower bound |
| `maxWarning` | number (double), nullable |  | Warning threshold upper bound |
| `strWarning` | string, nullable |  | Warning string condition |
| `minCritical` | number (double), nullable |  | Critical threshold lower bound |
| `maxCritical` | number (double), nullable |  | Critical threshold upper bound |
| `strCritical` | string, nullable |  | Critical string condition |
| `minFfEvent` | integer, nullable |  | Event flip-flop threshold |
| `deletePending` | boolean, nullable |  | Whether the module is pending deletion |
| `policyLinked` | integer, nullable |  | Policy link state |
| `policyAdopted` | boolean, nullable |  | Whether the module was adopted from a policy |
| `customString1` | string, nullable |  | First custom string value |
| `customString2` | string, nullable |  | Second custom string value |
| `customString3` | string, nullable |  | Third custom string value |
| `customInteger1` | integer, nullable |  | First custom integer value |
| `customInteger2` | integer, nullable |  | Second custom integer value |
| `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  | Wizard visibility level |
| `macros` | string, nullable |  | Serialized module macros |
| `criticalInstructions` | string, nullable |  | Instructions for critical status |
| `warningInstructions` | string, nullable |  | Instructions for warning status |
| `unknownInstructions` | string, nullable |  | Instructions for unknown status |
| `quiet` | boolean, nullable |  | Whether event generation is silenced |
| `criticalInverse` | boolean, nullable |  | Whether the critical threshold is inverted |
| `warningInverse` | boolean, nullable |  | Whether the warning threshold is inverted |
| `idCategory` | integer, nullable |  | Module category identifier |
| `disabledTypesEvent` | string, nullable |  | Serialized disabled event types |
| `moduleMacros` | string, nullable |  | Serialized module macro definitions |
| `minFfEventNormal` | integer, nullable |  | Normal status flip-flop threshold |
| `minFfEventWarning` | integer, nullable |  | Warning status flip-flop threshold |
| `minFfEventCritical` | integer, nullable |  | Critical status flip-flop threshold |
| `ffType` | integer, nullable |  | Flip-flop calculation type |
| `eachFf` | boolean, nullable |  | Whether each status has an independent flip-flop threshold |
| `ffTimeout` | integer, nullable |  | Flip-flop timeout |
| `dynamicInterval` | integer, nullable |  | Dynamic interval value |
| `dynamicMax` | integer, nullable |  | Dynamic interval upper bound |
| `dynamicMin` | integer, nullable |  | Dynamic interval lower bound |
| `dynamicNext` | integer (int64), nullable |  | Next calculated dynamic execution time |
| `dynamicTwoTailed` | boolean, nullable |  | Whether dynamic thresholds are two-tailed |
| `predictionSampleWindow` | integer, nullable |  | Prediction sample window |
| `predictionSamples` | integer, nullable |  | Number of prediction samples |
| `predictionThreshold` | integer, nullable |  | Prediction threshold |
| `apiTimeout` | integer, nullable |  | API request timeout |
| `apiUrl` | string, nullable |  | API request URL |
| `apiMethod` | string, nullable |  | API HTTP method |
| `apiIgnoreCert` | boolean, nullable |  | Whether API certificate validation is disabled |
| `apiJsonq` | string, nullable |  | JSON query used to extract the API result |
| `apiBody` | string, nullable |  | API request body |
| `apiHeaders` | object, nullable |  | API request headers |
| `apiErrorCodes` | string, nullable |  | API error code configuration |
| `apiConditions` | object, nullable |  | API response conditions |
| `parentModuleId` | integer, nullable |  | Parent module identifier |
| `cps` | boolean, nullable |  | Whether change-per-second calculation is enabled |
| `cpsInhibit` | integer, nullable |  | Change-per-second inhibition interval |
| `debugContent` | string, nullable |  | Last module debug content |
| `percentageCritical` | boolean, nullable |  | Whether critical thresholds are percentages |
| `percentageWarning` | boolean, nullable |  | Whether warning thresholds are percentages |
| `warningTime` | integer, nullable |  | Minimum warning duration |
| `quietByDowntime` | boolean, nullable |  | Whether downtime silenced the module |
| `disabledByDowntime` | boolean, nullable |  | Whether downtime disabled the module |
| `madeEnabled` | boolean, nullable |  | Whether downtime enabled the module |
| `ignoreUnknown` | boolean, nullable |  | Whether unknown status is ignored |
| `extraData` | string, nullable |  | Additional serialized module data |
| `idDataTranslation` | integer, nullable |  | Data translation identifier |
| `serverId` | integer, nullable |  | Node identifier for metaconsole operations |
| `idAgentModule` |  |  |  |
| `deletePending` |  |  | Filter modules pending deletion. Defaults to false |
| `policyLinked` |  |  |  |
| `policyAdopted` |  |  |  |
| `serverId` | integer, nullable |  | Node identifier. Required when listing modules from a metaconsole |
| `freeSearch` | string, nullable |  | Find text in module name and description fields |
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
| `multipleSearch.field` | enum: `idAgentModule`, `idAgent`, `idModuleType`, `description`, `extendedInfo`, `name`, `unit`, `idPolicyModule`, `max`, `min`, `moduleInterval`, `cronInterval`, `moduleFfInterval`, `tcpPort`, `tcpRcv`, `snmpOid`, `ipTarget`, `idModuleGroup`, `flag`, `idModule`, `disabled`, `disabledBySafeMode`, `idExport`, `pluginUser`, `idPlugin`, `postProcess`, `predictionModule`, `maxTimeout`, `maxRetries`, `customId`, `historyData`, `minWarning`, `maxWarning`, `strWarning`, `minCritical`, `maxCritical`, `strCritical`, `minFfEvent`, `deletePending`, `policyLinked`, `policyAdopted`, `customString1`, `customString2`, `customString3`, `customInteger1`, `customInteger2`, `wizardLevel`, `criticalInstructions`, `warningInstructions`, `unknownInstructions`, `quiet`, `criticalInverse`, `warningInverse`, `idCategory`, `disabledTypesEvent`, `minFfEventNormal`, `minFfEventWarning`, `minFfEventCritical`, `ffType`, `eachFf`, `ffTimeout`, `dynamicInterval`, `dynamicMax`, `dynamicMin`, `dynamicNext`, `dynamicTwoTailed`, `predictionSampleWindow`, `predictionSamples`, `predictionThreshold`, `apiTimeout`, `apiMethod`, `apiIgnoreCert`, `apiJsonq`, `apiErrorCodes`, `parentModuleId`, `cps`, `cpsInhibit`, `percentageCritical`, `percentageWarning`, `warningTime`, `quietByDowntime`, `disabledByDowntime`, `madeEnabled`, `ignoreUnknown`, `idDataTranslation` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAgentModule`, `idAgent`, `idModuleType`, `description`, `extendedInfo`, `name`, `unit`, `idPolicyModule`, `max`, `min`, `moduleInterval`, `cronInterval`, `moduleFfInterval`, `tcpPort`, `tcpRcv`, `snmpOid`, `ipTarget`, `idModuleGroup`, `flag`, `idModule`, `disabled`, `disabledBySafeMode`, `idExport`, `pluginUser`, `idPlugin`, `postProcess`, `predictionModule`, `maxTimeout`, `maxRetries`, `customId`, `historyData`, `minWarning`, `maxWarning`, `strWarning`, `minCritical`, `maxCritical`, `strCritical`, `minFfEvent`, `deletePending`, `policyLinked`, `policyAdopted`, `customString1`, `customString2`, `customString3`, `customInteger1`, `customInteger2`, `wizardLevel`, `criticalInstructions`, `warningInstructions`, `unknownInstructions`, `quiet`, `criticalInverse`, `warningInverse`, `idCategory`, `disabledTypesEvent`, `minFfEventNormal`, `minFfEventWarning`, `minFfEventCritical`, `ffType`, `eachFf`, `ffTimeout`, `dynamicInterval`, `dynamicMax`, `dynamicMin`, `dynamicNext`, `dynamicTwoTailed`, `predictionSampleWindow`, `predictionSamples`, `predictionThreshold`, `apiTimeout`, `apiMethod`, `apiIgnoreCert`, `apiJsonq`, `apiErrorCodes`, `parentModuleId`, `cps`, `cpsInhibit`, `percentageCritical`, `percentageWarning`, `warningTime`, `quietByDowntime`, `disabledByDowntime`, `madeEnabled`, `ignoreUnknown`, `idDataTranslation` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": 0,
      "idModuleType": 0,
      "description": "string",
      "extendedInfo": "string",
      "name": "string",
      "unit": "string",
      "idPolicyModule": 0,
      "max": 0,
      "min": 0,
      "moduleInterval": 0,
      "cronInterval": "string",
      "moduleFfInterval": 0,
      "tcpPort": 0,
      "tcpSend": "string",
      "tcpRcv": "string",
      "snmpCommunity": "string",
      "snmpOid": "string",
      "ipTarget": "string",
      "idModuleGroup": 0,
      "flag": 0,
      "idModule": 0,
      "disabled": false,
      "disabledBySafeMode": false,
      "idExport": 0,
      "pluginUser": "string",
      "pluginPass": "string",
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
      "customString1": "string",
      "customString2": "string",
      "customString3": "string",
      "customInteger1": 0,
      "customInteger2": 0,
      "wizardLevel": "basic",
      "macros": "string",
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "quiet": false,
      "criticalInverse": false,
      "warningInverse": false,
      "idCategory": 0,
      "disabledTypesEvent": "string",
      "moduleMacros": "string",
      "minFfEventNormal": 0,
      "minFfEventWarning": 0,
      "minFfEventCritical": 0,
      "ffType": 0,
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
      "apiBody": "string",
      "apiHeaders": {},
      "apiErrorCodes": "string",
      "apiConditions": {},
      "parentModuleId": 0,
      "cps": false,
      "cpsInhibit": 0,
      "debugContent": "string",
      "percentageCritical": false,
      "percentageWarning": false,
      "warningTime": 0,
      "quietByDowntime": false,
      "disabledByDowntime": false,
      "madeEnabled": false,
      "ignoreUnknown": false,
      "extraData": "string",
      "idDataTranslation": 0,
      "idAgentModule": null,
      "deletePending": false,
      "policyLinked": null,
      "policyAdopted": null,
      "serverId": 0,
      "freeSearch": "string",
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
      }
    }
    ```

**Response 200**: Agent module list

??? note "Response fields (108 fields)"

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
    | `data.[].idAgentModule` | integer, nullable |  | Agent module identifier |
    | `data.[].idAgent` | integer |  | Identifier of the agent that owns the module |
    | `data.[].idModuleType` | integer |  | Module data type identifier |
    | `data.[].description` | string, nullable |  | Module description |
    | `data.[].extendedInfo` | string, nullable |  | Additional module information |
    | `data.[].name` | string |  | Module name |
    | `data.[].unit` | string, nullable |  | Value unit |
    | `data.[].idPolicyModule` | integer, nullable |  | Source policy module identifier |
    | `data.[].max` | integer (int64), nullable |  | Maximum accepted value |
    | `data.[].min` | integer (int64), nullable |  | Minimum accepted value |
    | `data.[].moduleInterval` | integer, nullable |  | Module execution interval in seconds |
    | `data.[].cronInterval` | string, nullable |  | Cron expression used as the module interval |
    | `data.[].moduleFfInterval` | integer, nullable |  | Flip-flop execution interval |
    | `data.[].tcpPort` | integer, nullable |  | Target TCP port |
    | `data.[].tcpSend` | string, nullable |  | Payload sent to the TCP target |
    | `data.[].tcpRcv` | string, nullable |  | Expected TCP response |
    | `data.[].snmpCommunity` | string, nullable |  | SNMP community |
    | `data.[].snmpOid` | string, nullable |  | SNMP object identifier |
    | `data.[].ipTarget` | string, nullable |  | Module target address |
    | `data.[].idModuleGroup` | integer, nullable |  | Module group identifier |
    | `data.[].flag` | integer, nullable |  | Module state flag |
    | `data.[].idModule` | integer |  | Module server type identifier |
    | `data.[].disabled` | boolean, nullable |  | Whether the module is disabled |
    | `data.[].disabledBySafeMode` | boolean, nullable |  | Whether safe mode disabled the module |
    | `data.[].idExport` | integer, nullable |  | Export server identifier |
    | `data.[].pluginUser` | string, nullable |  | Plugin authentication user |
    | `data.[].pluginPass` | string, nullable |  | Plugin authentication password |
    | `data.[].pluginParameter` | string, nullable |  | Plugin parameters |
    | `data.[].idPlugin` | integer, nullable |  | Plugin identifier |
    | `data.[].postProcess` | number (double), nullable |  | Post-processing multiplier |
    | `data.[].predictionModule` | integer (int64), nullable |  | Prediction source module or mode |
    | `data.[].maxTimeout` | integer, nullable |  | Maximum execution timeout |
    | `data.[].maxRetries` | integer, nullable |  | Maximum execution retries |
    | `data.[].customId` | string, nullable |  | External module identifier |
    | `data.[].historyData` | boolean, nullable |  | Whether historical data is stored |
    | `data.[].minWarning` | number (double), nullable |  | Warning threshold lower bound |
    | `data.[].maxWarning` | number (double), nullable |  | Warning threshold upper bound |
    | `data.[].strWarning` | string, nullable |  | Warning string condition |
    | `data.[].minCritical` | number (double), nullable |  | Critical threshold lower bound |
    | `data.[].maxCritical` | number (double), nullable |  | Critical threshold upper bound |
    | `data.[].strCritical` | string, nullable |  | Critical string condition |
    | `data.[].minFfEvent` | integer, nullable |  | Event flip-flop threshold |
    | `data.[].deletePending` | boolean, nullable |  | Whether the module is pending deletion |
    | `data.[].policyLinked` | integer, nullable |  | Policy link state |
    | `data.[].policyAdopted` | boolean, nullable |  | Whether the module was adopted from a policy |
    | `data.[].customString1` | string, nullable |  | First custom string value |
    | `data.[].customString2` | string, nullable |  | Second custom string value |
    | `data.[].customString3` | string, nullable |  | Third custom string value |
    | `data.[].customInteger1` | integer, nullable |  | First custom integer value |
    | `data.[].customInteger2` | integer, nullable |  | Second custom integer value |
    | `data.[].wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  | Wizard visibility level |
    | `data.[].macros` | string, nullable |  | Serialized module macros |
    | `data.[].criticalInstructions` | string, nullable |  | Instructions for critical status |
    | `data.[].warningInstructions` | string, nullable |  | Instructions for warning status |
    | `data.[].unknownInstructions` | string, nullable |  | Instructions for unknown status |
    | `data.[].quiet` | boolean, nullable |  | Whether event generation is silenced |
    | `data.[].criticalInverse` | boolean, nullable |  | Whether the critical threshold is inverted |
    | `data.[].warningInverse` | boolean, nullable |  | Whether the warning threshold is inverted |
    | `data.[].idCategory` | integer, nullable |  | Module category identifier |
    | `data.[].disabledTypesEvent` | string, nullable |  | Serialized disabled event types |
    | `data.[].moduleMacros` | string, nullable |  | Serialized module macro definitions |
    | `data.[].minFfEventNormal` | integer, nullable |  | Normal status flip-flop threshold |
    | `data.[].minFfEventWarning` | integer, nullable |  | Warning status flip-flop threshold |
    | `data.[].minFfEventCritical` | integer, nullable |  | Critical status flip-flop threshold |
    | `data.[].ffType` | integer, nullable |  | Flip-flop calculation type |
    | `data.[].eachFf` | boolean, nullable |  | Whether each status has an independent flip-flop threshold |
    | `data.[].ffTimeout` | integer, nullable |  | Flip-flop timeout |
    | `data.[].dynamicInterval` | integer, nullable |  | Dynamic interval value |
    | `data.[].dynamicMax` | integer, nullable |  | Dynamic interval upper bound |
    | `data.[].dynamicMin` | integer, nullable |  | Dynamic interval lower bound |
    | `data.[].dynamicNext` | integer (int64), nullable |  | Next calculated dynamic execution time |
    | `data.[].dynamicTwoTailed` | boolean, nullable |  | Whether dynamic thresholds are two-tailed |
    | `data.[].predictionSampleWindow` | integer, nullable |  | Prediction sample window |
    | `data.[].predictionSamples` | integer, nullable |  | Number of prediction samples |
    | `data.[].predictionThreshold` | integer, nullable |  | Prediction threshold |
    | `data.[].apiTimeout` | integer, nullable |  | API request timeout |
    | `data.[].apiUrl` | string, nullable |  | API request URL |
    | `data.[].apiMethod` | string, nullable |  | API HTTP method |
    | `data.[].apiIgnoreCert` | boolean, nullable |  | Whether API certificate validation is disabled |
    | `data.[].apiJsonq` | string, nullable |  | JSON query used to extract the API result |
    | `data.[].apiBody` | string, nullable |  | API request body |
    | `data.[].apiHeaders` | object, nullable |  | API request headers |
    | `data.[].apiErrorCodes` | string, nullable |  | API error code configuration |
    | `data.[].apiConditions` | object, nullable |  | API response conditions |
    | `data.[].parentModuleId` | integer, nullable |  | Parent module identifier |
    | `data.[].cps` | boolean, nullable |  | Whether change-per-second calculation is enabled |
    | `data.[].cpsInhibit` | integer, nullable |  | Change-per-second inhibition interval |
    | `data.[].debugContent` | string, nullable |  | Last module debug content |
    | `data.[].percentageCritical` | boolean, nullable |  | Whether critical thresholds are percentages |
    | `data.[].percentageWarning` | boolean, nullable |  | Whether warning thresholds are percentages |
    | `data.[].warningTime` | integer, nullable |  | Minimum warning duration |
    | `data.[].quietByDowntime` | boolean, nullable |  | Whether downtime silenced the module |
    | `data.[].disabledByDowntime` | boolean, nullable |  | Whether downtime disabled the module |
    | `data.[].madeEnabled` | boolean, nullable |  | Whether downtime enabled the module |
    | `data.[].ignoreUnknown` | boolean, nullable |  | Whether unknown status is ignored |
    | `data.[].extraData` | string, nullable |  | Additional serialized module data |
    | `data.[].idDataTranslation` | integer, nullable |  | Data translation identifier |
    | `data.[].serverId` | integer, nullable |  | Node identifier for metaconsole operations |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/agentModule/{idAgentModule}/graph` { #post-agentmodule-idagentmodule-graph }

Render a module graph as a base64 image

Read-only operation. serverId is required on a metaconsole and is rejected on a node.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `period` | integer |  | Duration in seconds. Cannot be combined with dateFrom; may be combined with dateTo. |
| `dateFrom` | string (date-time) |  | Range start. Cannot be combined with period; the range must last at least 300 seconds. |
| `dateTo` | string (date-time) |  | Range end, no later than now. May be combined with period. Defaults to now. |
| `graphType` | enum: `data`, `histogram` |  |  |
| `modeChart` | enum: `avg`, `max`, `min`, `avg-max-min`, `tip` |  | Data graphs only; rejected for histogram. tip cannot use a positive periodSliceChart. |
| `chartType` | enum: `line`, `area`, `bar` |  |  |
| `timeComparison` | enum: `default`, `separated`, `overlapped` |  |  |
| `showUnknown` | boolean |  |  |
| `drawEvents` | boolean |  |  |
| `drawAlerts` | boolean |  |  |
| `showPercentile` | boolean |  |  |
| `baseline` | boolean |  | When true, timeComparison must be omitted or default. Not supported for histogram. |
| `periodSliceChart` | integer |  | Aggregation slice in seconds; cannot exceed the resolved graph period. |
| `enableProjectedPeriod` | boolean |  |  |
| `periodProjected` | integer |  | Only send this field when enableProjectedPeriod is true. |
| `idDataTranslation` | integer |  |  |
| `timezone` | string |  |  |
| `width` | integer |  |  |
| `height` | integer |  |  |
| `enableProjectedPeriod` | enum: `True` | yes |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "period": 86400,
      "dateFrom": "string",
      "dateTo": "string",
      "graphType": "data",
      "modeChart": "avg",
      "chartType": "line",
      "timeComparison": "default",
      "showUnknown": true,
      "drawEvents": false,
      "drawAlerts": false,
      "showPercentile": false,
      "baseline": false,
      "periodSliceChart": 0,
      "enableProjectedPeriod": true,
      "periodProjected": 300,
      "idDataTranslation": 0,
      "timezone": "Europe/Madrid",
      "width": 600,
      "height": 225
    }
    ```

**Response 200**: Module graph

??? note "Response fields (9 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAgentModule` | integer | yes |  |
    | `serverId` | integer, nullable |  |  |
    | `period` | integer | yes |  |
    | `dateFrom` | string (date-time) | yes |  |
    | `dateTo` | string (date-time) | yes |  |
    | `graphType` | enum: `data`, `histogram` | yes |  |
    | `mimeType` | enum: `image/png`, `image/jpeg` | yes |  |
    | `encoding` | enum: `base64` | yes |  |
    | `graph` | string (byte) | yes |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

## AgentModuleData

API Endpoints for agent module data

### <span class="api-method api-get">GET</span> `/agentModule/{idAgentModule}/agentModuleData/{utimestamp}` { #get-agentmodule-idagentmodule-agentmoduledata-utimestamp }

Gets historical agent module data

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `utimestamp` | path | integer (int64) | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Agent module data

??? note "Response fields (4 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAgentModule` | integer |  |  |
    | `data` |  |  |  |
    | `utimestamp` | integer (int64) |  |  |
    | `serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/agentModule/{idAgentModule}/agentModuleData/list` { #post-agentmodule-idagentmodule-agentmoduledata-list }

Lists historical agent module data

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgentModule` | integer |  |  |
| `data` |  |  |  |
| `utimestamp` | integer (int64) |  |  |
| `serverId` | integer, nullable |  |  |
| `fromUtimestamp` | integer (int64), nullable |  |  |
| `toUtimestamp` | integer (int64), nullable |  |  |
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
| `multipleSearch.field` | enum: `idAgentModule`, `data`, `utimestamp` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAgentModule`, `data`, `utimestamp` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "fromUtimestamp": 0,
      "toUtimestamp": 0,
      "serverId": 0,
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
      }
    }
    ```

**Response 200**: Agent module data list

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
    | `data.[].idAgentModule` | integer |  |  |
    | `data.[].data` |  |  |  |
    | `data.[].utimestamp` | integer (int64) |  |  |
    | `data.[].serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/agentModule/{idAgentModule}/agentModuleData/uncompressed/list` { #get-agentmodule-idagentmodule-agentmoduledata-uncompressed-list }

Lists uncompressed historical agent module data

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `fromUtimestamp` | query | integer (int64) |  |  |
| `toUtimestamp` | query | integer (int64) |  |  |
| `period` | query | enum: `hour`, `day`, `week`, `month` |  |  |
| `sliceSize` | query | integer |  |  |

**Response 200**: Uncompressed agent module data list

??? note "Response fields (9 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `data` | array of object |  |  |
    | `data.[].idAgentModule` | integer |  |  |
    | `data.[].data` |  |  |  |
    | `data.[].utimestamp` | integer (int64) |  |  |
    | `data.[].serverId` | integer, nullable |  |  |
    | `metadata` | object |  |  |
    | `metadata.fromUtimestamp` | integer (int64) |  |  |
    | `metadata.toUtimestamp` | integer (int64) |  |  |
    | `metadata.sliceSize` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/agentModule/{idAgentModule}/agentModuleData/uncompressed/list` { #post-agentmodule-idagentmodule-agentmoduledata-uncompressed-list }

Lists uncompressed historical agent module data

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `fromUtimestamp` | integer (int64) |  |  |
| `toUtimestamp` | integer (int64) |  |  |
| `period` | enum: `hour`, `day`, `week`, `month` |  |  |
| `sliceSize` | integer, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "fromUtimestamp": 0,
      "toUtimestamp": 0,
      "period": "hour",
      "sliceSize": 0
    }
    ```

**Response 200**: Uncompressed agent module data list

??? note "Response fields (9 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `data` | array of object |  |  |
    | `data.[].idAgentModule` | integer |  |  |
    | `data.[].data` |  |  |  |
    | `data.[].utimestamp` | integer (int64) |  |  |
    | `data.[].serverId` | integer, nullable |  |  |
    | `metadata` | object |  |  |
    | `metadata.fromUtimestamp` | integer (int64) |  |  |
    | `metadata.toUtimestamp` | integer (int64) |  |  |
    | `metadata.sliceSize` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

## AgentModuleStates

API Endpoints for agent module states

### <span class="api-method api-get">GET</span> `/agentModule/{idAgentModule}/agentModuleState` { #get-agentmodule-idagentmodule-agentmodulestate }

Gets the current state of an agent module

Reads tagente_estado. The monitoring system remains the only writer.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Agent module state

??? note "Response fields (25 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAgentModuleState` | integer |  |  |
    | `idAgentModule` | integer |  |  |
    | `idAgent` | integer |  |  |
    | `data` | string, nullable |  |  |
    | `timestamp` | string |  |  |
    | `status` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Module status: 0 normal, 1 critical, 2 warning, 3 unknown, 4 no data, 5 not initialized, 6 not normal, 7 forced normal, 100 critical with alert fired, 200 warning with alert fired, 300 normal with alert fired |
    | `knownStatus` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Last known module status, using the same values as status |
    | `lastTry` | string, nullable |  |  |
    | `utimestamp` | integer (int64) |  |  |
    | `currentInterval` | integer |  |  |
    | `runningBy` | integer, nullable |  |  |
    | `lastExecutionTry` | integer (int64) |  |  |
    | `statusChanges` | integer |  |  |
    | `lastStatus` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Previous module status, using the same values as status |
    | `lastKnownStatus` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Previous known module status, using the same values as status |
    | `lastError` | integer |  |  |
    | `ffStartUtimestamp` | integer (int64), nullable |  |  |
    | `ffNormal` | integer |  |  |
    | `ffWarning` | integer |  |  |
    | `ffCritical` | integer |  |  |
    | `lastDynamicUpdate` | integer (int64) |  |  |
    | `lastUnknownUpdate` | integer (int64) |  |  |
    | `lastStatusChange` | integer (int64) |  |  |
    | `warningCount` | integer |  |  |
    | `serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/agentModuleState/list` { #get-agentmodulestate-list }

Lists current agent module states

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Agent module state list

??? note "Response fields (35 fields)"

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
    | `data.[].idAgentModuleState` | integer |  |  |
    | `data.[].idAgentModule` | integer |  |  |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].data` | string, nullable |  |  |
    | `data.[].timestamp` | string |  |  |
    | `data.[].status` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Module status: 0 normal, 1 critical, 2 warning, 3 unknown, 4 no data, 5 not initialized, 6 not normal, 7 forced normal, 100 critical with alert fired, 200 warning with alert fired, 300 normal with alert fired |
    | `data.[].knownStatus` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Last known module status, using the same values as status |
    | `data.[].lastTry` | string, nullable |  |  |
    | `data.[].utimestamp` | integer (int64) |  |  |
    | `data.[].currentInterval` | integer |  |  |
    | `data.[].runningBy` | integer, nullable |  |  |
    | `data.[].lastExecutionTry` | integer (int64) |  |  |
    | `data.[].statusChanges` | integer |  |  |
    | `data.[].lastStatus` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Previous module status, using the same values as status |
    | `data.[].lastKnownStatus` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Previous known module status, using the same values as status |
    | `data.[].lastError` | integer |  |  |
    | `data.[].ffStartUtimestamp` | integer (int64), nullable |  |  |
    | `data.[].ffNormal` | integer |  |  |
    | `data.[].ffWarning` | integer |  |  |
    | `data.[].ffCritical` | integer |  |  |
    | `data.[].lastDynamicUpdate` | integer (int64) |  |  |
    | `data.[].lastUnknownUpdate` | integer (int64) |  |  |
    | `data.[].lastStatusChange` | integer (int64) |  |  |
    | `data.[].warningCount` | integer |  |  |
    | `data.[].serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/agentModuleState/list` { #post-agentmodulestate-list }

Lists current agent module states

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
| `idAgentModuleState` | integer |  |  |
| `idAgentModule` | integer |  |  |
| `idAgent` | integer |  |  |
| `data` | string, nullable |  |  |
| `timestamp` | string |  |  |
| `status` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Module status: 0 normal, 1 critical, 2 warning, 3 unknown, 4 no data, 5 not initialized, 6 not normal, 7 forced normal, 100 critical with alert fired, 200 warning with alert fired, 300 normal with alert fired |
| `knownStatus` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Last known module status, using the same values as status |
| `lastTry` | string, nullable |  |  |
| `utimestamp` | integer (int64) |  |  |
| `currentInterval` | integer |  |  |
| `runningBy` | integer, nullable |  |  |
| `lastExecutionTry` | integer (int64) |  |  |
| `statusChanges` | integer |  |  |
| `lastStatus` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Previous module status, using the same values as status |
| `lastKnownStatus` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Previous known module status, using the same values as status |
| `lastError` | integer |  |  |
| `ffStartUtimestamp` | integer (int64), nullable |  |  |
| `ffNormal` | integer |  |  |
| `ffWarning` | integer |  |  |
| `ffCritical` | integer |  |  |
| `lastDynamicUpdate` | integer (int64) |  |  |
| `lastUnknownUpdate` | integer (int64) |  |  |
| `lastStatusChange` | integer (int64) |  |  |
| `warningCount` | integer |  |  |
| `serverId` | integer, nullable |  |  |
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
| `multipleSearch.field` | enum: `idAgentModuleState`, `idAgentModule`, `idAgent`, `data`, `timestamp`, `status`, `knownStatus`, `lastTry`, `utimestamp`, `currentInterval`, `runningBy`, `lastExecutionTry`, `statusChanges`, `lastStatus`, `lastKnownStatus`, `lastError`, `ffStartUtimestamp`, `ffNormal`, `ffWarning`, `ffCritical`, `lastDynamicUpdate`, `lastUnknownUpdate`, `lastStatusChange`, `warningCount` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAgentModuleState`, `idAgentModule`, `idAgent`, `data`, `timestamp`, `status`, `knownStatus`, `lastTry`, `utimestamp`, `currentInterval`, `runningBy`, `lastExecutionTry`, `statusChanges`, `lastStatus`, `lastKnownStatus`, `lastError`, `ffStartUtimestamp`, `ffNormal`, `ffWarning`, `ffCritical`, `lastDynamicUpdate`, `lastUnknownUpdate`, `lastStatusChange`, `warningCount` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "serverId": 0,
      "requestedFields": [
        "idAgentModuleState"
      ],
      "fieldConditions": [
        {
          "field": "idAgentModuleState",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idAgentModuleState",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAgentModuleState",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Agent module state list

??? note "Response fields (35 fields)"

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
    | `data.[].idAgentModuleState` | integer |  |  |
    | `data.[].idAgentModule` | integer |  |  |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].data` | string, nullable |  |  |
    | `data.[].timestamp` | string |  |  |
    | `data.[].status` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Module status: 0 normal, 1 critical, 2 warning, 3 unknown, 4 no data, 5 not initialized, 6 not normal, 7 forced normal, 100 critical with alert fired, 200 warning with alert fired, 300 normal with alert fired |
    | `data.[].knownStatus` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Last known module status, using the same values as status |
    | `data.[].lastTry` | string, nullable |  |  |
    | `data.[].utimestamp` | integer (int64) |  |  |
    | `data.[].currentInterval` | integer |  |  |
    | `data.[].runningBy` | integer, nullable |  |  |
    | `data.[].lastExecutionTry` | integer (int64) |  |  |
    | `data.[].statusChanges` | integer |  |  |
    | `data.[].lastStatus` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Previous module status, using the same values as status |
    | `data.[].lastKnownStatus` | enum: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `100`, `200`, `300` |  | Previous known module status, using the same values as status |
    | `data.[].lastError` | integer |  |  |
    | `data.[].ffStartUtimestamp` | integer (int64), nullable |  |  |
    | `data.[].ffNormal` | integer |  |  |
    | `data.[].ffWarning` | integer |  |  |
    | `data.[].ffCritical` | integer |  |  |
    | `data.[].lastDynamicUpdate` | integer (int64) |  |  |
    | `data.[].lastUnknownUpdate` | integer (int64) |  |  |
    | `data.[].lastStatusChange` | integer (int64) |  |  |
    | `data.[].warningCount` | integer |  |  |
    | `data.[].serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

## AgentModuleTags

API Endpoints for tags assigned to agent modules

### <span class="api-method api-post">POST</span> `/agentModule/{idAgentModule}/tag` { #post-agentmodule-idagentmodule-tag }

Associates a tag with an agent module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idTag` | integer | yes |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idTag": 0
    }
    ```

**Response 200**: Agent module tag

Schema: [`AgentModuleTag`](#model-agentmoduletag)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/agentModule/{idAgentModule}/tag/{idTag}` { #get-agentmodule-idagentmodule-tag-idtag }

Gets an agent module tag association

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `idTag` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Agent module tag

Schema: [`AgentModuleTag`](#model-agentmoduletag)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/agentModule/{idAgentModule}/tag/{idTag}` { #delete-agentmodule-idagentmodule-tag-idtag }

Removes a manual tag association from an agent module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `idTag` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/agentModule/{idAgentModule}/tag/list` { #get-agentmodule-idagentmodule-tag-list }

Lists tags associated with an agent module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Agent module tag list

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
    | `data.[].idAgentModule` | integer |  |  |
    | `data.[].idTag` | integer |  |  |
    | `data.[].idPolicyModule` | integer |  |  |
    | `data.[].serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/agentModule/{idAgentModule}/tag/list` { #post-agentmodule-idagentmodule-tag-list }

Lists tags associated with an agent module

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgentModule` | integer |  |  |
| `idTag` | integer |  |  |
| `idPolicyModule` | integer |  |  |
| `serverId` | integer, nullable |  |  |
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
| `multipleSearch.field` | enum: `idAgentModule`, `idTag`, `idPolicyModule` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAgentModule`, `idTag`, `idPolicyModule` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idTag": 0,
      "serverId": 0,
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
      }
    }
    ```

**Response 200**: Agent module tag list

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
    | `data.[].idAgentModule` | integer |  |  |
    | `data.[].idTag` | integer |  |  |
    | `data.[].idPolicyModule` | integer |  |  |
    | `data.[].serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

## AgentModulePolicies

Relink or unlink modules from their existing source policy

### <span class="api-method api-post">POST</span> `/agentModule/{idAgentModule}/policy/link` { #post-agentmodule-idagentmodule-policy-link }

Relink a module to its source policy

No body is required. Policy is inferred from the module. 0 becomes 11; 10 becomes 1.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes | Agent module instance identifier |
| `serverId` | query | integer |  | Node selector on a metaconsole; required for mutations, optional for aggregated lists |

**Response 200**: Resulting link state; states 1 and 11 are idempotent

Schema: [`PolicyLinking`](#model-policylinking)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-post">POST</span> `/agentModule/{idAgentModule}/policy/unlink` { #post-agentmodule-idagentmodule-policy-unlink }

Unlink a module from its source policy

No body is required. 1 becomes 10; 11 becomes 0. Source and adoption are preserved.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes | Agent module instance identifier |
| `serverId` | query | integer |  | Node selector on a metaconsole; required for mutations, optional for aggregated lists |

**Response 200**: Resulting link state; states 0 and 10 are idempotent

Schema: [`PolicyLinking`](#model-policylinking)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

## ModuleGroups

API Endpoints for module groups

### <span class="api-method api-post">POST</span> `/moduleGroup` { #post-modulegroup }

Creates a new module groups

**Request body** (`application/json`): [`ModuleGroup`](#model-modulegroup)

**Response 200**: Module group object

Schema: [`ModuleGroup`](#model-modulegroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/moduleGroup/{idModuleGroup}` { #get-modulegroup-idmodulegroup }

Show module group

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idModuleGroup` | path | integer | yes |  |

**Response 200**: Module group object

Schema: [`ModuleGroup`](#model-modulegroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/moduleGroup/{idModuleGroup}` { #put-modulegroup-idmodulegroup }

Updates an moduleGroup

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idModuleGroup` | path | integer | yes |  |

**Request body** (`application/json`): [`ModuleGroup`](#model-modulegroup)

**Response 200**: Module group object

Schema: [`ModuleGroup`](#model-modulegroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/moduleGroup/{idModuleGroup}` { #delete-modulegroup-idmodulegroup }

Deletes an module group object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idModuleGroup` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/moduleGroup/list` { #get-modulegroup-list }

List module groups

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Incidence object

??? note "Response fields (12 fields)"

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
    | `data.[].idModuleGroup` | integer |  | Module group identifier |
    | `data.[].name` | string | yes | Module group name |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/moduleGroup/list` { #post-modulegroup-list }

List module groups

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
| `idModuleGroup` | integer |  | Module group identifier |
| `name` | string | yes | Module group name |
| `idModuleGroup` |  |  |  |
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
| `multipleSearch.field` | enum: `idModuleGroup`, `name` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idModuleGroup`, `name` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idModuleGroup": null,
      "freeSearch": "string",
      "requestedFields": [
        "idModuleGroup"
      ],
      "fieldConditions": [
        {
          "field": "idModuleGroup",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idModuleGroup",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idModuleGroup",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List Incidence object

??? note "Response fields (12 fields)"

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
    | `data.[].idModuleGroup` | integer |  | Module group identifier |
    | `data.[].name` | string | yes | Module group name |


Error responses: `400`, `401`, `403`, `404`, `500`.

## ModuleTypes

API Endpoints for module types

### <span class="api-method api-get">GET</span> `/moduleType/{idModuleType}` { #get-moduletype-idmoduletype }

Get a module type

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idModuleType` | path | integer | yes |  |

**Response 200**: Module type object

??? note "Response fields (6 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idModuleType` | integer |  |  |
    | `name` | string |  |  |
    | `category` | integer |  |  |
    | `description` | string |  |  |
    | `icon` | string, nullable |  |  |
    | `dataType` | enum: `numeric`, `boolean`, `string` |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/moduleType/list` { #get-moduletype-list }

List module types

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Module type list

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
    | `data.[].idModuleType` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].category` | integer |  |  |
    | `data.[].description` | string |  |  |
    | `data.[].icon` | string, nullable |  |  |
    | `data.[].dataType` | enum: `numeric`, `boolean`, `string` |  |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/moduleType/list` { #post-moduletype-list }

List and filter module types

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
| `idModuleType` | integer |  |  |
| `name` | string |  |  |
| `category` | integer |  |  |
| `description` | string |  |  |
| `icon` | string, nullable |  |  |
| `dataType` | enum: `numeric`, `boolean`, `string` |  |  |
| `idModuleType` |  |  |  |
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
| `multipleSearch.field` | enum: `idModuleType`, `name`, `category`, `description`, `icon`, `dataType` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idModuleType`, `name`, `category`, `description`, `icon`, `dataType` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "category": 0,
      "description": "string",
      "icon": "string",
      "dataType": "numeric",
      "idModuleType": null,
      "freeSearch": "string",
      "requestedFields": [
        "idModuleType"
      ],
      "fieldConditions": [
        {
          "field": "idModuleType",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idModuleType",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idModuleType",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Module type list

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
    | `data.[].idModuleType` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].category` | integer |  |  |
    | `data.[].description` | string |  |  |
    | `data.[].icon` | string, nullable |  |  |
    | `data.[].dataType` | enum: `numeric`, `boolean`, `string` |  |  |


Error responses: `400`, `401`, `403`, `500`.

## LocalComponents

API Endpoints for local components

### <span class="api-method api-post">POST</span> `/localComponent` { #post-localcomponent }

Creates a new local component

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idLocalComponent` | integer |  | Local component identifier |
| `name` | string, nullable | yes | Local component name |
| `data` | string, nullable | yes | Module configuration text |
| `description` | string, nullable |  | Local component description |
| `idOs` | integer, nullable | yes | Operating system identifier |
| `osVersion` | string, nullable |  | Operating system version |
| `idNetworkComponentGroup` | integer, nullable | yes | Component group identifier |
| `idModuleType` | integer, nullable |  | Module type identifier |
| `max` | integer, nullable |  | Maximum value |
| `min` | integer, nullable |  | Minimum value |
| `moduleInterval` | integer, nullable |  | Module interval in seconds |
| `idModuleGroup` | integer, nullable |  | Module group identifier |
| `historyData` | boolean, nullable |  | Store module history |
| `minWarning` | number, nullable |  | Warning minimum threshold |
| `maxWarning` | number, nullable |  | Warning maximum threshold |
| `strWarning` | string, nullable |  | Warning string threshold |
| `minCritical` | number, nullable |  | Critical minimum threshold |
| `maxCritical` | number, nullable |  | Critical maximum threshold |
| `strCritical` | string, nullable |  | Critical string threshold |
| `minFfEvent` | integer, nullable |  | Minimum events for flip-flop |
| `postProcess` | number, nullable |  | Post-process value |
| `unit` | string, nullable |  | Module unit |
| `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  | Wizard level |
| `macros` | string, nullable |  | Macros text |
| `criticalInstructions` | string, nullable |  | Critical instructions |
| `warningInstructions` | string, nullable |  | Warning instructions |
| `unknownInstructions` | string, nullable |  | Unknown instructions |
| `criticalInverse` | boolean, nullable |  | Inverse critical comparison |
| `warningInverse` | boolean, nullable |  | Inverse warning comparison |
| `idCategory` | integer, nullable |  | Category identifier |
| `tags` | string, nullable |  | Comma-separated tag identifiers |
| `disabledTypesEvent` | string, nullable |  | Disabled event types as JSON |
| `minFfEventNormal` | integer, nullable |  | Minimum normal events |
| `minFfEventWarning` | integer, nullable |  | Minimum warning events |
| `minFfEventCritical` | integer, nullable |  | Minimum critical events |
| `ffType` | boolean, nullable |  | Flip-flop type |
| `eachFf` | boolean, nullable |  | Evaluate each flip-flop |
| `ffTimeout` | integer, nullable |  | Flip-flop timeout |
| `dynamicInterval` | integer, nullable |  | Dynamic interval |
| `dynamicMax` | integer, nullable |  | Dynamic maximum |
| `dynamicMin` | integer, nullable |  | Dynamic minimum |
| `dynamicNext` | integer, nullable |  | Next dynamic execution |
| `dynamicTwoTailed` | boolean, nullable |  | Dynamic two-tailed mode |
| `predictionSampleWindow` | integer, nullable |  | Prediction sample window |
| `predictionSamples` | integer, nullable |  | Prediction samples |
| `predictionThreshold` | integer, nullable |  | Prediction threshold |
| `percentageCritical` | boolean, nullable |  | Critical percentage mode |
| `percentageWarning` | boolean, nullable |  | Warning percentage mode |
| `warningTime` | integer, nullable |  | Warning time |
| `moduleMacros` | string, nullable |  | Base64 encoded module macros |
| `isInternal` | boolean |  | Internal component flag |
| `idDataTranslation` | integer, nullable |  | Data translation identifier |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "data": "string",
      "description": "string",
      "idOs": 0,
      "osVersion": "string",
      "idNetworkComponentGroup": 0,
      "idModuleType": 0,
      "max": 0,
      "min": 0,
      "moduleInterval": 0,
      "idModuleGroup": 0,
      "historyData": false,
      "minWarning": 0,
      "maxWarning": 0,
      "strWarning": "string",
      "minCritical": 0,
      "maxCritical": 0,
      "strCritical": "string",
      "minFfEvent": 0,
      "postProcess": 0,
      "unit": "string",
      "wizardLevel": "basic",
      "macros": "string",
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "criticalInverse": false,
      "warningInverse": false,
      "idCategory": 0,
      "tags": "string",
      "disabledTypesEvent": "string",
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
      "percentageCritical": false,
      "percentageWarning": false,
      "warningTime": 0,
      "moduleMacros": "string",
      "idDataTranslation": 0
    }
    ```

**Response 200**: Local component object

Schema: [`LocalComponent`](#model-localcomponent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/localComponent/{idLocalComponent}` { #get-localcomponent-idlocalcomponent }

Show a local component

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idLocalComponent` | path | integer | yes |  |

**Response 200**: Local component object

Schema: [`LocalComponent`](#model-localcomponent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/localComponent/{idLocalComponent}` { #put-localcomponent-idlocalcomponent }

Updates a local component

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idLocalComponent` | path | integer | yes |  |

**Request body** (`application/json`): [`LocalComponent`](#model-localcomponent)

**Response 200**: Local component object

Schema: [`LocalComponent`](#model-localcomponent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/localComponent/{idLocalComponent}` { #delete-localcomponent-idlocalcomponent }

Deletes a local component

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idLocalComponent` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/localComponent/list` { #get-localcomponent-list }

List local components using query filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `freeSearch` | query | string |  |  |
| `idLocalComponent` | query | integer |  |  |
| `name` | query | string |  |  |
| `description` | query | string |  |  |
| `idOs` | query | integer |  |  |
| `osVersion` | query | string |  |  |
| `idNetworkComponentGroup` | query | integer |  |  |
| `idModuleType` | query | integer |  |  |
| `idModuleGroup` | query | integer |  |  |
| `wizardLevel` | query | enum: `basic`, `advanced`, `nowizard` |  |  |
| `idCategory` | query | integer |  |  |
| `moduleInterval` | query | integer |  |  |
| `tags` | query | string |  |  |

**Response 200**: Local component list

??? note "Response fields (62 fields)"

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
    | `data.[].idLocalComponent` | integer |  | Local component identifier |
    | `data.[].name` | string, nullable |  | Local component name |
    | `data.[].data` | string, nullable |  | Module configuration text |
    | `data.[].description` | string, nullable |  | Local component description |
    | `data.[].idOs` | integer, nullable |  | Operating system identifier |
    | `data.[].osVersion` | string, nullable |  | Operating system version |
    | `data.[].idNetworkComponentGroup` | integer, nullable |  | Component group identifier |
    | `data.[].idModuleType` | integer, nullable |  | Module type identifier |
    | `data.[].max` | integer, nullable |  | Maximum value |
    | `data.[].min` | integer, nullable |  | Minimum value |
    | `data.[].moduleInterval` | integer, nullable |  | Module interval in seconds |
    | `data.[].idModuleGroup` | integer, nullable |  | Module group identifier |
    | `data.[].historyData` | boolean, nullable |  | Store module history |
    | `data.[].minWarning` | number, nullable |  | Warning minimum threshold |
    | `data.[].maxWarning` | number, nullable |  | Warning maximum threshold |
    | `data.[].strWarning` | string, nullable |  | Warning string threshold |
    | `data.[].minCritical` | number, nullable |  | Critical minimum threshold |
    | `data.[].maxCritical` | number, nullable |  | Critical maximum threshold |
    | `data.[].strCritical` | string, nullable |  | Critical string threshold |
    | `data.[].minFfEvent` | integer, nullable |  | Minimum events for flip-flop |
    | `data.[].postProcess` | number, nullable |  | Post-process value |
    | `data.[].unit` | string, nullable |  | Module unit |
    | `data.[].wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  | Wizard level |
    | `data.[].macros` | string, nullable |  | Macros text |
    | `data.[].criticalInstructions` | string, nullable |  | Critical instructions |
    | `data.[].warningInstructions` | string, nullable |  | Warning instructions |
    | `data.[].unknownInstructions` | string, nullable |  | Unknown instructions |
    | `data.[].criticalInverse` | boolean, nullable |  | Inverse critical comparison |
    | `data.[].warningInverse` | boolean, nullable |  | Inverse warning comparison |
    | `data.[].idCategory` | integer, nullable |  | Category identifier |
    | `data.[].tags` | string, nullable |  | Comma-separated tag identifiers |
    | `data.[].disabledTypesEvent` | string, nullable |  | Disabled event types as JSON |
    | `data.[].minFfEventNormal` | integer, nullable |  | Minimum normal events |
    | `data.[].minFfEventWarning` | integer, nullable |  | Minimum warning events |
    | `data.[].minFfEventCritical` | integer, nullable |  | Minimum critical events |
    | `data.[].ffType` | boolean, nullable |  | Flip-flop type |
    | `data.[].eachFf` | boolean, nullable |  | Evaluate each flip-flop |
    | `data.[].ffTimeout` | integer, nullable |  | Flip-flop timeout |
    | `data.[].dynamicInterval` | integer, nullable |  | Dynamic interval |
    | `data.[].dynamicMax` | integer, nullable |  | Dynamic maximum |
    | `data.[].dynamicMin` | integer, nullable |  | Dynamic minimum |
    | `data.[].dynamicNext` | integer, nullable |  | Next dynamic execution |
    | `data.[].dynamicTwoTailed` | boolean, nullable |  | Dynamic two-tailed mode |
    | `data.[].predictionSampleWindow` | integer, nullable |  | Prediction sample window |
    | `data.[].predictionSamples` | integer, nullable |  | Prediction samples |
    | `data.[].predictionThreshold` | integer, nullable |  | Prediction threshold |
    | `data.[].percentageCritical` | boolean, nullable |  | Critical percentage mode |
    | `data.[].percentageWarning` | boolean, nullable |  | Warning percentage mode |
    | `data.[].warningTime` | integer, nullable |  | Warning time |
    | `data.[].moduleMacros` | string, nullable |  | Base64 encoded module macros |
    | `data.[].isInternal` | boolean |  | Internal component flag |
    | `data.[].idDataTranslation` | integer, nullable |  | Data translation identifier |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/localComponent/list` { #post-localcomponent-list }

List local components using advanced filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `freeSearch` | query | string |  |  |
| `idLocalComponent` | query | integer |  |  |
| `name` | query | string |  |  |
| `description` | query | string |  |  |
| `idOs` | query | integer |  |  |
| `osVersion` | query | string |  |  |
| `idNetworkComponentGroup` | query | integer |  |  |
| `idModuleType` | query | integer |  |  |
| `idModuleGroup` | query | integer |  |  |
| `wizardLevel` | query | enum: `basic`, `advanced`, `nowizard` |  |  |
| `idCategory` | query | integer |  |  |
| `moduleInterval` | query | integer |  |  |
| `tags` | query | string |  |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idLocalComponent` | integer |  | Local component identifier |
| `name` | string, nullable |  | Local component name |
| `data` | string, nullable |  | Module configuration text |
| `description` | string, nullable |  | Local component description |
| `idOs` | integer, nullable |  | Operating system identifier |
| `osVersion` | string, nullable |  | Operating system version |
| `idNetworkComponentGroup` | integer, nullable |  | Component group identifier |
| `idModuleType` | integer, nullable |  | Module type identifier |
| `max` | integer, nullable |  | Maximum value |
| `min` | integer, nullable |  | Minimum value |
| `moduleInterval` | integer, nullable |  | Module interval in seconds |
| `idModuleGroup` | integer, nullable |  | Module group identifier |
| `historyData` | boolean, nullable |  | Store module history |
| `minWarning` | number, nullable |  | Warning minimum threshold |
| `maxWarning` | number, nullable |  | Warning maximum threshold |
| `strWarning` | string, nullable |  | Warning string threshold |
| `minCritical` | number, nullable |  | Critical minimum threshold |
| `maxCritical` | number, nullable |  | Critical maximum threshold |
| `strCritical` | string, nullable |  | Critical string threshold |
| `minFfEvent` | integer, nullable |  | Minimum events for flip-flop |
| `postProcess` | number, nullable |  | Post-process value |
| `unit` | string, nullable |  | Module unit |
| `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  | Wizard level |
| `macros` | string, nullable |  | Macros text |
| `criticalInstructions` | string, nullable |  | Critical instructions |
| `warningInstructions` | string, nullable |  | Warning instructions |
| `unknownInstructions` | string, nullable |  | Unknown instructions |
| `criticalInverse` | boolean, nullable |  | Inverse critical comparison |
| `warningInverse` | boolean, nullable |  | Inverse warning comparison |
| `idCategory` | integer, nullable |  | Category identifier |
| `tags` | string, nullable |  | Comma-separated tag identifiers |
| `disabledTypesEvent` | string, nullable |  | Disabled event types as JSON |
| `minFfEventNormal` | integer, nullable |  | Minimum normal events |
| `minFfEventWarning` | integer, nullable |  | Minimum warning events |
| `minFfEventCritical` | integer, nullable |  | Minimum critical events |
| `ffType` | boolean, nullable |  | Flip-flop type |
| `eachFf` | boolean, nullable |  | Evaluate each flip-flop |
| `ffTimeout` | integer, nullable |  | Flip-flop timeout |
| `dynamicInterval` | integer, nullable |  | Dynamic interval |
| `dynamicMax` | integer, nullable |  | Dynamic maximum |
| `dynamicMin` | integer, nullable |  | Dynamic minimum |
| `dynamicNext` | integer, nullable |  | Next dynamic execution |
| `dynamicTwoTailed` | boolean, nullable |  | Dynamic two-tailed mode |
| `predictionSampleWindow` | integer, nullable |  | Prediction sample window |
| `predictionSamples` | integer, nullable |  | Prediction samples |
| `predictionThreshold` | integer, nullable |  | Prediction threshold |
| `percentageCritical` | boolean, nullable |  | Critical percentage mode |
| `percentageWarning` | boolean, nullable |  | Warning percentage mode |
| `warningTime` | integer, nullable |  | Warning time |
| `moduleMacros` | string, nullable |  | Base64 encoded module macros |
| `isInternal` | boolean |  | Internal component flag |
| `idDataTranslation` | integer, nullable |  | Data translation identifier |
| `idLocalComponent` |  |  |  |
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
| `multipleSearch.field` | enum: `idLocalComponent`, `name`, `data`, `description`, `idOs`, `osVersion`, `idNetworkComponentGroup`, `idModuleType`, `max`, `min`, `moduleInterval`, `idModuleGroup`, `historyData`, `minWarning`, `maxWarning`, `strWarning`, `minCritical`, `maxCritical`, `strCritical`, `minFfEvent`, `postProcess`, `unit`, `wizardLevel`, `macros`, `criticalInstructions`, `warningInstructions`, `unknownInstructions`, `criticalInverse`, `warningInverse`, `idCategory`, `tags`, `disabledTypesEvent`, `minFfEventNormal`, `minFfEventWarning`, `minFfEventCritical`, `ffType`, `eachFf`, `ffTimeout`, `dynamicInterval`, `dynamicMax`, `dynamicMin`, `dynamicNext`, `dynamicTwoTailed`, `predictionSampleWindow`, `predictionSamples`, `predictionThreshold`, `percentageCritical`, `percentageWarning`, `warningTime`, `moduleMacros`, `isInternal`, `idDataTranslation` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idLocalComponent`, `name`, `data`, `description`, `idOs`, `osVersion`, `idNetworkComponentGroup`, `idModuleType`, `max`, `min`, `moduleInterval`, `idModuleGroup`, `historyData`, `minWarning`, `maxWarning`, `strWarning`, `minCritical`, `maxCritical`, `strCritical`, `minFfEvent`, `postProcess`, `unit`, `wizardLevel`, `macros`, `criticalInstructions`, `warningInstructions`, `unknownInstructions`, `criticalInverse`, `warningInverse`, `idCategory`, `tags`, `disabledTypesEvent`, `minFfEventNormal`, `minFfEventWarning`, `minFfEventCritical`, `ffType`, `eachFf`, `ffTimeout`, `dynamicInterval`, `dynamicMax`, `dynamicMin`, `dynamicNext`, `dynamicTwoTailed`, `predictionSampleWindow`, `predictionSamples`, `predictionThreshold`, `percentageCritical`, `percentageWarning`, `warningTime`, `moduleMacros`, `isInternal`, `idDataTranslation` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "data": "string",
      "description": "string",
      "idOs": 0,
      "osVersion": "string",
      "idNetworkComponentGroup": 0,
      "idModuleType": 0,
      "max": 0,
      "min": 0,
      "moduleInterval": 0,
      "idModuleGroup": 0,
      "historyData": false,
      "minWarning": 0,
      "maxWarning": 0,
      "strWarning": "string",
      "minCritical": 0,
      "maxCritical": 0,
      "strCritical": "string",
      "minFfEvent": 0,
      "postProcess": 0,
      "unit": "string",
      "wizardLevel": "basic",
      "macros": "string",
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "criticalInverse": false,
      "warningInverse": false,
      "idCategory": 0,
      "tags": "string",
      "disabledTypesEvent": "string",
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
      "percentageCritical": false,
      "percentageWarning": false,
      "warningTime": 0,
      "moduleMacros": "string",
      "idDataTranslation": 0,
      "idLocalComponent": null,
      "freeSearch": "string",
      "requestedFields": [
        "idLocalComponent"
      ],
      "fieldConditions": [
        {
          "field": "idLocalComponent",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idLocalComponent",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idLocalComponent",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Local component list

??? note "Response fields (62 fields)"

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
    | `data.[].idLocalComponent` | integer |  | Local component identifier |
    | `data.[].name` | string, nullable |  | Local component name |
    | `data.[].data` | string, nullable |  | Module configuration text |
    | `data.[].description` | string, nullable |  | Local component description |
    | `data.[].idOs` | integer, nullable |  | Operating system identifier |
    | `data.[].osVersion` | string, nullable |  | Operating system version |
    | `data.[].idNetworkComponentGroup` | integer, nullable |  | Component group identifier |
    | `data.[].idModuleType` | integer, nullable |  | Module type identifier |
    | `data.[].max` | integer, nullable |  | Maximum value |
    | `data.[].min` | integer, nullable |  | Minimum value |
    | `data.[].moduleInterval` | integer, nullable |  | Module interval in seconds |
    | `data.[].idModuleGroup` | integer, nullable |  | Module group identifier |
    | `data.[].historyData` | boolean, nullable |  | Store module history |
    | `data.[].minWarning` | number, nullable |  | Warning minimum threshold |
    | `data.[].maxWarning` | number, nullable |  | Warning maximum threshold |
    | `data.[].strWarning` | string, nullable |  | Warning string threshold |
    | `data.[].minCritical` | number, nullable |  | Critical minimum threshold |
    | `data.[].maxCritical` | number, nullable |  | Critical maximum threshold |
    | `data.[].strCritical` | string, nullable |  | Critical string threshold |
    | `data.[].minFfEvent` | integer, nullable |  | Minimum events for flip-flop |
    | `data.[].postProcess` | number, nullable |  | Post-process value |
    | `data.[].unit` | string, nullable |  | Module unit |
    | `data.[].wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  | Wizard level |
    | `data.[].macros` | string, nullable |  | Macros text |
    | `data.[].criticalInstructions` | string, nullable |  | Critical instructions |
    | `data.[].warningInstructions` | string, nullable |  | Warning instructions |
    | `data.[].unknownInstructions` | string, nullable |  | Unknown instructions |
    | `data.[].criticalInverse` | boolean, nullable |  | Inverse critical comparison |
    | `data.[].warningInverse` | boolean, nullable |  | Inverse warning comparison |
    | `data.[].idCategory` | integer, nullable |  | Category identifier |
    | `data.[].tags` | string, nullable |  | Comma-separated tag identifiers |
    | `data.[].disabledTypesEvent` | string, nullable |  | Disabled event types as JSON |
    | `data.[].minFfEventNormal` | integer, nullable |  | Minimum normal events |
    | `data.[].minFfEventWarning` | integer, nullable |  | Minimum warning events |
    | `data.[].minFfEventCritical` | integer, nullable |  | Minimum critical events |
    | `data.[].ffType` | boolean, nullable |  | Flip-flop type |
    | `data.[].eachFf` | boolean, nullable |  | Evaluate each flip-flop |
    | `data.[].ffTimeout` | integer, nullable |  | Flip-flop timeout |
    | `data.[].dynamicInterval` | integer, nullable |  | Dynamic interval |
    | `data.[].dynamicMax` | integer, nullable |  | Dynamic maximum |
    | `data.[].dynamicMin` | integer, nullable |  | Dynamic minimum |
    | `data.[].dynamicNext` | integer, nullable |  | Next dynamic execution |
    | `data.[].dynamicTwoTailed` | boolean, nullable |  | Dynamic two-tailed mode |
    | `data.[].predictionSampleWindow` | integer, nullable |  | Prediction sample window |
    | `data.[].predictionSamples` | integer, nullable |  | Prediction samples |
    | `data.[].predictionThreshold` | integer, nullable |  | Prediction threshold |
    | `data.[].percentageCritical` | boolean, nullable |  | Critical percentage mode |
    | `data.[].percentageWarning` | boolean, nullable |  | Warning percentage mode |
    | `data.[].warningTime` | integer, nullable |  | Warning time |
    | `data.[].moduleMacros` | string, nullable |  | Base64 encoded module macros |
    | `data.[].isInternal` | boolean |  | Internal component flag |
    | `data.[].idDataTranslation` | integer, nullable |  | Data translation identifier |


Error responses: `400`, `401`, `403`, `404`, `500`.

## NetworkComponents

API Endpoints for network components

### <span class="api-method api-post">POST</span> `/networkComponent` { #post-networkcomponent }

Creates a new network component

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idNetworkComponent` | integer |  |  |
| `name` | string, nullable | yes |  |
| `description` | string, nullable |  |  |
| `idNetworkComponentGroup` | integer, nullable | yes |  |
| `idModuleType` | integer, nullable | yes |  |
| `max` | integer (int64), nullable |  |  |
| `min` | integer (int64), nullable |  |  |
| `moduleInterval` | integer, nullable |  |  |
| `tcpPort` | integer, nullable |  |  |
| `tcpSend` | string, nullable |  |  |
| `tcpRcv` | string, nullable |  |  |
| `snmpOid` | string, nullable |  |  |
| `idModuleGroup` | integer, nullable |  |  |
| `idModule` | integer, nullable | yes |  |
| `idPlugin` | integer, nullable |  |  |
| `pluginUser` | string, nullable |  |  |
| `pluginParameter` | string, nullable |  |  |
| `maxTimeout` | integer, nullable |  |  |
| `maxRetries` | integer, nullable |  |  |
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
| `postProcess` | number, nullable |  |  |
| `unit` | string, nullable |  |  |
| `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  |  |
| `macros` |  |  | Plugin macro list or wizard configuration object. |
| `criticalInstructions` | string, nullable |  |  |
| `warningInstructions` | string, nullable |  |  |
| `unknownInstructions` | string, nullable |  |  |
| `criticalInverse` | boolean, nullable |  |  |
| `warningInverse` | boolean, nullable |  |  |
| `idCategory` | integer, nullable |  |  |
| `tags` | string, nullable |  |  |
| `disabledTypesEvent` | object, nullable |  |  |
| `moduleMacros` | object, nullable |  |  |
| `minFfEventNormal` | integer, nullable |  |  |
| `minFfEventWarning` | integer, nullable |  |  |
| `minFfEventCritical` | integer, nullable |  |  |
| `ffType` | boolean, nullable |  |  |
| `eachFf` | boolean, nullable |  |  |
| `dynamicInterval` | integer, nullable |  |  |
| `dynamicMax` | integer, nullable |  |  |
| `dynamicMin` | integer, nullable |  |  |
| `dynamicNext` | integer (int64), nullable |  |  |
| `dynamicTwoTailed` | boolean, nullable |  |  |
| `moduleType` | integer, nullable |  |  |
| `protocol` | string, nullable |  |  |
| `manufacturerId` | string, nullable |  |  |
| `executionType` | integer, nullable |  |  |
| `scanType` | integer, nullable |  |  |
| `value` | string, nullable |  |  |
| `valueOperations` | string, nullable |  |  |
| `moduleEnabled` | boolean, nullable |  |  |
| `nameOid` | string, nullable |  |  |
| `queryClass` | string, nullable |  |  |
| `queryKeyField` | string, nullable |  |  |
| `scanFilters` | object, nullable |  |  |
| `queryFilters` | object, nullable |  |  |
| `enabled` | boolean, nullable |  |  |
| `percentageCritical` | boolean, nullable |  |  |
| `percentageWarning` | boolean, nullable |  |  |
| `warningTime` | integer, nullable |  |  |
| `targetIp` | string, nullable |  |  |
| `isInternal` | boolean |  |  |
| `idDataTranslation` | integer, nullable |  |  |
| `snmpCommunity` | string, nullable |  | SNMP credential. Accepted on input only; never returned. |
| `pluginPass` | string, nullable |  | Plugin or SNMP authentication password. Accepted on input only; never returned. |
| `customString1` | string, nullable |  | Family-specific configuration. Input only; never returned. |
| `customString2` | string, nullable |  | Family-specific configuration or SNMPv3 privacy password. Input only; never returned. |
| `customString3` | string, nullable |  | Family-specific configuration. Input only; never returned. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idNetworkComponentGroup": 0,
      "idModuleType": 0,
      "max": 0,
      "min": 0,
      "moduleInterval": 0,
      "tcpPort": 0,
      "tcpSend": "string",
      "tcpRcv": "string",
      "snmpOid": "string",
      "idModuleGroup": 0,
      "idModule": 0,
      "idPlugin": 0,
      "pluginUser": "string",
      "pluginParameter": "string",
      "maxTimeout": 0,
      "maxRetries": 0,
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
      "postProcess": 0,
      "unit": "string",
      "wizardLevel": "basic",
      "macros": [
        {}
      ],
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "criticalInverse": false,
      "warningInverse": false,
      "idCategory": 0,
      "tags": "string",
      "disabledTypesEvent": {},
      "moduleMacros": {},
      "minFfEventNormal": 0,
      "minFfEventWarning": 0,
      "minFfEventCritical": 0,
      "ffType": false,
      "eachFf": false,
      "dynamicInterval": 0,
      "dynamicMax": 0,
      "dynamicMin": 0,
      "dynamicNext": 0,
      "dynamicTwoTailed": false,
      "moduleType": 0,
      "protocol": "string",
      "manufacturerId": "string",
      "executionType": 0,
      "scanType": 0,
      "value": "string",
      "valueOperations": "string",
      "moduleEnabled": false,
      "nameOid": "string",
      "queryClass": "string",
      "queryKeyField": "string",
      "scanFilters": {},
      "queryFilters": {},
      "enabled": false,
      "percentageCritical": false,
      "percentageWarning": false,
      "warningTime": 0,
      "targetIp": "string",
      "idDataTranslation": 0,
      "snmpCommunity": "string",
      "pluginPass": "string",
      "customString1": "string",
      "customString2": "string",
      "customString3": "string"
    }
    ```

**Response 200**: Network component object

Schema: [`NetworkComponentResponse`](#model-networkcomponentresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/networkComponent/{idNetworkComponent}` { #get-networkcomponent-idnetworkcomponent }

Show a network component

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idNetworkComponent` | path | integer | yes |  |

**Response 200**: Network component object

Schema: [`NetworkComponentResponse`](#model-networkcomponentresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/networkComponent/{idNetworkComponent}` { #put-networkcomponent-idnetworkcomponent }

Updates a network component

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idNetworkComponent` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idNetworkComponent` | integer |  |  |
| `name` | string, nullable |  |  |
| `description` | string, nullable |  |  |
| `idNetworkComponentGroup` | integer, nullable |  |  |
| `idModuleType` | integer, nullable |  |  |
| `max` | integer (int64), nullable |  |  |
| `min` | integer (int64), nullable |  |  |
| `moduleInterval` | integer, nullable |  |  |
| `tcpPort` | integer, nullable |  |  |
| `tcpSend` | string, nullable |  |  |
| `tcpRcv` | string, nullable |  |  |
| `snmpOid` | string, nullable |  |  |
| `idModuleGroup` | integer, nullable |  |  |
| `idModule` | integer, nullable |  |  |
| `idPlugin` | integer, nullable |  |  |
| `pluginUser` | string, nullable |  |  |
| `pluginParameter` | string, nullable |  |  |
| `maxTimeout` | integer, nullable |  |  |
| `maxRetries` | integer, nullable |  |  |
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
| `postProcess` | number, nullable |  |  |
| `unit` | string, nullable |  |  |
| `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  |  |
| `macros` |  |  | Plugin macro list or wizard configuration object. |
| `criticalInstructions` | string, nullable |  |  |
| `warningInstructions` | string, nullable |  |  |
| `unknownInstructions` | string, nullable |  |  |
| `criticalInverse` | boolean, nullable |  |  |
| `warningInverse` | boolean, nullable |  |  |
| `idCategory` | integer, nullable |  |  |
| `tags` | string, nullable |  |  |
| `disabledTypesEvent` | object, nullable |  |  |
| `moduleMacros` | object, nullable |  |  |
| `minFfEventNormal` | integer, nullable |  |  |
| `minFfEventWarning` | integer, nullable |  |  |
| `minFfEventCritical` | integer, nullable |  |  |
| `ffType` | boolean, nullable |  |  |
| `eachFf` | boolean, nullable |  |  |
| `dynamicInterval` | integer, nullable |  |  |
| `dynamicMax` | integer, nullable |  |  |
| `dynamicMin` | integer, nullable |  |  |
| `dynamicNext` | integer (int64), nullable |  |  |
| `dynamicTwoTailed` | boolean, nullable |  |  |
| `moduleType` | integer, nullable |  |  |
| `protocol` | string, nullable |  |  |
| `manufacturerId` | string, nullable |  |  |
| `executionType` | integer, nullable |  |  |
| `scanType` | integer, nullable |  |  |
| `value` | string, nullable |  |  |
| `valueOperations` | string, nullable |  |  |
| `moduleEnabled` | boolean, nullable |  |  |
| `nameOid` | string, nullable |  |  |
| `queryClass` | string, nullable |  |  |
| `queryKeyField` | string, nullable |  |  |
| `scanFilters` | object, nullable |  |  |
| `queryFilters` | object, nullable |  |  |
| `enabled` | boolean, nullable |  |  |
| `percentageCritical` | boolean, nullable |  |  |
| `percentageWarning` | boolean, nullable |  |  |
| `warningTime` | integer, nullable |  |  |
| `targetIp` | string, nullable |  |  |
| `isInternal` | boolean |  |  |
| `idDataTranslation` | integer, nullable |  |  |
| `snmpCommunity` | string, nullable |  | SNMP credential. Accepted on input only; never returned. |
| `pluginPass` | string, nullable |  | Plugin or SNMP authentication password. Accepted on input only; never returned. |
| `customString1` | string, nullable |  | Family-specific configuration. Input only; never returned. |
| `customString2` | string, nullable |  | Family-specific configuration or SNMPv3 privacy password. Input only; never returned. |
| `customString3` | string, nullable |  | Family-specific configuration. Input only; never returned. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idNetworkComponentGroup": 0,
      "idModuleType": 0,
      "max": 0,
      "min": 0,
      "moduleInterval": 0,
      "tcpPort": 0,
      "tcpSend": "string",
      "tcpRcv": "string",
      "snmpOid": "string",
      "idModuleGroup": 0,
      "idModule": 0,
      "idPlugin": 0,
      "pluginUser": "string",
      "pluginParameter": "string",
      "maxTimeout": 0,
      "maxRetries": 0,
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
      "postProcess": 0,
      "unit": "string",
      "wizardLevel": "basic",
      "macros": [
        {}
      ],
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "criticalInverse": false,
      "warningInverse": false,
      "idCategory": 0,
      "tags": "string",
      "disabledTypesEvent": {},
      "moduleMacros": {},
      "minFfEventNormal": 0,
      "minFfEventWarning": 0,
      "minFfEventCritical": 0,
      "ffType": false,
      "eachFf": false,
      "dynamicInterval": 0,
      "dynamicMax": 0,
      "dynamicMin": 0,
      "dynamicNext": 0,
      "dynamicTwoTailed": false,
      "moduleType": 0,
      "protocol": "string",
      "manufacturerId": "string",
      "executionType": 0,
      "scanType": 0,
      "value": "string",
      "valueOperations": "string",
      "moduleEnabled": false,
      "nameOid": "string",
      "queryClass": "string",
      "queryKeyField": "string",
      "scanFilters": {},
      "queryFilters": {},
      "enabled": false,
      "percentageCritical": false,
      "percentageWarning": false,
      "warningTime": 0,
      "targetIp": "string",
      "idDataTranslation": 0,
      "snmpCommunity": "string",
      "pluginPass": "string",
      "customString1": "string",
      "customString2": "string",
      "customString3": "string"
    }
    ```

**Response 200**: Network component object

Schema: [`NetworkComponentResponse`](#model-networkcomponentresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/networkComponent/{idNetworkComponent}` { #delete-networkcomponent-idnetworkcomponent }

Deletes a network component

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idNetworkComponent` | path | integer | yes |  |

**Response 200**: Network component deleted

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/networkComponent/list` { #get-networkcomponent-list }

List network components using query filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `freeSearch` | query | string |  |  |
| `idNetworkComponent` | query | integer |  |  |
| `name` | query | string |  |  |
| `description` | query | string |  |  |
| `idNetworkComponentGroup` | query | integer |  |  |
| `idModuleType` | query | integer |  |  |
| `idModuleGroup` | query | integer |  |  |
| `idCategory` | query | integer |  |  |
| `idModule` | query | integer |  |  |
| `tags` | query | string |  |  |

**Response 200**: Network component list

??? note "Response fields (82 fields)"

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
    | `data.[].idNetworkComponent` | integer |  |  |
    | `data.[].name` | string, nullable |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].idNetworkComponentGroup` | integer, nullable |  |  |
    | `data.[].idModuleType` | integer, nullable |  |  |
    | `data.[].max` | integer (int64), nullable |  |  |
    | `data.[].min` | integer (int64), nullable |  |  |
    | `data.[].moduleInterval` | integer, nullable |  |  |
    | `data.[].tcpPort` | integer, nullable |  |  |
    | `data.[].tcpSend` | string, nullable |  |  |
    | `data.[].tcpRcv` | string, nullable |  |  |
    | `data.[].snmpOid` | string, nullable |  |  |
    | `data.[].idModuleGroup` | integer, nullable |  |  |
    | `data.[].idModule` | integer, nullable |  |  |
    | `data.[].idPlugin` | integer, nullable |  |  |
    | `data.[].pluginUser` | string, nullable |  |  |
    | `data.[].pluginParameter` | string, nullable |  |  |
    | `data.[].maxTimeout` | integer, nullable |  |  |
    | `data.[].maxRetries` | integer, nullable |  |  |
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
    | `data.[].postProcess` | number, nullable |  |  |
    | `data.[].unit` | string, nullable |  |  |
    | `data.[].wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  |  |
    | `data.[].macros` |  |  | Plugin macro list or wizard configuration object. |
    | `data.[].criticalInstructions` | string, nullable |  |  |
    | `data.[].warningInstructions` | string, nullable |  |  |
    | `data.[].unknownInstructions` | string, nullable |  |  |
    | `data.[].criticalInverse` | boolean, nullable |  |  |
    | `data.[].warningInverse` | boolean, nullable |  |  |
    | `data.[].idCategory` | integer, nullable |  |  |
    | `data.[].tags` | string, nullable |  |  |
    | `data.[].disabledTypesEvent` | object, nullable |  |  |
    | `data.[].moduleMacros` | object, nullable |  |  |
    | `data.[].minFfEventNormal` | integer, nullable |  |  |
    | `data.[].minFfEventWarning` | integer, nullable |  |  |
    | `data.[].minFfEventCritical` | integer, nullable |  |  |
    | `data.[].ffType` | boolean, nullable |  |  |
    | `data.[].eachFf` | boolean, nullable |  |  |
    | `data.[].dynamicInterval` | integer, nullable |  |  |
    | `data.[].dynamicMax` | integer, nullable |  |  |
    | `data.[].dynamicMin` | integer, nullable |  |  |
    | `data.[].dynamicNext` | integer (int64), nullable |  |  |
    | `data.[].dynamicTwoTailed` | boolean, nullable |  |  |
    | `data.[].moduleType` | integer, nullable |  |  |
    | `data.[].protocol` | string, nullable |  |  |
    | `data.[].manufacturerId` | string, nullable |  |  |
    | `data.[].executionType` | integer, nullable |  |  |
    | `data.[].scanType` | integer, nullable |  |  |
    | `data.[].value` | string, nullable |  |  |
    | `data.[].valueOperations` | string, nullable |  |  |
    | `data.[].moduleEnabled` | boolean, nullable |  |  |
    | `data.[].nameOid` | string, nullable |  |  |
    | `data.[].queryClass` | string, nullable |  |  |
    | `data.[].queryKeyField` | string, nullable |  |  |
    | `data.[].scanFilters` | object, nullable |  |  |
    | `data.[].queryFilters` | object, nullable |  |  |
    | `data.[].enabled` | boolean, nullable |  |  |
    | `data.[].percentageCritical` | boolean, nullable |  |  |
    | `data.[].percentageWarning` | boolean, nullable |  |  |
    | `data.[].warningTime` | integer, nullable |  |  |
    | `data.[].targetIp` | string, nullable |  |  |
    | `data.[].isInternal` | boolean |  |  |
    | `data.[].idDataTranslation` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/networkComponent/list` { #post-networkcomponent-list }

List network components using advanced filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `freeSearch` | query | string |  |  |
| `idNetworkComponent` | query | integer |  |  |
| `name` | query | string |  |  |
| `description` | query | string |  |  |
| `idNetworkComponentGroup` | query | integer |  |  |
| `idModuleType` | query | integer |  |  |
| `idModuleGroup` | query | integer |  |  |
| `idCategory` | query | integer |  |  |
| `idModule` | query | integer |  |  |
| `tags` | query | string |  |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idNetworkComponent` | integer |  |  |
| `name` | string, nullable |  |  |
| `description` | string, nullable |  |  |
| `idNetworkComponentGroup` | integer, nullable |  |  |
| `idModuleType` | integer, nullable |  |  |
| `max` | integer (int64), nullable |  |  |
| `min` | integer (int64), nullable |  |  |
| `moduleInterval` | integer, nullable |  |  |
| `tcpPort` | integer, nullable |  |  |
| `tcpSend` | string, nullable |  |  |
| `tcpRcv` | string, nullable |  |  |
| `snmpOid` | string, nullable |  |  |
| `idModuleGroup` | integer, nullable |  |  |
| `idModule` | integer, nullable |  |  |
| `idPlugin` | integer, nullable |  |  |
| `pluginUser` | string, nullable |  |  |
| `pluginParameter` | string, nullable |  |  |
| `maxTimeout` | integer, nullable |  |  |
| `maxRetries` | integer, nullable |  |  |
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
| `postProcess` | number, nullable |  |  |
| `unit` | string, nullable |  |  |
| `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  |  |
| `macros` |  |  | Plugin macro list or wizard configuration object. |
| `criticalInstructions` | string, nullable |  |  |
| `warningInstructions` | string, nullable |  |  |
| `unknownInstructions` | string, nullable |  |  |
| `criticalInverse` | boolean, nullable |  |  |
| `warningInverse` | boolean, nullable |  |  |
| `idCategory` | integer, nullable |  |  |
| `tags` | string, nullable |  |  |
| `disabledTypesEvent` | object, nullable |  |  |
| `moduleMacros` | object, nullable |  |  |
| `minFfEventNormal` | integer, nullable |  |  |
| `minFfEventWarning` | integer, nullable |  |  |
| `minFfEventCritical` | integer, nullable |  |  |
| `ffType` | boolean, nullable |  |  |
| `eachFf` | boolean, nullable |  |  |
| `dynamicInterval` | integer, nullable |  |  |
| `dynamicMax` | integer, nullable |  |  |
| `dynamicMin` | integer, nullable |  |  |
| `dynamicNext` | integer (int64), nullable |  |  |
| `dynamicTwoTailed` | boolean, nullable |  |  |
| `moduleType` | integer, nullable |  |  |
| `protocol` | string, nullable |  |  |
| `manufacturerId` | string, nullable |  |  |
| `executionType` | integer, nullable |  |  |
| `scanType` | integer, nullable |  |  |
| `value` | string, nullable |  |  |
| `valueOperations` | string, nullable |  |  |
| `moduleEnabled` | boolean, nullable |  |  |
| `nameOid` | string, nullable |  |  |
| `queryClass` | string, nullable |  |  |
| `queryKeyField` | string, nullable |  |  |
| `scanFilters` | object, nullable |  |  |
| `queryFilters` | object, nullable |  |  |
| `enabled` | boolean, nullable |  |  |
| `percentageCritical` | boolean, nullable |  |  |
| `percentageWarning` | boolean, nullable |  |  |
| `warningTime` | integer, nullable |  |  |
| `targetIp` | string, nullable |  |  |
| `isInternal` | boolean |  |  |
| `idDataTranslation` | integer, nullable |  |  |
| `idNetworkComponent` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in name and description fields. |
| `page` | integer, nullable |  |  |
| `sizePage` | integer, nullable |  |  |
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
| `multipleSearch.field` | enum: `idNetworkComponent`, `name`, `description`, `idNetworkComponentGroup`, `idModuleType`, `max`, `min`, `moduleInterval`, `tcpPort`, `snmpOid`, `idModuleGroup`, `idModule`, `idPlugin`, `pluginUser`, `maxTimeout`, `maxRetries`, `historyData`, `minWarning`, `maxWarning`, `strWarning`, `minCritical`, `maxCritical`, `strCritical`, `minFfEvent`, `customInteger1`, `customInteger2`, `postProcess`, `unit`, `wizardLevel`, `criticalInstructions`, `warningInstructions`, `unknownInstructions`, `criticalInverse`, `warningInverse`, `idCategory`, `tags`, `minFfEventNormal`, `minFfEventWarning`, `minFfEventCritical`, `ffType`, `eachFf`, `dynamicInterval`, `dynamicMax`, `dynamicMin`, `dynamicNext`, `dynamicTwoTailed`, `moduleType`, `protocol`, `manufacturerId`, `executionType`, `scanType`, `value`, `moduleEnabled`, `nameOid`, `queryClass`, `queryKeyField`, `enabled`, `percentageCritical`, `percentageWarning`, `warningTime`, `targetIp`, `isInternal`, `idDataTranslation` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idNetworkComponent`, `name`, `description`, `idNetworkComponentGroup`, `idModuleType`, `max`, `min`, `moduleInterval`, `tcpPort`, `snmpOid`, `idModuleGroup`, `idModule`, `idPlugin`, `pluginUser`, `maxTimeout`, `maxRetries`, `historyData`, `minWarning`, `maxWarning`, `strWarning`, `minCritical`, `maxCritical`, `strCritical`, `minFfEvent`, `customInteger1`, `customInteger2`, `postProcess`, `unit`, `wizardLevel`, `criticalInstructions`, `warningInstructions`, `unknownInstructions`, `criticalInverse`, `warningInverse`, `idCategory`, `tags`, `minFfEventNormal`, `minFfEventWarning`, `minFfEventCritical`, `ffType`, `eachFf`, `dynamicInterval`, `dynamicMax`, `dynamicMin`, `dynamicNext`, `dynamicTwoTailed`, `moduleType`, `protocol`, `manufacturerId`, `executionType`, `scanType`, `value`, `moduleEnabled`, `nameOid`, `queryClass`, `queryKeyField`, `enabled`, `percentageCritical`, `percentageWarning`, `warningTime`, `targetIp`, `isInternal`, `idDataTranslation` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idNetworkComponentGroup": 0,
      "idModuleType": 0,
      "max": 0,
      "min": 0,
      "moduleInterval": 0,
      "tcpPort": 0,
      "tcpSend": "string",
      "tcpRcv": "string",
      "snmpOid": "string",
      "idModuleGroup": 0,
      "idModule": 0,
      "idPlugin": 0,
      "pluginUser": "string",
      "pluginParameter": "string",
      "maxTimeout": 0,
      "maxRetries": 0,
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
      "postProcess": 0,
      "unit": "string",
      "wizardLevel": "basic",
      "macros": [
        {}
      ],
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "criticalInverse": false,
      "warningInverse": false,
      "idCategory": 0,
      "tags": "string",
      "disabledTypesEvent": {},
      "moduleMacros": {},
      "minFfEventNormal": 0,
      "minFfEventWarning": 0,
      "minFfEventCritical": 0,
      "ffType": false,
      "eachFf": false,
      "dynamicInterval": 0,
      "dynamicMax": 0,
      "dynamicMin": 0,
      "dynamicNext": 0,
      "dynamicTwoTailed": false,
      "moduleType": 0,
      "protocol": "string",
      "manufacturerId": "string",
      "executionType": 0,
      "scanType": 0,
      "value": "string",
      "valueOperations": "string",
      "moduleEnabled": false,
      "nameOid": "string",
      "queryClass": "string",
      "queryKeyField": "string",
      "scanFilters": {},
      "queryFilters": {},
      "enabled": false,
      "percentageCritical": false,
      "percentageWarning": false,
      "warningTime": 0,
      "targetIp": "string",
      "idDataTranslation": 0,
      "idNetworkComponent": null,
      "freeSearch": "string",
      "page": 0,
      "sizePage": 0,
      "requestedFields": [
        "idNetworkComponent"
      ],
      "fieldConditions": [
        {
          "field": "idNetworkComponent",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idNetworkComponent",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idNetworkComponent",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Network component list

??? note "Response fields (82 fields)"

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
    | `data.[].idNetworkComponent` | integer |  |  |
    | `data.[].name` | string, nullable |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].idNetworkComponentGroup` | integer, nullable |  |  |
    | `data.[].idModuleType` | integer, nullable |  |  |
    | `data.[].max` | integer (int64), nullable |  |  |
    | `data.[].min` | integer (int64), nullable |  |  |
    | `data.[].moduleInterval` | integer, nullable |  |  |
    | `data.[].tcpPort` | integer, nullable |  |  |
    | `data.[].tcpSend` | string, nullable |  |  |
    | `data.[].tcpRcv` | string, nullable |  |  |
    | `data.[].snmpOid` | string, nullable |  |  |
    | `data.[].idModuleGroup` | integer, nullable |  |  |
    | `data.[].idModule` | integer, nullable |  |  |
    | `data.[].idPlugin` | integer, nullable |  |  |
    | `data.[].pluginUser` | string, nullable |  |  |
    | `data.[].pluginParameter` | string, nullable |  |  |
    | `data.[].maxTimeout` | integer, nullable |  |  |
    | `data.[].maxRetries` | integer, nullable |  |  |
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
    | `data.[].postProcess` | number, nullable |  |  |
    | `data.[].unit` | string, nullable |  |  |
    | `data.[].wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  |  |
    | `data.[].macros` |  |  | Plugin macro list or wizard configuration object. |
    | `data.[].criticalInstructions` | string, nullable |  |  |
    | `data.[].warningInstructions` | string, nullable |  |  |
    | `data.[].unknownInstructions` | string, nullable |  |  |
    | `data.[].criticalInverse` | boolean, nullable |  |  |
    | `data.[].warningInverse` | boolean, nullable |  |  |
    | `data.[].idCategory` | integer, nullable |  |  |
    | `data.[].tags` | string, nullable |  |  |
    | `data.[].disabledTypesEvent` | object, nullable |  |  |
    | `data.[].moduleMacros` | object, nullable |  |  |
    | `data.[].minFfEventNormal` | integer, nullable |  |  |
    | `data.[].minFfEventWarning` | integer, nullable |  |  |
    | `data.[].minFfEventCritical` | integer, nullable |  |  |
    | `data.[].ffType` | boolean, nullable |  |  |
    | `data.[].eachFf` | boolean, nullable |  |  |
    | `data.[].dynamicInterval` | integer, nullable |  |  |
    | `data.[].dynamicMax` | integer, nullable |  |  |
    | `data.[].dynamicMin` | integer, nullable |  |  |
    | `data.[].dynamicNext` | integer (int64), nullable |  |  |
    | `data.[].dynamicTwoTailed` | boolean, nullable |  |  |
    | `data.[].moduleType` | integer, nullable |  |  |
    | `data.[].protocol` | string, nullable |  |  |
    | `data.[].manufacturerId` | string, nullable |  |  |
    | `data.[].executionType` | integer, nullable |  |  |
    | `data.[].scanType` | integer, nullable |  |  |
    | `data.[].value` | string, nullable |  |  |
    | `data.[].valueOperations` | string, nullable |  |  |
    | `data.[].moduleEnabled` | boolean, nullable |  |  |
    | `data.[].nameOid` | string, nullable |  |  |
    | `data.[].queryClass` | string, nullable |  |  |
    | `data.[].queryKeyField` | string, nullable |  |  |
    | `data.[].scanFilters` | object, nullable |  |  |
    | `data.[].queryFilters` | object, nullable |  |  |
    | `data.[].enabled` | boolean, nullable |  |  |
    | `data.[].percentageCritical` | boolean, nullable |  |  |
    | `data.[].percentageWarning` | boolean, nullable |  |  |
    | `data.[].warningTime` | integer, nullable |  |  |
    | `data.[].targetIp` | string, nullable |  |  |
    | `data.[].isInternal` | boolean |  |  |
    | `data.[].idDataTranslation` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

## NetworkComponentGroups

API Endpoints for network component groups

### <span class="api-method api-post">POST</span> `/networkComponentGroup` { #post-networkcomponentgroup }

Creates a new network component group

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idNetworkComponentGroup` | integer |  |  |
| `name` | string | yes |  |
| `idParentNetworkComponentGroup` | integer, nullable |  | Parent group identifier. 0 means root. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idParentNetworkComponentGroup": 0
    }
    ```

**Response 200**: Network component group object

Schema: [`NetworkComponentGroup`](#model-networkcomponentgroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/networkComponentGroup/{idNetworkComponentGroup}` { #get-networkcomponentgroup-idnetworkcomponentgroup }

Show a network component group

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idNetworkComponentGroup` | path | integer | yes |  |

**Response 200**: Network component group object

Schema: [`NetworkComponentGroup`](#model-networkcomponentgroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/networkComponentGroup/{idNetworkComponentGroup}` { #put-networkcomponentgroup-idnetworkcomponentgroup }

Updates a network component group

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idNetworkComponentGroup` | path | integer | yes |  |

**Request body** (`application/json`): [`NetworkComponentGroup`](#model-networkcomponentgroup)

**Response 200**: Network component group object

Schema: [`NetworkComponentGroup`](#model-networkcomponentgroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/networkComponentGroup/{idNetworkComponentGroup}` { #delete-networkcomponentgroup-idnetworkcomponentgroup }

Deletes a network component group

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idNetworkComponentGroup` | path | integer | yes |  |

**Response 200**: Network component group deleted

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/networkComponentGroup/list` { #get-networkcomponentgroup-list }

List network component groups using query filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `freeSearch` | query | string |  |  |
| `idNetworkComponentGroup` | query | integer |  |  |
| `name` | query | string |  |  |
| `idParentNetworkComponentGroup` | query | integer |  |  |

**Response 200**: Network component group list

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
    | `data.[].idNetworkComponentGroup` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].idParentNetworkComponentGroup` | integer, nullable |  | Parent group identifier. 0 means root. |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/networkComponentGroup/list` { #post-networkcomponentgroup-list }

List network component groups using advanced filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `freeSearch` | query | string |  |  |
| `idNetworkComponentGroup` | query | integer |  |  |
| `name` | query | string |  |  |
| `idParentNetworkComponentGroup` | query | integer |  |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idNetworkComponentGroup` | integer |  |  |
| `name` | string |  |  |
| `idParentNetworkComponentGroup` | integer, nullable |  | Parent group identifier. 0 means root. |
| `idNetworkComponentGroup` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in the name field. |
| `page` | integer, nullable |  |  |
| `sizePage` | integer, nullable |  |  |
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
| `multipleSearch.field` | enum: `idNetworkComponentGroup`, `name`, `idParentNetworkComponentGroup` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idNetworkComponentGroup`, `name`, `idParentNetworkComponentGroup` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idParentNetworkComponentGroup": 0,
      "idNetworkComponentGroup": null,
      "freeSearch": "string",
      "page": 0,
      "sizePage": 0,
      "requestedFields": [
        "idNetworkComponentGroup"
      ],
      "fieldConditions": [
        {
          "field": "idNetworkComponentGroup",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idNetworkComponentGroup",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idNetworkComponentGroup",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Network component group list

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
    | `data.[].idNetworkComponentGroup` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].idParentNetworkComponentGroup` | integer, nullable |  | Parent group identifier. 0 means root. |


Error responses: `400`, `401`, `403`, `404`, `500`.

## DataTranslations

API Endpoints of data translations

### <span class="api-method api-post">POST</span> `/dataTranslation` { #post-datatranslation }

Creates a new data translation

**Request body** (`application/json`): [`DataTranslation`](#model-datatranslation)

**Response 200**: DataTranslation object

Schema: [`DataTranslation`](#model-datatranslation)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/dataTranslation/{idDataTranslation}` { #get-datatranslation-iddatatranslation }

Show data translation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idDataTranslation` | path | integer | yes |  |

**Response 200**: DataTranslation object

Schema: [`DataTranslation`](#model-datatranslation)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/dataTranslation/{idDataTranslation}` { #put-datatranslation-iddatatranslation }

Updates a data translation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idDataTranslation` | path | integer | yes |  |

**Request body** (`application/json`): [`DataTranslation`](#model-datatranslation)

**Response 200**: DataTranslation object

Schema: [`DataTranslation`](#model-datatranslation)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/dataTranslation/{idDataTranslation}` { #delete-datatranslation-iddatatranslation }

Deletes a data translation object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idDataTranslation` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/dataTranslation/list` { #get-datatranslation-list }

List data translations

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List DataTranslation objects

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
    | `data.[].idDataTranslation` | integer |  | Id Data Translation |
    | `data.[].name` | string |  | Name of the data translation |
    | `data.[].type` | string |  | Type of the data translation: string or math |
    | `data.[].values` | string, nullable |  | JSON encoded translation values |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/dataTranslation/list` { #post-datatranslation-list }

List data translations

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
| `idDataTranslation` | integer |  | Id Data Translation |
| `name` | string |  | Name of the data translation |
| `type` | string |  | Type of the data translation: string or math |
| `values` | string, nullable |  | JSON encoded translation values |
| `idDataTranslation` |  |  |  |
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
| `multipleSearch.field` | enum: `idDataTranslation`, `name`, `values` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idDataTranslation`, `name`, `values` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "type": "string",
      "values": "string",
      "idDataTranslation": null,
      "freeSearch": "string",
      "requestedFields": [
        "idDataTranslation"
      ],
      "fieldConditions": [
        {
          "field": "idDataTranslation",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idDataTranslation",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idDataTranslation",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List DataTranslation objects

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
    | `data.[].idDataTranslation` | integer |  | Id Data Translation |
    | `data.[].name` | string |  | Name of the data translation |
    | `data.[].type` | string |  | Type of the data translation: string or math |
    | `data.[].values` | string, nullable |  | JSON encoded translation values |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: AgentModule { #model-agentmodule }

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgentModule` | integer, nullable |  | Agent module identifier |
| `idAgent` | integer |  | Identifier of the agent that owns the module |
| `idModuleType` | integer |  | Module data type identifier |
| `description` | string, nullable |  | Module description |
| `extendedInfo` | string, nullable |  | Additional module information |
| `name` | string |  | Module name |
| `unit` | string, nullable |  | Value unit |
| `idPolicyModule` | integer, nullable |  | Source policy module identifier |
| `max` | integer (int64), nullable |  | Maximum accepted value |
| `min` | integer (int64), nullable |  | Minimum accepted value |
| `moduleInterval` | integer, nullable |  | Module execution interval in seconds |
| `cronInterval` | string, nullable |  | Cron expression used as the module interval |
| `moduleFfInterval` | integer, nullable |  | Flip-flop execution interval |
| `tcpPort` | integer, nullable |  | Target TCP port |
| `tcpSend` | string, nullable |  | Payload sent to the TCP target |
| `tcpRcv` | string, nullable |  | Expected TCP response |
| `snmpCommunity` | string, nullable |  | SNMP community |
| `snmpOid` | string, nullable |  | SNMP object identifier |
| `ipTarget` | string, nullable |  | Module target address |
| `idModuleGroup` | integer, nullable |  | Module group identifier |
| `flag` | integer, nullable |  | Module state flag |
| `idModule` | integer |  | Module server type identifier |
| `disabled` | boolean, nullable |  | Whether the module is disabled |
| `disabledBySafeMode` | boolean, nullable |  | Whether safe mode disabled the module |
| `idExport` | integer, nullable |  | Export server identifier |
| `pluginUser` | string, nullable |  | Plugin authentication user |
| `pluginPass` | string, nullable |  | Plugin authentication password |
| `pluginParameter` | string, nullable |  | Plugin parameters |
| `idPlugin` | integer, nullable |  | Plugin identifier |
| `postProcess` | number (double), nullable |  | Post-processing multiplier |
| `predictionModule` | integer (int64), nullable |  | Prediction source module or mode |
| `maxTimeout` | integer, nullable |  | Maximum execution timeout |
| `maxRetries` | integer, nullable |  | Maximum execution retries |
| `customId` | string, nullable |  | External module identifier |
| `historyData` | boolean, nullable |  | Whether historical data is stored |
| `minWarning` | number (double), nullable |  | Warning threshold lower bound |
| `maxWarning` | number (double), nullable |  | Warning threshold upper bound |
| `strWarning` | string, nullable |  | Warning string condition |
| `minCritical` | number (double), nullable |  | Critical threshold lower bound |
| `maxCritical` | number (double), nullable |  | Critical threshold upper bound |
| `strCritical` | string, nullable |  | Critical string condition |
| `minFfEvent` | integer, nullable |  | Event flip-flop threshold |
| `deletePending` | boolean, nullable |  | Whether the module is pending deletion |
| `policyLinked` | integer, nullable |  | Policy link state |
| `policyAdopted` | boolean, nullable |  | Whether the module was adopted from a policy |
| `customString1` | string, nullable |  | First custom string value |
| `customString2` | string, nullable |  | Second custom string value |
| `customString3` | string, nullable |  | Third custom string value |
| `customInteger1` | integer, nullable |  | First custom integer value |
| `customInteger2` | integer, nullable |  | Second custom integer value |
| `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  | Wizard visibility level |
| `macros` | string, nullable |  | Serialized module macros |
| `criticalInstructions` | string, nullable |  | Instructions for critical status |
| `warningInstructions` | string, nullable |  | Instructions for warning status |
| `unknownInstructions` | string, nullable |  | Instructions for unknown status |
| `quiet` | boolean, nullable |  | Whether event generation is silenced |
| `criticalInverse` | boolean, nullable |  | Whether the critical threshold is inverted |
| `warningInverse` | boolean, nullable |  | Whether the warning threshold is inverted |
| `idCategory` | integer, nullable |  | Module category identifier |
| `disabledTypesEvent` | string, nullable |  | Serialized disabled event types |
| `moduleMacros` | string, nullable |  | Serialized module macro definitions |
| `minFfEventNormal` | integer, nullable |  | Normal status flip-flop threshold |
| `minFfEventWarning` | integer, nullable |  | Warning status flip-flop threshold |
| `minFfEventCritical` | integer, nullable |  | Critical status flip-flop threshold |
| `ffType` | integer, nullable |  | Flip-flop calculation type |
| `eachFf` | boolean, nullable |  | Whether each status has an independent flip-flop threshold |
| `ffTimeout` | integer, nullable |  | Flip-flop timeout |
| `dynamicInterval` | integer, nullable |  | Dynamic interval value |
| `dynamicMax` | integer, nullable |  | Dynamic interval upper bound |
| `dynamicMin` | integer, nullable |  | Dynamic interval lower bound |
| `dynamicNext` | integer (int64), nullable |  | Next calculated dynamic execution time |
| `dynamicTwoTailed` | boolean, nullable |  | Whether dynamic thresholds are two-tailed |
| `predictionSampleWindow` | integer, nullable |  | Prediction sample window |
| `predictionSamples` | integer, nullable |  | Number of prediction samples |
| `predictionThreshold` | integer, nullable |  | Prediction threshold |
| `apiTimeout` | integer, nullable |  | API request timeout |
| `apiUrl` | string, nullable |  | API request URL |
| `apiMethod` | string, nullable |  | API HTTP method |
| `apiIgnoreCert` | boolean, nullable |  | Whether API certificate validation is disabled |
| `apiJsonq` | string, nullable |  | JSON query used to extract the API result |
| `apiBody` | string, nullable |  | API request body |
| `apiHeaders` | object, nullable |  | API request headers |
| `apiErrorCodes` | string, nullable |  | API error code configuration |
| `apiConditions` | object, nullable |  | API response conditions |
| `parentModuleId` | integer, nullable |  | Parent module identifier |
| `cps` | boolean, nullable |  | Whether change-per-second calculation is enabled |
| `cpsInhibit` | integer, nullable |  | Change-per-second inhibition interval |
| `debugContent` | string, nullable |  | Last module debug content |
| `percentageCritical` | boolean, nullable |  | Whether critical thresholds are percentages |
| `percentageWarning` | boolean, nullable |  | Whether warning thresholds are percentages |
| `warningTime` | integer, nullable |  | Minimum warning duration |
| `quietByDowntime` | boolean, nullable |  | Whether downtime silenced the module |
| `disabledByDowntime` | boolean, nullable |  | Whether downtime disabled the module |
| `madeEnabled` | boolean, nullable |  | Whether downtime enabled the module |
| `ignoreUnknown` | boolean, nullable |  | Whether unknown status is ignored |
| `extraData` | string, nullable |  | Additional serialized module data |
| `idDataTranslation` | integer, nullable |  | Data translation identifier |
| `serverId` | integer, nullable |  | Node identifier for metaconsole operations |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": 0,
      "idModuleType": 0,
      "description": "string",
      "extendedInfo": "string",
      "name": "string",
      "unit": "string",
      "idPolicyModule": 0,
      "max": 0,
      "min": 0,
      "moduleInterval": 0,
      "cronInterval": "string",
      "moduleFfInterval": 0,
      "tcpPort": 0,
      "tcpSend": "string",
      "tcpRcv": "string",
      "snmpCommunity": "string",
      "snmpOid": "string",
      "ipTarget": "string",
      "idModuleGroup": 0,
      "flag": 0,
      "idModule": 0,
      "disabled": false,
      "disabledBySafeMode": false,
      "idExport": 0,
      "pluginUser": "string",
      "pluginPass": "string",
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
      "customString1": "string",
      "customString2": "string",
      "customString3": "string",
      "customInteger1": 0,
      "customInteger2": 0,
      "wizardLevel": "basic",
      "macros": "string",
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "quiet": false,
      "criticalInverse": false,
      "warningInverse": false,
      "idCategory": 0,
      "disabledTypesEvent": "string",
      "moduleMacros": "string",
      "minFfEventNormal": 0,
      "minFfEventWarning": 0,
      "minFfEventCritical": 0,
      "ffType": 0,
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
      "apiBody": "string",
      "apiHeaders": {},
      "apiErrorCodes": "string",
      "apiConditions": {},
      "parentModuleId": 0,
      "cps": false,
      "cpsInhibit": 0,
      "debugContent": "string",
      "percentageCritical": false,
      "percentageWarning": false,
      "warningTime": 0,
      "quietByDowntime": false,
      "disabledByDowntime": false,
      "madeEnabled": false,
      "ignoreUnknown": false,
      "extraData": "string",
      "idDataTranslation": 0
    }
    ```

### Model: AgentModuleTag { #model-agentmoduletag }

??? note "Fields (4 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAgentModule` | integer |  |  |
    | `idTag` | integer |  |  |
    | `idPolicyModule` | integer |  |  |
    | `serverId` | integer, nullable |  |  |


### Model: DataTranslation { #model-datatranslation }

| Field | Type | Required | Description |
|---|---|---|---|
| `idDataTranslation` | integer |  | Id Data Translation |
| `name` | string |  | Name of the data translation |
| `type` | string |  | Type of the data translation: string or math |
| `values` | string, nullable |  | JSON encoded translation values |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "type": "string",
      "values": "string"
    }
    ```

### Model: LocalComponent { #model-localcomponent }

| Field | Type | Required | Description |
|---|---|---|---|
| `idLocalComponent` | integer |  | Local component identifier |
| `name` | string, nullable |  | Local component name |
| `data` | string, nullable |  | Module configuration text |
| `description` | string, nullable |  | Local component description |
| `idOs` | integer, nullable |  | Operating system identifier |
| `osVersion` | string, nullable |  | Operating system version |
| `idNetworkComponentGroup` | integer, nullable |  | Component group identifier |
| `idModuleType` | integer, nullable |  | Module type identifier |
| `max` | integer, nullable |  | Maximum value |
| `min` | integer, nullable |  | Minimum value |
| `moduleInterval` | integer, nullable |  | Module interval in seconds |
| `idModuleGroup` | integer, nullable |  | Module group identifier |
| `historyData` | boolean, nullable |  | Store module history |
| `minWarning` | number, nullable |  | Warning minimum threshold |
| `maxWarning` | number, nullable |  | Warning maximum threshold |
| `strWarning` | string, nullable |  | Warning string threshold |
| `minCritical` | number, nullable |  | Critical minimum threshold |
| `maxCritical` | number, nullable |  | Critical maximum threshold |
| `strCritical` | string, nullable |  | Critical string threshold |
| `minFfEvent` | integer, nullable |  | Minimum events for flip-flop |
| `postProcess` | number, nullable |  | Post-process value |
| `unit` | string, nullable |  | Module unit |
| `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  | Wizard level |
| `macros` | string, nullable |  | Macros text |
| `criticalInstructions` | string, nullable |  | Critical instructions |
| `warningInstructions` | string, nullable |  | Warning instructions |
| `unknownInstructions` | string, nullable |  | Unknown instructions |
| `criticalInverse` | boolean, nullable |  | Inverse critical comparison |
| `warningInverse` | boolean, nullable |  | Inverse warning comparison |
| `idCategory` | integer, nullable |  | Category identifier |
| `tags` | string, nullable |  | Comma-separated tag identifiers |
| `disabledTypesEvent` | string, nullable |  | Disabled event types as JSON |
| `minFfEventNormal` | integer, nullable |  | Minimum normal events |
| `minFfEventWarning` | integer, nullable |  | Minimum warning events |
| `minFfEventCritical` | integer, nullable |  | Minimum critical events |
| `ffType` | boolean, nullable |  | Flip-flop type |
| `eachFf` | boolean, nullable |  | Evaluate each flip-flop |
| `ffTimeout` | integer, nullable |  | Flip-flop timeout |
| `dynamicInterval` | integer, nullable |  | Dynamic interval |
| `dynamicMax` | integer, nullable |  | Dynamic maximum |
| `dynamicMin` | integer, nullable |  | Dynamic minimum |
| `dynamicNext` | integer, nullable |  | Next dynamic execution |
| `dynamicTwoTailed` | boolean, nullable |  | Dynamic two-tailed mode |
| `predictionSampleWindow` | integer, nullable |  | Prediction sample window |
| `predictionSamples` | integer, nullable |  | Prediction samples |
| `predictionThreshold` | integer, nullable |  | Prediction threshold |
| `percentageCritical` | boolean, nullable |  | Critical percentage mode |
| `percentageWarning` | boolean, nullable |  | Warning percentage mode |
| `warningTime` | integer, nullable |  | Warning time |
| `moduleMacros` | string, nullable |  | Base64 encoded module macros |
| `isInternal` | boolean |  | Internal component flag |
| `idDataTranslation` | integer, nullable |  | Data translation identifier |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "data": "string",
      "description": "string",
      "idOs": 0,
      "osVersion": "string",
      "idNetworkComponentGroup": 0,
      "idModuleType": 0,
      "max": 0,
      "min": 0,
      "moduleInterval": 0,
      "idModuleGroup": 0,
      "historyData": false,
      "minWarning": 0,
      "maxWarning": 0,
      "strWarning": "string",
      "minCritical": 0,
      "maxCritical": 0,
      "strCritical": "string",
      "minFfEvent": 0,
      "postProcess": 0,
      "unit": "string",
      "wizardLevel": "basic",
      "macros": "string",
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "criticalInverse": false,
      "warningInverse": false,
      "idCategory": 0,
      "tags": "string",
      "disabledTypesEvent": "string",
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
      "percentageCritical": false,
      "percentageWarning": false,
      "warningTime": 0,
      "moduleMacros": "string",
      "idDataTranslation": 0
    }
    ```

### Model: ModuleGroup { #model-modulegroup }

| Field | Type | Required | Description |
|---|---|---|---|
| `idModuleGroup` | integer |  | Module group identifier |
| `name` | string | yes | Module group name |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string"
    }
    ```

### Model: NetworkComponentGroup { #model-networkcomponentgroup }

| Field | Type | Required | Description |
|---|---|---|---|
| `idNetworkComponentGroup` | integer |  |  |
| `name` | string |  |  |
| `idParentNetworkComponentGroup` | integer, nullable |  | Parent group identifier. 0 means root. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idParentNetworkComponentGroup": 0
    }
    ```

### Model: NetworkComponentResponse { #model-networkcomponentresponse }

??? note "Fields (72 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idNetworkComponent` | integer |  |  |
    | `name` | string, nullable |  |  |
    | `description` | string, nullable |  |  |
    | `idNetworkComponentGroup` | integer, nullable |  |  |
    | `idModuleType` | integer, nullable |  |  |
    | `max` | integer (int64), nullable |  |  |
    | `min` | integer (int64), nullable |  |  |
    | `moduleInterval` | integer, nullable |  |  |
    | `tcpPort` | integer, nullable |  |  |
    | `tcpSend` | string, nullable |  |  |
    | `tcpRcv` | string, nullable |  |  |
    | `snmpOid` | string, nullable |  |  |
    | `idModuleGroup` | integer, nullable |  |  |
    | `idModule` | integer, nullable |  |  |
    | `idPlugin` | integer, nullable |  |  |
    | `pluginUser` | string, nullable |  |  |
    | `pluginParameter` | string, nullable |  |  |
    | `maxTimeout` | integer, nullable |  |  |
    | `maxRetries` | integer, nullable |  |  |
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
    | `postProcess` | number, nullable |  |  |
    | `unit` | string, nullable |  |  |
    | `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  |  |
    | `macros` |  |  | Plugin macro list or wizard configuration object. |
    | `criticalInstructions` | string, nullable |  |  |
    | `warningInstructions` | string, nullable |  |  |
    | `unknownInstructions` | string, nullable |  |  |
    | `criticalInverse` | boolean, nullable |  |  |
    | `warningInverse` | boolean, nullable |  |  |
    | `idCategory` | integer, nullable |  |  |
    | `tags` | string, nullable |  |  |
    | `disabledTypesEvent` | object, nullable |  |  |
    | `moduleMacros` | object, nullable |  |  |
    | `minFfEventNormal` | integer, nullable |  |  |
    | `minFfEventWarning` | integer, nullable |  |  |
    | `minFfEventCritical` | integer, nullable |  |  |
    | `ffType` | boolean, nullable |  |  |
    | `eachFf` | boolean, nullable |  |  |
    | `dynamicInterval` | integer, nullable |  |  |
    | `dynamicMax` | integer, nullable |  |  |
    | `dynamicMin` | integer, nullable |  |  |
    | `dynamicNext` | integer (int64), nullable |  |  |
    | `dynamicTwoTailed` | boolean, nullable |  |  |
    | `moduleType` | integer, nullable |  |  |
    | `protocol` | string, nullable |  |  |
    | `manufacturerId` | string, nullable |  |  |
    | `executionType` | integer, nullable |  |  |
    | `scanType` | integer, nullable |  |  |
    | `value` | string, nullable |  |  |
    | `valueOperations` | string, nullable |  |  |
    | `moduleEnabled` | boolean, nullable |  |  |
    | `nameOid` | string, nullable |  |  |
    | `queryClass` | string, nullable |  |  |
    | `queryKeyField` | string, nullable |  |  |
    | `scanFilters` | object, nullable |  |  |
    | `queryFilters` | object, nullable |  |  |
    | `enabled` | boolean, nullable |  |  |
    | `percentageCritical` | boolean, nullable |  |  |
    | `percentageWarning` | boolean, nullable |  |  |
    | `warningTime` | integer, nullable |  |  |
    | `targetIp` | string, nullable |  |  |
    | `isInternal` | boolean |  |  |
    | `idDataTranslation` | integer, nullable |  |  |


### Model: PolicyLinking { #model-policylinking }

??? note "Fields (9 fields)"

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
