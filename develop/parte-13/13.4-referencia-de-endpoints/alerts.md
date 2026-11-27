# Alerts

Alert templates, actions, commands, calendars and special days, module alerts and the alert queues.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-get">GET</span> | [`/alert/summary`](#get-alert-summary) | Alert counters |
| <span class="api-method api-post">POST</span> | [`/alert/template/{idAlertTemplate}/copy`](#post-alert-template-idalerttemplate-copy) | Copy an alert template |
| <span class="api-method api-post">POST</span> | [`/alert/template`](#post-alert-template) | Create an alert template |
| <span class="api-method api-get">GET</span> | [`/alert/template/{idAlertTemplate}`](#get-alert-template-idalerttemplate) | Get an alert template |
| <span class="api-method api-put">PUT</span> | [`/alert/template/{idAlertTemplate}`](#put-alert-template-idalerttemplate) | Update an alert template |
| <span class="api-method api-delete">DELETE</span> | [`/alert/template/{idAlertTemplate}`](#delete-alert-template-idalerttemplate) | Delete an alert template |
| <span class="api-method api-post">POST</span> | [`/alert/template/list`](#post-alert-template-list) | List alert templates |
| <span class="api-method api-post">POST</span> | [`/alert/action/{idAlertAction}/copy`](#post-alert-action-idalertaction-copy) | Copy an alert action |
| <span class="api-method api-post">POST</span> | [`/alert/action`](#post-alert-action) | Create an alert action |
| <span class="api-method api-get">GET</span> | [`/alert/action/{idAlertAction}`](#get-alert-action-idalertaction) | Get an alert action |
| <span class="api-method api-put">PUT</span> | [`/alert/action/{idAlertAction}`](#put-alert-action-idalertaction) | Update an alert action |
| <span class="api-method api-delete">DELETE</span> | [`/alert/action/{idAlertAction}`](#delete-alert-action-idalertaction) | Delete an alert action |
| <span class="api-method api-get">GET</span> | [`/alert/action/list`](#get-alert-action-list) | List alert actions using query parameters |
| <span class="api-method api-post">POST</span> | [`/alert/action/list`](#post-alert-action-list) | List alert actions |
| <span class="api-method api-post">POST</span> | [`/alert/command/{idAlertCommand}/copy`](#post-alert-command-idalertcommand-copy) | copyAlertCommand |
| <span class="api-method api-post">POST</span> | [`/alert/command`](#post-alert-command) | createAlertCommand |
| <span class="api-method api-get">GET</span> | [`/alert/command/{idAlertCommand}`](#get-alert-command-idalertcommand) | getAlertCommand |
| <span class="api-method api-put">PUT</span> | [`/alert/command/{idAlertCommand}`](#put-alert-command-idalertcommand) | updateAlertCommand |
| <span class="api-method api-delete">DELETE</span> | [`/alert/command/{idAlertCommand}`](#delete-alert-command-idalertcommand) | deleteAlertCommand |
| <span class="api-method api-get">GET</span> | [`/alert/command/list`](#get-alert-command-list) | listAlertCommandsGet |
| <span class="api-method api-post">POST</span> | [`/alert/command/list`](#post-alert-command-list) | listAlertCommands |
| <span class="api-method api-post">POST</span> | [`/alert/calendar`](#post-alert-calendar) | createAlertCalendar |
| <span class="api-method api-get">GET</span> | [`/alert/calendar/{idAlertCalendar}`](#get-alert-calendar-idalertcalendar) | getAlertCalendar |
| <span class="api-method api-put">PUT</span> | [`/alert/calendar/{idAlertCalendar}`](#put-alert-calendar-idalertcalendar) | updateAlertCalendar |
| <span class="api-method api-delete">DELETE</span> | [`/alert/calendar/{idAlertCalendar}`](#delete-alert-calendar-idalertcalendar) | deleteAlertCalendar |
| <span class="api-method api-get">GET</span> | [`/alert/calendar/list`](#get-alert-calendar-list) | listAlertCalendarsGet |
| <span class="api-method api-post">POST</span> | [`/alert/calendar/list`](#post-alert-calendar-list) | listAlertCalendars |
| <span class="api-method api-post">POST</span> | [`/alert/calendar/{idAlertCalendar}/special-day`](#post-alert-calendar-idalertcalendar-special-day) | createAlertSpecialDay |
| <span class="api-method api-get">GET</span> | [`/alert/calendar/{idAlertCalendar}/special-day/{idAlertSpecialDay}`](#get-alert-calendar-idalertcalendar-special-day-idalertspecialday) | getAlertSpecialDay |
| <span class="api-method api-put">PUT</span> | [`/alert/calendar/{idAlertCalendar}/special-day/{idAlertSpecialDay}`](#put-alert-calendar-idalertcalendar-special-day-idalertspecialday) | updateAlertSpecialDay |
| <span class="api-method api-delete">DELETE</span> | [`/alert/calendar/{idAlertCalendar}/special-day/{idAlertSpecialDay}`](#delete-alert-calendar-idalertcalendar-special-day-idalertspecialday) | deleteAlertSpecialDay |
| <span class="api-method api-get">GET</span> | [`/alert/calendar/{idAlertCalendar}/special-day/list`](#get-alert-calendar-idalertcalendar-special-day-list) | listAlertSpecialDaysGet |
| <span class="api-method api-post">POST</span> | [`/alert/calendar/{idAlertCalendar}/special-day/list`](#post-alert-calendar-idalertcalendar-special-day-list) | listAlertSpecialDays |
| <span class="api-method api-post">POST</span> | [`/agentModule/{idAgentModule}/alert`](#post-agentmodule-idagentmodule-alert) | createAgentModuleAlert |
| <span class="api-method api-get">GET</span> | [`/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}`](#get-agentmodule-idagentmodule-alert-idagentmodulealert) | getAgentModuleAlert |
| <span class="api-method api-put">PUT</span> | [`/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}`](#put-agentmodule-idagentmodule-alert-idagentmodulealert) | updateAgentModuleAlert |
| <span class="api-method api-delete">DELETE</span> | [`/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}`](#delete-agentmodule-idagentmodule-alert-idagentmodulealert) | deleteAgentModuleAlert |
| <span class="api-method api-get">GET</span> | [`/agentModule/{idAgentModule}/alert/list`](#get-agentmodule-idagentmodule-alert-list) | listAgentModuleAlertsByGet |
| <span class="api-method api-post">POST</span> | [`/agentModule/{idAgentModule}/alert/list`](#post-agentmodule-idagentmodule-alert-list) | listAgentModuleAlerts |
| <span class="api-method api-get">GET</span> | [`/agentModule/alert/list`](#get-agentmodule-alert-list) | listGlobalAgentModuleAlertsByGet |
| <span class="api-method api-post">POST</span> | [`/agentModule/alert/list`](#post-agentmodule-alert-list) | listGlobalAgentModuleAlerts |
| <span class="api-method api-post">POST</span> | [`/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}/action`](#post-agentmodule-idagentmodule-alert-idagentmodulealert-action) | createAgentModuleAlertAction |
| <span class="api-method api-get">GET</span> | [`/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}/action/{idAgentModuleAlertAction}`](#get-agentmodule-idagentmodule-alert-idagentmodulealert-action-idagentmodulealertaction) | getAgentModuleAlertAction |
| <span class="api-method api-put">PUT</span> | [`/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}/action/{idAgentModuleAlertAction}`](#put-agentmodule-idagentmodule-alert-idagentmodulealert-action-idagentmodulealertaction) | updateAgentModuleAlertAction |
| <span class="api-method api-delete">DELETE</span> | [`/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}/action/{idAgentModuleAlertAction}`](#delete-agentmodule-idagentmodule-alert-idagentmodulealert-action-idagentmodulealertaction) | deleteAgentModuleAlertAction |
| <span class="api-method api-get">GET</span> | [`/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}/action/list`](#get-agentmodule-idagentmodule-alert-idagentmodulealert-action-list) | getAgentModuleAlertActions |
| <span class="api-method api-post">POST</span> | [`/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}/action/list`](#post-agentmodule-idagentmodule-alert-idagentmodulealert-action-list) | listAgentModuleAlertActions |
| <span class="api-method api-get">GET</span> | [`/alert/executionQueue/{idAlertExecutionQueue}`](#get-alert-executionqueue-idalertexecutionqueue) | Get an alert execution queue entry |
| <span class="api-method api-get">GET</span> | [`/alert/executionQueue/list`](#get-alert-executionqueue-list) | List alert execution queue entries |
| <span class="api-method api-post">POST</span> | [`/alert/executionQueue/list`](#post-alert-executionqueue-list) | List alert execution queue entries |
| <span class="api-method api-get">GET</span> | [`/alert/fired/{idAlertFired}`](#get-alert-fired-idalertfired) | Get an alert fired history entry |
| <span class="api-method api-get">GET</span> | [`/alert/fired/list`](#get-alert-fired-list) | List alert fired history |
| <span class="api-method api-post">POST</span> | [`/alert/fired/list`](#post-alert-fired-list) | List alert fired history |

## Alerts

### <span class="api-method api-get">GET</span> `/alert/summary` { #get-alert-summary }

Alert counters

**Response 200**: Alert summary

??? note "Response fields (2 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `configured` | integer |  |  |
    | `fired` | integer |  |  |


Error responses: `401`, `403`, `500`.

## AlertTemplates

API Endpoints for alert templates

### <span class="api-method api-post">POST</span> `/alert/template/{idAlertTemplate}/copy` { #post-alert-template-idalerttemplate-copy }

Copy an alert template

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertTemplate` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string |  |  |
| `idGroup` | integer |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idGroup": 0
    }
    ```

**Response 200**: Alert template

Schema: [`AlertTemplateResponse`](#model-alerttemplateresponse)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-post">POST</span> `/alert/template` { #post-alert-template }

Create an alert template

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAlertTemplate` | integer |  |  |
| `name` | string | yes |  |
| `description` | string, nullable |  |  |
| `idAlertAction` | integer, nullable |  |  |
| `fields` | array of string |  |  |
| `recoveryFields` | array of string |  |  |
| `type` | enum: `regex`, `max_min`, `max`, `min`, `equal`, `not_equal`, `warning`, `critical`, `onchange`, `unknown`, `always`, `not_normal`, `complex` |  |  |
| `value` | string, nullable |  |  |
| `matchesValue` | boolean |  |  |
| `maxValue` | number, nullable |  |  |
| `minValue` | number, nullable |  |  |
| `timeWindow` | enum: `thirty_days`, `this_month`, `seven_days`, `this_week`, `one_day`, `today` |  |  |
| `mathFunction` | enum: `avg`, `min`, `max`, `sum` |  |  |
| `condition` | enum: `lower`, `greater`, `equal` |  |  |
| `timeThreshold` | integer |  |  |
| `maxAlerts` | integer |  |  |
| `minAlerts` | integer |  |  |
| `timeFrom` | string (time) |  |  |
| `timeTo` | string (time) |  |  |
| `monday` | boolean |  |  |
| `tuesday` | boolean |  |  |
| `wednesday` | boolean |  |  |
| `thursday` | boolean |  |  |
| `friday` | boolean |  |  |
| `saturday` | boolean |  |  |
| `sunday` | boolean |  |  |
| `recoveryNotify` | boolean |  |  |
| `priority` | integer |  |  |
| `idGroup` | integer |  |  |
| `specialDay` | integer |  | Alert calendar identifier; 0 disables special days |
| `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  |  |
| `minAlertsResetCounter` | boolean |  |  |
| `disableEvent` | boolean |  |  |
| `schedule` | object, nullable |  |  |
| `recoveryOnNormalStatus` | boolean |  |  |
| `isInternal` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idAlertAction": 0,
      "fields": [
        "string"
      ],
      "recoveryFields": [
        "string"
      ],
      "type": "regex",
      "value": "string",
      "matchesValue": true,
      "maxValue": 0,
      "minValue": 0,
      "timeWindow": "thirty_days",
      "mathFunction": "avg",
      "condition": "lower",
      "timeThreshold": 86400,
      "maxAlerts": 1,
      "minAlerts": 0,
      "timeFrom": "00:00:00",
      "timeTo": "00:00:00",
      "monday": false,
      "tuesday": false,
      "wednesday": false,
      "thursday": false,
      "friday": false,
      "saturday": false,
      "sunday": false,
      "recoveryNotify": false,
      "priority": 1,
      "idGroup": 0,
      "specialDay": 0,
      "wizardLevel": "basic",
      "minAlertsResetCounter": false,
      "disableEvent": false,
      "schedule": {},
      "recoveryOnNormalStatus": false
    }
    ```

**Response 200**: Alert template

Schema: [`AlertTemplateResponse`](#model-alerttemplateresponse)

Error responses: `400`, `401`, `403`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/alert/template/{idAlertTemplate}` { #get-alert-template-idalerttemplate }

Get an alert template

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertTemplate` | path | integer | yes |  |

**Response 200**: Alert template

Schema: [`AlertTemplateResponse`](#model-alerttemplateresponse)

Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/alert/template/{idAlertTemplate}` { #put-alert-template-idalerttemplate }

Update an alert template

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertTemplate` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAlertTemplate` | integer |  |  |
| `name` | string |  |  |
| `description` | string, nullable |  |  |
| `idAlertAction` | integer, nullable |  |  |
| `fields` | array of string |  |  |
| `recoveryFields` | array of string |  |  |
| `type` | enum: `regex`, `max_min`, `max`, `min`, `equal`, `not_equal`, `warning`, `critical`, `onchange`, `unknown`, `always`, `not_normal`, `complex` |  |  |
| `value` | string, nullable |  |  |
| `matchesValue` | boolean |  |  |
| `maxValue` | number, nullable |  |  |
| `minValue` | number, nullable |  |  |
| `timeWindow` | enum: `thirty_days`, `this_month`, `seven_days`, `this_week`, `one_day`, `today` |  |  |
| `mathFunction` | enum: `avg`, `min`, `max`, `sum` |  |  |
| `condition` | enum: `lower`, `greater`, `equal` |  |  |
| `timeThreshold` | integer |  |  |
| `maxAlerts` | integer |  |  |
| `minAlerts` | integer |  |  |
| `timeFrom` | string (time) |  |  |
| `timeTo` | string (time) |  |  |
| `monday` | boolean |  |  |
| `tuesday` | boolean |  |  |
| `wednesday` | boolean |  |  |
| `thursday` | boolean |  |  |
| `friday` | boolean |  |  |
| `saturday` | boolean |  |  |
| `sunday` | boolean |  |  |
| `recoveryNotify` | boolean |  |  |
| `priority` | integer |  |  |
| `idGroup` | integer |  |  |
| `specialDay` | integer |  | Alert calendar identifier; 0 disables special days |
| `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  |  |
| `minAlertsResetCounter` | boolean |  |  |
| `disableEvent` | boolean |  |  |
| `schedule` | object, nullable |  |  |
| `recoveryOnNormalStatus` | boolean |  |  |
| `isInternal` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idAlertAction": 0,
      "fields": [
        "string"
      ],
      "recoveryFields": [
        "string"
      ],
      "type": "regex",
      "value": "string",
      "matchesValue": true,
      "maxValue": 0,
      "minValue": 0,
      "timeWindow": "thirty_days",
      "mathFunction": "avg",
      "condition": "lower",
      "timeThreshold": 86400,
      "maxAlerts": 1,
      "minAlerts": 0,
      "timeFrom": "00:00:00",
      "timeTo": "00:00:00",
      "monday": false,
      "tuesday": false,
      "wednesday": false,
      "thursday": false,
      "friday": false,
      "saturday": false,
      "sunday": false,
      "recoveryNotify": false,
      "priority": 1,
      "idGroup": 0,
      "specialDay": 0,
      "wizardLevel": "basic",
      "minAlertsResetCounter": false,
      "disableEvent": false,
      "schedule": {},
      "recoveryOnNormalStatus": false
    }
    ```

**Response 200**: Alert template

Schema: [`AlertTemplateResponse`](#model-alerttemplateresponse)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-delete">DELETE</span> `/alert/template/{idAlertTemplate}` { #delete-alert-template-idalerttemplate }

Delete an alert template

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertTemplate` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-post">POST</span> `/alert/template/list` { #post-alert-template-list }

List alert templates

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAlertTemplate` | integer |  |  |
| `name` | string |  |  |
| `description` | string, nullable |  |  |
| `idAlertAction` | integer, nullable |  |  |
| `fields` | array of string |  |  |
| `recoveryFields` | array of string |  |  |
| `type` | enum: `regex`, `max_min`, `max`, `min`, `equal`, `not_equal`, `warning`, `critical`, `onchange`, `unknown`, `always`, `not_normal`, `complex` |  |  |
| `value` | string, nullable |  |  |
| `matchesValue` | boolean |  |  |
| `maxValue` | number, nullable |  |  |
| `minValue` | number, nullable |  |  |
| `timeWindow` | enum: `thirty_days`, `this_month`, `seven_days`, `this_week`, `one_day`, `today` |  |  |
| `mathFunction` | enum: `avg`, `min`, `max`, `sum` |  |  |
| `condition` | enum: `lower`, `greater`, `equal` |  |  |
| `timeThreshold` | integer |  |  |
| `maxAlerts` | integer |  |  |
| `minAlerts` | integer |  |  |
| `timeFrom` | string (time) |  |  |
| `timeTo` | string (time) |  |  |
| `monday` | boolean |  |  |
| `tuesday` | boolean |  |  |
| `wednesday` | boolean |  |  |
| `thursday` | boolean |  |  |
| `friday` | boolean |  |  |
| `saturday` | boolean |  |  |
| `sunday` | boolean |  |  |
| `recoveryNotify` | boolean |  |  |
| `priority` | integer |  |  |
| `idGroup` | integer |  |  |
| `specialDay` | integer |  | Alert calendar identifier; 0 disables special days |
| `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  |  |
| `minAlertsResetCounter` | boolean |  |  |
| `disableEvent` | boolean |  |  |
| `schedule` | object, nullable |  |  |
| `recoveryOnNormalStatus` | boolean |  |  |
| `isInternal` | boolean |  |  |
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
| `multipleSearch.field` | enum: `idAlertTemplate`, `name`, `description`, `idAlertAction`, `type`, `value`, `matchesValue`, `maxValue`, `minValue`, `timeWindow`, `mathFunction`, `condition`, `timeThreshold`, `maxAlerts`, `minAlerts`, `priority`, `idGroup`, `wizardLevel`, `isInternal` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAlertTemplate`, `name`, `description`, `idAlertAction`, `type`, `value`, `matchesValue`, `maxValue`, `minValue`, `timeWindow`, `mathFunction`, `condition`, `timeThreshold`, `maxAlerts`, `minAlerts`, `priority`, `idGroup`, `wizardLevel`, `isInternal` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "idAlertAction": 0,
      "fields": [
        "string"
      ],
      "recoveryFields": [
        "string"
      ],
      "type": "regex",
      "value": "string",
      "matchesValue": true,
      "maxValue": 0,
      "minValue": 0,
      "timeWindow": "thirty_days",
      "mathFunction": "avg",
      "condition": "lower",
      "timeThreshold": 86400,
      "maxAlerts": 1,
      "minAlerts": 0,
      "timeFrom": "00:00:00",
      "timeTo": "00:00:00",
      "monday": false,
      "tuesday": false,
      "wednesday": false,
      "thursday": false,
      "friday": false,
      "saturday": false,
      "sunday": false,
      "recoveryNotify": false,
      "priority": 1,
      "idGroup": 0,
      "specialDay": 0,
      "wizardLevel": "basic",
      "minAlertsResetCounter": false,
      "disableEvent": false,
      "schedule": {},
      "recoveryOnNormalStatus": false,
      "freeSearch": "string",
      "requestedFields": [
        "idAlertTemplate"
      ],
      "fieldConditions": [
        {
          "field": "idAlertTemplate",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idAlertTemplate",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAlertTemplate",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Alert template list

??? note "Response fields (46 fields)"

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
    | `data.[].idAlertTemplate` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].idAlertAction` | integer, nullable |  |  |
    | `data.[].fields` | array of string |  |  |
    | `data.[].recoveryFields` | array of string |  |  |
    | `data.[].type` | enum: `regex`, `max_min`, `max`, `min`, `equal`, `not_equal`, `warning`, `critical`, `onchange`, `unknown`, `always`, `not_normal`, `complex` |  |  |
    | `data.[].value` | string, nullable |  |  |
    | `data.[].matchesValue` | boolean |  |  |
    | `data.[].maxValue` | number, nullable |  |  |
    | `data.[].minValue` | number, nullable |  |  |
    | `data.[].timeWindow` | enum: `thirty_days`, `this_month`, `seven_days`, `this_week`, `one_day`, `today` |  |  |
    | `data.[].mathFunction` | enum: `avg`, `min`, `max`, `sum` |  |  |
    | `data.[].condition` | enum: `lower`, `greater`, `equal` |  |  |
    | `data.[].timeThreshold` | integer |  |  |
    | `data.[].maxAlerts` | integer |  |  |
    | `data.[].minAlerts` | integer |  |  |
    | `data.[].timeFrom` | string (time) |  |  |
    | `data.[].timeTo` | string (time) |  |  |
    | `data.[].monday` | boolean |  |  |
    | `data.[].tuesday` | boolean |  |  |
    | `data.[].wednesday` | boolean |  |  |
    | `data.[].thursday` | boolean |  |  |
    | `data.[].friday` | boolean |  |  |
    | `data.[].saturday` | boolean |  |  |
    | `data.[].sunday` | boolean |  |  |
    | `data.[].recoveryNotify` | boolean |  |  |
    | `data.[].priority` | integer |  |  |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].specialDay` | integer |  | Alert calendar identifier; 0 disables special days |
    | `data.[].wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  |  |
    | `data.[].minAlertsResetCounter` | boolean |  |  |
    | `data.[].disableEvent` | boolean |  |  |
    | `data.[].schedule` | object, nullable |  |  |
    | `data.[].recoveryOnNormalStatus` | boolean |  |  |
    | `data.[].isInternal` | boolean |  |  |


Error responses: `400`, `401`, `403`, `500`.

## AlertActions

API Endpoints for alert actions

### <span class="api-method api-post">POST</span> `/alert/action/{idAlertAction}/copy` { #post-alert-action-idalertaction-copy }

Copy an alert action

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertAction` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string"
    }
    ```

**Response 200**: Alert action object

Schema: [`AlertActionResponse`](#model-alertactionresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/alert/action` { #post-alert-action }

Create an alert action

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string | yes |  |
| `idAlertCommand` | integer | yes |  |
| `idGroup` | integer |  |  |
| `actionThreshold` | integer |  |  |
| `fields` | array of string |  |  |
| `recoveryFields` | array of string |  |  |
| `createWorkunitInItsm` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idAlertCommand": 0,
      "idGroup": 0,
      "actionThreshold": 0,
      "fields": [],
      "recoveryFields": [],
      "createWorkunitInItsm": false
    }
    ```

**Response 200**: Alert action object

Schema: [`AlertActionResponse`](#model-alertactionresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/alert/action/{idAlertAction}` { #get-alert-action-idalertaction }

Get an alert action

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertAction` | path | integer | yes |  |

**Response 200**: Alert action object

Schema: [`AlertActionResponse`](#model-alertactionresponse)

Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/alert/action/{idAlertAction}` { #put-alert-action-idalertaction }

Update an alert action

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertAction` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string |  |  |
| `idAlertCommand` | integer |  |  |
| `idGroup` | integer |  |  |
| `actionThreshold` | integer |  |  |
| `fields` | array of string |  |  |
| `recoveryFields` | array of string |  |  |
| `createWorkunitInItsm` | boolean, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idAlertCommand": 0,
      "idGroup": 0,
      "actionThreshold": 0,
      "fields": [
        "string"
      ],
      "recoveryFields": [
        "string"
      ],
      "createWorkunitInItsm": false
    }
    ```

**Response 200**: Alert action object

Schema: [`AlertActionResponse`](#model-alertactionresponse)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/alert/action/{idAlertAction}` { #delete-alert-action-idalertaction }

Delete an alert action

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertAction` | path | integer | yes |  |

**Response 200**: Alert action deleted

Error responses: `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/alert/action/list` { #get-alert-action-list }

List alert actions using query parameters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Alert action list

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
    | `data.[].idAlertAction` | integer | yes |  |
    | `data.[].name` | string | yes |  |
    | `data.[].idAlertCommand` | integer | yes |  |
    | `data.[].idGroup` | integer | yes |  |
    | `data.[].actionThreshold` | integer | yes |  |
    | `data.[].fields` | array of string | yes |  |
    | `data.[].recoveryFields` | array of string | yes |  |
    | `data.[].createWorkunitInItsm` | boolean, nullable |  |  |
    | `data.[].isDefault` | boolean | yes |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/alert/action/list` { #post-alert-action-list }

List alert actions

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAlertAction` | integer | yes |  |
| `name` | string | yes |  |
| `idAlertCommand` | integer | yes |  |
| `idGroup` | integer | yes |  |
| `actionThreshold` | integer | yes |  |
| `fields` | array of string | yes |  |
| `recoveryFields` | array of string | yes |  |
| `createWorkunitInItsm` | boolean, nullable |  |  |
| `isDefault` | boolean | yes |  |
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
| `multipleSearch.field` | enum: `idAlertAction`, `name`, `idAlertCommand`, `idGroup`, `actionThreshold`, `createWorkunitInItsm`, `isDefault` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAlertAction`, `name`, `idAlertCommand`, `idGroup`, `actionThreshold`, `createWorkunitInItsm`, `isDefault` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idAlertCommand": 0,
      "idGroup": 0,
      "actionThreshold": 0,
      "fields": [
        "string"
      ],
      "recoveryFields": [
        "string"
      ],
      "createWorkunitInItsm": false,
      "freeSearch": "string",
      "requestedFields": [
        "idAlertAction"
      ],
      "fieldConditions": [
        {
          "field": "idAlertAction",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idAlertAction",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAlertAction",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Alert action list

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
    | `data.[].idAlertAction` | integer | yes |  |
    | `data.[].name` | string | yes |  |
    | `data.[].idAlertCommand` | integer | yes |  |
    | `data.[].idGroup` | integer | yes |  |
    | `data.[].actionThreshold` | integer | yes |  |
    | `data.[].fields` | array of string | yes |  |
    | `data.[].recoveryFields` | array of string | yes |  |
    | `data.[].createWorkunitInItsm` | boolean, nullable |  |  |
    | `data.[].isDefault` | boolean | yes |  |


Error responses: `400`, `401`, `403`, `500`.

## AlertCommands

API Endpoints for alert commands

### <span class="api-method api-post">POST</span> `/alert/command/{idAlertCommand}/copy` { #post-alert-command-idalertcommand-copy }

copyAlertCommand

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCommand` | path | integer | yes |  |

**Response 200**: Detailed alert command

Schema: [`AlertCommand`](#model-alertcommand)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/alert/command` { #post-alert-command }

createAlertCommand

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string | yes |  |
| `command` | string | yes |  |
| `idGroup` | integer |  |  |
| `description` | string, nullable |  |  |
| `fieldDescriptions` | array of string |  |  |
| `fieldValues` | array of string |  |  |
| `fieldHidden` | array of boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "command": "string",
      "idGroup": 0,
      "description": "string",
      "fieldDescriptions": [
        "string"
      ],
      "fieldValues": [
        "string"
      ],
      "fieldHidden": [
        false
      ]
    }
    ```

**Response 200**: Detailed alert command

Schema: [`AlertCommand`](#model-alertcommand)

Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-get">GET</span> `/alert/command/{idAlertCommand}` { #get-alert-command-idalertcommand }

getAlertCommand

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCommand` | path | integer | yes |  |

**Response 200**: Detailed alert command

Schema: [`AlertCommand`](#model-alertcommand)

Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/alert/command/{idAlertCommand}` { #put-alert-command-idalertcommand }

updateAlertCommand

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCommand` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string |  |  |
| `command` | string |  |  |
| `idGroup` | integer |  |  |
| `description` | string, nullable |  |  |
| `fieldDescriptions` | array of string |  |  |
| `fieldValues` | array of string |  |  |
| `fieldHidden` | array of boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "command": "string",
      "idGroup": 0,
      "description": "string",
      "fieldDescriptions": [
        "string"
      ],
      "fieldValues": [
        "string"
      ],
      "fieldHidden": [
        false
      ]
    }
    ```

**Response 200**: Detailed alert command

Schema: [`AlertCommand`](#model-alertcommand)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/alert/command/{idAlertCommand}` { #delete-alert-command-idalertcommand }

deleteAlertCommand

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCommand` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/alert/command/list` { #get-alert-command-list }

listAlertCommandsGet

**Response 200**: Alert command summary list without command or fieldValues

Schema: [`AlertCommandListResponse`](#model-alertcommandlistresponse)

Error responses: `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/alert/command/list` { #post-alert-command-list }

listAlertCommands

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAlertCommand` | integer | yes | Alert command identifier |
| `name` | string | yes | Unique alert command name |
| `command` | string, nullable |  | Executable command template. Returned only by detailed endpoints requiring PM permission |
| `idGroup` | integer | yes | Owning group, or 0 for All |
| `description` | string, nullable |  | Alert command description |
| `internal` | boolean | yes | Whether this is a protected built-in command |
| `fieldDescriptions` | array of string | yes |  |
| `fieldValues` | array, nullable |  | Macro defaults. Returned only by detailed endpoints requiring PM permission |
| `fieldHidden` | array of boolean | yes |  |
| `freeSearch` | string, nullable |  | Search in name and description |
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
| `multipleSearch.field` | enum: `idAlertCommand`, `name`, `idGroup`, `description`, `internal` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAlertCommand`, `name`, `idGroup`, `description`, `internal` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "command": "string",
      "idGroup": 0,
      "description": "string",
      "fieldDescriptions": [
        "string"
      ],
      "fieldValues": [
        "string"
      ],
      "fieldHidden": [
        false
      ],
      "freeSearch": "string",
      "requestedFields": [
        "idAlertCommand"
      ],
      "fieldConditions": [
        {
          "field": "idAlertCommand",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idAlertCommand",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAlertCommand",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Alert command summary list without command or fieldValues

Schema: [`AlertCommandListResponse`](#model-alertcommandlistresponse)

Error responses: `400`, `401`, `403`, `500`.

## AlertCalendars

API Endpoints for alert calendars

### <span class="api-method api-post">POST</span> `/alert/calendar` { #post-alert-calendar }

createAlertCalendar

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string | yes |  |
| `idGroup` | integer |  |  |
| `description` | string, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idGroup": 0,
      "description": "string"
    }
    ```

**Response 200**: Alert calendar

Schema: [`AlertCalendar`](#model-alertcalendar)

Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-get">GET</span> `/alert/calendar/{idAlertCalendar}` { #get-alert-calendar-idalertcalendar }

getAlertCalendar

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCalendar` | path | integer | yes |  |

**Response 200**: Alert calendar

Schema: [`AlertCalendar`](#model-alertcalendar)

Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/alert/calendar/{idAlertCalendar}` { #put-alert-calendar-idalertcalendar }

updateAlertCalendar

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCalendar` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | string |  |  |
| `idGroup` | integer |  |  |
| `description` | string, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idGroup": 0,
      "description": "string"
    }
    ```

**Response 200**: Alert calendar

Schema: [`AlertCalendar`](#model-alertcalendar)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/alert/calendar/{idAlertCalendar}` { #delete-alert-calendar-idalertcalendar }

deleteAlertCalendar

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCalendar` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/alert/calendar/list` { #get-alert-calendar-list }

listAlertCalendarsGet

**Response 200**: Alert calendar list

Schema: [`AlertCalendarListResponse`](#model-alertcalendarlistresponse)

Error responses: `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/alert/calendar/list` { #post-alert-calendar-list }

listAlertCalendars

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAlertCalendar` | integer | yes |  |
| `name` | string | yes |  |
| `idGroup` | integer | yes |  |
| `description` | string, nullable |  |  |
| `freeSearch` | string, nullable |  | Search in name and description |
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
| `multipleSearch.field` | enum: `idAlertCalendar`, `name`, `idGroup`, `description` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAlertCalendar`, `name`, `idGroup`, `description` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idGroup": 0,
      "description": "string",
      "freeSearch": "string",
      "requestedFields": [
        "idAlertCalendar"
      ],
      "fieldConditions": [
        {
          "field": "idAlertCalendar",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idAlertCalendar",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAlertCalendar",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Alert calendar list

Schema: [`AlertCalendarListResponse`](#model-alertcalendarlistresponse)

Error responses: `400`, `401`, `403`, `500`.

## AlertSpecialDays

API Endpoints for alert special days

### <span class="api-method api-post">POST</span> `/alert/calendar/{idAlertCalendar}/special-day` { #post-alert-calendar-idalertcalendar-special-day }

createAlertSpecialDay

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCalendar` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idGroup` | integer |  |  |
| `date` | string (date) | yes |  |
| `dayCode` | integer | yes |  |
| `description` | string, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroup": 0,
      "date": "string",
      "dayCode": 0,
      "description": "string"
    }
    ```

**Response 200**: Alert special day created

Schema: [`AlertSpecialDay`](#model-alertspecialday)

Error responses: `400`, `401`, `403`, `404`, `409`, `500`.

### <span class="api-method api-get">GET</span> `/alert/calendar/{idAlertCalendar}/special-day/{idAlertSpecialDay}` { #get-alert-calendar-idalertcalendar-special-day-idalertspecialday }

getAlertSpecialDay

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCalendar` | path | integer | yes |  |
| `idAlertSpecialDay` | path | integer | yes |  |

**Response 200**: Alert special day

Schema: [`AlertSpecialDay`](#model-alertspecialday)

Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/alert/calendar/{idAlertCalendar}/special-day/{idAlertSpecialDay}` { #put-alert-calendar-idalertcalendar-special-day-idalertspecialday }

updateAlertSpecialDay

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCalendar` | path | integer | yes |  |
| `idAlertSpecialDay` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idGroup` | integer |  |  |
| `date` | string (date) |  |  |
| `dayCode` | integer |  |  |
| `description` | string, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroup": 0,
      "date": "string",
      "dayCode": 0,
      "description": "string"
    }
    ```

**Response 200**: Alert special day updated

Schema: [`AlertSpecialDay`](#model-alertspecialday)

Error responses: `400`, `401`, `403`, `404`, `409`.

### <span class="api-method api-delete">DELETE</span> `/alert/calendar/{idAlertCalendar}/special-day/{idAlertSpecialDay}` { #delete-alert-calendar-idalertcalendar-special-day-idalertspecialday }

deleteAlertSpecialDay

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCalendar` | path | integer | yes |  |
| `idAlertSpecialDay` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `401`, `403`, `404`.

### <span class="api-method api-get">GET</span> `/alert/calendar/{idAlertCalendar}/special-day/list` { #get-alert-calendar-idalertcalendar-special-day-list }

listAlertSpecialDaysGet

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCalendar` | path | integer | yes |  |

**Response 200**: Alert special day list

Schema: [`AlertSpecialDayListResponse`](#model-alertspecialdaylistresponse)

Error responses: `401`, `403`, `404`.

### <span class="api-method api-post">POST</span> `/alert/calendar/{idAlertCalendar}/special-day/list` { #post-alert-calendar-idalertcalendar-special-day-list }

listAlertSpecialDays

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertCalendar` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAlertSpecialDay` | integer | yes |  |
| `idAlertCalendar` | integer | yes |  |
| `idGroup` | integer | yes |  |
| `date` | string (date) | yes |  |
| `dayCode` | integer | yes |  |
| `description` | string, nullable |  |  |
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
| `multipleSearch.field` | enum: `idAlertSpecialDay`, `idAlertCalendar`, `idGroup`, `date`, `dayCode`, `description` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAlertSpecialDay`, `idAlertCalendar`, `idGroup`, `date`, `dayCode`, `description` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroup": 0,
      "date": "string",
      "dayCode": 0,
      "description": "string",
      "requestedFields": [
        "idAlertSpecialDay"
      ],
      "fieldConditions": [
        {
          "field": "idAlertSpecialDay",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idAlertSpecialDay",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAlertSpecialDay",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Alert special day list

Schema: [`AlertSpecialDayListResponse`](#model-alertspecialdaylistresponse)

Error responses: `400`, `401`, `403`, `404`.

## AgentModuleAlerts

API Endpoints for alerts assigned to agent modules

### <span class="api-method api-post">POST</span> `/agentModule/{idAgentModule}/alert` { #post-agentmodule-idagentmodule-alert }

createAgentModuleAlert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`AgentModuleAlert`](#model-agentmodulealert)

**Response 200**: Agent module alert

Schema: [`AgentModuleAlert`](#model-agentmodulealert)

### <span class="api-method api-get">GET</span> `/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}` { #get-agentmodule-idagentmodule-alert-idagentmodulealert }

getAgentModuleAlert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `idAgentModuleAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Agent module alert

Schema: [`AgentModuleAlert`](#model-agentmodulealert)

### <span class="api-method api-put">PUT</span> `/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}` { #put-agentmodule-idagentmodule-alert-idagentmodulealert }

updateAgentModuleAlert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `idAgentModuleAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`AgentModuleAlert`](#model-agentmodulealert)

**Response 200**: Agent module alert

Schema: [`AgentModuleAlert`](#model-agentmodulealert)

### <span class="api-method api-delete">DELETE</span> `/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}` { #delete-agentmodule-idagentmodule-alert-idagentmodulealert }

deleteAgentModuleAlert

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `idAgentModuleAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Deleted

### <span class="api-method api-get">GET</span> `/agentModule/{idAgentModule}/alert/list` { #get-agentmodule-idagentmodule-alert-list }

listAgentModuleAlertsByGet

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Agent module alerts

### <span class="api-method api-post">POST</span> `/agentModule/{idAgentModule}/alert/list` { #post-agentmodule-idagentmodule-alert-list }

listAgentModuleAlerts

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Agent module alerts

### <span class="api-method api-get">GET</span> `/agentModule/alert/list` { #get-agentmodule-alert-list }

listGlobalAgentModuleAlertsByGet

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `status` | query | enum: `fired`, `notFired`, `disabled`, `allEnabled` |  |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Agent module alerts

### <span class="api-method api-post">POST</span> `/agentModule/alert/list` { #post-agentmodule-alert-list }

listGlobalAgentModuleAlerts

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
| `idAgentModuleAlert` | integer |  |  |
| `idAgentModule` | integer |  |  |
| `idAlertTemplate` | integer |  |  |
| `idPolicyAlerts` | integer |  |  |
| `internalCounter` | integer |  |  |
| `lastFired` | integer |  |  |
| `lastReference` | integer |  |  |
| `timesFired` | integer |  |  |
| `disabled` | boolean |  |  |
| `standby` | boolean |  |  |
| `priority` | integer |  |  |
| `forceExecution` | boolean |  |  |
| `disabledByDowntime` | boolean |  |  |
| `serverId` | integer, nullable |  |  |
| `status` | enum: `fired`, `notFired`, `disabled`, `allEnabled` |  |  |
| `serverId` | integer, nullable |  | Node identifier. Required when listing alerts from a metaconsole |
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
| `multipleSearch.field` | enum: `idAgentModuleAlert`, `idAgentModule`, `idAlertTemplate`, `idPolicyAlerts`, `internalCounter`, `lastFired`, `lastReference`, `timesFired`, `disabled`, `standby`, `priority`, `forceExecution`, `disabledByDowntime` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAgentModuleAlert`, `idAgentModule`, `idAlertTemplate`, `idPolicyAlerts`, `internalCounter`, `lastFired`, `lastReference`, `timesFired`, `disabled`, `standby`, `priority`, `forceExecution`, `disabledByDowntime` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAlertTemplate": 0,
      "disabled": false,
      "standby": false,
      "priority": 0,
      "forceExecution": false,
      "status": "fired",
      "serverId": 0,
      "requestedFields": [
        "idAgentModuleAlert"
      ],
      "fieldConditions": [
        {
          "field": "idAgentModuleAlert",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idAgentModuleAlert",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAgentModuleAlert",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Agent module alerts

## AgentModuleAlertActions

API Endpoints for actions assigned to agent module alerts

### <span class="api-method api-post">POST</span> `/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}/action` { #post-agentmodule-idagentmodule-alert-idagentmodulealert-action }

createAgentModuleAlertAction

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `idAgentModuleAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`AgentModuleAlertAction`](#model-agentmodulealertaction)

**Response 200**: Agent module alert action

Schema: [`AgentModuleAlertAction`](#model-agentmodulealertaction)

### <span class="api-method api-get">GET</span> `/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}/action/{idAgentModuleAlertAction}` { #get-agentmodule-idagentmodule-alert-idagentmodulealert-action-idagentmodulealertaction }

getAgentModuleAlertAction

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `idAgentModuleAlert` | path | integer | yes |  |
| `idAgentModuleAlertAction` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Agent module alert action

Schema: [`AgentModuleAlertAction`](#model-agentmodulealertaction)

### <span class="api-method api-put">PUT</span> `/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}/action/{idAgentModuleAlertAction}` { #put-agentmodule-idagentmodule-alert-idagentmodulealert-action-idagentmodulealertaction }

updateAgentModuleAlertAction

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `idAgentModuleAlert` | path | integer | yes |  |
| `idAgentModuleAlertAction` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`AgentModuleAlertAction`](#model-agentmodulealertaction)

**Response 200**: Agent module alert action

### <span class="api-method api-delete">DELETE</span> `/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}/action/{idAgentModuleAlertAction}` { #delete-agentmodule-idagentmodule-alert-idagentmodulealert-action-idagentmodulealertaction }

deleteAgentModuleAlertAction

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `idAgentModuleAlert` | path | integer | yes |  |
| `idAgentModuleAlertAction` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Deleted

### <span class="api-method api-get">GET</span> `/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}/action/list` { #get-agentmodule-idagentmodule-alert-idagentmodulealert-action-list }

getAgentModuleAlertActions

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `idAgentModuleAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Agent module alert action list

### <span class="api-method api-post">POST</span> `/agentModule/{idAgentModule}/alert/{idAgentModuleAlert}/action/list` { #post-agentmodule-idagentmodule-alert-idagentmodulealert-action-list }

listAgentModuleAlertActions

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAgentModule` | path | integer | yes |  |
| `idAgentModuleAlert` | path | integer | yes |  |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Agent module alert action list

## AlertExecutionQueue

Read-only alert execution queue entries from nodes and metaconsole federation

### <span class="api-method api-get">GET</span> `/alert/executionQueue/{idAlertExecutionQueue}` { #get-alert-executionqueue-idalertexecutionqueue }

Get an alert execution queue entry

Metaconsole: omit serverId or 0 for local; 1+ selects one node. Not aggregated.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertExecutionQueue` | path | integer | yes | Alert execution queue identifier |
| `serverId` | query | integer |  | Omit or use 0 for the local console queue; 1+ selects a node from a metaconsole. |

**Response 200**: Alert execution queue entry

??? note "Response fields (4 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `serverId` | integer, nullable |  | Console that owns the resource |
    | `idAlertExecutionQueue` | integer |  | Alert execution queue identifier |
    | `utimestamp` | integer |  | Unix timestamp when the alert was queued |
    | `data` | array, nullable |  | Decoded queued arguments: 1=agent, 2=module, 3=alert, 4=mode, 5=time, 7=macros |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`, `503`, `504`.

### <span class="api-method api-get">GET</span> `/alert/executionQueue/list` { #get-alert-executionqueue-list }

List alert execution queue entries

Simple filters via query string; advanced filters and limit/offset via POST body.
Metaconsole: omit serverId or 0 for local; 1+ selects one node. Not aggregated.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Omit or use 0 for the local console queue; 1+ selects a node from a metaconsole. |
| `idAlertExecutionQueue` | query | integer |  |  |
| `utimestamp` | query | integer |  |  |
| `freeSearch` | query | string |  |  |

**Response 200**: Alert execution queue list

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
    | `data` | array of FederatedAlertExecutionQueue |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idAlertExecutionQueue` | integer |  | Alert execution queue identifier |
    | `data.[].utimestamp` | integer |  | Unix timestamp when the alert was queued |
    | `data.[].data` | array, nullable |  | Decoded queued arguments: 1=agent, 2=module, 3=alert, 4=mode, 5=time, 7=macros |


Error responses: `400`, `401`, `403`, `500`, `502`, `503`, `504`.

### <span class="api-method api-post">POST</span> `/alert/executionQueue/list` { #post-alert-executionqueue-list }

List alert execution queue entries

Body filters override the same simple query filters.
Metaconsole: omit serverId or 0 for local; 1+ selects one node. Not aggregated.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Omit or use 0 for the local console queue; 1+ selects a node from a metaconsole. |
| `idAlertExecutionQueue` | query | integer |  |  |
| `utimestamp` | query | integer |  |  |
| `freeSearch` | query | string |  |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idAlertExecutionQueue` | integer |  | Alert execution queue identifier |
| `utimestamp` | integer |  | Unix timestamp when the alert was queued |
| `data` | array, nullable |  | Decoded queued arguments: 1=agent, 2=module, 3=alert, 4=mode, 5=time, 7=macros |
| `serverId` | integer, nullable |  | 0 or null selects the local console queue; 1+ selects a node from a metaconsole |
| `freeSearch` | string, nullable |  | Find a word in the decoded queued payload |
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
| `multipleSearch.field` | enum: `idAlertExecutionQueue`, `utimestamp`, `data` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAlertExecutionQueue`, `utimestamp`, `data` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "serverId": 0,
      "freeSearch": "string",
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "requestedFields": [
        "idAlertExecutionQueue"
      ],
      "fieldConditions": [
        {
          "field": "idAlertExecutionQueue",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "multipleSearch": {
        "field": "idAlertExecutionQueue",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAlertExecutionQueue",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Alert execution queue list

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
    | `data` | array of FederatedAlertExecutionQueue |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idAlertExecutionQueue` | integer |  | Alert execution queue identifier |
    | `data.[].utimestamp` | integer |  | Unix timestamp when the alert was queued |
    | `data.[].data` | array, nullable |  | Decoded queued arguments: 1=agent, 2=module, 3=alert, 4=mode, 5=time, 7=macros |


Error responses: `400`, `401`, `403`, `500`, `502`, `503`, `504`.

## AlertFired

API Endpoints for alert fired history

### <span class="api-method api-get">GET</span> `/alert/fired/{idAlertFired}` { #get-alert-fired-idalertfired }

Get an alert fired history entry

Rows whose alert assignment no longer exists cannot be authorized and return 404.
On a metaconsole, serverId is required and selects one enabled node; calls are not aggregated.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idAlertFired` | path | integer | yes | Alert fired history identifier |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Alert fired history entry

??? note "Response fields (9 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `serverId` | integer, nullable |  | Console that owns the resource |
    | `idAlertFired` | integer |  | Alert fired history identifier |
    | `idAgentModuleAlert` | integer |  | Alert assignment identifier (talert_template_modules.id) |
    | `utimestamp` | integer |  | Unix timestamp when the alert fired. Zero means an unknown or orphaned fire |
    | `actions` | string, nullable |  | JSON payload with the actions executed when the alert fired |
    | `recovered` | boolean |  | Whether the fired alert is already recovered |
    | `recoveryUtimestamp` | integer |  | Unix timestamp when the alert recovered |
    | `recoveryActions` | string, nullable |  | JSON payload with the actions executed when the alert recovered |
    | `recoveryType` | integer |  | 0=unknown, 1=recovered, 2=ceased, 3=manual validation |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`, `503`, `504`.

### <span class="api-method api-get">GET</span> `/alert/fired/list` { #get-alert-fired-list }

List alert fired history

Query-string variant. Orphaned rows without an alert assignment are not returned.
On a metaconsole, serverId is required and selects one enabled node; calls are not aggregated.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List of alert fired history entries

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
    | `data` | array of FederatedAlertFired |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idAlertFired` | integer |  | Alert fired history identifier |
    | `data.[].idAgentModuleAlert` | integer |  | Alert assignment identifier (talert_template_modules.id) |
    | `data.[].utimestamp` | integer |  | Unix timestamp when the alert fired. Zero means an unknown or orphaned fire |
    | `data.[].actions` | string, nullable |  | JSON payload with the actions executed when the alert fired |
    | `data.[].recovered` | boolean |  | Whether the fired alert is already recovered |
    | `data.[].recoveryUtimestamp` | integer |  | Unix timestamp when the alert recovered |
    | `data.[].recoveryActions` | string, nullable |  | JSON payload with the actions executed when the alert recovered |
    | `data.[].recoveryType` | integer |  | 0=unknown, 1=recovered, 2=ceased, 3=manual validation |


Error responses: `400`, `401`, `403`, `500`, `502`, `503`, `504`.

### <span class="api-method api-post">POST</span> `/alert/fired/list` { #post-alert-fired-list }

List alert fired history

Orphaned rows without an alert assignment are not returned.
On a metaconsole, serverId is required and selects one enabled node; calls are not aggregated.

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
| `idAlertFired` | integer |  | Alert fired history identifier |
| `idAgentModuleAlert` | integer |  | Alert assignment identifier (talert_template_modules.id) |
| `utimestamp` | integer |  | Unix timestamp when the alert fired. Zero means an unknown or orphaned fire |
| `actions` | string, nullable |  | JSON payload with the actions executed when the alert fired |
| `recovered` | boolean |  | Whether the fired alert is already recovered |
| `recoveryUtimestamp` | integer |  | Unix timestamp when the alert recovered |
| `recoveryActions` | string, nullable |  | JSON payload with the actions executed when the alert recovered |
| `recoveryType` | integer |  | 0=unknown, 1=recovered, 2=ceased, 3=manual validation |
| `serverId` | integer, nullable |  | Node identifier. Required when listing alert history from a metaconsole |
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
| `multipleSearch.field` | enum: `idAlertFired`, `idAgentModuleAlert`, `utimestamp`, `recovered`, `recoveryUtimestamp`, `recoveryType` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idAlertFired`, `idAgentModuleAlert`, `utimestamp`, `recovered`, `recoveryUtimestamp`, `recoveryType` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "serverId": 0,
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "requestedFields": [
        "idAlertFired"
      ],
      "fieldConditions": [
        {
          "field": "idAlertFired",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "multipleSearch": {
        "field": "idAlertFired",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idAlertFired",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List of alert fired history entries

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
    | `data` | array of FederatedAlertFired |  |  |
    | `data.[].serverId` | integer, nullable |  | Console that owns the resource |
    | `data.[].idAlertFired` | integer |  | Alert fired history identifier |
    | `data.[].idAgentModuleAlert` | integer |  | Alert assignment identifier (talert_template_modules.id) |
    | `data.[].utimestamp` | integer |  | Unix timestamp when the alert fired. Zero means an unknown or orphaned fire |
    | `data.[].actions` | string, nullable |  | JSON payload with the actions executed when the alert fired |
    | `data.[].recovered` | boolean |  | Whether the fired alert is already recovered |
    | `data.[].recoveryUtimestamp` | integer |  | Unix timestamp when the alert recovered |
    | `data.[].recoveryActions` | string, nullable |  | JSON payload with the actions executed when the alert recovered |
    | `data.[].recoveryType` | integer |  | 0=unknown, 1=recovered, 2=ceased, 3=manual validation |


Error responses: `400`, `401`, `403`, `500`, `502`, `503`, `504`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: AgentModuleAlert { #model-agentmodulealert }

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgentModuleAlert` | integer |  |  |
| `idAgentModule` | integer |  |  |
| `idAlertTemplate` | integer |  |  |
| `idPolicyAlerts` | integer |  |  |
| `internalCounter` | integer |  |  |
| `lastFired` | integer |  |  |
| `lastReference` | integer |  |  |
| `timesFired` | integer |  |  |
| `disabled` | boolean |  |  |
| `standby` | boolean |  |  |
| `priority` | integer |  |  |
| `forceExecution` | boolean |  |  |
| `disabledByDowntime` | boolean |  |  |
| `serverId` | integer, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAlertTemplate": 0,
      "disabled": false,
      "standby": false,
      "priority": 0,
      "forceExecution": false
    }
    ```

### Model: AgentModuleAlertAction { #model-agentmodulealertaction }

| Field | Type | Required | Description |
|---|---|---|---|
| `idAgentModuleAlertAction` | integer |  |  |
| `idAgentModuleAlert` | integer |  |  |
| `idAlertAction` | integer |  |  |
| `firesMin` | integer |  |  |
| `firesMax` | integer |  |  |
| `moduleActionThreshold` | integer |  |  |
| `lastExecution` | integer |  |  |
| `recovered` | boolean |  |  |
| `serverId` | integer, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAlertAction": 0,
      "firesMin": 0,
      "firesMax": 0,
      "moduleActionThreshold": 0
    }
    ```

### Model: AlertActionResponse { #model-alertactionresponse }

??? note "Fields (9 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAlertAction` | integer | yes |  |
    | `name` | string | yes |  |
    | `idAlertCommand` | integer | yes |  |
    | `idGroup` | integer | yes |  |
    | `actionThreshold` | integer | yes |  |
    | `fields` | array of string | yes |  |
    | `recoveryFields` | array of string | yes |  |
    | `createWorkunitInItsm` | boolean, nullable |  |  |
    | `isDefault` | boolean | yes |  |


### Model: AlertCalendar { #model-alertcalendar }

??? note "Fields (4 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAlertCalendar` | integer | yes |  |
    | `name` | string | yes |  |
    | `idGroup` | integer | yes |  |
    | `description` | string, nullable |  |  |


### Model: AlertCalendarListResponse { #model-alertcalendarlistresponse }

??? note "Fields (14 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object | yes | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object | yes |  |
    | `data.[].idAlertCalendar` | integer | yes |  |
    | `data.[].name` | string | yes |  |
    | `data.[].idGroup` | integer | yes |  |
    | `data.[].description` | string, nullable |  |  |


### Model: AlertCommand { #model-alertcommand }

??? note "Fields (9 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAlertCommand` | integer | yes | Alert command identifier |
    | `name` | string | yes | Unique alert command name |
    | `command` | string, nullable |  | Executable command template. Returned only by detailed endpoints requiring PM permission |
    | `idGroup` | integer | yes | Owning group, or 0 for All |
    | `description` | string, nullable |  | Alert command description |
    | `internal` | boolean | yes | Whether this is a protected built-in command |
    | `fieldDescriptions` | array of string | yes |  |
    | `fieldValues` | array, nullable |  | Macro defaults. Returned only by detailed endpoints requiring PM permission |
    | `fieldHidden` | array of boolean | yes |  |


### Model: AlertCommandListResponse { #model-alertcommandlistresponse }

??? note "Fields (17 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object | yes | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object | yes |  |
    | `data.[].idAlertCommand` | integer | yes |  |
    | `data.[].name` | string | yes |  |
    | `data.[].idGroup` | integer | yes |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].internal` | boolean | yes |  |
    | `data.[].fieldDescriptions` | array of string | yes |  |
    | `data.[].fieldHidden` | array of boolean | yes |  |


### Model: AlertSpecialDay { #model-alertspecialday }

??? note "Fields (6 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAlertSpecialDay` | integer | yes |  |
    | `idAlertCalendar` | integer | yes |  |
    | `idGroup` | integer | yes |  |
    | `date` | string (date) | yes |  |
    | `dayCode` | integer | yes |  |
    | `description` | string, nullable |  |  |


### Model: AlertSpecialDayListResponse { #model-alertspecialdaylistresponse }

??? note "Fields (16 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `paginationData` | object | yes | Info pagination data |
    | `paginationData.totalPages` | integer, nullable |  | Number of pages |
    | `paginationData.sizePage` | integer, nullable |  | Items per page |
    | `paginationData.totalRegisters` | integer, nullable |  | Number of items |
    | `paginationData.totalRegistersPage` | integer, nullable |  | Number of items this page |
    | `paginationData.unfilteredTotalRegisters` | integer, nullable |  | Number of unfiltered items |
    | `paginationData.currentPage` | integer, nullable |  | Zero-based current page index. 0 is the first page. Null for limit/offset windows. |
    | `paginationData.limit` | integer, nullable |  | Present in limit/offset pagination. Null means no row limit; zero returns an empty window. |
    | `paginationData.offset` | integer |  | Present in limit/offset pagination. Actual zero-based number of rows skipped. |
    | `data` | array of object | yes |  |
    | `data.[].idAlertSpecialDay` | integer | yes |  |
    | `data.[].idAlertCalendar` | integer | yes |  |
    | `data.[].idGroup` | integer | yes |  |
    | `data.[].date` | string (date) | yes |  |
    | `data.[].dayCode` | integer | yes |  |
    | `data.[].description` | string, nullable |  |  |


### Model: AlertTemplateResponse { #model-alerttemplateresponse }

??? note "Fields (36 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idAlertTemplate` | integer |  |  |
    | `name` | string |  |  |
    | `description` | string, nullable |  |  |
    | `idAlertAction` | integer, nullable |  |  |
    | `fields` | array of string |  |  |
    | `recoveryFields` | array of string |  |  |
    | `type` | enum: `regex`, `max_min`, `max`, `min`, `equal`, `not_equal`, `warning`, `critical`, `onchange`, `unknown`, `always`, `not_normal`, `complex` |  |  |
    | `value` | string, nullable |  |  |
    | `matchesValue` | boolean |  |  |
    | `maxValue` | number, nullable |  |  |
    | `minValue` | number, nullable |  |  |
    | `timeWindow` | enum: `thirty_days`, `this_month`, `seven_days`, `this_week`, `one_day`, `today` |  |  |
    | `mathFunction` | enum: `avg`, `min`, `max`, `sum` |  |  |
    | `condition` | enum: `lower`, `greater`, `equal` |  |  |
    | `timeThreshold` | integer |  |  |
    | `maxAlerts` | integer |  |  |
    | `minAlerts` | integer |  |  |
    | `timeFrom` | string (time) |  |  |
    | `timeTo` | string (time) |  |  |
    | `monday` | boolean |  |  |
    | `tuesday` | boolean |  |  |
    | `wednesday` | boolean |  |  |
    | `thursday` | boolean |  |  |
    | `friday` | boolean |  |  |
    | `saturday` | boolean |  |  |
    | `sunday` | boolean |  |  |
    | `recoveryNotify` | boolean |  |  |
    | `priority` | integer |  |  |
    | `idGroup` | integer |  |  |
    | `specialDay` | integer |  | Alert calendar identifier; 0 disables special days |
    | `wizardLevel` | enum: `basic`, `advanced`, `nowizard` |  |  |
    | `minAlertsResetCounter` | boolean |  |  |
    | `disableEvent` | boolean |  |  |
    | `schedule` | object, nullable |  |  |
    | `recoveryOnNormalStatus` | boolean |  |  |
    | `isInternal` | boolean |  |  |
