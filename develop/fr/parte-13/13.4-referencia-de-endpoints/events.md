# Events

Events, comments, filters, tags and lifetime, and event alerts with their rules and actions.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-post">POST</span> | [`/event`](#post-event) | Creates a new events |
| <span class="api-method api-post">POST</span> | [`/events`](#post-events) | Creates a multiple new events |
| <span class="api-method api-get">GET</span> | [`/event/{idEvent}`](#get-event-idevent) | Show event |
| <span class="api-method api-put">PUT</span> | [`/event/{idEvent}`](#put-event-idevent) | Updates an event |
| <span class="api-method api-delete">DELETE</span> | [`/event/{idEvent}`](#delete-event-idevent) | Deletes an event object. |
| <span class="api-method api-get">GET</span> | [`/event/summary`](#get-event-summary) | Event counters grouped by severity and status |
| <span class="api-method api-get">GET</span> | [`/event/list`](#get-event-list) | List events |
| <span class="api-method api-post">POST</span> | [`/event/list`](#post-event-list) | List events |
| <span class="api-method api-post">POST</span> | [`/event/{idEvent}/comment`](#post-event-idevent-comment) | Creates a new field into events comments |
| <span class="api-method api-get">GET</span> | [`/event/{idEvent}/comment/{idComment}`](#get-event-idevent-comment-idcomment) | show field events comments |
| <span class="api-method api-put">PUT</span> | [`/event/{idEvent}/comment/{idComment}`](#put-event-idevent-comment-idcomment) | Updates an event comment |
| <span class="api-method api-delete">DELETE</span> | [`/event/{idEvent}/comment/{idComment}`](#delete-event-idevent-comment-idcomment) | Deletes an event comment |
| <span class="api-method api-get">GET</span> | [`/event/{idEvent}/comment/list`](#get-event-idevent-comment-list) | List comments event |
| <span class="api-method api-post">POST</span> | [`/event/{idEvent}/comment/list`](#post-event-idevent-comment-list) | List comments event |
| <span class="api-method api-post">POST</span> | [`/event/filter`](#post-event-filter) | Creates a new event filter |
| <span class="api-method api-get">GET</span> | [`/event/filter/{idEventFilter}`](#get-event-filter-ideventfilter) | Show eventFilter |
| <span class="api-method api-put">PUT</span> | [`/event/filter/{idEventFilter}`](#put-event-filter-ideventfilter) | Updates an eventFilter |
| <span class="api-method api-delete">DELETE</span> | [`/event/filter/{idEventFilter}`](#delete-event-filter-ideventfilter) | Deletes an eventFilter object. |
| <span class="api-method api-get">GET</span> | [`/event/filter/list`](#get-event-filter-list) | List event filter |
| <span class="api-method api-post">POST</span> | [`/event/filter/list`](#post-event-filter-list) | List event filter |
| <span class="api-method api-post">POST</span> | [`/event/eventTag`](#post-event-eventtag) | Creates a new event tag |
| <span class="api-method api-get">GET</span> | [`/event/eventTag/{idEventTag}`](#get-event-eventtag-ideventtag) | Show event tag |
| <span class="api-method api-put">PUT</span> | [`/event/eventTag/{idEventTag}`](#put-event-eventtag-ideventtag) | Updates an event tag |
| <span class="api-method api-delete">DELETE</span> | [`/event/eventTag/{idEventTag}`](#delete-event-eventtag-ideventtag) | Deletes an event tag object. |
| <span class="api-method api-get">GET</span> | [`/event/eventTag/list`](#get-event-eventtag-list) | List event tags |
| <span class="api-method api-post">POST</span> | [`/event/eventTag/list`](#post-event-eventtag-list) | List event tags |
| <span class="api-method api-post">POST</span> | [`/event/{idEvent}/tag/{idEventTag}`](#post-event-idevent-tag-ideventtag) | Assign an event tag to an event |
| <span class="api-method api-get">GET</span> | [`/event/{idEvent}/tag/{idEventTagRelation}`](#get-event-idevent-tag-ideventtagrelation) | Show event tag relation |
| <span class="api-method api-delete">DELETE</span> | [`/event/{idEvent}/tag/{idEventTagRelation}`](#delete-event-idevent-tag-ideventtagrelation) | Remove an event tag relation from an event |
| <span class="api-method api-get">GET</span> | [`/event/{idEvent}/tag/list`](#get-event-idevent-tag-list) | List event tag relations of an event |
| <span class="api-method api-post">POST</span> | [`/event/{idEvent}/tag/list`](#post-event-idevent-tag-list) | List event tag relations of an event |
| <span class="api-method api-get">GET</span> | [`/event/{idEvent}/lifetime/{idLifetime}`](#get-event-idevent-lifetime-idlifetime) | Get a single event lifetime status entry |
| <span class="api-method api-get">GET</span> | [`/event/{idEvent}/lifetime/list`](#get-event-idevent-lifetime-list) | List the lifecycle status history of an event |
| <span class="api-method api-post">POST</span> | [`/event/{idEvent}/lifetime/list`](#post-event-idevent-lifetime-list) | List the lifecycle status history of an event |
| <span class="api-method api-post">POST</span> | [`/alert/event`](#post-alert-event) | createEventAlert |
| <span class="api-method api-get">GET</span> | [`/alert/event/{idEventAlert}`](#get-alert-event-ideventalert) | getEventAlert |
| <span class="api-method api-put">PUT</span> | [`/alert/event/{idEventAlert}`](#put-alert-event-ideventalert) | updateEventAlert |
| <span class="api-method api-delete">DELETE</span> | [`/alert/event/{idEventAlert}`](#delete-alert-event-ideventalert) | deleteEventAlert |
| <span class="api-method api-get">GET</span> | [`/alert/event/list`](#get-alert-event-list) | listEventAlertsByQuery |
| <span class="api-method api-post">POST</span> | [`/alert/event/list`](#post-alert-event-list) | listEventAlerts |
| <span class="api-method api-post">POST</span> | [`/alert/event/{idEventAlert}/rule`](#post-alert-event-ideventalert-rule) | Associate an action with an event alert |
| <span class="api-method api-get">GET</span> | [`/alert/event/{idEventAlert}/rule/{idEventRule}`](#get-alert-event-ideventalert-rule-ideventrule) | Get an event alert rule |
| <span class="api-method api-put">PUT</span> | [`/alert/event/{idEventAlert}/rule/{idEventRule}`](#put-alert-event-ideventalert-rule-ideventrule) | Update an event alert rule |
| <span class="api-method api-delete">DELETE</span> | [`/alert/event/{idEventAlert}/rule/{idEventRule}`](#delete-alert-event-ideventalert-rule-ideventrule) | Delete an event alert rule |
| <span class="api-method api-get">GET</span> | [`/alert/event/{idEventAlert}/rule/list`](#get-alert-event-ideventalert-rule-list) | List actions associated with an event alert |
| <span class="api-method api-post">POST</span> | [`/alert/event/{idEventAlert}/rule/list`](#post-alert-event-ideventalert-rule-list) | List actions associated with an event alert |
| <span class="api-method api-post">POST</span> | [`/alert/event/{idEventAlert}/action`](#post-alert-event-ideventalert-action) | Associate an action with an event alert |
| <span class="api-method api-get">GET</span> | [`/alert/event/{idEventAlert}/action/{idEventAlertAction}`](#get-alert-event-ideventalert-action-ideventalertaction) | Get an event alert action |
| <span class="api-method api-put">PUT</span> | [`/alert/event/{idEventAlert}/action/{idEventAlertAction}`](#put-alert-event-ideventalert-action-ideventalertaction) | Update an event alert action |
| <span class="api-method api-delete">DELETE</span> | [`/alert/event/{idEventAlert}/action/{idEventAlertAction}`](#delete-alert-event-ideventalert-action-ideventalertaction) | Delete an event alert action |
| <span class="api-method api-get">GET</span> | [`/alert/event/{idEventAlert}/action/list`](#get-alert-event-ideventalert-action-list) | List actions associated with an event alert |
| <span class="api-method api-post">POST</span> | [`/alert/event/{idEventAlert}/action/list`](#post-alert-event-ideventalert-action-list) | List actions associated with an event alert |

## Events

API Endpoints of events

### <span class="api-method api-post">POST</span> `/event` { #post-event }

Creates a new events

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`EventCreate`](#model-eventcreate)

**Response 200**: Event object

Schema: [`FederatedEvent`](#model-federatedevent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/events` { #post-events }

Creates a multiple new events

Creates events only in the console receiving the request. This operation cannot target a remote node.

**Request body** (`application/json`): list of [`EventCreate`](#model-eventcreate)

**Response 200**: Array of Event objects

??? note "Response fields (25 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `[].idEvent` | integer |  | Id event |
    | `[].idAgent` | integer, nullable |  | Id agent |
    | `[].idUser` | string, nullable |  | Id user |
    | `[].idGroup` | integer, nullable |  | Id group |
    | `[].status` | enum: `new`, `validated`, `inprocess` |  | Event status, the available status are: new, validated, inprocess |
    | `[].timestamp` | string, nullable |  | Event registration date |
    | `[].event` | string |  | Description event |
    | `[].utimestamp` | integer, nullable |  | Event registration date |
    | `[].eventType` | enum: `going_unknown`, `unknown`, `alert_fired`, `alert_recovered`, `alert_ceased`, `alert_manual_validation`, `recon_host_detected`, `system`, `error`, `new_agent`, `going_up_critical`, `going_down_critical`, `going_up_warning`, `going_down_warning`, `going_up_normal`, `going_down_normal`, `configuration_change`, `ncm` |  | Event status, the available status are: going_unknown, unknown, alert_fired, alert_recovered, alert_ceased, alert_manual_validation, recon_host_detected, system, error, new_agent, going_up_critical, going_down_critical, going_up_warning, going_down_warning, going_up_normal, going_down_normal, configuration_change, ncm |
    | `[].idAgentModule` | integer, nullable |  | Id agent module |
    | `[].idAlertAm` | integer, nullable |  | Id alert action |
    | `[].severity` | enum: `maintenance`, `informational`, `normal`, `warning`, `critical`, `minor`, `major` |  | Event severity, the available severity are: maintenance, informational, normal, warning, critical, minor, major |
    | `[].tags` | string, nullable |  | Tags |
    | `[].source` | string, nullable |  | Source |
    | `[].idExtra` | string, nullable |  | Extra id |
    | `[].criticalInstructions` | string, nullable |  | Critical instructions |
    | `[].warningInstructions` | string, nullable |  | Warning instructions |
    | `[].unknownInstructions` | string, nullable |  | Unknows instructions |
    | `[].defaultInstructions` | string, nullable |  | Default instructions, will be use when Critical/Warning/Unknown are empty |
    | `[].ownerUser` | string, nullable |  | Id user |
    | `[].ackUtimestamp` | integer, nullable |  | Event ack utimestamp |
    | `[].customData` | string, nullable |  | Custom data |
    | `[].data` | string, nullable |  | Data |
    | `[].moduleStatus` | integer, nullable |  | Module status |
    | `[].eventCustomId` | string, nullable |  | Events Custom Id |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/event/{idEvent}` { #get-event-idevent }

Show event

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Event object

Schema: [`FederatedEvent`](#model-federatedevent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/event/{idEvent}` { #put-event-idevent }

Updates an event

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idEvent` | integer |  | Id event |
| `idAgent` | integer, nullable |  | Id agent |
| `idUser` | string, nullable |  | Id user |
| `idGroup` | integer, nullable |  | Id group |
| `status` | enum: `new`, `validated`, `inprocess` |  | Event status, the available status are: new, validated, inprocess |
| `timestamp` | string, nullable |  | Event registration date |
| `event` | string |  | Description event |
| `utimestamp` | integer, nullable |  | Event registration date |
| `eventType` | enum: `going_unknown`, `unknown`, `alert_fired`, `alert_recovered`, `alert_ceased`, `alert_manual_validation`, `recon_host_detected`, `system`, `error`, `new_agent`, `going_up_critical`, `going_down_critical`, `going_up_warning`, `going_down_warning`, `going_up_normal`, `going_down_normal`, `configuration_change`, `ncm` |  | Event status, the available status are: going_unknown, unknown, alert_fired, alert_recovered, alert_ceased, alert_manual_validation, recon_host_detected, system, error, new_agent, going_up_critical, going_down_critical, going_up_warning, going_down_warning, going_up_normal, going_down_normal, configuration_change, ncm |
| `idAgentModule` | integer, nullable |  | Id agent module |
| `idAlertAm` | integer, nullable |  | Id alert action |
| `severity` | enum: `maintenance`, `informational`, `normal`, `warning`, `critical`, `minor`, `major` |  | Event severity, the available severity are: maintenance, informational, normal, warning, critical, minor, major |
| `tags` | string, nullable |  | Tags |
| `source` | string, nullable |  | Source |
| `idExtra` | string, nullable |  | Extra id |
| `criticalInstructions` | string, nullable |  | Critical instructions |
| `warningInstructions` | string, nullable |  | Warning instructions |
| `unknownInstructions` | string, nullable |  | Unknows instructions |
| `defaultInstructions` | string, nullable |  | Default instructions, will be use when Critical/Warning/Unknown are empty |
| `ownerUser` | string, nullable |  | Id user |
| `ackUtimestamp` | integer, nullable |  | Event ack utimestamp |
| `customData` | string, nullable |  | Custom data |
| `data` | string, nullable |  | Data |
| `moduleStatus` | integer, nullable |  | Module status |
| `eventCustomId` | string, nullable |  | Events Custom Id |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "status": "new",
      "ownerUser": "string",
      "eventCustomId": "string"
    }
    ```

**Response 200**: Event object

Schema: [`FederatedEvent`](#model-federatedevent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/event/{idEvent}` { #delete-event-idevent }

Deletes an event object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/event/summary` { #get-event-summary }

Event counters grouped by severity and status

Returns event counters for the requested date range. Defaults to the last 8 hours. In a metaconsole, serverId travels in the EventFilter body as an array of node ids, exactly as in /event/list.

**Request body** (`application/json`): [`EventFilter`](#model-eventfilter)

**Response 200**: Event summary

??? note "Response fields (3 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `total` | integer |  |  |
    | `bySeverity` | object |  |  |
    | `byStatus` | object |  |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-get">GET</span> `/event/list` { #get-event-list }

List events

Uses the event-specific filter contract. fieldConditions, requestedFields, and multipleSearchString are not supported. Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Events Object

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
    | `data.[].idEvent` | integer |  | Id event |
    | `data.[].idAgent` | integer, nullable |  | Id agent |
    | `data.[].idUser` | string, nullable |  | Id user |
    | `data.[].idGroup` | integer, nullable |  | Id group |
    | `data.[].status` | enum: `new`, `validated`, `inprocess` |  | Event status, the available status are: new, validated, inprocess |
    | `data.[].timestamp` | string, nullable |  | Event registration date |
    | `data.[].event` | string |  | Description event |
    | `data.[].utimestamp` | integer, nullable |  | Event registration date |
    | `data.[].eventType` | enum: `going_unknown`, `unknown`, `alert_fired`, `alert_recovered`, `alert_ceased`, `alert_manual_validation`, `recon_host_detected`, `system`, `error`, `new_agent`, `going_up_critical`, `going_down_critical`, `going_up_warning`, `going_down_warning`, `going_up_normal`, `going_down_normal`, `configuration_change`, `ncm` |  | Event status, the available status are: going_unknown, unknown, alert_fired, alert_recovered, alert_ceased, alert_manual_validation, recon_host_detected, system, error, new_agent, going_up_critical, going_down_critical, going_up_warning, going_down_warning, going_up_normal, going_down_normal, configuration_change, ncm |
    | `data.[].idAgentModule` | integer, nullable |  | Id agent module |
    | `data.[].idAlertAm` | integer, nullable |  | Id alert action |
    | `data.[].severity` | enum: `maintenance`, `informational`, `normal`, `warning`, `critical`, `minor`, `major` |  | Event severity, the available severity are: maintenance, informational, normal, warning, critical, minor, major |
    | `data.[].tags` | string, nullable |  | Tags |
    | `data.[].source` | string, nullable |  | Source |
    | `data.[].idExtra` | string, nullable |  | Extra id |
    | `data.[].criticalInstructions` | string, nullable |  | Critical instructions |
    | `data.[].warningInstructions` | string, nullable |  | Warning instructions |
    | `data.[].unknownInstructions` | string, nullable |  | Unknows instructions |
    | `data.[].defaultInstructions` | string, nullable |  | Default instructions, will be use when Critical/Warning/Unknown are empty |
    | `data.[].ownerUser` | string, nullable |  | Id user |
    | `data.[].ackUtimestamp` | integer, nullable |  | Event ack utimestamp |
    | `data.[].customData` | string, nullable |  | Custom data |
    | `data.[].data` | string, nullable |  | Data |
    | `data.[].moduleStatus` | integer, nullable |  | Module status |
    | `data.[].eventCustomId` | string, nullable |  | Events Custom Id |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/event/list` { #post-event-list }

List events

Uses the event-specific filter contract. fieldConditions, requestedFields, and multipleSearchString are not supported.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`): [`EventFilter`](#model-eventfilter)

**Response 200**: List Events Object

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
    | `data.[].idEvent` | integer |  | Id event |
    | `data.[].idAgent` | integer, nullable |  | Id agent |
    | `data.[].idUser` | string, nullable |  | Id user |
    | `data.[].idGroup` | integer, nullable |  | Id group |
    | `data.[].status` | enum: `new`, `validated`, `inprocess` |  | Event status, the available status are: new, validated, inprocess |
    | `data.[].timestamp` | string, nullable |  | Event registration date |
    | `data.[].event` | string |  | Description event |
    | `data.[].utimestamp` | integer, nullable |  | Event registration date |
    | `data.[].eventType` | enum: `going_unknown`, `unknown`, `alert_fired`, `alert_recovered`, `alert_ceased`, `alert_manual_validation`, `recon_host_detected`, `system`, `error`, `new_agent`, `going_up_critical`, `going_down_critical`, `going_up_warning`, `going_down_warning`, `going_up_normal`, `going_down_normal`, `configuration_change`, `ncm` |  | Event status, the available status are: going_unknown, unknown, alert_fired, alert_recovered, alert_ceased, alert_manual_validation, recon_host_detected, system, error, new_agent, going_up_critical, going_down_critical, going_up_warning, going_down_warning, going_up_normal, going_down_normal, configuration_change, ncm |
    | `data.[].idAgentModule` | integer, nullable |  | Id agent module |
    | `data.[].idAlertAm` | integer, nullable |  | Id alert action |
    | `data.[].severity` | enum: `maintenance`, `informational`, `normal`, `warning`, `critical`, `minor`, `major` |  | Event severity, the available severity are: maintenance, informational, normal, warning, critical, minor, major |
    | `data.[].tags` | string, nullable |  | Tags |
    | `data.[].source` | string, nullable |  | Source |
    | `data.[].idExtra` | string, nullable |  | Extra id |
    | `data.[].criticalInstructions` | string, nullable |  | Critical instructions |
    | `data.[].warningInstructions` | string, nullable |  | Warning instructions |
    | `data.[].unknownInstructions` | string, nullable |  | Unknows instructions |
    | `data.[].defaultInstructions` | string, nullable |  | Default instructions, will be use when Critical/Warning/Unknown are empty |
    | `data.[].ownerUser` | string, nullable |  | Id user |
    | `data.[].ackUtimestamp` | integer, nullable |  | Event ack utimestamp |
    | `data.[].customData` | string, nullable |  | Custom data |
    | `data.[].data` | string, nullable |  | Data |
    | `data.[].moduleStatus` | integer, nullable |  | Module status |
    | `data.[].eventCustomId` | string, nullable |  | Events Custom Id |


Error responses: `400`, `401`, `403`, `404`, `500`.

## EventComments

API Endpoints for event comments

### <span class="api-method api-post">POST</span> `/event/{idEvent}/comment` { #post-event-idevent-comment }

Creates a new field into events comments

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`EventComment`](#model-eventcomment)

**Response 200**: Event comment object

Schema: [`FederatedEventComment`](#model-federatedeventcomment)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/event/{idEvent}/comment/{idComment}` { #get-event-idevent-comment-idcomment }

show field events comments

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `idComment` | path | integer | yes | Event comment id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Event comment object

Schema: [`FederatedEventComment`](#model-federatedeventcomment)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/event/{idEvent}/comment/{idComment}` { #put-event-idevent-comment-idcomment }

Updates an event comment

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `idComment` | path | integer | yes | Event comment id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`EventComment`](#model-eventcomment)

**Response 200**: Event comment object

Schema: [`FederatedEventComment`](#model-federatedeventcomment)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/event/{idEvent}/comment/{idComment}` { #delete-event-idevent-comment-idcomment }

Deletes an event comment

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `idComment` | path | integer | yes | Event comment id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/event/{idEvent}/comment/list` { #get-event-idevent-comment-list }

List comments event

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Comments event object

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
    | `data` | array of FederatedEventComment |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idEventComment` | integer |  | id event comment |
    | `data.[].idEvent` | integer |  | id event comment |
    | `data.[].utimestamp` | integer, nullable |  | Event comment utimestamp create |
    | `data.[].comment` | string |  | content of the comment |
    | `data.[].idUser` | string |  | User id create comment |
    | `data.[].action` | string |  | content of the action |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/event/{idEvent}/comment/list` { #post-event-idevent-comment-list }

List comments event

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventComment` | integer |  | id event comment |
| `idEvent` | integer |  | id event comment |
| `utimestamp` | integer, nullable |  | Event comment utimestamp create |
| `comment` | string |  | content of the comment |
| `idUser` | string |  | User id create comment |
| `action` | string |  | content of the action |
| `idEventComment` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in label fields. |
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
| `multipleSearch.field` | enum: `idEventComment`, `idEvent`, `idUser`, `utimestamp`, `comment`, `action` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idEventComment`, `idEvent`, `idUser`, `utimestamp`, `comment`, `action` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "comment": "string",
      "idEventComment": null,
      "freeSearch": "string",
      "requestedFields": [
        "idEventComment"
      ],
      "fieldConditions": [
        {
          "field": "idEventComment",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idEventComment",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idEventComment",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List Comments event object

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
    | `data` | array of FederatedEventComment |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idEventComment` | integer |  | id event comment |
    | `data.[].idEvent` | integer |  | id event comment |
    | `data.[].utimestamp` | integer, nullable |  | Event comment utimestamp create |
    | `data.[].comment` | string |  | content of the comment |
    | `data.[].idUser` | string |  | User id create comment |
    | `data.[].action` | string |  | content of the action |


Error responses: `400`, `401`, `403`, `500`.

## EventFilters

API Endpoints for event filters

### <span class="api-method api-post">POST</span> `/event/filter` { #post-event-filter }

Creates a new event filter

**Request body** (`application/json`): [`EventFilter`](#model-eventfilter)

**Response 200**: EventFilter object

Schema: [`EventFilter`](#model-eventfilter)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/event/filter/{idEventFilter}` { #get-event-filter-ideventfilter }

Show eventFilter

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventFilter` | path | integer | yes | EventFilter id |

**Response 200**: EventFilter object

Schema: [`EventFilter`](#model-eventfilter)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/event/filter/{idEventFilter}` { #put-event-filter-ideventfilter }

Updates an eventFilter

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventFilter` | path | integer | yes | EventFilter id |

**Request body** (`application/json`): [`EventFilter`](#model-eventfilter)

**Response 200**: EventFilter object

Schema: [`EventFilter`](#model-eventfilter)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/event/filter/{idEventFilter}` { #delete-event-filter-ideventfilter }

Deletes an eventFilter object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventFilter` | path | integer | yes | EventFilter id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/event/filter/list` { #get-event-filter-list }

List event filter

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Incidence object

??? note "Response fields (41 fields)"

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
    | `data.[].idEventFilter` | integer |  | Id EventFilter |
    | `data.[].idGroupFilter` | integer, nullable |  | Id group filter |
    | `data.[].name` | string |  | Name of the eventFilter |
    | `data.[].idGroup` | integer, nullable |  | Id group |
    | `data.[].severity` | array, nullable |  | Severity event filter |
    | `data.[].status` | enum: `-1`, `0`, `1`, `2`, `3`, `4`, `all`, `new`, `validated`, `inprocess`, `not_validated`, `not_in_process` |  | Event status, the available status are: all, new, validated, inprocess, not_validated, not_in_process |
    | `data.[].eventType` | enum: `going_unknown`, `unknown`, `alert_fired`, `alert_recovered`, `alert_ceased`, `alert_manual_validation`, `recon_host_detected`, `system`, `error`, `new_agent`, `going_up_critical`, `going_down_critical`, `going_up_warning`, `going_down_warning`, `going_up_normal`, `going_down_normal`, `configuration_change`, `ncm` |  | Event status, the available status are: going_unknown, unknown, alert_fired, alert_recovered, alert_ceased, alert_manual_validation, recon_host_detected, system, error, new_agent, going_up_critical, going_down_critical, going_up_warning, going_down_warning, going_up_normal, going_down_normal, configuration_change, ncm |
    | `data.[].search` | string, nullable |  | Search in fields id, event, extraId, source and custom_data |
    | `data.[].isNotSearch` | boolean, nullable |  | Not search |
    | `data.[].textAgent` | string, nullable |  | Name agent |
    | `data.[].idAgent` | integer, nullable |  | Id agent |
    | `data.[].idAgentModule` | integer, nullable |  | Id agent module |
    | `data.[].pagination` | integer, nullable |  | Block size pagination |
    | `data.[].idUserAck` | string, nullable |  | Id user ack |
    | `data.[].groupBy` | enum: `all`, `events`, `agents`, `extra_ids` |  | Event filter group by, the available group by are: all, events, agents, extra_ids |
    | `data.[].tagWith` | array, nullable |  | Tags filter |
    | `data.[].tagWithout` | array, nullable |  | Tags not filter |
    | `data.[].filterOnlyAlert` | enum: `all`, `filter_alert_events`, `only_alert_events` |  | Event filter event by, the available filter are: all, filter_alert_events, only_alert_events |
    | `data.[].searchSecondaryGroups` | boolean, nullable |  | Search in secondary groups |
    | `data.[].searchRecursiveGroups` | boolean, nullable |  | Search in recursive groups |
    | `data.[].dateRange` | string, nullable |  | Search event registration date range |
    | `data.[].source` | string, nullable |  | Search source field |
    | `data.[].idExtra` | string, nullable |  | Search source idExtra |
    | `data.[].userComment` | string, nullable |  | Search source userComment |
    | `data.[].idSourceEvent` | integer, nullable |  | Search id source event |
    | `data.[].serverId` | array, nullable |  | Server ids filter, only metaconsole |
    | `data.[].customData` | string, nullable |  | Search custom data |
    | `data.[].customDataFilterType` | enum: `only_alert_events`, `filter_alert_events` |  | Event filter event by, the available filter are: all, filter_alert_events, only_alert_events |
    | `data.[].ownerUser` | string, nullable |  | Search owner user |
    | `data.[].privateFilterUser` | string, nullable |  | Search private filter user |
    | `data.[].regex` | string, nullable |  | Search regex |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/event/filter/list` { #post-event-filter-list }

List event filter

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
| `idEventFilter` | integer |  | Id EventFilter |
| `idGroupFilter` | integer, nullable |  | Id group filter |
| `name` | string |  | Name of the eventFilter |
| `idGroup` | integer, nullable |  | Id group |
| `severity` | array, nullable |  | Severity event filter |
| `status` | enum: `-1`, `0`, `1`, `2`, `3`, `4`, `all`, `new`, `validated`, `inprocess`, `not_validated`, `not_in_process` |  | Event status, the available status are: all, new, validated, inprocess, not_validated, not_in_process |
| `eventType` | enum: `going_unknown`, `unknown`, `alert_fired`, `alert_recovered`, `alert_ceased`, `alert_manual_validation`, `recon_host_detected`, `system`, `error`, `new_agent`, `going_up_critical`, `going_down_critical`, `going_up_warning`, `going_down_warning`, `going_up_normal`, `going_down_normal`, `configuration_change`, `ncm` |  | Event status, the available status are: going_unknown, unknown, alert_fired, alert_recovered, alert_ceased, alert_manual_validation, recon_host_detected, system, error, new_agent, going_up_critical, going_down_critical, going_up_warning, going_down_warning, going_up_normal, going_down_normal, configuration_change, ncm |
| `search` | string, nullable |  | Search in fields id, event, extraId, source and custom_data |
| `isNotSearch` | boolean, nullable |  | Not search |
| `textAgent` | string, nullable |  | Name agent |
| `idAgent` | integer, nullable |  | Id agent |
| `idAgentModule` | integer, nullable |  | Id agent module |
| `pagination` | integer, nullable |  | Block size pagination |
| `idUserAck` | string, nullable |  | Id user ack |
| `groupBy` | enum: `all`, `events`, `agents`, `extra_ids` |  | Event filter group by, the available group by are: all, events, agents, extra_ids |
| `tagWith` | array, nullable |  | Tags filter |
| `tagWithout` | array, nullable |  | Tags not filter |
| `filterOnlyAlert` | enum: `all`, `filter_alert_events`, `only_alert_events` |  | Event filter event by, the available filter are: all, filter_alert_events, only_alert_events |
| `searchSecondaryGroups` | boolean, nullable |  | Search in secondary groups |
| `searchRecursiveGroups` | boolean, nullable |  | Search in recursive groups |
| `dateRange` | string, nullable |  | Search event registration date range |
| `source` | string, nullable |  | Search source field |
| `idExtra` | string, nullable |  | Search source idExtra |
| `userComment` | string, nullable |  | Search source userComment |
| `idSourceEvent` | integer, nullable |  | Search id source event |
| `serverId` | array, nullable |  | Server ids filter, only metaconsole |
| `customData` | string, nullable |  | Search custom data |
| `customDataFilterType` | enum: `only_alert_events`, `filter_alert_events` |  | Event filter event by, the available filter are: all, filter_alert_events, only_alert_events |
| `ownerUser` | string, nullable |  | Search owner user |
| `privateFilterUser` | string, nullable |  | Search private filter user |
| `regex` | string, nullable |  | Search regex |
| `idEventFilter` |  |  |  |
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
| `multipleSearch.field` | enum: `idEventFilter`, `idGroupFilter`, `name`, `idGroup`, `search`, `isNotSearch`, `textAgent`, `idAgent`, `idAgentModule`, `pagination`, `idUserAck`, `searchSecondaryGroups`, `searchRecursiveGroups`, `source`, `idExtra`, `userComment`, `idSourceEvent`, `customData`, `ownerUser`, `privateFilterUser` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idEventFilter`, `idGroupFilter`, `name`, `idGroup`, `search`, `isNotSearch`, `textAgent`, `idAgent`, `idAgentModule`, `pagination`, `idUserAck`, `searchSecondaryGroups`, `searchRecursiveGroups`, `source`, `idExtra`, `userComment`, `idSourceEvent`, `customData`, `ownerUser`, `privateFilterUser` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroupFilter": 0,
      "name": "string",
      "idGroup": 0,
      "severity": [
        0
      ],
      "status": -1,
      "eventType": "going_unknown",
      "search": "string",
      "isNotSearch": false,
      "idAgent": 0,
      "idAgentModule": 0,
      "pagination": 0,
      "idUserAck": "string",
      "groupBy": "all",
      "tagWith": [
        0
      ],
      "tagWithout": [
        0
      ],
      "filterOnlyAlert": "all",
      "searchSecondaryGroups": false,
      "searchRecursiveGroups": false,
      "dateRange": "{'end': {'mode': 'absolute', 'value': '2025-04-07 08:56:54'}, 'start': {'mode': 'absolute', 'value': '2025-04-01 00:00:00'}}",
      "source": "string",
      "idExtra": "string",
      "userComment": "string",
      "idSourceEvent": 0,
      "serverId": [
        0
      ],
      "customData": "string",
      "customDataFilterType": "only_alert_events",
      "ownerUser": "string",
      "privateFilterUser": "string",
      "regex": "string",
      "idEventFilter": null,
      "freeSearch": "string",
      "requestedFields": [
        "idEventFilter"
      ],
      "fieldConditions": [
        {
          "field": "idEventFilter",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idEventFilter",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idEventFilter",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List Incidence object

??? note "Response fields (41 fields)"

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
    | `data.[].idEventFilter` | integer |  | Id EventFilter |
    | `data.[].idGroupFilter` | integer, nullable |  | Id group filter |
    | `data.[].name` | string |  | Name of the eventFilter |
    | `data.[].idGroup` | integer, nullable |  | Id group |
    | `data.[].severity` | array, nullable |  | Severity event filter |
    | `data.[].status` | enum: `-1`, `0`, `1`, `2`, `3`, `4`, `all`, `new`, `validated`, `inprocess`, `not_validated`, `not_in_process` |  | Event status, the available status are: all, new, validated, inprocess, not_validated, not_in_process |
    | `data.[].eventType` | enum: `going_unknown`, `unknown`, `alert_fired`, `alert_recovered`, `alert_ceased`, `alert_manual_validation`, `recon_host_detected`, `system`, `error`, `new_agent`, `going_up_critical`, `going_down_critical`, `going_up_warning`, `going_down_warning`, `going_up_normal`, `going_down_normal`, `configuration_change`, `ncm` |  | Event status, the available status are: going_unknown, unknown, alert_fired, alert_recovered, alert_ceased, alert_manual_validation, recon_host_detected, system, error, new_agent, going_up_critical, going_down_critical, going_up_warning, going_down_warning, going_up_normal, going_down_normal, configuration_change, ncm |
    | `data.[].search` | string, nullable |  | Search in fields id, event, extraId, source and custom_data |
    | `data.[].isNotSearch` | boolean, nullable |  | Not search |
    | `data.[].textAgent` | string, nullable |  | Name agent |
    | `data.[].idAgent` | integer, nullable |  | Id agent |
    | `data.[].idAgentModule` | integer, nullable |  | Id agent module |
    | `data.[].pagination` | integer, nullable |  | Block size pagination |
    | `data.[].idUserAck` | string, nullable |  | Id user ack |
    | `data.[].groupBy` | enum: `all`, `events`, `agents`, `extra_ids` |  | Event filter group by, the available group by are: all, events, agents, extra_ids |
    | `data.[].tagWith` | array, nullable |  | Tags filter |
    | `data.[].tagWithout` | array, nullable |  | Tags not filter |
    | `data.[].filterOnlyAlert` | enum: `all`, `filter_alert_events`, `only_alert_events` |  | Event filter event by, the available filter are: all, filter_alert_events, only_alert_events |
    | `data.[].searchSecondaryGroups` | boolean, nullable |  | Search in secondary groups |
    | `data.[].searchRecursiveGroups` | boolean, nullable |  | Search in recursive groups |
    | `data.[].dateRange` | string, nullable |  | Search event registration date range |
    | `data.[].source` | string, nullable |  | Search source field |
    | `data.[].idExtra` | string, nullable |  | Search source idExtra |
    | `data.[].userComment` | string, nullable |  | Search source userComment |
    | `data.[].idSourceEvent` | integer, nullable |  | Search id source event |
    | `data.[].serverId` | array, nullable |  | Server ids filter, only metaconsole |
    | `data.[].customData` | string, nullable |  | Search custom data |
    | `data.[].customDataFilterType` | enum: `only_alert_events`, `filter_alert_events` |  | Event filter event by, the available filter are: all, filter_alert_events, only_alert_events |
    | `data.[].ownerUser` | string, nullable |  | Search owner user |
    | `data.[].privateFilterUser` | string, nullable |  | Search private filter user |
    | `data.[].regex` | string, nullable |  | Search regex |


Error responses: `400`, `401`, `403`, `404`, `500`.

## EventTags

API Endpoints for event tags and event tag relations

### <span class="api-method api-post">POST</span> `/event/eventTag` { #post-event-eventtag }

Creates a new event tag

**Request body** (`application/json`): [`EventTag`](#model-eventtag)

**Response 200**: EventTag object

Schema: [`EventTag`](#model-eventtag)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/event/eventTag/{idEventTag}` { #get-event-eventtag-ideventtag }

Show event tag

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventTag` | path | integer | yes | Event tag id |

**Response 200**: EventTag object

Schema: [`EventTag`](#model-eventtag)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/event/eventTag/{idEventTag}` { #put-event-eventtag-ideventtag }

Updates an event tag

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventTag` | path | integer | yes | Event tag id |

**Request body** (`application/json`): [`EventTag`](#model-eventtag)

**Response 200**: EventTag object

Schema: [`EventTag`](#model-eventtag)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/event/eventTag/{idEventTag}` { #delete-event-eventtag-ideventtag }

Deletes an event tag object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventTag` | path | integer | yes | Event tag id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/event/eventTag/list` { #get-event-eventtag-list }

List event tags

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List event tag objects

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
    | `data.[].idEventTag` | integer |  | Id event tag |
    | `data.[].title` | string |  | Title of the event tag |
    | `data.[].description` | string, nullable |  | Description of the event tag |
    | `data.[].backgroundColor` | string |  | Background color hex code (e.g. #FFFFFF) |
    | `data.[].textColor` | string |  | Text color hex code (e.g. #000000) |
    | `data.[].createdAt` | string, nullable |  | Creation date |
    | `data.[].updatedAt` | string, nullable |  | Last update date |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/event/eventTag/list` { #post-event-eventtag-list }

List event tags

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
| `idEventTag` | integer |  | Id event tag |
| `title` | string |  | Title of the event tag |
| `description` | string, nullable |  | Description of the event tag |
| `backgroundColor` | string |  | Background color hex code (e.g. #FFFFFF) |
| `textColor` | string |  | Text color hex code (e.g. #000000) |
| `createdAt` | string, nullable |  | Creation date |
| `updatedAt` | string, nullable |  | Last update date |
| `idEventTag` |  |  |  |
| `backgroundColor` | string, nullable |  | Filter by background color hex code. Leave null to ignore. |
| `textColor` | string, nullable |  | Filter by text color hex code. Leave null to ignore. |
| `freeSearch` | string, nullable |  | Find word in title or description fields. |
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
| `multipleSearch.field` | enum: `idEventTag`, `title`, `description`, `backgroundColor`, `textColor`, `createdAt`, `updatedAt` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idEventTag`, `title`, `description`, `backgroundColor`, `textColor`, `createdAt`, `updatedAt` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "title": "string",
      "description": "string",
      "backgroundColor": "string",
      "textColor": "string",
      "idEventTag": null,
      "freeSearch": "string",
      "requestedFields": [
        "idEventTag"
      ],
      "fieldConditions": [
        {
          "field": "idEventTag",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idEventTag",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idEventTag",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List event tag objects

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
    | `data.[].idEventTag` | integer |  | Id event tag |
    | `data.[].title` | string |  | Title of the event tag |
    | `data.[].description` | string, nullable |  | Description of the event tag |
    | `data.[].backgroundColor` | string |  | Background color hex code (e.g. #FFFFFF) |
    | `data.[].textColor` | string |  | Text color hex code (e.g. #000000) |
    | `data.[].createdAt` | string, nullable |  | Creation date |
    | `data.[].updatedAt` | string, nullable |  | Last update date |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/event/{idEvent}/tag/{idEventTag}` { #post-event-idevent-tag-ideventtag }

Assign an event tag to an event

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `idEventTag` | path | integer | yes | Event tag id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Event Tag Relation object

Schema: [`FederatedEventTagRelation`](#model-federatedeventtagrelation)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/event/{idEvent}/tag/{idEventTagRelation}` { #get-event-idevent-tag-ideventtagrelation }

Show event tag relation

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `idEventTagRelation` | path | integer | yes | EventTagRelation id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Event Tag Relation object

Schema: [`FederatedEventTagRelation`](#model-federatedeventtagrelation)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/event/{idEvent}/tag/{idEventTagRelation}` { #delete-event-idevent-tag-ideventtagrelation }

Remove an event tag relation from an event

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `idEventTagRelation` | path | integer | yes | EventTagRelation id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/event/{idEvent}/tag/list` { #get-event-idevent-tag-list }

List event tag relations of an event

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List event tag relation objects

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
    | `data` | array of FederatedEventTagRelation |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idEventTagRelation` | integer |  | Id EventTagRelation |
    | `data.[].idEvent` | integer, nullable |  | Id of the Event |
    | `data.[].idEventTag` | integer, nullable |  | Id of the EventTag |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/event/{idEvent}/tag/list` { #post-event-idevent-tag-list }

List event tag relations of an event

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventTagRelation` | integer |  | Id EventTagRelation |
| `idEvent` | integer, nullable |  | Id of the Event |
| `idEventTag` | integer, nullable |  | Id of the EventTag |
| `idEventTagRelation` |  |  |  |
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
| `multipleSearch.field` | enum: `idEventTagRelation`, `idEvent`, `idEventTag` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idEventTagRelation`, `idEvent`, `idEventTag` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idEvent": 0,
      "idEventTag": 0,
      "idEventTagRelation": null,
      "requestedFields": [
        "idEventTagRelation"
      ],
      "fieldConditions": [
        {
          "field": "idEventTagRelation",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idEventTagRelation",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idEventTagRelation",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List event tag relation objects

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
    | `data` | array of FederatedEventTagRelation |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idEventTagRelation` | integer |  | Id EventTagRelation |
    | `data.[].idEvent` | integer, nullable |  | Id of the Event |
    | `data.[].idEventTag` | integer, nullable |  | Id of the EventTag |


Error responses: `400`, `401`, `403`, `500`.

## EventLifetime

API Endpoints for event lifetime rules

### <span class="api-method api-get">GET</span> `/event/{idEvent}/lifetime/{idLifetime}` { #get-event-idevent-lifetime-idlifetime }

Get a single event lifetime status entry

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `idLifetime` | path | integer | yes | Event lifetime id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Event lifetime object

??? note "Response fields (6 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `serverId` | integer, nullable |  | Console that owns the resource |
    | `idEventLifetime` | integer |  | id event lifetime |
    | `idEvent` | integer |  | id of the associated event |
    | `utimestamp` | integer, nullable |  | Timestamp of the status change |
    | `status` | integer |  | Event status at this point in time (0=new, 1=validated, 2=in process, 3=not validated) |
    | `idUser` | string, nullable |  | User who triggered the status change |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/event/{idEvent}/lifetime/list` { #get-event-idevent-lifetime-list }

List the lifecycle status history of an event

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List of event lifetime status entries

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
    | `data` | array of FederatedEventLifetime |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idEventLifetime` | integer |  | id event lifetime |
    | `data.[].idEvent` | integer |  | id of the associated event |
    | `data.[].utimestamp` | integer, nullable |  | Timestamp of the status change |
    | `data.[].status` | integer |  | Event status at this point in time (0=new, 1=validated, 2=in process, 3=not validated) |
    | `data.[].idUser` | string, nullable |  | User who triggered the status change |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/event/{idEvent}/lifetime/list` { #post-event-idevent-lifetime-list }

List the lifecycle status history of an event

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEvent` | path | integer | yes | Event id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventLifetime` | integer |  | id event lifetime |
| `idEvent` | integer |  | id of the associated event |
| `utimestamp` | integer, nullable |  | Timestamp of the status change |
| `status` | integer |  | Event status at this point in time (0=new, 1=validated, 2=in process, 3=not validated) |
| `idUser` | string, nullable |  | User who triggered the status change |
| `idEventLifetime` |  |  |  |
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
| `multipleSearch.field` | enum: `idEventLifetime`, `idEvent`, `idUser`, `utimestamp`, `status` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idEventLifetime`, `idEvent`, `idUser`, `utimestamp`, `status` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idEventLifetime": null,
      "requestedFields": [
        "idEventLifetime"
      ],
      "fieldConditions": [
        {
          "field": "idEventLifetime",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idEventLifetime",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idEventLifetime",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List of event lifetime status entries

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
    | `data` | array of FederatedEventLifetime |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idEventLifetime` | integer |  | id event lifetime |
    | `data.[].idEvent` | integer |  | id of the associated event |
    | `data.[].utimestamp` | integer, nullable |  | Timestamp of the status change |
    | `data.[].status` | integer |  | Event status at this point in time (0=new, 1=validated, 2=in process, 3=not validated) |
    | `data.[].idUser` | string, nullable |  | User who triggered the status change |


Error responses: `400`, `401`, `403`, `500`.

## EventAlerts

API Endpoints for event alerts

### <span class="api-method api-post">POST</span> `/alert/event` { #post-alert-event }

createEventAlert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventAlert` | integer |  |  |
| `name` | string | yes |  |
| `description` | string |  |  |
| `order` | integer |  |  |
| `idGroup` | integer | yes |  |
| `mode` | enum: `PASS`, `DROP` |  |  |
| `fields` | array of string |  |  |
| `recoveryFields` | array of string |  |  |
| `schedule` | object, nullable |  |  |
| `timeThreshold` | integer |  |  |
| `minAlerts` | integer |  |  |
| `maxAlerts` | integer |  |  |
| `recoveryNotify` | boolean |  |  |
| `disabled` | boolean |  |  |
| `standby` | boolean |  |  |
| `priority` | integer |  |  |
| `forceExecution` | boolean |  |  |
| `groupBy` | enum: ``, `id_agente`, `id_agentmodule`, `id_alert_am`, `id_grupo` |  |  |
| `specialDays` | boolean |  |  |
| `disableEvent` | boolean |  |  |
| `idTemplateConditions` | integer |  |  |
| `idTemplateFields` | integer |  |  |
| `internalCounter` | integer |  |  |
| `lastFired` | integer |  |  |
| `lastReference` | integer |  |  |
| `timesFired` | integer |  |  |
| `lastEvaluation` | integer |  |  |
| `poolOccurrences` | integer |  |  |
| `serverId` | integer, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "mode": "PASS",
      "fields": [
        "string"
      ],
      "recoveryFields": [
        "string"
      ],
      "schedule": {},
      "timeThreshold": 0,
      "minAlerts": 0,
      "maxAlerts": 0,
      "recoveryNotify": false,
      "disabled": false,
      "standby": false,
      "priority": 0,
      "forceExecution": false,
      "groupBy": "",
      "specialDays": false,
      "disableEvent": false,
      "idTemplateConditions": 0,
      "idTemplateFields": 0
    }
    ```

**Response 200**: Event alert

Schema: [`EventAlert`](#model-eventalert)

Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-get">GET</span> `/alert/event/{idEventAlert}` { #get-alert-event-ideventalert }

getEventAlert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Event alert

Schema: [`EventAlert`](#model-eventalert)

Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/alert/event/{idEventAlert}` { #put-alert-event-ideventalert }

updateEventAlert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`EventAlert`](#model-eventalert)

**Response 200**: Event alert

Schema: [`EventAlert`](#model-eventalert)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/alert/event/{idEventAlert}` { #delete-alert-event-ideventalert }

deleteEventAlert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 204**: Deleted

Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/alert/event/list` { #get-alert-event-list }

listEventAlertsByQuery

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Event alert list

### <span class="api-method api-post">POST</span> `/alert/event/list` { #post-alert-event-list }

listEventAlerts

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventAlert` | integer |  |  |
| `name` | string |  |  |
| `description` | string |  |  |
| `order` | integer |  |  |
| `idGroup` | integer |  |  |
| `mode` | enum: `PASS`, `DROP` |  |  |
| `fields` | array of string |  |  |
| `recoveryFields` | array of string |  |  |
| `schedule` | object, nullable |  |  |
| `timeThreshold` | integer |  |  |
| `minAlerts` | integer |  |  |
| `maxAlerts` | integer |  |  |
| `recoveryNotify` | boolean |  |  |
| `disabled` | boolean |  |  |
| `standby` | boolean |  |  |
| `priority` | integer |  |  |
| `forceExecution` | boolean |  |  |
| `groupBy` | enum: ``, `id_agente`, `id_agentmodule`, `id_alert_am`, `id_grupo` |  |  |
| `specialDays` | boolean |  |  |
| `disableEvent` | boolean |  |  |
| `idTemplateConditions` | integer |  |  |
| `idTemplateFields` | integer |  |  |
| `internalCounter` | integer |  |  |
| `lastFired` | integer |  |  |
| `lastReference` | integer |  |  |
| `timesFired` | integer |  |  |
| `lastEvaluation` | integer |  |  |
| `poolOccurrences` | integer |  |  |
| `serverId` | integer, nullable |  |  |
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
| `multipleSearch.field` | enum: `idEventAlert`, `name`, `description`, `order`, `mode`, `timeThreshold`, `maxAlerts`, `minAlerts`, `recoveryNotify`, `idGroup`, `internalCounter`, `lastFired`, `lastReference`, `timesFired`, `disabled`, `standby`, `priority`, `forceExecution`, `groupBy`, `specialDays`, `disableEvent`, `idTemplateConditions`, `idTemplateFields`, `lastEvaluation`, `poolOccurrences` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idEventAlert`, `name`, `description`, `order`, `mode`, `timeThreshold`, `maxAlerts`, `minAlerts`, `recoveryNotify`, `idGroup`, `internalCounter`, `lastFired`, `lastReference`, `timesFired`, `disabled`, `standby`, `priority`, `forceExecution`, `groupBy`, `specialDays`, `disableEvent`, `idTemplateConditions`, `idTemplateFields`, `lastEvaluation`, `poolOccurrences` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "mode": "PASS",
      "fields": [
        "string"
      ],
      "recoveryFields": [
        "string"
      ],
      "schedule": {},
      "timeThreshold": 0,
      "minAlerts": 0,
      "maxAlerts": 0,
      "recoveryNotify": false,
      "disabled": false,
      "standby": false,
      "priority": 0,
      "forceExecution": false,
      "groupBy": "",
      "specialDays": false,
      "disableEvent": false,
      "idTemplateConditions": 0,
      "idTemplateFields": 0,
      "freeSearch": "string",
      "requestedFields": [
        "idEventAlert"
      ],
      "fieldConditions": [
        {
          "field": "idEventAlert",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idEventAlert",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idEventAlert",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Event alert list

Error responses: `400`, `401`, `403`, `500`.

## EventAlertRules

Event alert rule management

### <span class="api-method api-post">POST</span> `/alert/event/{idEventAlert}/rule` { #post-alert-event-ideventalert-rule }

Associate an action with an event alert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventRule` | integer |  |  |
| `idEventAlert` | integer |  |  |
| `operation` | enum: `NOP`, `AND`, `OR`, `XOR`, `NAND`, `NOR`, `NXOR` | yes |  |
| `order` | integer |  |  |
| `window` | integer |  |  |
| `count` | integer |  |  |
| `agent` | string, nullable |  |  |
| `idUser` | string, nullable |  |  |
| `idGroup` | string, nullable |  |  |
| `event` | string, nullable |  |  |
| `eventType` | string, nullable |  |  |
| `module` | string, nullable |  |  |
| `alert` | string, nullable |  |  |
| `criticity` | string, nullable |  |  |
| `idTag` | string, nullable |  |  |
| `name` | string, nullable |  |  |
| `groupRecursion` | string, nullable |  |  |
| `logContent` | string, nullable |  |  |
| `logSource` | string, nullable |  |  |
| `logAgent` | string, nullable |  |  |
| `operatorAgent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorIdUser` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorIdGroup` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorEvent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorEventType` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorModule` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorAlert` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorCriticity` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorIdTag` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorLogContent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorLogSource` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorLogAgent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "operation": "NOP",
      "order": 0,
      "window": 0,
      "count": 1,
      "agent": "string",
      "idUser": "string",
      "idGroup": "string",
      "event": "string",
      "eventType": "string",
      "module": "string",
      "alert": "string",
      "criticity": "string",
      "idTag": "string",
      "name": "string",
      "groupRecursion": "string",
      "logContent": "string",
      "logSource": "string",
      "logAgent": "string",
      "operatorAgent": ">",
      "operatorIdUser": ">",
      "operatorIdGroup": ">",
      "operatorEvent": ">",
      "operatorEventType": ">",
      "operatorModule": ">",
      "operatorAlert": ">",
      "operatorCriticity": ">",
      "operatorIdTag": ">",
      "operatorLogContent": ">",
      "operatorLogSource": ">",
      "operatorLogAgent": ">"
    }
    ```

**Response 200**: Event alert rule

Schema: [`FederatedEventAlertRule`](#model-federatedeventalertrule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/alert/event/{idEventAlert}/rule/{idEventRule}` { #get-alert-event-ideventalert-rule-ideventrule }

Get an event alert rule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `idEventRule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Event alert rule

Schema: [`FederatedEventAlertRule`](#model-federatedeventalertrule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/alert/event/{idEventAlert}/rule/{idEventRule}` { #put-alert-event-ideventalert-rule-ideventrule }

Update an event alert rule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `idEventRule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventRule` | integer |  |  |
| `idEventAlert` | integer |  |  |
| `operation` | enum: `NOP`, `AND`, `OR`, `XOR`, `NAND`, `NOR`, `NXOR` |  |  |
| `order` | integer |  |  |
| `window` | integer |  |  |
| `count` | integer |  |  |
| `agent` | string, nullable |  |  |
| `idUser` | string, nullable |  |  |
| `idGroup` | string, nullable |  |  |
| `event` | string, nullable |  |  |
| `eventType` | string, nullable |  |  |
| `module` | string, nullable |  |  |
| `alert` | string, nullable |  |  |
| `criticity` | string, nullable |  |  |
| `idTag` | string, nullable |  |  |
| `name` | string, nullable |  |  |
| `groupRecursion` | string, nullable |  |  |
| `logContent` | string, nullable |  |  |
| `logSource` | string, nullable |  |  |
| `logAgent` | string, nullable |  |  |
| `operatorAgent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorIdUser` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorIdGroup` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorEvent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorEventType` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorModule` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorAlert` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorCriticity` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorIdTag` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorLogContent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorLogSource` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorLogAgent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "operation": "NOP",
      "order": 0,
      "window": 0,
      "count": 1,
      "agent": "string",
      "idUser": "string",
      "idGroup": "string",
      "event": "string",
      "eventType": "string",
      "module": "string",
      "alert": "string",
      "criticity": "string",
      "idTag": "string",
      "name": "string",
      "groupRecursion": "string",
      "logContent": "string",
      "logSource": "string",
      "logAgent": "string",
      "operatorAgent": ">",
      "operatorIdUser": ">",
      "operatorIdGroup": ">",
      "operatorEvent": ">",
      "operatorEventType": ">",
      "operatorModule": ">",
      "operatorAlert": ">",
      "operatorCriticity": ">",
      "operatorIdTag": ">",
      "operatorLogContent": ">",
      "operatorLogSource": ">",
      "operatorLogAgent": ">"
    }
    ```

**Response 200**: Event alert rule

Schema: [`FederatedEventAlertRule`](#model-federatedeventalertrule)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/alert/event/{idEventAlert}/rule/{idEventRule}` { #delete-alert-event-ideventalert-rule-ideventrule }

Delete an event alert rule

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `idEventRule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 204**: Event alert action deleted

Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/alert/event/{idEventAlert}/rule/list` { #get-alert-event-ideventalert-rule-list }

List actions associated with an event alert

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Event alert action list

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
    | `data` | array of FederatedEventAlertRule |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idEventRule` | integer |  |  |
    | `data.[].idEventAlert` | integer |  |  |
    | `data.[].operation` | enum: `NOP`, `AND`, `OR`, `XOR`, `NAND`, `NOR`, `NXOR` |  |  |
    | `data.[].order` | integer |  |  |
    | `data.[].window` | integer |  |  |
    | `data.[].count` | integer |  |  |
    | `data.[].agent` | string, nullable |  |  |
    | `data.[].idUser` | string, nullable |  |  |
    | `data.[].idGroup` | string, nullable |  |  |
    | `data.[].event` | string, nullable |  |  |
    | `data.[].eventType` | string, nullable |  |  |
    | `data.[].module` | string, nullable |  |  |
    | `data.[].alert` | string, nullable |  |  |
    | `data.[].criticity` | string, nullable |  |  |
    | `data.[].idTag` | string, nullable |  |  |
    | `data.[].name` | string, nullable |  |  |
    | `data.[].groupRecursion` | string, nullable |  |  |
    | `data.[].logContent` | string, nullable |  |  |
    | `data.[].logSource` | string, nullable |  |  |
    | `data.[].logAgent` | string, nullable |  |  |
    | `data.[].operatorAgent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorIdUser` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorIdGroup` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorEvent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorEventType` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorModule` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorAlert` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorCriticity` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorIdTag` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorLogContent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorLogSource` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorLogAgent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/alert/event/{idEventAlert}/rule/list` { #post-alert-event-ideventalert-rule-list }

List actions associated with an event alert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventRule` | integer |  |  |
| `idEventAlert` | integer |  |  |
| `operation` | enum: `NOP`, `AND`, `OR`, `XOR`, `NAND`, `NOR`, `NXOR` |  |  |
| `order` | integer |  |  |
| `window` | integer |  |  |
| `count` | integer |  |  |
| `agent` | string, nullable |  |  |
| `idUser` | string, nullable |  |  |
| `idGroup` | string, nullable |  |  |
| `event` | string, nullable |  |  |
| `eventType` | string, nullable |  |  |
| `module` | string, nullable |  |  |
| `alert` | string, nullable |  |  |
| `criticity` | string, nullable |  |  |
| `idTag` | string, nullable |  |  |
| `name` | string, nullable |  |  |
| `groupRecursion` | string, nullable |  |  |
| `logContent` | string, nullable |  |  |
| `logSource` | string, nullable |  |  |
| `logAgent` | string, nullable |  |  |
| `operatorAgent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorIdUser` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorIdGroup` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorEvent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorEventType` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorModule` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorAlert` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorCriticity` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorIdTag` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorLogContent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorLogSource` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `operatorLogAgent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
| `idEventRule` |  |  |  |
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
| `multipleSearch.field` | enum: `idEventRule`, `idEventAlert`, `operation`, `order`, `window`, `count`, `agent`, `idUser`, `idGroup`, `event`, `eventType`, `module`, `alert`, `criticity`, `idTag`, `name`, `groupRecursion`, `logContent`, `logSource`, `logAgent`, `operatorAgent`, `operatorIdUser`, `operatorIdGroup`, `operatorEvent`, `operatorEventType`, `operatorModule`, `operatorAlert`, `operatorCriticity`, `operatorIdTag`, `operatorLogContent`, `operatorLogSource`, `operatorLogAgent` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idEventRule`, `idEventAlert`, `operation`, `order`, `window`, `count`, `agent`, `idUser`, `idGroup`, `event`, `eventType`, `module`, `alert`, `criticity`, `idTag`, `name`, `groupRecursion`, `logContent`, `logSource`, `logAgent`, `operatorAgent`, `operatorIdUser`, `operatorIdGroup`, `operatorEvent`, `operatorEventType`, `operatorModule`, `operatorAlert`, `operatorCriticity`, `operatorIdTag`, `operatorLogContent`, `operatorLogSource`, `operatorLogAgent` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "operation": "NOP",
      "order": 0,
      "window": 0,
      "count": 1,
      "agent": "string",
      "idUser": "string",
      "idGroup": "string",
      "event": "string",
      "eventType": "string",
      "module": "string",
      "alert": "string",
      "criticity": "string",
      "idTag": "string",
      "name": "string",
      "groupRecursion": "string",
      "logContent": "string",
      "logSource": "string",
      "logAgent": "string",
      "operatorAgent": ">",
      "operatorIdUser": ">",
      "operatorIdGroup": ">",
      "operatorEvent": ">",
      "operatorEventType": ">",
      "operatorModule": ">",
      "operatorAlert": ">",
      "operatorCriticity": ">",
      "operatorIdTag": ">",
      "operatorLogContent": ">",
      "operatorLogSource": ">",
      "operatorLogAgent": ">",
      "idEventRule": null,
      "requestedFields": [
        "idEventRule"
      ],
      "fieldConditions": [
        {
          "field": "idEventRule",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idEventRule",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idEventRule",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Event alert action list

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
    | `data` | array of FederatedEventAlertRule |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idEventRule` | integer |  |  |
    | `data.[].idEventAlert` | integer |  |  |
    | `data.[].operation` | enum: `NOP`, `AND`, `OR`, `XOR`, `NAND`, `NOR`, `NXOR` |  |  |
    | `data.[].order` | integer |  |  |
    | `data.[].window` | integer |  |  |
    | `data.[].count` | integer |  |  |
    | `data.[].agent` | string, nullable |  |  |
    | `data.[].idUser` | string, nullable |  |  |
    | `data.[].idGroup` | string, nullable |  |  |
    | `data.[].event` | string, nullable |  |  |
    | `data.[].eventType` | string, nullable |  |  |
    | `data.[].module` | string, nullable |  |  |
    | `data.[].alert` | string, nullable |  |  |
    | `data.[].criticity` | string, nullable |  |  |
    | `data.[].idTag` | string, nullable |  |  |
    | `data.[].name` | string, nullable |  |  |
    | `data.[].groupRecursion` | string, nullable |  |  |
    | `data.[].logContent` | string, nullable |  |  |
    | `data.[].logSource` | string, nullable |  |  |
    | `data.[].logAgent` | string, nullable |  |  |
    | `data.[].operatorAgent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorIdUser` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorIdGroup` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorEvent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorEventType` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorModule` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorAlert` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorCriticity` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorIdTag` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorLogContent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorLogSource` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `data.[].operatorLogAgent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |


Error responses: `400`, `401`, `403`, `500`.

## EventAlertActions

API Endpoints for actions associated with event alerts

### <span class="api-method api-post">POST</span> `/alert/event/{idEventAlert}/action` { #post-alert-event-ideventalert-action }

Associate an action with an event alert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventAlertAction` | integer |  |  |
| `idEventAlert` | integer |  |  |
| `idAlertAction` | integer | yes |  |
| `firesMin` | integer |  |  |
| `firesMax` | integer |  |  |
| `moduleActionThreshold` | integer |  |  |
| `lastExecution` | integer |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAlertAction": 0,
      "firesMin": 0,
      "firesMax": 0,
      "moduleActionThreshold": 0
    }
    ```

**Response 200**: Event alert action

Schema: [`FederatedEventAlertAction`](#model-federatedeventalertaction)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/alert/event/{idEventAlert}/action/{idEventAlertAction}` { #get-alert-event-ideventalert-action-ideventalertaction }

Get an event alert action

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `idEventAlertAction` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Event alert action

Schema: [`FederatedEventAlertAction`](#model-federatedeventalertaction)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/alert/event/{idEventAlert}/action/{idEventAlertAction}` { #put-alert-event-ideventalert-action-ideventalertaction }

Update an event alert action

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `idEventAlertAction` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventAlertAction` | integer |  |  |
| `idEventAlert` | integer |  |  |
| `idAlertAction` | integer |  |  |
| `firesMin` | integer |  |  |
| `firesMax` | integer |  |  |
| `moduleActionThreshold` | integer |  |  |
| `lastExecution` | integer |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAlertAction": 0,
      "firesMin": 0,
      "firesMax": 0,
      "moduleActionThreshold": 0
    }
    ```

**Response 200**: Event alert action

Schema: [`FederatedEventAlertAction`](#model-federatedeventalertaction)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/alert/event/{idEventAlert}/action/{idEventAlertAction}` { #delete-alert-event-ideventalert-action-ideventalertaction }

Delete an event alert action

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `idEventAlertAction` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 204**: Event alert action deleted

Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/alert/event/{idEventAlert}/action/list` { #get-alert-event-ideventalert-action-list }

List actions associated with an event alert

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Event alert action list

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
    | `data` | array of FederatedEventAlertAction |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idEventAlertAction` | integer |  |  |
    | `data.[].idEventAlert` | integer |  |  |
    | `data.[].idAlertAction` | integer |  |  |
    | `data.[].firesMin` | integer |  |  |
    | `data.[].firesMax` | integer |  |  |
    | `data.[].moduleActionThreshold` | integer |  |  |
    | `data.[].lastExecution` | integer |  |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/alert/event/{idEventAlert}/action/list` { #post-alert-event-ideventalert-action-list }

List actions associated with an event alert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idEventAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventAlertAction` | integer |  |  |
| `idEventAlert` | integer |  |  |
| `idAlertAction` | integer |  |  |
| `firesMin` | integer |  |  |
| `firesMax` | integer |  |  |
| `moduleActionThreshold` | integer |  |  |
| `lastExecution` | integer |  |  |
| `idEventAlertAction` |  |  |  |
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
| `multipleSearch.field` | enum: `idEventAlertAction`, `idEventAlert`, `idAlertAction`, `firesMin`, `firesMax`, `moduleActionThreshold`, `lastExecution` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idEventAlertAction`, `idEventAlert`, `idAlertAction`, `firesMin`, `firesMax`, `moduleActionThreshold`, `lastExecution` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAlertAction": 0,
      "firesMin": 0,
      "firesMax": 0,
      "moduleActionThreshold": 0,
      "idEventAlertAction": null,
      "requestedFields": [
        "idEventAlertAction"
      ],
      "fieldConditions": [
        {
          "field": "idEventAlertAction",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idEventAlertAction",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idEventAlertAction",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Event alert action list

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
    | `data` | array of FederatedEventAlertAction |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idEventAlertAction` | integer |  |  |
    | `data.[].idEventAlert` | integer |  |  |
    | `data.[].idAlertAction` | integer |  |  |
    | `data.[].firesMin` | integer |  |  |
    | `data.[].firesMax` | integer |  |  |
    | `data.[].moduleActionThreshold` | integer |  |  |
    | `data.[].lastExecution` | integer |  |  |


Error responses: `400`, `401`, `403`, `500`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: EventAlert { #model-eventalert }

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventAlert` | integer |  |  |
| `name` | string |  |  |
| `description` | string |  |  |
| `order` | integer |  |  |
| `idGroup` | integer |  |  |
| `mode` | enum: `PASS`, `DROP` |  |  |
| `fields` | array of string |  |  |
| `recoveryFields` | array of string |  |  |
| `schedule` | object, nullable |  |  |
| `timeThreshold` | integer |  |  |
| `minAlerts` | integer |  |  |
| `maxAlerts` | integer |  |  |
| `recoveryNotify` | boolean |  |  |
| `disabled` | boolean |  |  |
| `standby` | boolean |  |  |
| `priority` | integer |  |  |
| `forceExecution` | boolean |  |  |
| `groupBy` | enum: ``, `id_agente`, `id_agentmodule`, `id_alert_am`, `id_grupo` |  |  |
| `specialDays` | boolean |  |  |
| `disableEvent` | boolean |  |  |
| `idTemplateConditions` | integer |  |  |
| `idTemplateFields` | integer |  |  |
| `internalCounter` | integer |  |  |
| `lastFired` | integer |  |  |
| `lastReference` | integer |  |  |
| `timesFired` | integer |  |  |
| `lastEvaluation` | integer |  |  |
| `poolOccurrences` | integer |  |  |
| `serverId` | integer, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idGroup": 0,
      "mode": "PASS",
      "fields": [
        "string"
      ],
      "recoveryFields": [
        "string"
      ],
      "schedule": {},
      "timeThreshold": 0,
      "minAlerts": 0,
      "maxAlerts": 0,
      "recoveryNotify": false,
      "disabled": false,
      "standby": false,
      "priority": 0,
      "forceExecution": false,
      "groupBy": "",
      "specialDays": false,
      "disableEvent": false,
      "idTemplateConditions": 0,
      "idTemplateFields": 0
    }
    ```

### Model: EventComment { #model-eventcomment }

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventComment` | integer |  | id event comment |
| `idEvent` | integer |  | id event comment |
| `utimestamp` | integer, nullable |  | Event comment utimestamp create |
| `comment` | string |  | content of the comment |
| `idUser` | string |  | User id create comment |
| `action` | string |  | content of the action |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "comment": "string"
    }
    ```

### Model: EventCreate { #model-eventcreate }

| Field | Type | Required | Description |
|---|---|---|---|
| `idEvent` | integer |  | Id event |
| `idAgent` | integer, nullable |  | Id agent |
| `idUser` | string, nullable |  | Id user |
| `idGroup` | integer, nullable | yes | Id group |
| `status` | enum: `new`, `validated`, `inprocess` |  | Event status, the available status are: new, validated, inprocess |
| `timestamp` | string, nullable |  | Event registration date |
| `event` | string | yes | Description event |
| `utimestamp` | integer, nullable |  | Event registration date |
| `eventType` | enum: `going_unknown`, `unknown`, `alert_fired`, `alert_recovered`, `alert_ceased`, `alert_manual_validation`, `recon_host_detected`, `system`, `error`, `new_agent`, `going_up_critical`, `going_down_critical`, `going_up_warning`, `going_down_warning`, `going_up_normal`, `going_down_normal`, `configuration_change`, `ncm` |  | Event status, the available status are: going_unknown, unknown, alert_fired, alert_recovered, alert_ceased, alert_manual_validation, recon_host_detected, system, error, new_agent, going_up_critical, going_down_critical, going_up_warning, going_down_warning, going_up_normal, going_down_normal, configuration_change, ncm |
| `idAgentModule` | integer, nullable |  | Id agent module |
| `idAlertAm` | integer, nullable |  | Id alert action |
| `severity` | enum: `maintenance`, `informational`, `normal`, `warning`, `critical`, `minor`, `major` |  | Event severity, the available severity are: maintenance, informational, normal, warning, critical, minor, major |
| `tags` | string, nullable |  | Tags |
| `source` | string, nullable |  | Source |
| `idExtra` | string, nullable |  | Extra id |
| `criticalInstructions` | string, nullable |  | Critical instructions |
| `warningInstructions` | string, nullable |  | Warning instructions |
| `unknownInstructions` | string, nullable |  | Unknows instructions |
| `defaultInstructions` | string, nullable |  | Default instructions, will be use when Critical/Warning/Unknown are empty |
| `ownerUser` | string, nullable |  | Id user |
| `ackUtimestamp` | integer, nullable |  | Event ack utimestamp |
| `customData` | string, nullable |  | Custom data |
| `data` | string, nullable |  | Data |
| `moduleStatus` | integer, nullable |  | Module status |
| `eventCustomId` | string, nullable |  | Events Custom Id |
| `idGroup` | integer | yes | Group id. Use 0 for the All group |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": 0,
      "idUser": "string",
      "idGroup": 0,
      "status": "new",
      "event": "Event created for api",
      "eventType": "going_unknown",
      "idAgentModule": 0,
      "idAlertAm": 0,
      "severity": "maintenance",
      "tags": "string",
      "source": "string",
      "idExtra": "string",
      "criticalInstructions": "string",
      "warningInstructions": "string",
      "unknownInstructions": "string",
      "defaultInstructions": "string",
      "ownerUser": "string",
      "customData": "string",
      "data": "string",
      "eventCustomId": "string"
    }
    ```

### Model: EventFilter { #model-eventfilter }

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventFilter` | integer |  | Id EventFilter |
| `idGroupFilter` | integer, nullable |  | Id group filter |
| `name` | string |  | Name of the eventFilter |
| `idGroup` | integer, nullable |  | Id group |
| `severity` | array, nullable |  | Severity event filter |
| `status` | enum: `-1`, `0`, `1`, `2`, `3`, `4`, `all`, `new`, `validated`, `inprocess`, `not_validated`, `not_in_process` |  | Event status, the available status are: all, new, validated, inprocess, not_validated, not_in_process |
| `eventType` | enum: `going_unknown`, `unknown`, `alert_fired`, `alert_recovered`, `alert_ceased`, `alert_manual_validation`, `recon_host_detected`, `system`, `error`, `new_agent`, `going_up_critical`, `going_down_critical`, `going_up_warning`, `going_down_warning`, `going_up_normal`, `going_down_normal`, `configuration_change`, `ncm` |  | Event status, the available status are: going_unknown, unknown, alert_fired, alert_recovered, alert_ceased, alert_manual_validation, recon_host_detected, system, error, new_agent, going_up_critical, going_down_critical, going_up_warning, going_down_warning, going_up_normal, going_down_normal, configuration_change, ncm |
| `search` | string, nullable |  | Search in fields id, event, extraId, source and custom_data |
| `isNotSearch` | boolean, nullable |  | Not search |
| `textAgent` | string, nullable |  | Name agent |
| `idAgent` | integer, nullable |  | Id agent |
| `idAgentModule` | integer, nullable |  | Id agent module |
| `pagination` | integer, nullable |  | Block size pagination |
| `idUserAck` | string, nullable |  | Id user ack |
| `groupBy` | enum: `all`, `events`, `agents`, `extra_ids` |  | Event filter group by, the available group by are: all, events, agents, extra_ids |
| `tagWith` | array, nullable |  | Tags filter |
| `tagWithout` | array, nullable |  | Tags not filter |
| `filterOnlyAlert` | enum: `all`, `filter_alert_events`, `only_alert_events` |  | Event filter event by, the available filter are: all, filter_alert_events, only_alert_events |
| `searchSecondaryGroups` | boolean, nullable |  | Search in secondary groups |
| `searchRecursiveGroups` | boolean, nullable |  | Search in recursive groups |
| `dateRange` | string, nullable |  | Search event registration date range |
| `source` | string, nullable |  | Search source field |
| `idExtra` | string, nullable |  | Search source idExtra |
| `userComment` | string, nullable |  | Search source userComment |
| `idSourceEvent` | integer, nullable |  | Search id source event |
| `serverId` | array, nullable |  | Server ids filter, only metaconsole |
| `customData` | string, nullable |  | Search custom data |
| `customDataFilterType` | enum: `only_alert_events`, `filter_alert_events` |  | Event filter event by, the available filter are: all, filter_alert_events, only_alert_events |
| `ownerUser` | string, nullable |  | Search owner user |
| `privateFilterUser` | string, nullable |  | Search private filter user |
| `regex` | string, nullable |  | Search regex |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroupFilter": 0,
      "name": "string",
      "idGroup": 0,
      "severity": [
        0
      ],
      "status": -1,
      "eventType": "going_unknown",
      "search": "string",
      "isNotSearch": false,
      "idAgent": 0,
      "idAgentModule": 0,
      "pagination": 0,
      "idUserAck": "string",
      "groupBy": "all",
      "tagWith": [
        0
      ],
      "tagWithout": [
        0
      ],
      "filterOnlyAlert": "all",
      "searchSecondaryGroups": false,
      "searchRecursiveGroups": false,
      "dateRange": "{'end': {'mode': 'absolute', 'value': '2025-04-07 08:56:54'}, 'start': {'mode': 'absolute', 'value': '2025-04-01 00:00:00'}}",
      "source": "string",
      "idExtra": "string",
      "userComment": "string",
      "idSourceEvent": 0,
      "serverId": [
        0
      ],
      "customData": "string",
      "customDataFilterType": "only_alert_events",
      "ownerUser": "string",
      "privateFilterUser": "string",
      "regex": "string"
    }
    ```

### Model: EventTag { #model-eventtag }

| Field | Type | Required | Description |
|---|---|---|---|
| `idEventTag` | integer |  | Id event tag |
| `title` | string |  | Title of the event tag |
| `description` | string, nullable |  | Description of the event tag |
| `backgroundColor` | string |  | Background color hex code (e.g. #FFFFFF) |
| `textColor` | string |  | Text color hex code (e.g. #000000) |
| `createdAt` | string, nullable |  | Creation date |
| `updatedAt` | string, nullable |  | Last update date |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "title": "string",
      "description": "string",
      "backgroundColor": "#FFFFFF",
      "textColor": "#000000"
    }
    ```

### Model: FederatedEvent { #model-federatedevent }

??? note "Fields (26 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `serverId` | integer, nullable |  | Console that owns the resource |
    | `idEvent` | integer |  | Id event |
    | `idAgent` | integer, nullable |  | Id agent |
    | `idUser` | string, nullable |  | Id user |
    | `idGroup` | integer, nullable |  | Id group |
    | `status` | enum: `new`, `validated`, `inprocess` |  | Event status, the available status are: new, validated, inprocess |
    | `timestamp` | string, nullable |  | Event registration date |
    | `event` | string |  | Description event |
    | `utimestamp` | integer, nullable |  | Event registration date |
    | `eventType` | enum: `going_unknown`, `unknown`, `alert_fired`, `alert_recovered`, `alert_ceased`, `alert_manual_validation`, `recon_host_detected`, `system`, `error`, `new_agent`, `going_up_critical`, `going_down_critical`, `going_up_warning`, `going_down_warning`, `going_up_normal`, `going_down_normal`, `configuration_change`, `ncm` |  | Event status, the available status are: going_unknown, unknown, alert_fired, alert_recovered, alert_ceased, alert_manual_validation, recon_host_detected, system, error, new_agent, going_up_critical, going_down_critical, going_up_warning, going_down_warning, going_up_normal, going_down_normal, configuration_change, ncm |
    | `idAgentModule` | integer, nullable |  | Id agent module |
    | `idAlertAm` | integer, nullable |  | Id alert action |
    | `severity` | enum: `maintenance`, `informational`, `normal`, `warning`, `critical`, `minor`, `major` |  | Event severity, the available severity are: maintenance, informational, normal, warning, critical, minor, major |
    | `tags` | string, nullable |  | Tags |
    | `source` | string, nullable |  | Source |
    | `idExtra` | string, nullable |  | Extra id |
    | `criticalInstructions` | string, nullable |  | Critical instructions |
    | `warningInstructions` | string, nullable |  | Warning instructions |
    | `unknownInstructions` | string, nullable |  | Unknows instructions |
    | `defaultInstructions` | string, nullable |  | Default instructions, will be use when Critical/Warning/Unknown are empty |
    | `ownerUser` | string, nullable |  | Id user |
    | `ackUtimestamp` | integer, nullable |  | Event ack utimestamp |
    | `customData` | string, nullable |  | Custom data |
    | `data` | string, nullable |  | Data |
    | `moduleStatus` | integer, nullable |  | Module status |
    | `eventCustomId` | string, nullable |  | Events Custom Id |


### Model: FederatedEventAlertAction { #model-federatedeventalertaction }

??? note "Fields (8 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `serverId` | integer, nullable |  | Console that owns the resource |
    | `idEventAlertAction` | integer |  |  |
    | `idEventAlert` | integer |  |  |
    | `idAlertAction` | integer |  |  |
    | `firesMin` | integer |  |  |
    | `firesMax` | integer |  |  |
    | `moduleActionThreshold` | integer |  |  |
    | `lastExecution` | integer |  |  |


### Model: FederatedEventAlertRule { #model-federatedeventalertrule }

??? note "Fields (33 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `serverId` | integer, nullable |  | Console that owns the resource |
    | `idEventRule` | integer |  |  |
    | `idEventAlert` | integer |  |  |
    | `operation` | enum: `NOP`, `AND`, `OR`, `XOR`, `NAND`, `NOR`, `NXOR` |  |  |
    | `order` | integer |  |  |
    | `window` | integer |  |  |
    | `count` | integer |  |  |
    | `agent` | string, nullable |  |  |
    | `idUser` | string, nullable |  |  |
    | `idGroup` | string, nullable |  |  |
    | `event` | string, nullable |  |  |
    | `eventType` | string, nullable |  |  |
    | `module` | string, nullable |  |  |
    | `alert` | string, nullable |  |  |
    | `criticity` | string, nullable |  |  |
    | `idTag` | string, nullable |  |  |
    | `name` | string, nullable |  |  |
    | `groupRecursion` | string, nullable |  |  |
    | `logContent` | string, nullable |  |  |
    | `logSource` | string, nullable |  |  |
    | `logAgent` | string, nullable |  |  |
    | `operatorAgent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `operatorIdUser` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `operatorIdGroup` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `operatorEvent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `operatorEventType` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `operatorModule` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `operatorAlert` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `operatorCriticity` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `operatorIdTag` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `operatorLogContent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `operatorLogSource` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |
    | `operatorLogAgent` | enum: `>`, `<`, `>=`, `<=`, `==`, `!=`, `REGEX`, `NOT REGEX` |  |  |


### Model: FederatedEventComment { #model-federatedeventcomment }

??? note "Fields (7 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `serverId` | integer, nullable |  | Console that owns the resource |
    | `idEventComment` | integer |  | id event comment |
    | `idEvent` | integer |  | id event comment |
    | `utimestamp` | integer, nullable |  | Event comment utimestamp create |
    | `comment` | string |  | content of the comment |
    | `idUser` | string |  | User id create comment |
    | `action` | string |  | content of the action |


### Model: FederatedEventTagRelation { #model-federatedeventtagrelation }

??? note "Fields (4 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `serverId` | integer, nullable |  | Console that owns the resource |
    | `idEventTagRelation` | integer |  | Id EventTagRelation |
    | `idEvent` | integer, nullable |  | Id of the Event |
    | `idEventTag` | integer, nullable |  | Id of the EventTag |
