# Services and scheduled downtimes

Services with their elements, and scheduled downtimes for agents and modules.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-post">POST</span> | [`/service`](#post-service) | Creates a new service |
| <span class="api-method api-get">GET</span> | [`/service/{idService}`](#get-service-idservice) | Show a service |
| <span class="api-method api-put">PUT</span> | [`/service/{idService}`](#put-service-idservice) | Updates a service |
| <span class="api-method api-delete">DELETE</span> | [`/service/{idService}`](#delete-service-idservice) | Deletes a service object. |
| <span class="api-method api-get">GET</span> | [`/service/list`](#get-service-list) | List services |
| <span class="api-method api-post">POST</span> | [`/service/list`](#post-service-list) | List services |
| <span class="api-method api-post">POST</span> | [`/service/{idService}/element`](#post-service-idservice-element) | Creates a new service element |
| <span class="api-method api-get">GET</span> | [`/service/{idService}/element/{idServiceElement}`](#get-service-idservice-element-idserviceelement) | Show a service element |
| <span class="api-method api-put">PUT</span> | [`/service/{idService}/element/{idServiceElement}`](#put-service-idservice-element-idserviceelement) | Updates a service element |
| <span class="api-method api-delete">DELETE</span> | [`/service/{idService}/element/{idServiceElement}`](#delete-service-idservice-element-idserviceelement) | Deletes a service element object. |
| <span class="api-method api-get">GET</span> | [`/service/{idService}/element/list`](#get-service-idservice-element-list) | List service elements |
| <span class="api-method api-post">POST</span> | [`/service/{idService}/element/list`](#post-service-idservice-element-list) | List service elements |
| <span class="api-method api-post">POST</span> | [`/scheduledDowntime`](#post-scheduleddowntime) | Create a scheduled downtime on a node |
| <span class="api-method api-get">GET</span> | [`/scheduledDowntime/{idScheduledDowntime}`](#get-scheduleddowntime-idscheduleddowntime) | Get a scheduled downtime |
| <span class="api-method api-put">PUT</span> | [`/scheduledDowntime/{idScheduledDowntime}`](#put-scheduleddowntime-idscheduleddowntime) | Update a scheduled downtime on a node |
| <span class="api-method api-delete">DELETE</span> | [`/scheduledDowntime/{idScheduledDowntime}`](#delete-scheduleddowntime-idscheduleddowntime) | Delete a scheduled downtime on a node |
| <span class="api-method api-get">GET</span> | [`/scheduledDowntime/list`](#get-scheduleddowntime-list) | List scheduled downtimes |
| <span class="api-method api-post">POST</span> | [`/scheduledDowntime/list`](#post-scheduleddowntime-list) | List scheduled downtimes with advanced filters |
| <span class="api-method api-post">POST</span> | [`/scheduledDowntime/{idScheduledDowntime}/agent`](#post-scheduleddowntime-idscheduleddowntime-agent) | Add an agent to a scheduled downtime |
| <span class="api-method api-get">GET</span> | [`/scheduledDowntime/{idScheduledDowntime}/agent/{idScheduledDowntimeAgent}`](#get-scheduleddowntime-idscheduleddowntime-agent-idscheduleddowntimeagent) | Get an agent assigned to a scheduled downtime |
| <span class="api-method api-put">PUT</span> | [`/scheduledDowntime/{idScheduledDowntime}/agent/{idScheduledDowntimeAgent}`](#put-scheduleddowntime-idscheduleddowntime-agent-idscheduleddowntimeagent) | Update an agent assigned to a scheduled downtime |
| <span class="api-method api-delete">DELETE</span> | [`/scheduledDowntime/{idScheduledDowntime}/agent/{idScheduledDowntimeAgent}`](#delete-scheduleddowntime-idscheduleddowntime-agent-idscheduleddowntimeagent) | Remove an agent from a scheduled downtime |
| <span class="api-method api-get">GET</span> | [`/scheduledDowntime/{idScheduledDowntime}/agent/list`](#get-scheduleddowntime-idscheduleddowntime-agent-list) | List agents assigned to a scheduled downtime |
| <span class="api-method api-post">POST</span> | [`/scheduledDowntime/{idScheduledDowntime}/agent/list`](#post-scheduleddowntime-idscheduleddowntime-agent-list) | List agents assigned to a scheduled downtime |
| <span class="api-method api-post">POST</span> | [`/scheduledDowntime/{idScheduledDowntime}/module`](#post-scheduleddowntime-idscheduleddowntime-module) | Add a module to a scheduled downtime |
| <span class="api-method api-get">GET</span> | [`/scheduledDowntime/{idScheduledDowntime}/module/{idScheduledDowntimeModule}`](#get-scheduleddowntime-idscheduleddowntime-module-idscheduleddowntimemodule) | Get a module assigned to a scheduled downtime |
| <span class="api-method api-delete">DELETE</span> | [`/scheduledDowntime/{idScheduledDowntime}/module/{idScheduledDowntimeModule}`](#delete-scheduleddowntime-idscheduleddowntime-module-idscheduleddowntimemodule) | Remove a module from a scheduled downtime |
| <span class="api-method api-get">GET</span> | [`/scheduledDowntime/{idScheduledDowntime}/module/list`](#get-scheduleddowntime-idscheduleddowntime-module-list) | List modules assigned to a scheduled downtime |
| <span class="api-method api-post">POST</span> | [`/scheduledDowntime/{idScheduledDowntime}/module/list`](#post-scheduleddowntime-idscheduleddowntime-module-list) | List modules assigned to a scheduled downtime |

## Services

API Endpoints for services

### <span class="api-method api-post">POST</span> `/service` { #post-service }

Creates a new service

On a node, idAgent is required. Metaconsole requests with serverId require an agent on that node.
For local metaconsole creation, omit idAgent; a container agent is created automatically.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`ServiceCreate`](#model-servicecreate)

**Response 200**: Service object

Schema: [`Service`](#model-service)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/service/{idService}` { #get-service-idservice }

Show a service

Reads the service locally on a node. On a metaconsole, serverId identifies the node that owns it.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idService` | path | integer | yes | Service id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Service object

Schema: [`Service`](#model-service)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-put">PUT</span> `/service/{idService}` { #put-service-idservice }

Updates a service

Updates the service locally on a node. On a metaconsole, serverId identifies the target node.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idService` | path | integer | yes | Service id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`ServiceCreate`](#model-servicecreate)

**Response 200**: Service object

Schema: [`Service`](#model-service)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-delete">DELETE</span> `/service/{idService}` { #delete-service-idservice }

Deletes a service object.

Deletes the service locally on a node. On a metaconsole, serverId identifies the target node.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idService` | path | integer | yes | Service id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/service/list` { #get-service-list }

List services

On a metaconsole the list aggregates the local console and every node unless the filter serverId selects specific nodes. Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Service object

??? note "Response fields (43 fields)"

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
    | `data.[].idService` | integer, nullable |  | Service identifier |
    | `data.[].name` | string |  | Service name |
    | `data.[].description` | string, nullable |  | Service description |
    | `data.[].idGroup` | integer |  | Group the service belongs to |
    | `data.[].autoCalculate` | enum: `0`, `1` |  | Calculation mode: 0 manual, 1 smart |
    | `data.[].critical` | number, nullable |  | Critical threshold |
    | `data.[].warning` | number, nullable |  | Warning threshold |
    | `data.[].unknownAsCritical` | boolean, nullable |  | Treat unknown elements as critical |
    | `data.[].serviceInterval` | integer, nullable |  | Service value module interval in seconds |
    | `data.[].slaInterval` | integer, nullable |  | SLA calculation window in seconds |
    | `data.[].slaLimit` | number, nullable |  | Minimum SLA percentage |
    | `data.[].slaModuleInterval` | integer, nullable |  | SLA module interval in seconds |
    | `data.[].slaValueModuleInterval` | integer, nullable |  | SLA value module interval in seconds |
    | `data.[].evaluateSla` | boolean, nullable |  | Whether the SLA is evaluated |
    | `data.[].quiet` | boolean, nullable |  | Disable alerts and events |
    | `data.[].cascadeProtection` | boolean, nullable |  | Enable cascade protection |
    | `data.[].isFavourite` | boolean, nullable |  | Mark as favourite |
    | `data.[].enableSunburst` | boolean, nullable |  | Render the service map as sunburst |
    | `data.[].enableHorizontalTree` | boolean, nullable |  | Render the service map as horizontal tree |
    | `data.[].asynchronous` | boolean, nullable |  | Evaluate the service asynchronously |
    | `data.[].idTemplateAlertWarning` | integer, nullable |  | Alert template for warning state |
    | `data.[].idTemplateAlertCritical` | integer, nullable |  | Alert template for critical state |
    | `data.[].idTemplateAlertUnknown` | integer, nullable |  | Alert template for unknown state |
    | `data.[].idTemplateAlertCriticalSla` | integer, nullable |  | Alert template for critical SLA state |
    | `data.[].status` | integer, nullable |  | Current status: -1 unknown, 0 normal, 1 critical, 2 warning |
    | `data.[].serviceValue` | number, nullable |  | Last calculated service value |
    | `data.[].utimestamp` | integer, nullable |  | Last update timestamp |
    | `data.[].idAgentModule` | integer, nullable |  | Agent module that stores the service value |
    | `data.[].slaIdModule` | integer, nullable |  | Agent module that stores the SLA |
    | `data.[].slaValueIdModule` | integer, nullable |  | Agent module that stores the SLA value |
    | `data.[].cpsInhibit` | integer, nullable |  | Cascade protection inhibition counter, managed by the server |
    | `data.[].rca` | string, nullable |  | Raw root cause analysis chain stored by the server |
    | `data.[].serverId` | integer, nullable |  | Node identifier for metaconsole operations |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/service/list` { #post-service-list }

List services

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
| `idService` | integer, nullable |  | Service identifier |
| `name` | string |  | Service name |
| `description` | string, nullable |  | Service description |
| `idGroup` | integer |  | Group the service belongs to |
| `autoCalculate` | enum: `0`, `1` |  | Calculation mode: 0 manual, 1 smart |
| `critical` | number, nullable |  | Critical threshold |
| `warning` | number, nullable |  | Warning threshold |
| `unknownAsCritical` | boolean, nullable |  | Treat unknown elements as critical |
| `serviceInterval` | integer, nullable |  | Service value module interval in seconds |
| `slaInterval` | integer, nullable |  | SLA calculation window in seconds |
| `slaLimit` | number, nullable |  | Minimum SLA percentage |
| `slaModuleInterval` | integer, nullable |  | SLA module interval in seconds |
| `slaValueModuleInterval` | integer, nullable |  | SLA value module interval in seconds |
| `evaluateSla` | boolean, nullable |  | Whether the SLA is evaluated |
| `quiet` | boolean, nullable |  | Disable alerts and events |
| `cascadeProtection` | boolean, nullable |  | Enable cascade protection |
| `isFavourite` | boolean, nullable |  | Mark as favourite |
| `enableSunburst` | boolean, nullable |  | Render the service map as sunburst |
| `enableHorizontalTree` | boolean, nullable |  | Render the service map as horizontal tree |
| `asynchronous` | boolean, nullable |  | Evaluate the service asynchronously |
| `idTemplateAlertWarning` | integer, nullable |  | Alert template for warning state |
| `idTemplateAlertCritical` | integer, nullable |  | Alert template for critical state |
| `idTemplateAlertUnknown` | integer, nullable |  | Alert template for unknown state |
| `idTemplateAlertCriticalSla` | integer, nullable |  | Alert template for critical SLA state |
| `status` | integer, nullable |  | Current status: -1 unknown, 0 normal, 1 critical, 2 warning |
| `serviceValue` | number, nullable |  | Last calculated service value |
| `utimestamp` | integer, nullable |  | Last update timestamp |
| `idAgentModule` | integer, nullable |  | Agent module that stores the service value |
| `slaIdModule` | integer, nullable |  | Agent module that stores the SLA |
| `slaValueIdModule` | integer, nullable |  | Agent module that stores the SLA value |
| `cpsInhibit` | integer, nullable |  | Cascade protection inhibition counter, managed by the server |
| `rca` | string, nullable |  | Raw root cause analysis chain stored by the server |
| `serverId` | integer, nullable |  | Node identifier for metaconsole operations |
| `idService` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in name and description fields. |
| `serverId` | array, nullable |  | Node identifiers to aggregate on a metaconsole. Empty means every node plus the local console. |
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
| `multipleSearch.field` | enum: `idService`, `name`, `description`, `idGroup`, `autoCalculate`, `critical`, `warning`, `unknownAsCritical`, `status`, `isFavourite`, `evaluateSla`, `quiet`, `cascadeProtection`, `asynchronous`, `serviceInterval`, `slaInterval`, `utimestamp`, `cpsInhibit` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idService`, `name`, `description`, `idGroup`, `autoCalculate`, `critical`, `warning`, `unknownAsCritical`, `status`, `isFavourite`, `evaluateSla`, `quiet`, `cascadeProtection`, `asynchronous`, `serviceInterval`, `slaInterval`, `utimestamp`, `cpsInhibit` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "autoCalculate": 0,
      "critical": 0,
      "warning": 0,
      "unknownAsCritical": false,
      "serviceInterval": 0,
      "slaInterval": 0,
      "slaLimit": 0,
      "slaModuleInterval": 0,
      "slaValueModuleInterval": 0,
      "evaluateSla": false,
      "quiet": false,
      "cascadeProtection": false,
      "isFavourite": false,
      "enableSunburst": false,
      "enableHorizontalTree": false,
      "asynchronous": false,
      "idTemplateAlertWarning": 0,
      "idTemplateAlertCritical": 0,
      "idTemplateAlertUnknown": 0,
      "idTemplateAlertCriticalSla": 0,
      "idService": null,
      "freeSearch": "string",
      "serverId": [
        0
      ],
      "requestedFields": [
        "idService"
      ],
      "fieldConditions": [
        {
          "field": "idService",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idService",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idService",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List Service object

??? note "Response fields (43 fields)"

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
    | `data.[].idService` | integer, nullable |  | Service identifier |
    | `data.[].name` | string |  | Service name |
    | `data.[].description` | string, nullable |  | Service description |
    | `data.[].idGroup` | integer |  | Group the service belongs to |
    | `data.[].autoCalculate` | enum: `0`, `1` |  | Calculation mode: 0 manual, 1 smart |
    | `data.[].critical` | number, nullable |  | Critical threshold |
    | `data.[].warning` | number, nullable |  | Warning threshold |
    | `data.[].unknownAsCritical` | boolean, nullable |  | Treat unknown elements as critical |
    | `data.[].serviceInterval` | integer, nullable |  | Service value module interval in seconds |
    | `data.[].slaInterval` | integer, nullable |  | SLA calculation window in seconds |
    | `data.[].slaLimit` | number, nullable |  | Minimum SLA percentage |
    | `data.[].slaModuleInterval` | integer, nullable |  | SLA module interval in seconds |
    | `data.[].slaValueModuleInterval` | integer, nullable |  | SLA value module interval in seconds |
    | `data.[].evaluateSla` | boolean, nullable |  | Whether the SLA is evaluated |
    | `data.[].quiet` | boolean, nullable |  | Disable alerts and events |
    | `data.[].cascadeProtection` | boolean, nullable |  | Enable cascade protection |
    | `data.[].isFavourite` | boolean, nullable |  | Mark as favourite |
    | `data.[].enableSunburst` | boolean, nullable |  | Render the service map as sunburst |
    | `data.[].enableHorizontalTree` | boolean, nullable |  | Render the service map as horizontal tree |
    | `data.[].asynchronous` | boolean, nullable |  | Evaluate the service asynchronously |
    | `data.[].idTemplateAlertWarning` | integer, nullable |  | Alert template for warning state |
    | `data.[].idTemplateAlertCritical` | integer, nullable |  | Alert template for critical state |
    | `data.[].idTemplateAlertUnknown` | integer, nullable |  | Alert template for unknown state |
    | `data.[].idTemplateAlertCriticalSla` | integer, nullable |  | Alert template for critical SLA state |
    | `data.[].status` | integer, nullable |  | Current status: -1 unknown, 0 normal, 1 critical, 2 warning |
    | `data.[].serviceValue` | number, nullable |  | Last calculated service value |
    | `data.[].utimestamp` | integer, nullable |  | Last update timestamp |
    | `data.[].idAgentModule` | integer, nullable |  | Agent module that stores the service value |
    | `data.[].slaIdModule` | integer, nullable |  | Agent module that stores the SLA |
    | `data.[].slaValueIdModule` | integer, nullable |  | Agent module that stores the SLA value |
    | `data.[].cpsInhibit` | integer, nullable |  | Cascade protection inhibition counter, managed by the server |
    | `data.[].rca` | string, nullable |  | Raw root cause analysis chain stored by the server |
    | `data.[].serverId` | integer, nullable |  | Node identifier for metaconsole operations |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

## ServiceElements

API Endpoints for service elements

### <span class="api-method api-post">POST</span> `/service/{idService}/element` { #post-service-idservice-element }

Creates a new service element

Creates the element on the node that owns the parent service; serverId selects it on a metaconsole.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idService` | path | integer | yes | Service id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idServiceElement` | integer, nullable |  | Service element identifier |
| `idService` | integer |  | Parent service identifier |
| `description` | string, nullable | yes | Element description |
| `weightOk` | number, nullable |  | Weight applied when the element is normal. Not allowed on smart services (autoCalculate=1). |
| `weightWarning` | number, nullable |  | Weight applied when the element is in warning. Not allowed on smart services (autoCalculate=1). |
| `weightCritical` | number, nullable |  | Weight applied when the element is critical. Not allowed on smart services (autoCalculate=1). |
| `weightUnknown` | number, nullable |  | Weight applied when the element is unknown. Not allowed on smart services (autoCalculate=1). |
| `idAgenteModulo` | integer, nullable |  | Agent module identifier for module elements |
| `idAgent` | integer, nullable |  | Agent identifier for agent elements |
| `idServiceChild` | integer, nullable |  | Child service identifier for service elements |
| `idServerMeta` | integer, nullable |  | Node identifier that owns the child service element (cross console link) |
| `rules` | object, nullable |  | Dynamic element rules |
| `serverId` | integer, nullable |  | Node identifier for metaconsole operations |
| `idAgenteModulo` | integer | yes |  |
| `idAgent` | integer | yes |  |
| `idServiceChild` | integer | yes |  |
| `rules` | object | yes |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "description": "string",
      "weightOk": 0,
      "weightWarning": 0,
      "weightCritical": 0,
      "weightUnknown": 0,
      "idAgenteModulo": 0,
      "idAgent": 0,
      "idServiceChild": 0,
      "idServerMeta": 0,
      "rules": {}
    }
    ```

**Response 200**: Service element object

Schema: [`ServiceElement`](#model-serviceelement)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/service/{idService}/element/{idServiceElement}` { #get-service-idservice-element-idserviceelement }

Show a service element

Reads the element on the node that owns the parent service; serverId selects it on a metaconsole.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idService` | path | integer | yes | Service id |
| `idServiceElement` | path | integer | yes | Service element id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Service element object

Schema: [`ServiceElement`](#model-serviceelement)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-put">PUT</span> `/service/{idService}/element/{idServiceElement}` { #put-service-idservice-element-idserviceelement }

Updates a service element

Partial update on the parent service's node; serverId selects the node on a metaconsole.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idService` | path | integer | yes | Service id |
| `idServiceElement` | path | integer | yes | Service element id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idServiceElement` | integer, nullable |  | Service element identifier |
| `idService` | integer |  | Parent service identifier |
| `description` | string, nullable |  | Element description |
| `weightOk` | number, nullable |  | Weight applied when the element is normal. Not allowed on smart services (autoCalculate=1). |
| `weightWarning` | number, nullable |  | Weight applied when the element is in warning. Not allowed on smart services (autoCalculate=1). |
| `weightCritical` | number, nullable |  | Weight applied when the element is critical. Not allowed on smart services (autoCalculate=1). |
| `weightUnknown` | number, nullable |  | Weight applied when the element is unknown. Not allowed on smart services (autoCalculate=1). |
| `idAgenteModulo` | integer, nullable |  | Agent module identifier for module elements |
| `idAgent` | integer, nullable |  | Agent identifier for agent elements |
| `idServiceChild` | integer, nullable |  | Child service identifier for service elements |
| `idServerMeta` | integer, nullable |  | Node identifier that owns the child service element (cross console link) |
| `rules` | object, nullable |  | Dynamic element rules |
| `serverId` | integer, nullable |  | Node identifier for metaconsole operations |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "description": "string",
      "weightOk": 0,
      "weightWarning": 0,
      "weightCritical": 0,
      "weightUnknown": 0,
      "idAgenteModulo": 0,
      "idAgent": 0,
      "idServiceChild": 0,
      "idServerMeta": 0,
      "rules": {}
    }
    ```

**Response 200**: Service element object

Schema: [`ServiceElement`](#model-serviceelement)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-delete">DELETE</span> `/service/{idService}/element/{idServiceElement}` { #delete-service-idservice-element-idserviceelement }

Deletes a service element object.

Deletes the element on the node that owns the parent service; serverId selects it on a metaconsole.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idService` | path | integer | yes | Service id |
| `idServiceElement` | path | integer | yes | Service element id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/service/{idService}/element/list` { #get-service-idservice-element-list }

List service elements

Lists the elements on the node that owns the parent service; serverId selects it on a metaconsole. Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idService` | path | integer | yes | Service id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Service element object

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
    | `data.[].idServiceElement` | integer, nullable |  | Service element identifier |
    | `data.[].idService` | integer |  | Parent service identifier |
    | `data.[].description` | string, nullable |  | Element description |
    | `data.[].weightOk` | number, nullable |  | Weight applied when the element is normal. Not allowed on smart services (autoCalculate=1). |
    | `data.[].weightWarning` | number, nullable |  | Weight applied when the element is in warning. Not allowed on smart services (autoCalculate=1). |
    | `data.[].weightCritical` | number, nullable |  | Weight applied when the element is critical. Not allowed on smart services (autoCalculate=1). |
    | `data.[].weightUnknown` | number, nullable |  | Weight applied when the element is unknown. Not allowed on smart services (autoCalculate=1). |
    | `data.[].idAgenteModulo` | integer, nullable |  | Agent module identifier for module elements |
    | `data.[].idAgent` | integer, nullable |  | Agent identifier for agent elements |
    | `data.[].idServiceChild` | integer, nullable |  | Child service identifier for service elements |
    | `data.[].idServerMeta` | integer, nullable |  | Node identifier that owns the child service element (cross console link) |
    | `data.[].rules` | object, nullable |  | Dynamic element rules |
    | `data.[].serverId` | integer, nullable |  | Node identifier for metaconsole operations |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/service/{idService}/element/list` { #post-service-idservice-element-list }

List service elements

Lists the elements on the node that owns the parent service; serverId selects it on a metaconsole.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idService` | path | integer | yes | Service id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idServiceElement` | integer, nullable |  | Service element identifier |
| `idService` | integer |  | Parent service identifier |
| `description` | string, nullable |  | Element description |
| `weightOk` | number, nullable |  | Weight applied when the element is normal. Not allowed on smart services (autoCalculate=1). |
| `weightWarning` | number, nullable |  | Weight applied when the element is in warning. Not allowed on smart services (autoCalculate=1). |
| `weightCritical` | number, nullable |  | Weight applied when the element is critical. Not allowed on smart services (autoCalculate=1). |
| `weightUnknown` | number, nullable |  | Weight applied when the element is unknown. Not allowed on smart services (autoCalculate=1). |
| `idAgenteModulo` | integer, nullable |  | Agent module identifier for module elements |
| `idAgent` | integer, nullable |  | Agent identifier for agent elements |
| `idServiceChild` | integer, nullable |  | Child service identifier for service elements |
| `idServerMeta` | integer, nullable |  | Node identifier that owns the child service element (cross console link) |
| `rules` | object, nullable |  | Dynamic element rules |
| `serverId` | integer, nullable |  | Node identifier for metaconsole operations |
| `idServiceElement` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in description field. |
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
| `multipleSearch.field` | enum: `idServiceElement`, `idService`, `description`, `idAgenteModulo`, `idAgent`, `idServiceChild`, `weightOk`, `weightWarning`, `weightCritical`, `weightUnknown` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idServiceElement`, `idService`, `description`, `idAgenteModulo`, `idAgent`, `idServiceChild`, `weightOk`, `weightWarning`, `weightCritical`, `weightUnknown` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "description": "string",
      "weightOk": 0,
      "weightWarning": 0,
      "weightCritical": 0,
      "weightUnknown": 0,
      "idAgenteModulo": 0,
      "idAgent": 0,
      "idServiceChild": 0,
      "idServerMeta": 0,
      "rules": {},
      "idServiceElement": null,
      "freeSearch": "string",
      "requestedFields": [
        "idServiceElement"
      ],
      "fieldConditions": [
        {
          "field": "idServiceElement",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idServiceElement",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idServiceElement",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List Service element object

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
    | `data.[].idServiceElement` | integer, nullable |  | Service element identifier |
    | `data.[].idService` | integer |  | Parent service identifier |
    | `data.[].description` | string, nullable |  | Element description |
    | `data.[].weightOk` | number, nullable |  | Weight applied when the element is normal. Not allowed on smart services (autoCalculate=1). |
    | `data.[].weightWarning` | number, nullable |  | Weight applied when the element is in warning. Not allowed on smart services (autoCalculate=1). |
    | `data.[].weightCritical` | number, nullable |  | Weight applied when the element is critical. Not allowed on smart services (autoCalculate=1). |
    | `data.[].weightUnknown` | number, nullable |  | Weight applied when the element is unknown. Not allowed on smart services (autoCalculate=1). |
    | `data.[].idAgenteModulo` | integer, nullable |  | Agent module identifier for module elements |
    | `data.[].idAgent` | integer, nullable |  | Agent identifier for agent elements |
    | `data.[].idServiceChild` | integer, nullable |  | Child service identifier for service elements |
    | `data.[].idServerMeta` | integer, nullable |  | Node identifier that owns the child service element (cross console link) |
    | `data.[].rules` | object, nullable |  | Dynamic element rules |
    | `data.[].serverId` | integer, nullable |  | Node identifier for metaconsole operations |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

## ScheduledDowntimes

API Endpoints for scheduled downtimes

### <span class="api-method api-post">POST</span> `/scheduledDowntime` { #post-scheduleddowntime }

Create a scheduled downtime on a node

**Request body** (`application/json`): [`ScheduledDowntime`](#model-scheduleddowntime)

**Response 200**: Planned downtime object

Schema: [`FederatedScheduledDowntime`](#model-federatedscheduleddowntime)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/scheduledDowntime/{idScheduledDowntime}` { #get-scheduleddowntime-idscheduleddowntime }

Get a scheduled downtime

On a metaconsole, serverId is required and selects one enabled node.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Planned downtime object

Schema: [`FederatedScheduledDowntime`](#model-federatedscheduleddowntime)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`, `503`, `504`.

### <span class="api-method api-put">PUT</span> `/scheduledDowntime/{idScheduledDowntime}` { #put-scheduleddowntime-idscheduleddowntime }

Update a scheduled downtime on a node

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |

**Request body** (`application/json`): [`ScheduledDowntime`](#model-scheduleddowntime)

**Response 200**: Planned downtime object

Schema: [`FederatedScheduledDowntime`](#model-federatedscheduleddowntime)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-delete">DELETE</span> `/scheduledDowntime/{idScheduledDowntime}` { #delete-scheduleddowntime-idscheduleddowntime }

Delete a scheduled downtime on a node

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/scheduledDowntime/list` { #get-scheduleddowntime-list }

List scheduled downtimes

On a metaconsole, serverId is required and selects one enabled node.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List of scheduled downtimes

??? note "Response fields (38 fields)"

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
    | `data` | array of FederatedScheduledDowntime |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idScheduledDowntime` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].dateFrom` | integer |  | Unix timestamp |
    | `data.[].dateTo` | integer |  | Unix timestamp |
    | `data.[].executed` | boolean |  |  |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].onlyAlerts` | boolean |  |  |
    | `data.[].monday` | boolean |  |  |
    | `data.[].tuesday` | boolean |  |  |
    | `data.[].wednesday` | boolean |  |  |
    | `data.[].thursday` | boolean |  |  |
    | `data.[].friday` | boolean |  |  |
    | `data.[].saturday` | boolean |  |  |
    | `data.[].sunday` | boolean |  |  |
    | `data.[].periodicallyTimeFrom` | string, nullable |  |  |
    | `data.[].periodicallyTimeTo` | string, nullable |  |  |
    | `data.[].periodicallyDayFrom` | integer, nullable |  |  |
    | `data.[].periodicallyDayTo` | integer, nullable |  |  |
    | `data.[].typeDowntime` | enum: `quiet`, `disable_agents`, `disable_agent_modules`, `disable_agents_alerts` |  |  |
    | `data.[].typeExecution` | enum: `once`, `periodically`, `cron` |  |  |
    | `data.[].typePeriodicity` | enum: `weekly`, `monthly` |  |  |
    | `data.[].idUser` | string |  |  |
    | `data.[].cronIntervalFrom` | string, nullable |  |  |
    | `data.[].cronIntervalTo` | string, nullable |  |  |
    | `data.[].creationDate` | integer |  |  |
    | `data.[].expirationDate` | integer |  | Zero means never expires |


Error responses: `400`, `401`, `403`, `500`, `502`, `503`, `504`.

### <span class="api-method api-post">POST</span> `/scheduledDowntime/list` { #post-scheduleddowntime-list }

List scheduled downtimes with advanced filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idScheduledDowntime` | integer |  |  |
| `name` | string |  |  |
| `description` | string, nullable |  |  |
| `dateFrom` | integer |  | Unix timestamp |
| `dateTo` | integer |  | Unix timestamp |
| `executed` | boolean |  |  |
| `idGroup` | integer |  |  |
| `onlyAlerts` | boolean |  |  |
| `monday` | boolean |  |  |
| `tuesday` | boolean |  |  |
| `wednesday` | boolean |  |  |
| `thursday` | boolean |  |  |
| `friday` | boolean |  |  |
| `saturday` | boolean |  |  |
| `sunday` | boolean |  |  |
| `periodicallyTimeFrom` | string, nullable |  |  |
| `periodicallyTimeTo` | string, nullable |  |  |
| `periodicallyDayFrom` | integer, nullable |  |  |
| `periodicallyDayTo` | integer, nullable |  |  |
| `typeDowntime` | enum: `quiet`, `disable_agents`, `disable_agent_modules`, `disable_agents_alerts` |  |  |
| `typeExecution` | enum: `once`, `periodically`, `cron` |  |  |
| `typePeriodicity` | enum: `weekly`, `monthly` |  |  |
| `idUser` | string |  |  |
| `cronIntervalFrom` | string, nullable |  |  |
| `cronIntervalTo` | string, nullable |  |  |
| `creationDate` | integer |  |  |
| `expirationDate` | integer |  | Zero means never expires |
| `serverId` | integer, nullable |  |  |
| `freeSearch` | string, nullable |  |  |
| `idAgent` | integer, nullable |  |  |
| `idAgentModule` | integer, nullable |  |  |
| `hidePast` | boolean, nullable |  |  |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `limit` | integer |  |  |
| `offset` | integer |  |  |
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
| `multipleSearch.field` | enum: `idScheduledDowntime`, `name`, `description`, `dateFrom`, `dateTo`, `executed`, `idGroup`, `onlyAlerts`, `monday`, `tuesday`, `wednesday`, `thursday`, `friday`, `saturday`, `sunday`, `periodicallyTimeFrom`, `periodicallyTimeTo`, `periodicallyDayFrom`, `periodicallyDayTo`, `typeDowntime`, `typeExecution`, `typePeriodicity`, `idUser`, `cronIntervalFrom`, `cronIntervalTo`, `creationDate`, `expirationDate` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idScheduledDowntime`, `name`, `description`, `dateFrom`, `dateTo`, `executed`, `idGroup`, `onlyAlerts`, `monday`, `tuesday`, `wednesday`, `thursday`, `friday`, `saturday`, `sunday`, `periodicallyTimeFrom`, `periodicallyTimeTo`, `periodicallyDayFrom`, `periodicallyDayTo`, `typeDowntime`, `typeExecution`, `typePeriodicity`, `idUser`, `cronIntervalFrom`, `cronIntervalTo`, `creationDate`, `expirationDate` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "dateFrom": 0,
      "dateTo": 0,
      "idGroup": 0,
      "monday": false,
      "tuesday": false,
      "wednesday": false,
      "thursday": false,
      "friday": false,
      "saturday": false,
      "sunday": false,
      "periodicallyTimeFrom": "00:00:00",
      "periodicallyTimeTo": "01:00:00",
      "periodicallyDayFrom": 0,
      "periodicallyDayTo": 0,
      "typeDowntime": "quiet",
      "typeExecution": "once",
      "typePeriodicity": "weekly",
      "cronIntervalFrom": "string",
      "cronIntervalTo": "string",
      "expirationDate": 0,
      "serverId": 0,
      "freeSearch": "string",
      "idAgent": 0,
      "idAgentModule": 0,
      "hidePast": false,
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "requestedFields": [
        "idScheduledDowntime"
      ],
      "fieldConditions": [
        {
          "field": "idScheduledDowntime",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "multipleSearch": {
        "field": "idScheduledDowntime",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idScheduledDowntime",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List of scheduled downtimes

??? note "Response fields (38 fields)"

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
    | `data` | array of FederatedScheduledDowntime |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idScheduledDowntime` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].dateFrom` | integer |  | Unix timestamp |
    | `data.[].dateTo` | integer |  | Unix timestamp |
    | `data.[].executed` | boolean |  |  |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].onlyAlerts` | boolean |  |  |
    | `data.[].monday` | boolean |  |  |
    | `data.[].tuesday` | boolean |  |  |
    | `data.[].wednesday` | boolean |  |  |
    | `data.[].thursday` | boolean |  |  |
    | `data.[].friday` | boolean |  |  |
    | `data.[].saturday` | boolean |  |  |
    | `data.[].sunday` | boolean |  |  |
    | `data.[].periodicallyTimeFrom` | string, nullable |  |  |
    | `data.[].periodicallyTimeTo` | string, nullable |  |  |
    | `data.[].periodicallyDayFrom` | integer, nullable |  |  |
    | `data.[].periodicallyDayTo` | integer, nullable |  |  |
    | `data.[].typeDowntime` | enum: `quiet`, `disable_agents`, `disable_agent_modules`, `disable_agents_alerts` |  |  |
    | `data.[].typeExecution` | enum: `once`, `periodically`, `cron` |  |  |
    | `data.[].typePeriodicity` | enum: `weekly`, `monthly` |  |  |
    | `data.[].idUser` | string |  |  |
    | `data.[].cronIntervalFrom` | string, nullable |  |  |
    | `data.[].cronIntervalTo` | string, nullable |  |  |
    | `data.[].creationDate` | integer |  |  |
    | `data.[].expirationDate` | integer |  | Zero means never expires |


Error responses: `400`, `401`, `403`, `500`, `502`, `503`, `504`.

## ScheduledDowntimeAgents

Agents assigned to scheduled downtimes

### <span class="api-method api-post">POST</span> `/scheduledDowntime/{idScheduledDowntime}/agent` { #post-scheduleddowntime-idscheduleddowntime-agent }

Add an agent to a scheduled downtime

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |

**Request body** (`application/json`): [`ScheduledDowntimeAgent`](#model-scheduleddowntimeagent)

**Response 200**: Scheduled downtime agent association

Schema: [`FederatedScheduledDowntimeAgent`](#model-federatedscheduleddowntimeagent)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/scheduledDowntime/{idScheduledDowntime}/agent/{idScheduledDowntimeAgent}` { #get-scheduleddowntime-idscheduleddowntime-agent-idscheduleddowntimeagent }

Get an agent assigned to a scheduled downtime

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |
| `idScheduledDowntimeAgent` | path | integer | yes |  |

**Response 200**: Scheduled downtime agent association

Schema: [`FederatedScheduledDowntimeAgent`](#model-federatedscheduleddowntimeagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/scheduledDowntime/{idScheduledDowntime}/agent/{idScheduledDowntimeAgent}` { #put-scheduleddowntime-idscheduleddowntime-agent-idscheduleddowntimeagent }

Update an agent assigned to a scheduled downtime

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |
| `idScheduledDowntimeAgent` | path | integer | yes |  |

**Request body** (`application/json`): [`ScheduledDowntimeAgent`](#model-scheduleddowntimeagent)

**Response 200**: Scheduled downtime agent association

Schema: [`FederatedScheduledDowntimeAgent`](#model-federatedscheduleddowntimeagent)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-delete">DELETE</span> `/scheduledDowntime/{idScheduledDowntime}/agent/{idScheduledDowntimeAgent}` { #delete-scheduleddowntime-idscheduleddowntime-agent-idscheduleddowntimeagent }

Remove an agent from a scheduled downtime

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |
| `idScheduledDowntimeAgent` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/scheduledDowntime/{idScheduledDowntime}/agent/list` { #get-scheduleddowntime-idscheduleddowntime-agent-list }

List agents assigned to a scheduled downtime

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Response 200**: Scheduled downtime agents

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
    | `data` | array of FederatedScheduledDowntimeAgent |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idScheduledDowntimeAgent` | integer |  |  |
    | `data.[].idScheduledDowntime` | integer |  |  |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].allModules` | boolean |  |  |
    | `data.[].manuallyDisabled` | boolean |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/scheduledDowntime/{idScheduledDowntime}/agent/list` { #post-scheduleddowntime-idscheduleddowntime-agent-list }

List agents assigned to a scheduled downtime

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idScheduledDowntimeAgent` | integer |  |  |
| `idScheduledDowntime` | integer |  |  |
| `idAgent` | integer |  |  |
| `allModules` | boolean |  |  |
| `manuallyDisabled` | boolean |  |  |
| `serverId` | integer, nullable |  |  |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `limit` | integer |  |  |
| `offset` | integer |  |  |
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
| `multipleSearch.field` | enum: `idScheduledDowntimeAgent`, `idScheduledDowntime`, `idAgent`, `allModules`, `manuallyDisabled` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idScheduledDowntimeAgent`, `idScheduledDowntime`, `idAgent`, `allModules`, `manuallyDisabled` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": 0,
      "allModules": false,
      "serverId": 0,
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "requestedFields": [
        "idScheduledDowntimeAgent"
      ],
      "fieldConditions": [
        {
          "field": "idScheduledDowntimeAgent",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "multipleSearch": {
        "field": "idScheduledDowntimeAgent",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idScheduledDowntimeAgent",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Scheduled downtime agents

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
    | `data` | array of FederatedScheduledDowntimeAgent |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idScheduledDowntimeAgent` | integer |  |  |
    | `data.[].idScheduledDowntime` | integer |  |  |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].allModules` | boolean |  |  |
    | `data.[].manuallyDisabled` | boolean |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

## ScheduledDowntimeModules

Modules assigned to scheduled downtimes

### <span class="api-method api-post">POST</span> `/scheduledDowntime/{idScheduledDowntime}/module` { #post-scheduleddowntime-idscheduleddowntime-module }

Add a module to a scheduled downtime

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idScheduledDowntimeModule` | integer |  |  |
| `idScheduledDowntime` | integer |  |  |
| `idAgent` | integer |  |  |
| `idAgentModule` | integer |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": 0,
      "idAgentModule": 0
    }
    ```

**Response 200**: Scheduled downtime module association

Schema: [`FederatedScheduledDowntimeModule`](#model-federatedscheduleddowntimemodule)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/scheduledDowntime/{idScheduledDowntime}/module/{idScheduledDowntimeModule}` { #get-scheduleddowntime-idscheduleddowntime-module-idscheduleddowntimemodule }

Get a module assigned to a scheduled downtime

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |
| `idScheduledDowntimeModule` | path | integer | yes |  |

**Response 200**: Scheduled downtime module association

Schema: [`FederatedScheduledDowntimeModule`](#model-federatedscheduleddowntimemodule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/scheduledDowntime/{idScheduledDowntime}/module/{idScheduledDowntimeModule}` { #delete-scheduleddowntime-idscheduleddowntime-module-idscheduleddowntimemodule }

Remove a module from a scheduled downtime

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |
| `idScheduledDowntimeModule` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/scheduledDowntime/{idScheduledDowntime}/module/list` { #get-scheduleddowntime-idscheduleddowntime-module-list }

List modules assigned to a scheduled downtime

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Response 200**: Scheduled downtime modules

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
    | `data` | array of FederatedScheduledDowntimeModule |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idScheduledDowntimeModule` | integer |  |  |
    | `data.[].idScheduledDowntime` | integer |  |  |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].idAgentModule` | integer |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/scheduledDowntime/{idScheduledDowntime}/module/list` { #post-scheduleddowntime-idscheduleddowntime-module-list }

List modules assigned to a scheduled downtime

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idScheduledDowntime` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idScheduledDowntimeModule` | integer |  |  |
| `idScheduledDowntime` | integer |  |  |
| `idAgent` | integer |  |  |
| `idAgentModule` | integer |  |  |
| `serverId` | integer, nullable |  |  |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `limit` | integer |  |  |
| `offset` | integer |  |  |
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
| `multipleSearch.field` | enum: `idScheduledDowntimeModule`, `idScheduledDowntime`, `idAgent`, `idAgentModule` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idScheduledDowntimeModule`, `idScheduledDowntime`, `idAgent`, `idAgentModule` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": 0,
      "idAgentModule": 0,
      "serverId": 0,
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "requestedFields": [
        "idScheduledDowntimeModule"
      ],
      "fieldConditions": [
        {
          "field": "idScheduledDowntimeModule",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "multipleSearch": {
        "field": "idScheduledDowntimeModule",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idScheduledDowntimeModule",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Scheduled downtime modules

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
    | `data` | array of FederatedScheduledDowntimeModule |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idScheduledDowntimeModule` | integer |  |  |
    | `data.[].idScheduledDowntime` | integer |  |  |
    | `data.[].idAgent` | integer |  |  |
    | `data.[].idAgentModule` | integer |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: FederatedScheduledDowntime { #model-federatedscheduleddowntime }

??? note "Fields (28 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `serverId` | integer, nullable |  | Console that owns the resource |
    | `idScheduledDowntime` | integer |  |  |
    | `name` | string |  |  |
    | `description` | string, nullable |  |  |
    | `dateFrom` | integer |  | Unix timestamp |
    | `dateTo` | integer |  | Unix timestamp |
    | `executed` | boolean |  |  |
    | `idGroup` | integer |  |  |
    | `onlyAlerts` | boolean |  |  |
    | `monday` | boolean |  |  |
    | `tuesday` | boolean |  |  |
    | `wednesday` | boolean |  |  |
    | `thursday` | boolean |  |  |
    | `friday` | boolean |  |  |
    | `saturday` | boolean |  |  |
    | `sunday` | boolean |  |  |
    | `periodicallyTimeFrom` | string, nullable |  |  |
    | `periodicallyTimeTo` | string, nullable |  |  |
    | `periodicallyDayFrom` | integer, nullable |  |  |
    | `periodicallyDayTo` | integer, nullable |  |  |
    | `typeDowntime` | enum: `quiet`, `disable_agents`, `disable_agent_modules`, `disable_agents_alerts` |  |  |
    | `typeExecution` | enum: `once`, `periodically`, `cron` |  |  |
    | `typePeriodicity` | enum: `weekly`, `monthly` |  |  |
    | `idUser` | string |  |  |
    | `cronIntervalFrom` | string, nullable |  |  |
    | `cronIntervalTo` | string, nullable |  |  |
    | `creationDate` | integer |  |  |
    | `expirationDate` | integer |  | Zero means never expires |


### Model: FederatedScheduledDowntimeAgent { #model-federatedscheduleddowntimeagent }

??? note "Fields (6 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `serverId` | integer, nullable |  | Console that owns the resource |
    | `idScheduledDowntimeAgent` | integer |  |  |
    | `idScheduledDowntime` | integer |  |  |
    | `idAgent` | integer |  |  |
    | `allModules` | boolean |  |  |
    | `manuallyDisabled` | boolean |  |  |


### Model: FederatedScheduledDowntimeModule { #model-federatedscheduleddowntimemodule }

??? note "Fields (5 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `serverId` | integer, nullable |  | Console that owns the resource |
    | `idScheduledDowntimeModule` | integer |  |  |
    | `idScheduledDowntime` | integer |  |  |
    | `idAgent` | integer |  |  |
    | `idAgentModule` | integer |  |  |


### Model: ScheduledDowntime { #model-scheduleddowntime }

| Field | Type | Required | Description |
|---|---|---|---|
| `idScheduledDowntime` | integer |  |  |
| `name` | string |  |  |
| `description` | string, nullable |  |  |
| `dateFrom` | integer |  | Unix timestamp |
| `dateTo` | integer |  | Unix timestamp |
| `executed` | boolean |  |  |
| `idGroup` | integer |  |  |
| `onlyAlerts` | boolean |  |  |
| `monday` | boolean |  |  |
| `tuesday` | boolean |  |  |
| `wednesday` | boolean |  |  |
| `thursday` | boolean |  |  |
| `friday` | boolean |  |  |
| `saturday` | boolean |  |  |
| `sunday` | boolean |  |  |
| `periodicallyTimeFrom` | string, nullable |  |  |
| `periodicallyTimeTo` | string, nullable |  |  |
| `periodicallyDayFrom` | integer, nullable |  |  |
| `periodicallyDayTo` | integer, nullable |  |  |
| `typeDowntime` | enum: `quiet`, `disable_agents`, `disable_agent_modules`, `disable_agents_alerts` |  |  |
| `typeExecution` | enum: `once`, `periodically`, `cron` |  |  |
| `typePeriodicity` | enum: `weekly`, `monthly` |  |  |
| `idUser` | string |  |  |
| `cronIntervalFrom` | string, nullable |  |  |
| `cronIntervalTo` | string, nullable |  |  |
| `creationDate` | integer |  |  |
| `expirationDate` | integer |  | Zero means never expires |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "dateFrom": 0,
      "dateTo": 0,
      "idGroup": 0,
      "monday": false,
      "tuesday": false,
      "wednesday": false,
      "thursday": false,
      "friday": false,
      "saturday": false,
      "sunday": false,
      "periodicallyTimeFrom": "00:00:00",
      "periodicallyTimeTo": "01:00:00",
      "periodicallyDayFrom": 0,
      "periodicallyDayTo": 0,
      "typeDowntime": "quiet",
      "typeExecution": "once",
      "typePeriodicity": "weekly",
      "cronIntervalFrom": "string",
      "cronIntervalTo": "string",
      "expirationDate": 0
    }
    ```

### Model: ScheduledDowntimeAgent { #model-scheduleddowntimeagent }

| Field | Type | Required | Description |
|---|---|---|---|
| `idScheduledDowntimeAgent` | integer |  |  |
| `idScheduledDowntime` | integer |  |  |
| `idAgent` | integer |  |  |
| `allModules` | boolean |  |  |
| `manuallyDisabled` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": 0,
      "allModules": false
    }
    ```

### Model: Service { #model-service }

??? note "Fields (33 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idService` | integer, nullable |  | Service identifier |
    | `name` | string |  | Service name |
    | `description` | string, nullable |  | Service description |
    | `idGroup` | integer |  | Group the service belongs to |
    | `autoCalculate` | enum: `0`, `1` |  | Calculation mode: 0 manual, 1 smart |
    | `critical` | number, nullable |  | Critical threshold |
    | `warning` | number, nullable |  | Warning threshold |
    | `unknownAsCritical` | boolean, nullable |  | Treat unknown elements as critical |
    | `serviceInterval` | integer, nullable |  | Service value module interval in seconds |
    | `slaInterval` | integer, nullable |  | SLA calculation window in seconds |
    | `slaLimit` | number, nullable |  | Minimum SLA percentage |
    | `slaModuleInterval` | integer, nullable |  | SLA module interval in seconds |
    | `slaValueModuleInterval` | integer, nullable |  | SLA value module interval in seconds |
    | `evaluateSla` | boolean, nullable |  | Whether the SLA is evaluated |
    | `quiet` | boolean, nullable |  | Disable alerts and events |
    | `cascadeProtection` | boolean, nullable |  | Enable cascade protection |
    | `isFavourite` | boolean, nullable |  | Mark as favourite |
    | `enableSunburst` | boolean, nullable |  | Render the service map as sunburst |
    | `enableHorizontalTree` | boolean, nullable |  | Render the service map as horizontal tree |
    | `asynchronous` | boolean, nullable |  | Evaluate the service asynchronously |
    | `idTemplateAlertWarning` | integer, nullable |  | Alert template for warning state |
    | `idTemplateAlertCritical` | integer, nullable |  | Alert template for critical state |
    | `idTemplateAlertUnknown` | integer, nullable |  | Alert template for unknown state |
    | `idTemplateAlertCriticalSla` | integer, nullable |  | Alert template for critical SLA state |
    | `status` | integer, nullable |  | Current status: -1 unknown, 0 normal, 1 critical, 2 warning |
    | `serviceValue` | number, nullable |  | Last calculated service value |
    | `utimestamp` | integer, nullable |  | Last update timestamp |
    | `idAgentModule` | integer, nullable |  | Agent module that stores the service value |
    | `slaIdModule` | integer, nullable |  | Agent module that stores the SLA |
    | `slaValueIdModule` | integer, nullable |  | Agent module that stores the SLA value |
    | `cpsInhibit` | integer, nullable |  | Cascade protection inhibition counter, managed by the server |
    | `rca` | string, nullable |  | Raw root cause analysis chain stored by the server |
    | `serverId` | integer, nullable |  | Node identifier for metaconsole operations |


### Model: ServiceCreate { #model-servicecreate }

| Field | Type | Required | Description |
|---|---|---|---|
| `idService` | integer, nullable |  | Service identifier |
| `name` | string | yes | Service name |
| `description` | string, nullable | yes | Service description |
| `idGroup` | integer | yes | Group the service belongs to |
| `autoCalculate` | enum: `0`, `1` |  | Calculation mode: 0 manual, 1 smart |
| `critical` | number, nullable |  | Critical threshold |
| `warning` | number, nullable |  | Warning threshold |
| `unknownAsCritical` | boolean, nullable |  | Treat unknown elements as critical |
| `serviceInterval` | integer, nullable |  | Service value module interval in seconds |
| `slaInterval` | integer, nullable |  | SLA calculation window in seconds |
| `slaLimit` | number, nullable |  | Minimum SLA percentage |
| `slaModuleInterval` | integer, nullable |  | SLA module interval in seconds |
| `slaValueModuleInterval` | integer, nullable |  | SLA value module interval in seconds |
| `evaluateSla` | boolean, nullable |  | Whether the SLA is evaluated |
| `quiet` | boolean, nullable |  | Disable alerts and events |
| `cascadeProtection` | boolean, nullable |  | Enable cascade protection |
| `isFavourite` | boolean, nullable |  | Mark as favourite |
| `enableSunburst` | boolean, nullable |  | Render the service map as sunburst |
| `enableHorizontalTree` | boolean, nullable |  | Render the service map as horizontal tree |
| `asynchronous` | boolean, nullable |  | Evaluate the service asynchronously |
| `idTemplateAlertWarning` | integer, nullable |  | Alert template for warning state |
| `idTemplateAlertCritical` | integer, nullable |  | Alert template for critical state |
| `idTemplateAlertUnknown` | integer, nullable |  | Alert template for unknown state |
| `idTemplateAlertCriticalSla` | integer, nullable |  | Alert template for critical SLA state |
| `status` | integer, nullable |  | Current status: -1 unknown, 0 normal, 1 critical, 2 warning |
| `serviceValue` | number, nullable |  | Last calculated service value |
| `utimestamp` | integer, nullable |  | Last update timestamp |
| `idAgentModule` | integer, nullable |  | Agent module that stores the service value |
| `slaIdModule` | integer, nullable |  | Agent module that stores the SLA |
| `slaValueIdModule` | integer, nullable |  | Agent module that stores the SLA value |
| `cpsInhibit` | integer, nullable |  | Cascade protection inhibition counter, managed by the server |
| `rca` | string, nullable |  | Raw root cause analysis chain stored by the server |
| `serverId` | integer, nullable |  | Node identifier for metaconsole operations |
| `idAgent` | integer, nullable |  | Agent that stores the service value modules. Required on the execution node, including forwarded requests. Omit for local metaconsole creation, which creates its own agent. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "autoCalculate": 0,
      "critical": 0,
      "warning": 0,
      "unknownAsCritical": false,
      "serviceInterval": 0,
      "slaInterval": 0,
      "slaLimit": 0,
      "slaModuleInterval": 0,
      "slaValueModuleInterval": 0,
      "evaluateSla": false,
      "quiet": false,
      "cascadeProtection": false,
      "isFavourite": false,
      "enableSunburst": false,
      "enableHorizontalTree": false,
      "asynchronous": false,
      "idTemplateAlertWarning": 0,
      "idTemplateAlertCritical": 0,
      "idTemplateAlertUnknown": 0,
      "idTemplateAlertCriticalSla": 0,
      "idAgent": 0
    }
    ```

### Model: ServiceElement { #model-serviceelement }

??? note "Fields (13 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idServiceElement` | integer, nullable |  | Service element identifier |
    | `idService` | integer |  | Parent service identifier |
    | `description` | string, nullable |  | Element description |
    | `weightOk` | number, nullable |  | Weight applied when the element is normal. Not allowed on smart services (autoCalculate=1). |
    | `weightWarning` | number, nullable |  | Weight applied when the element is in warning. Not allowed on smart services (autoCalculate=1). |
    | `weightCritical` | number, nullable |  | Weight applied when the element is critical. Not allowed on smart services (autoCalculate=1). |
    | `weightUnknown` | number, nullable |  | Weight applied when the element is unknown. Not allowed on smart services (autoCalculate=1). |
    | `idAgenteModulo` | integer, nullable |  | Agent module identifier for module elements |
    | `idAgent` | integer, nullable |  | Agent identifier for agent elements |
    | `idServiceChild` | integer, nullable |  | Child service identifier for service elements |
    | `idServerMeta` | integer, nullable |  | Node identifier that owns the child service element (cross console link) |
    | `rules` | object, nullable |  | Dynamic element rules |
    | `serverId` | integer, nullable |  | Node identifier for metaconsole operations |
