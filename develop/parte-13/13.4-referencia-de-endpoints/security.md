# Security

SIEM rules, events and logs, security vulnerabilities and Windows patches.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-post">POST</span> | [`/siem/rule/{idRule}/group`](#post-siem-rule-idrule-group) | Add a group to a rule |
| <span class="api-method api-post">POST</span> | [`/siem/rule`](#post-siem-rule) | Creates a new rule |
| <span class="api-method api-delete">DELETE</span> | [`/siem/rule/{idRule}/group/{idGroup}`](#delete-siem-rule-idrule-group-idgroup) | Delete group to rule object. |
| <span class="api-method api-get">GET</span> | [`/siem/rule/{idRule}`](#get-siem-rule-idrule) | Show rule |
| <span class="api-method api-put">PUT</span> | [`/siem/rule/{idRule}`](#put-siem-rule-idrule) | Updates a rule |
| <span class="api-method api-delete">DELETE</span> | [`/siem/rule/{idRule}`](#delete-siem-rule-idrule) | Deletes a rule object. |
| <span class="api-method api-put">PUT</span> | [`/siem/rules-reload`](#put-siem-rules-reload) | Hot reload rules |
| <span class="api-method api-post">POST</span> | [`/siem/rule/list`](#post-siem-rule-list) | List rules |
| <span class="api-method api-post">POST</span> | [`/siem/rule/{idRule}/group/list`](#post-siem-rule-idrule-group-list) | List groups of rules |
| <span class="api-method api-post">POST</span> | [`/siem/group`](#post-siem-group) | Creates a new SIEM group |
| <span class="api-method api-get">GET</span> | [`/siem/group/{idSiemGroup}`](#get-siem-group-idsiemgroup) | Show SIEM group |
| <span class="api-method api-put">PUT</span> | [`/siem/group/{idSiemGroup}`](#put-siem-group-idsiemgroup) | Updates a SIEM group |
| <span class="api-method api-delete">DELETE</span> | [`/siem/group/{idSiemGroup}`](#delete-siem-group-idsiemgroup) | Deletes a SIEM group object. |
| <span class="api-method api-post">POST</span> | [`/siem/group/list`](#post-siem-group-list) | List SIEM groups |
| <span class="api-method api-post">POST</span> | [`/siem/event/aggregate`](#post-siem-event-aggregate) | Count authorized SIEM events by one dimension |
| <span class="api-method api-get">GET</span> | [`/siem/event/{idEvent}`](#get-siem-event-idevent) | Get one authorized SIEM event |
| <span class="api-method api-get">GET</span> | [`/siem/event/list`](#get-siem-event-list) | List authorized SIEM events |
| <span class="api-method api-post">POST</span> | [`/siem/event/list`](#post-siem-event-list) | List authorized SIEM events with object filters |
| <span class="api-method api-post">POST</span> | [`/siem/log/aggregate`](#post-siem-log-aggregate) | Count authorized decoded SIEM logs by one dimension |
| <span class="api-method api-get">GET</span> | [`/siem/log/{idLog}`](#get-siem-log-idlog) | Get one authorized decoded SIEM log |
| <span class="api-method api-get">GET</span> | [`/siem/log/list`](#get-siem-log-list) | List authorized decoded SIEM logs |
| <span class="api-method api-post">POST</span> | [`/siem/log/list`](#post-siem-log-list) | List authorized decoded SIEM logs with object filters |
| <span class="api-method api-get">GET</span> | [`/securityVulnerability/{idAgent}/{hash}/{utimestamp}`](#get-securityvulnerability-idagent-hash-utimestamp) | Get one security vulnerability |
| <span class="api-method api-get">GET</span> | [`/securityVulnerability/list`](#get-securityvulnerability-list) | List security vulnerabilities using query filters |
| <span class="api-method api-post">POST</span> | [`/securityVulnerability/list`](#post-securityvulnerability-list) | List security vulnerabilities |
| <span class="api-method api-get">GET</span> | [`/windowsPatch/{idAgent}/{kb}/{utimestamp}`](#get-windowspatch-idagent-kb-utimestamp) | Get one installed Windows patch |
| <span class="api-method api-get">GET</span> | [`/windowsPatch/list`](#get-windowspatch-list) | List installed Windows patches using query filters |
| <span class="api-method api-post">POST</span> | [`/windowsPatch/list`](#post-windowspatch-list) | List installed Windows patches |

## SIEM

API Endpoints of SIEM (Security Information and Event Management)

### <span class="api-method api-post">POST</span> `/siem/rule/{idRule}/group` { #post-siem-rule-idrule-group }

Add a group to a rule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRule` | path | integer | yes | Rule id |

**Request body** (`application/json`): list of [`SiemGroup`](#model-siemgroup)

**Response 200**: Rule object

Schema: [`Rule`](#model-rule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/siem/rule` { #post-siem-rule }

Creates a new rule

**Request body** (`application/json`): [`Rule`](#model-rule)

**Response 200**: Rule object

Schema: [`Rule`](#model-rule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/siem/rule/{idRule}/group/{idGroup}` { #delete-siem-rule-idrule-group-idgroup }

Delete group to rule object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRule` | path | integer | yes | Rule id |
| `idGroup` | path | integer | yes | Group id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/siem/rule/{idRule}` { #get-siem-rule-idrule }

Show rule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRule` | path | integer | yes | Rule id |

**Response 200**: Rule object

Schema: [`Rule`](#model-rule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/siem/rule/{idRule}` { #put-siem-rule-idrule }

Updates a rule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRule` | path | integer | yes | Rule id |

**Request body** (`application/json`): [`Rule`](#model-rule)

**Response 200**: Rule object

Schema: [`Rule`](#model-rule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/siem/rule/{idRule}` { #delete-siem-rule-idrule }

Deletes a rule object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRule` | path | integer | yes | Rule id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/siem/rules-reload` { #put-siem-rules-reload }

Hot reload rules

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/siem/rule/list` { #post-siem-rule-list }

List rules

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
| `id` | integer |  | Rule ID |
| `idServer` | integer, nullable |  | Server ID for the rule |
| `description` | string |  | Rule description |
| `level` | integer, nullable |  | Rule level |
| `overwrite` | string, nullable |  | Overwrite flag |
| `decodedAs` | string, nullable |  | Decoded as value |
| `category` | string, nullable |  | Rule category |
| `programName` | string, nullable |  | Program name |
| `match` | array, nullable |  | Match patterns |
| `field` | array, nullable |  | Field patterns |
| `frequency` | integer, nullable |  | Rule frequency |
| `timeframe` | integer, nullable |  | Rule timeframe |
| `ignore` | integer, nullable |  | Ignore flag |
| `ifMatchedSid` | integer, nullable |  | If matched SID |
| `ifMatchedGroup` | string, nullable |  | If matched group |
| `ifSid` | array, nullable |  | If SID array |
| `ifGroup` | string, nullable |  | If group |
| `ifLevel` | integer, nullable |  | If level |
| `sameId` | integer, nullable |  | Same ID flag |
| `differentId` | integer, nullable |  | Different ID flag |
| `sameField` | array, nullable |  | Same field patterns |
| `differentField` | array, nullable |  | Different field patterns |
| `serverManaged` | boolean, nullable |  | Server managed flag |
| `enabled` | boolean, nullable |  | Enabled flag |
| `active` | boolean, nullable |  | Active flag |
| `maxsize` | integer, nullable |  | Maximum log size |
| `noalert` | integer, nullable |  | No alert flag |
| `timeFrom` | string, nullable |  | Time from |
| `timeTo` | string, nullable |  | Time to |
| `weekdate` | string, nullable |  | Week date |
| `ifFts` | integer, nullable |  | If FTS flag |
| `info` | string, nullable |  | Info text |
| `infoType` | string, nullable |  | Info type |
| `dynamicField` | array, nullable |  | Dynamic fields array |
| `mitre` | array, nullable |  | MITRE IDs |
| `id` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in description field. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "id": null,
      "idServer": 0,
      "description": "Rule created by API",
      "level": 0,
      "overwrite": "string",
      "decodedAs": "string",
      "category": "string",
      "programName": "string",
      "match": [
        "string"
      ],
      "field": [
        "string"
      ],
      "frequency": 0,
      "timeframe": 0,
      "ignore": 0,
      "ifMatchedSid": 0,
      "ifMatchedGroup": "string",
      "ifSid": [
        0
      ],
      "ifGroup": "string",
      "ifLevel": 0,
      "sameId": 0,
      "differentId": 0,
      "sameField": [
        "string"
      ],
      "differentField": [
        "string"
      ],
      "enabled": true,
      "active": true,
      "maxsize": 0,
      "noalert": 0,
      "timeFrom": "string",
      "timeTo": "string",
      "weekdate": "string",
      "ifFts": 0,
      "info": "string",
      "infoType": "string",
      "dynamicField": [
        "string"
      ],
      "mitre": [
        "string"
      ],
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

**Response 200**: List Rules Object

??? note "Response fields (45 fields)"

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
    | `data.[].id` | integer |  | Rule ID |
    | `data.[].idServer` | integer, nullable |  | Server ID for the rule |
    | `data.[].description` | string |  | Rule description |
    | `data.[].level` | integer, nullable |  | Rule level |
    | `data.[].overwrite` | string, nullable |  | Overwrite flag |
    | `data.[].decodedAs` | string, nullable |  | Decoded as value |
    | `data.[].category` | string, nullable |  | Rule category |
    | `data.[].programName` | string, nullable |  | Program name |
    | `data.[].match` | array, nullable |  | Match patterns |
    | `data.[].field` | array, nullable |  | Field patterns |
    | `data.[].frequency` | integer, nullable |  | Rule frequency |
    | `data.[].timeframe` | integer, nullable |  | Rule timeframe |
    | `data.[].ignore` | integer, nullable |  | Ignore flag |
    | `data.[].ifMatchedSid` | integer, nullable |  | If matched SID |
    | `data.[].ifMatchedGroup` | string, nullable |  | If matched group |
    | `data.[].ifSid` | array, nullable |  | If SID array |
    | `data.[].ifGroup` | string, nullable |  | If group |
    | `data.[].ifLevel` | integer, nullable |  | If level |
    | `data.[].sameId` | integer, nullable |  | Same ID flag |
    | `data.[].differentId` | integer, nullable |  | Different ID flag |
    | `data.[].sameField` | array, nullable |  | Same field patterns |
    | `data.[].differentField` | array, nullable |  | Different field patterns |
    | `data.[].serverManaged` | boolean, nullable |  | Server managed flag |
    | `data.[].enabled` | boolean, nullable |  | Enabled flag |
    | `data.[].active` | boolean, nullable |  | Active flag |
    | `data.[].maxsize` | integer, nullable |  | Maximum log size |
    | `data.[].noalert` | integer, nullable |  | No alert flag |
    | `data.[].timeFrom` | string, nullable |  | Time from |
    | `data.[].timeTo` | string, nullable |  | Time to |
    | `data.[].weekdate` | string, nullable |  | Week date |
    | `data.[].ifFts` | integer, nullable |  | If FTS flag |
    | `data.[].info` | string, nullable |  | Info text |
    | `data.[].infoType` | string, nullable |  | Info type |
    | `data.[].dynamicField` | array, nullable |  | Dynamic fields array |
    | `data.[].mitre` | array, nullable |  | MITRE IDs |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/siem/rule/{idRule}/group/list` { #post-siem-rule-idrule-group-list }

List groups of rules

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idRule` | path | integer | yes | Rule id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`): [`SiemGroupFilter`](#model-siemgroupfilter)

**Response 200**: List Groups Rules Object

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
    | `data.[].id` | integer, nullable |  | Group ID |
    | `data.[].name` | string |  | Group name |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/siem/group` { #post-siem-group }

Creates a new SIEM group

**Request body** (`application/json`): [`SiemGroup`](#model-siemgroup)

**Response 200**: SIEM Group object

Schema: [`SiemGroup`](#model-siemgroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/siem/group/{idSiemGroup}` { #get-siem-group-idsiemgroup }

Show SIEM group

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idSiemGroup` | path | integer | yes | SIEM Group id |

**Response 200**: SIEM Group object

Schema: [`SiemGroup`](#model-siemgroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/siem/group/{idSiemGroup}` { #put-siem-group-idsiemgroup }

Updates a SIEM group

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idSiemGroup` | path | integer | yes | SIEM Group id |

**Request body** (`application/json`): [`SiemGroup`](#model-siemgroup)

**Response 200**: SIEM Group object

Schema: [`SiemGroup`](#model-siemgroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/siem/group/{idSiemGroup}` { #delete-siem-group-idsiemgroup }

Deletes a SIEM group object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idSiemGroup` | path | integer | yes | SIEM Group id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/siem/group/list` { #post-siem-group-list }

List SIEM groups

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`): [`SiemGroupFilter`](#model-siemgroupfilter)

**Response 200**: List SIEM Groups Object

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
    | `data.[].id` | integer, nullable |  | Group ID |
    | `data.[].name` | string |  | Group name |


Error responses: `400`, `401`, `403`, `404`, `500`.

## SiemEvents

Read authorized SIEM events from nodes

### <span class="api-method api-post">POST</span> `/siem/event/aggregate` { #post-siem-event-aggregate }

Count authorized SIEM events by one dimension

Exact top-N by count descending, key ascending (numeric for rule/severity).
Same resource filters, UTC interval and ACL as listing; last 24h by default.
Metaconsole requires one explicit serverId in the body. No paging, custom sort or multi-node merge.
Decoder is multivalued: bucket counts may sum above totalEvents. Missing values are counted separately.
At most 10000 distinct groups are supported; incomplete bucket coverage fails as 503, never approximate
success. truncated only reports groups omitted by the requested top-N; returned counts stay exact.

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `groupBy` | enum: `rule`, `decoder`, `agentName`, `type`, `severity` | yes |  |
| `size` | integer |  |  |
| `startDate` | string (date-time) |  | Internal validated OpenSearch criteria, not a SQL FilterAbstract. |
| `endDate` | string (date-time) |  |  |
| `serverId` | integer |  | Required only on metaconsole |
| `level` | integer |  |  |
| `severity` | integer |  |  |
| `status` | enum: `0`, `1` |  |  |
| `idRule` | integer |  |  |
| `decoder` | string |  |  |
| `type` | string |  |  |
| `idGroup` | integer |  |  |
| `recursiveGroups` | boolean |  |  |
| `idAgent` | integer |  | Cached agent ID on metaconsole |
| `agentName` | string |  |  |
| `search` | string |  |  |
| `eventId` | string |  |  |
| `mitre` | array of string |  |  |
| `customFields` | object |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "groupBy": "rule",
      "size": 10,
      "startDate": "string",
      "endDate": "string",
      "serverId": 0,
      "level": 0,
      "severity": 0,
      "status": 0,
      "idRule": 0,
      "decoder": "string",
      "type": "string",
      "idGroup": 0,
      "recursiveGroups": false,
      "idAgent": 0,
      "agentName": "string",
      "search": "string",
      "eventId": "string",
      "mitre": [
        "string"
      ],
      "customFields": {}
    }
    ```

**Response 200**: Exact top-N and coverage metadata

??? note "Response fields (13 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `groupBy` | enum: `rule`, `decoder`, `agentName`, `type`, `severity` |  | Grouping dimension: rule ID, decoder name, stored agent name, event type or numeric severity. Rule and severity bucket keys are integers; the other dimensions return string keys. |
    | `data` | array of object |  |  |
    | `data.[].key` |  |  |  |
    | `data.[].count` | integer |  |  |
    | `totalEvents` | integer |  |  |
    | `totalGroups` | integer |  |  |
    | `missingEvents` | integer |  | Matching documents without a value for the grouped field |
    | `size` | integer |  |  |
    | `isExact` | boolean |  | Always true on success |
    | `truncated` | boolean |  | True when the requested top-N omits groups; returned counts remain exact |
    | `startDate` | string (date-time) |  |  |
    | `endDate` | string (date-time) |  |  |
    | `serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `502`, `503`, `504`, `500`.

### <span class="api-method api-get">GET</span> `/siem/event/{idEvent}` { #get-siem-event-idevent }

Get one authorized SIEM event

Search retained event indices on the selected node without the list's default date range.
Returns the same complete SiemEvent projection as the list, with literal log and dynamic fields.
Missing and non-visible IDs both return 404. Multiple visible documents with the same ID return 409.
Metaconsole requires serverId; node rejects it. No ITSM lookup or mutation is performed.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | string | yes | Opaque event ID, not necessarily UUID; URL-encode as one path segment |
| `serverId` | query | integer |  | Required on metaconsole, forbidden on node |

**Response 200**: Authorized SIEM event

??? note "Response fields (32 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idEvent` | string |  | Opaque OpenSearch document ID, not UUID |
    | `timestamp` | string (date-time) |  |  |
    | `description` | string |  | Literal text, not safe HTML |
    | `agentName` | string |  |  |
    | `idAgent` | integer, nullable |  |  |
    | `idAgentNode` | integer, nullable |  |  |
    | `level` | integer |  |  |
    | `severity` | integer |  |  |
    | `status` | enum: `0`, `1` |  |  |
    | `decoder` | array of string |  |  |
    | `idRule` | integer |  |  |
    | `rule` | string, nullable |  |  |
    | `type` | string |  |  |
    | `idGroup` | integer |  |  |
    | `groupName` | string, nullable |  |  |
    | `mitres` | array of object |  |  |
    | `mitres.[].id` | string |  |  |
    | `mitres.[].name` | string |  |  |
    | `mitres.[].url` | string |  |  |
    | `customFields` | object |  | Literal decoder fields; escape before HTML rendering |
    | `serverId` | integer, nullable |  |  |
    | `logText` | string, nullable |  | Literal event log content; escape before HTML rendering |
    | `sourceId` | string, nullable |  |  |
    | `programName` | string, nullable |  |  |
    | `utimestamp` | integer (int64), nullable |  |  |
    | `queueUtimestamp` | integer (int64), nullable |  |  |
    | `agentAlias` | string, nullable |  |  |
    | `siemGroups` | array of string |  | SIEM classification names, not authorization groups |
    | `idIncidences` | array of integer |  | Associated ticket IDs stored on the event; no ITSM lookup is performed |
    | `decoders` | array of object |  |  |
    | `decoders.[].idDecoder` | integer, nullable |  |  |
    | `decoders.[].name` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `409`, `502`, `503`, `504`, `500`.

### <span class="api-method api-get">GET</span> `/siem/event/list` { #get-siem-event-list }

List authorized SIEM events

Read-only, node-local or delegated to one explicit serverId. Last 24h by default.
Exact totals, zero-based pages, maximum window 10000. Not an immutable snapshot.
Unfiltered total uses the same interval and ACL, without optional resource filters.
Event text is literal, not safe HTML. Meta idAgent is cached; idAgentNode is the original ID.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `startDate` | query | string (date-time) |  | Paired UTC bounds; default last 24h |
| `endDate` | query | string (date-time) |  | Exclusive upper bound |
| `page` | query | integer |  |  |
| `sizePage` | query | integer |  |  |
| `sortField` | query | enum: `timestamp`, `description`, `agentName`, `level`, `severity`, `status`, `decoder`, `idRule`, `type`, `idGroup` |  |  |
| `sortDirection` | query | enum: `asc`, `desc` |  |  |
| `serverId` | query | integer |  | Required on metaconsole, forbidden on node |
| `level` | query | integer |  |  |
| `severity` | query | integer |  |  |
| `status` | query | enum: `0`, `1` |  |  |
| `idRule` | query | integer |  |  |
| `decoder` | query | string |  |  |
| `type` | query | string |  |  |
| `idGroup` | query | integer |  |  |
| `recursiveGroups` | query | boolean |  |  |
| `idAgent` | query | integer |  |  |
| `agentName` | query | string |  |  |
| `search` | query | string |  |  |
| `eventId` | query | string |  |  |
| `mitre[]` | query | array of string |  |  |
| `customFields` | query | object |  |  |

**Response 200**: Authorized SIEM events and exact counts

Schema: [`SiemEventList`](#model-siemeventlist)

Error responses: `400`, `401`, `403`, `404`, `502`, `503`, `504`, `500`.

### <span class="api-method api-post">POST</span> `/siem/event/list` { #post-siem-event-list }

List authorized SIEM events with object filters

Same filtering and response semantics as GET. Supply filters in the optional JSON object body.
On a metaconsole include serverId in that body. Omitted dates select the last 24 hours.

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `startDate` | string (date-time) |  | Internal validated OpenSearch criteria, not a SQL FilterAbstract. |
| `endDate` | string (date-time) |  |  |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `sortField` | enum: `timestamp`, `description`, `agentName`, `level`, `severity`, `status`, `decoder`, `idRule`, `type`, `idGroup` |  |  |
| `sortDirection` | enum: `asc`, `desc` |  |  |
| `serverId` | integer |  | Required only on metaconsole |
| `level` | integer |  |  |
| `severity` | integer |  |  |
| `status` | enum: `0`, `1` |  |  |
| `idRule` | integer |  |  |
| `decoder` | string |  |  |
| `type` | string |  |  |
| `idGroup` | integer |  |  |
| `recursiveGroups` | boolean |  |  |
| `idAgent` | integer |  | Cached agent ID on metaconsole |
| `agentName` | string |  |  |
| `search` | string |  |  |
| `eventId` | string |  |  |
| `mitre` | array of string |  |  |
| `customFields` | object |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "startDate": "string",
      "endDate": "string",
      "page": 0,
      "sizePage": 100,
      "sortField": "timestamp",
      "sortDirection": "asc",
      "serverId": 0,
      "level": 0,
      "severity": 0,
      "status": 0,
      "idRule": 0,
      "decoder": "string",
      "type": "string",
      "idGroup": 0,
      "recursiveGroups": false,
      "idAgent": 0,
      "agentName": "string",
      "search": "string",
      "eventId": "string",
      "mitre": [
        "string"
      ],
      "customFields": {}
    }
    ```

**Response 200**: Authorized SIEM events and exact counts

Schema: [`SiemEventList`](#model-siemeventlist)

Error responses: `400`, `401`, `403`, `404`, `502`, `503`, `504`, `500`.

## SiemLogs

Read authorized decoded SIEM logs from nodes

### <span class="api-method api-post">POST</span> `/siem/log/aggregate` { #post-siem-log-aggregate }

Count authorized decoded SIEM logs by one dimension

Exact top-N by count descending, string key ascending. Same filters, UTC date interval,
PM and AR visibility as listing. Last 24h by default. Supply one explicit serverId on metaconsole.
JSON body only; no pagination, projection, arbitrary dynamic dimensions or multi-node merge.
Decoder is multivalued: bucket counts can sum above totalLogs. Missing indexed values count separately.
At most 10000 distinct groups are supported. Incomplete bucket coverage returns 503, never approximate
success. truncated only indicates groups omitted by the requested top-N; returned counts remain exact.

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `groupBy` | enum: `decoder`, `agentName`, `type`, `programName` | yes |  |
| `size` | integer |  |  |
| `startDate` | string (date-time) |  | Validated non-SQL criteria; never accepts backend query DSL. |
| `endDate` | string (date-time) |  | Exclusive UTC upper bound |
| `serverId` | integer |  | Required on metaconsole; forbidden on a node |
| `decoder` | string |  | Exact decoder name |
| `type` | string |  | Exact keyword value |
| `programName` | string |  | Exact keyword value |
| `idAgent` | integer |  | Exact inventory identity, cached on metaconsole; combined with agentName as AND |
| `agentName` | string |  | Literal substring of the stored agent name, as in the SIEM Search viewer |
| `search` | string |  | Literal substring of indexed log_text; lines above index ignore_above cannot match |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "groupBy": "decoder",
      "size": 10,
      "startDate": "string",
      "endDate": "string",
      "serverId": 0,
      "decoder": "string",
      "type": "string",
      "programName": "string",
      "idAgent": 0,
      "agentName": "string",
      "search": "string"
    }
    ```

**Response 200**: Exact top-N and coverage metadata

??? note "Response fields (13 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `groupBy` | enum: `decoder`, `agentName`, `type`, `programName` |  | Grouping dimension: decoder, stored agent name, log type or program name. Keys are strings. |
    | `data` | array of object |  |  |
    | `data.[].key` | string |  |  |
    | `data.[].count` | integer |  |  |
    | `totalLogs` | integer |  |  |
    | `totalGroups` | integer |  |  |
    | `missingLogs` | integer |  | Matching documents without an indexed value for the grouped field |
    | `size` | integer |  |  |
    | `isExact` | boolean |  | Always true on success |
    | `truncated` | boolean |  | Requested top-N omits groups; returned counts remain exact |
    | `startDate` | string (date-time) |  |  |
    | `endDate` | string (date-time) |  |  |
    | `serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `502`, `503`, `504`, `500`.

### <span class="api-method api-get">GET</span> `/siem/log/{idLog}` { #get-siem-log-idlog }

Get one authorized decoded SIEM log

Requires PM and AR visibility. Searches retained decoded indices on one node without
the list default date range. Returns the same complete SiemLog representation as the list,
including literal content and all dynamic fields. Escape text before rendering HTML.
Missing, deleted and non-visible IDs all return 404. Multiple visible matches return 409.
Metaconsole requires serverId; a node rejects it. This operation does not mutate the log.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idLog` | path | string | yes | Opaque decoded document ID, not event ID; URL-encode one segment. Slash IDs are unsupported. |
| `serverId` | query | integer |  | Required on metaconsole; forbidden on a node |

**Response 200**: Authorized decoded SIEM log

??? note "Response fields (19 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idLog` | string |  | Opaque decoded document ID, not event ID |
    | `timestamp` | string (date-time) |  |  |
    | `logText` | string |  | Full literal content, not safe HTML. Legacy structured content is serialized as JSON text. |
    | `decoder` | array of string |  |  |
    | `type` | string, nullable |  |  |
    | `programName` | string, nullable |  |  |
    | `sourceId` | string, nullable |  |  |
    | `agentName` | string |  |  |
    | `idAgent` | integer, nullable |  |  |
    | `idAgentNode` | integer, nullable |  |  |
    | `agentAlias` | string, nullable |  |  |
    | `idGroup` | integer |  |  |
    | `groupName` | string, nullable |  |  |
    | `utimestamp` | integer, nullable |  |  |
    | `queueUtimestamp` | integer, nullable |  |  |
    | `processed` | integer, nullable |  |  |
    | `inProcess` | integer, nullable |  |  |
    | `customFields` | object |  | Dynamic decoder fields, optionally projected by fields. Escape values before HTML rendering. |
    | `serverId` | integer, nullable |  |  |


Error responses: `400`, `401`, `403`, `404`, `409`, `502`, `503`, `504`, `500`.

### <span class="api-method api-get">GET</span> `/siem/log/list` { #get-siem-log-list }

List authorized decoded SIEM logs

Requires PM and AR visibility. Decoded logs, not raw logs or SIEM events.
Last 24h by default; explicit dates must be paired. Interval [startDate,endDate), UTC.
Exact totals, zero-based pages, maximum result window 10000; not an immutable snapshot.
Unfiltered total uses the same interval and ACL without optional resource filters.
Full literal content is returned; indexed substring searches cannot match log_text above its
mapping ignore_above limit (8000 in the standard decoded mapping). Escape text before rendering HTML.
On metaconsole serverId selects one node; idAgent is cached and idAgentNode is the original ID.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `startDate` | query | string (date-time) |  | Validated non-SQL criteria; never accepts backend query DSL. |
| `endDate` | query | string (date-time) |  | Exclusive UTC upper bound |
| `page` | query | integer |  |  |
| `sizePage` | query | integer |  | Default siem_number_logs_viewed (50 when unset); accessible result window is 10000 |
| `order` | query | enum: `asc`, `desc` |  |  |
| `search` | query | string |  | Literal substring of indexed log_text; lines above index ignore_above cannot match |
| `decoder` | query | string |  | Exact decoder name |
| `type` | query | string |  | Exact keyword value |
| `programName` | query | string |  | Exact keyword value |
| `agentName` | query | string |  | Literal substring of the stored agent name, as in the SIEM Search viewer |
| `idAgent` | query | integer |  | Exact inventory identity, cached on metaconsole; combined with agentName as AND |
| `fields[]` | query | array of string |  | Optional dynamic-field projection. Omitted: all. Empty list: none. Fixed fields always remain. |
| `serverId` | query | integer |  | Required on metaconsole; forbidden on a node |

**Response 200**: Authorized decoded logs and exact counts

Schema: [`SiemLogList`](#model-siemloglist)

Error responses: `400`, `401`, `403`, `404`, `502`, `503`, `504`, `500`.

### <span class="api-method api-post">POST</span> `/siem/log/list` { #post-siem-log-list }

List authorized decoded SIEM logs with object filters

Same semantics and response as GET. Supply filters in the optional JSON object body.
Include serverId in that body on metaconsole. Omitted dates select the last 24 hours.

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `startDate` | string (date-time) |  | Validated non-SQL criteria; never accepts backend query DSL. |
| `endDate` | string (date-time) |  | Exclusive UTC upper bound |
| `page` | integer |  |  |
| `sizePage` | integer |  | Default siem_number_logs_viewed (50 when unset); accessible result window is 10000 |
| `order` | enum: `asc`, `desc` |  |  |
| `search` | string |  | Literal substring of indexed log_text; lines above index ignore_above cannot match |
| `decoder` | string |  | Exact decoder name |
| `type` | string |  | Exact keyword value |
| `programName` | string |  | Exact keyword value |
| `agentName` | string |  | Literal substring of the stored agent name, as in the SIEM Search viewer |
| `idAgent` | integer |  | Exact inventory identity, cached on metaconsole; combined with agentName as AND |
| `fields` | array of string |  | Optional dynamic-field projection. Omitted: all. Empty list: none. Fixed fields always remain. |
| `serverId` | integer |  | Required on metaconsole; forbidden on a node |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "startDate": "string",
      "endDate": "string",
      "page": 0,
      "sizePage": 0,
      "order": "asc",
      "search": "string",
      "decoder": "string",
      "type": "string",
      "programName": "string",
      "agentName": "string",
      "idAgent": 0,
      "fields": [
        "string"
      ],
      "serverId": 0
    }
    ```

**Response 200**: Authorized decoded logs and exact counts

Schema: [`SiemLogList`](#model-siemloglist)

Error responses: `400`, `401`, `403`, `404`, `502`, `503`, `504`, `500`.

## SecurityVulnerabilities

Read-only security vulnerabilities from nodes and metaconsole federation

### <span class="api-method api-get">GET</span> `/securityVulnerability/{idAgent}/{hash}/{utimestamp}` { #get-securityvulnerability-idagent-hash-utimestamp }

Get one security vulnerability

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `hash` | path | string | yes | Vulnerability hash |
| `utimestamp` | path | integer | yes | Scan timestamp |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Security vulnerability object

??? note "Response fields (6 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `hash` | string |  | Vulnerability identity hash |
    | `idAgente` | integer |  | Agent ID that owns the vulnerability |
    | `dataType` | enum: `vulnerabilities`, `ms-pending-kbs` |  | Vulnerability data source |
    | `data` | object, nullable |  | Vulnerability payload as stored in the console |
    | `utimestamp` | integer |  | Scan timestamp |
    | `serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/securityVulnerability/list` { #get-securityvulnerability-list }

List security vulnerabilities using query filters

Simple filters via query string; advanced filters and limit/offset via POST body.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `idAgente` | query | integer |  |  |
| `hash` | query | string |  |  |
| `dataType` | query | enum: `vulnerabilities`, `ms-pending-kbs` |  |  |
| `utimestamp` | query | integer |  |  |
| `freeSearch` | query | string |  |  |

**Response 200**: Security vulnerability list

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
    | `data.[].hash` | string |  | Vulnerability identity hash |
    | `data.[].idAgente` | integer |  | Agent ID that owns the vulnerability |
    | `data.[].dataType` | enum: `vulnerabilities`, `ms-pending-kbs` |  | Vulnerability data source |
    | `data.[].data` | object, nullable |  | Vulnerability payload as stored in the console |
    | `data.[].utimestamp` | integer |  | Scan timestamp |
    | `data.[].serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/securityVulnerability/list` { #post-securityvulnerability-list }

List security vulnerabilities

Body filters override the same simple query filters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `idAgente` | query | integer |  |  |
| `hash` | query | string |  |  |
| `dataType` | query | enum: `vulnerabilities`, `ms-pending-kbs` |  |  |
| `utimestamp` | query | integer |  |  |
| `freeSearch` | query | string |  |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `hash` | string |  | Vulnerability identity hash |
| `idAgente` | integer |  | Agent ID that owns the vulnerability |
| `dataType` | enum: `vulnerabilities`, `ms-pending-kbs` |  | Vulnerability data source |
| `data` | object, nullable |  | Vulnerability payload as stored in the console |
| `utimestamp` | integer |  | Scan timestamp |
| `serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |
| `serverId` | integer, nullable |  | Node identifier. Required when reading from a metaconsole |
| `freeSearch` | string, nullable |  | Find a word in the vulnerability payload or hash. |
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
| `multipleSearch.field` | enum: `hash`, `idAgente`, `dataType`, `data`, `utimestamp` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `hash`, `idAgente`, `dataType`, `data`, `utimestamp` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "serverId": 0,
      "freeSearch": "string",
      "requestedFields": [
        "hash"
      ],
      "fieldConditions": [
        {
          "field": "hash",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "hash",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "hash",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Security vulnerability list

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
    | `data.[].hash` | string |  | Vulnerability identity hash |
    | `data.[].idAgente` | integer |  | Agent ID that owns the vulnerability |
    | `data.[].dataType` | enum: `vulnerabilities`, `ms-pending-kbs` |  | Vulnerability data source |
    | `data.[].data` | object, nullable |  | Vulnerability payload as stored in the console |
    | `data.[].utimestamp` | integer |  | Scan timestamp |
    | `data.[].serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |


Error responses: `400`, `401`, `403`, `404`, `500`.

## WindowsPatches

Read-only installed Windows patches from nodes and metaconsole federation

### <span class="api-method api-get">GET</span> `/windowsPatch/{idAgent}/{kb}/{utimestamp}` { #get-windowspatch-idagent-kb-utimestamp }

Get one installed Windows patch

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgent` | path | integer | yes | Agent id |
| `kb` | path | string | yes | Windows patch identifier |
| `utimestamp` | path | integer | yes | Scan timestamp |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Windows patch object

??? note "Response fields (5 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `kb` | string |  | Installed Windows patch identifier |
    | `idAgente` | integer |  | Agent ID that owns the patch |
    | `utimestamp` | integer |  | Scan timestamp |
    | `description` | string, nullable |  | Patch description |
    | `serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/windowsPatch/list` { #get-windowspatch-list }

List installed Windows patches using query filters

Simple filters via query string; advanced filters and limit/offset via POST body.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `idAgente` | query | integer |  |  |
| `kb` | query | string |  |  |
| `utimestamp` | query | integer |  |  |
| `description` | query | string |  |  |
| `freeSearch` | query | string |  |  |

**Response 200**: Installed Windows patch list

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
    | `data.[].kb` | string |  | Installed Windows patch identifier |
    | `data.[].idAgente` | integer |  | Agent ID that owns the patch |
    | `data.[].utimestamp` | integer |  | Scan timestamp |
    | `data.[].description` | string, nullable |  | Patch description |
    | `data.[].serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/windowsPatch/list` { #post-windowspatch-list }

List installed Windows patches

Body filters override the same simple query filters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `idAgente` | query | integer |  |  |
| `kb` | query | string |  |  |
| `utimestamp` | query | integer |  |  |
| `description` | query | string |  |  |
| `freeSearch` | query | string |  |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `kb` | string |  | Installed Windows patch identifier |
| `idAgente` | integer |  | Agent ID that owns the patch |
| `utimestamp` | integer |  | Scan timestamp |
| `description` | string, nullable |  | Patch description |
| `serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |
| `serverId` | integer, nullable |  | Node identifier. Required when reading from a metaconsole |
| `freeSearch` | string, nullable |  | Find a word in the patch identifier or description. |
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
| `multipleSearch.field` | enum: `kb`, `idAgente`, `utimestamp`, `description` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `kb`, `idAgente`, `utimestamp`, `description` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "serverId": 0,
      "freeSearch": "string",
      "requestedFields": [
        "kb"
      ],
      "fieldConditions": [
        {
          "field": "kb",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "kb",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "kb",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Installed Windows patch list

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
    | `data.[].kb` | string |  | Installed Windows patch identifier |
    | `data.[].idAgente` | integer |  | Agent ID that owns the patch |
    | `data.[].utimestamp` | integer |  | Scan timestamp |
    | `data.[].description` | string, nullable |  | Patch description |
    | `data.[].serverId` | integer, nullable |  | Node identifier for records returned through a metaconsole |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: Rule { #model-rule }

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | integer |  | Rule ID |
| `idServer` | integer, nullable |  | Server ID for the rule |
| `description` | string |  | Rule description |
| `level` | integer, nullable |  | Rule level |
| `overwrite` | string, nullable |  | Overwrite flag |
| `decodedAs` | string, nullable |  | Decoded as value |
| `category` | string, nullable |  | Rule category |
| `programName` | string, nullable |  | Program name |
| `match` | array, nullable |  | Match patterns |
| `field` | array, nullable |  | Field patterns |
| `frequency` | integer, nullable |  | Rule frequency |
| `timeframe` | integer, nullable |  | Rule timeframe |
| `ignore` | integer, nullable |  | Ignore flag |
| `ifMatchedSid` | integer, nullable |  | If matched SID |
| `ifMatchedGroup` | string, nullable |  | If matched group |
| `ifSid` | array, nullable |  | If SID array |
| `ifGroup` | string, nullable |  | If group |
| `ifLevel` | integer, nullable |  | If level |
| `sameId` | integer, nullable |  | Same ID flag |
| `differentId` | integer, nullable |  | Different ID flag |
| `sameField` | array, nullable |  | Same field patterns |
| `differentField` | array, nullable |  | Different field patterns |
| `serverManaged` | boolean, nullable |  | Server managed flag |
| `enabled` | boolean, nullable |  | Enabled flag |
| `active` | boolean, nullable |  | Active flag |
| `maxsize` | integer, nullable |  | Maximum log size |
| `noalert` | integer, nullable |  | No alert flag |
| `timeFrom` | string, nullable |  | Time from |
| `timeTo` | string, nullable |  | Time to |
| `weekdate` | string, nullable |  | Week date |
| `ifFts` | integer, nullable |  | If FTS flag |
| `info` | string, nullable |  | Info text |
| `infoType` | string, nullable |  | Info type |
| `dynamicField` | array, nullable |  | Dynamic fields array |
| `mitre` | array, nullable |  | MITRE IDs |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "id": 0,
      "idServer": 0,
      "description": "Rule created by API",
      "level": 0,
      "overwrite": "string",
      "decodedAs": "string",
      "category": "string",
      "programName": "string",
      "match": [
        "string"
      ],
      "field": [
        "string"
      ],
      "frequency": 0,
      "timeframe": 0,
      "ignore": 0,
      "ifMatchedSid": 0,
      "ifMatchedGroup": "string",
      "ifSid": [
        0
      ],
      "ifGroup": "string",
      "ifLevel": 0,
      "sameId": 0,
      "differentId": 0,
      "sameField": [
        "string"
      ],
      "differentField": [
        "string"
      ],
      "enabled": true,
      "active": true,
      "maxsize": 0,
      "noalert": 0,
      "timeFrom": "string",
      "timeTo": "string",
      "weekdate": "string",
      "ifFts": 0,
      "info": "string",
      "infoType": "string",
      "dynamicField": [
        "string"
      ],
      "mitre": [
        "string"
      ]
    }
    ```

### Model: SiemEventList { #model-siemeventlist }

??? note "Fields (45 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `data` | array of object |  |  |
    | `data.[].idEvent` | string |  | Opaque OpenSearch document ID, not UUID |
    | `data.[].timestamp` | string (date-time) |  |  |
    | `data.[].description` | string |  | Literal text, not safe HTML |
    | `data.[].agentName` | string |  |  |
    | `data.[].idAgent` | integer, nullable |  |  |
    | `data.[].idAgentNode` | integer, nullable |  |  |
    | `data.[].level` | integer |  |  |
    | `data.[].severity` | integer |  |  |
    | `data.[].status` | enum: `0`, `1` |  |  |
    | `data.[].decoder` | array of string |  |  |
    | `data.[].idRule` | integer |  |  |
    | `data.[].rule` | string, nullable |  |  |
    | `data.[].type` | string |  |  |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].groupName` | string, nullable |  |  |
    | `data.[].mitres` | array of object |  |  |
    | `data.[].mitres.[].id` | string |  |  |
    | `data.[].mitres.[].name` | string |  |  |
    | `data.[].mitres.[].url` | string |  |  |
    | `data.[].customFields` | object |  | Literal decoder fields; escape before HTML rendering |
    | `data.[].serverId` | integer, nullable |  |  |
    | `data.[].logText` | string, nullable |  | Literal event log content; escape before HTML rendering |
    | `data.[].sourceId` | string, nullable |  |  |
    | `data.[].programName` | string, nullable |  |  |
    | `data.[].utimestamp` | integer (int64), nullable |  |  |
    | `data.[].queueUtimestamp` | integer (int64), nullable |  |  |
    | `data.[].agentAlias` | string, nullable |  |  |
    | `data.[].siemGroups` | array of string |  | SIEM classification names, not authorization groups |
    | `data.[].idIncidences` | array of integer |  | Associated ticket IDs stored on the event; no ITSM lookup is performed |
    | `data.[].decoders` | array of object |  |  |
    | `data.[].decoders.[].idDecoder` | integer, nullable |  |  |
    | `data.[].decoders.[].name` | string |  |  |
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `startDate` | string (date-time) |  |  |
    | `endDate` | string (date-time) |  |  |
    | `serverId` | integer, nullable |  |  |


### Model: SiemGroup { #model-siemgroup }

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | integer, nullable |  | Group ID |
| `name` | string |  | Group name |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string"
    }
    ```

### Model: SiemGroupFilter { #model-siemgroupfilter }

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | integer, nullable |  | Group ID |
| `name` | string |  | Group name |
| `id` |  |  |  |
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
      "id": null,
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

### Model: SiemLogList { #model-siemloglist }

??? note "Fields (32 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `data` | array of object |  |  |
    | `data.[].idLog` | string |  | Opaque decoded document ID, not event ID |
    | `data.[].timestamp` | string (date-time) |  |  |
    | `data.[].logText` | string |  | Full literal content, not safe HTML. Legacy structured content is serialized as JSON text. |
    | `data.[].decoder` | array of string |  |  |
    | `data.[].type` | string, nullable |  |  |
    | `data.[].programName` | string, nullable |  |  |
    | `data.[].sourceId` | string, nullable |  |  |
    | `data.[].agentName` | string |  |  |
    | `data.[].idAgent` | integer, nullable |  |  |
    | `data.[].idAgentNode` | integer, nullable |  |  |
    | `data.[].agentAlias` | string, nullable |  |  |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].groupName` | string, nullable |  |  |
    | `data.[].utimestamp` | integer, nullable |  |  |
    | `data.[].queueUtimestamp` | integer, nullable |  |  |
    | `data.[].processed` | integer, nullable |  |  |
    | `data.[].inProcess` | integer, nullable |  |  |
    | `data.[].customFields` | object |  | Dynamic decoder fields, optionally projected by fields. Escape values before HTML rendering. |
    | `data.[].serverId` | integer, nullable |  |  |
    | `paginationData` | object |  | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `startDate` | string (date-time) |  |  |
    | `endDate` | string (date-time) |  |  |
    | `serverId` | integer, nullable |  |  |
