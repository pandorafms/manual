# Dashboards and notifications

Dashboards, widgets and graphs, plus notifications and emails.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-post">POST</span> | [`/dashboard`](#post-dashboard) | Creates a dashboard |
| <span class="api-method api-get">GET</span> | [`/dashboard/{idDashboard}`](#get-dashboard-iddashboard) | Shows a dashboard |
| <span class="api-method api-put">PUT</span> | [`/dashboard/{idDashboard}`](#put-dashboard-iddashboard) | Updates a dashboard |
| <span class="api-method api-delete">DELETE</span> | [`/dashboard/{idDashboard}`](#delete-dashboard-iddashboard) | Deletes a dashboard |
| <span class="api-method api-get">GET</span> | [`/dashboard/list`](#get-dashboard-list) | Lists dashboards |
| <span class="api-method api-post">POST</span> | [`/dashboard/list`](#post-dashboard-list) | Lists dashboards |
| <span class="api-method api-post">POST</span> | [`/dashboard/{idDashboard}/widget`](#post-dashboard-iddashboard-widget) | Create an unconfigured or configured dashboard widget |
| <span class="api-method api-get">GET</span> | [`/dashboard/{idDashboard}/widget/{idDashboardWidget}`](#get-dashboard-iddashboard-widget-iddashboardwidget) | Show a dashboard widget |
| <span class="api-method api-put">PUT</span> | [`/dashboard/{idDashboard}/widget/{idDashboardWidget}`](#put-dashboard-iddashboard-widget-iddashboardwidget) | Update a dashboard widget |
| <span class="api-method api-delete">DELETE</span> | [`/dashboard/{idDashboard}/widget/{idDashboardWidget}`](#delete-dashboard-iddashboard-widget-iddashboardwidget) | Delete a dashboard widget |
| <span class="api-method api-get">GET</span> | [`/dashboard/{idDashboard}/widget/list`](#get-dashboard-iddashboard-widget-list) | List dashboard widgets |
| <span class="api-method api-post">POST</span> | [`/dashboard/{idDashboard}/widget/list`](#post-dashboard-iddashboard-widget-list) | List dashboard widgets |
| <span class="api-method api-get">GET</span> | [`/widget/{idWidget}`](#get-widget-idwidget) | Show widget |
| <span class="api-method api-get">GET</span> | [`/widget/list`](#get-widget-list) | List Widget |
| <span class="api-method api-post">POST</span> | [`/widget/list`](#post-widget-list) | List Widget |
| <span class="api-method api-post">POST</span> | [`/graph`](#post-graph) | Creates a combined graph |
| <span class="api-method api-get">GET</span> | [`/graph/{idGraph}`](#get-graph-idgraph) | Gets a combined graph |
| <span class="api-method api-put">PUT</span> | [`/graph/{idGraph}`](#put-graph-idgraph) | Updates a combined graph |
| <span class="api-method api-delete">DELETE</span> | [`/graph/{idGraph}`](#delete-graph-idgraph) | Deletes a combined graph and its sources |
| <span class="api-method api-get">GET</span> | [`/graph/list`](#get-graph-list) | Lists combined graphs |
| <span class="api-method api-post">POST</span> | [`/graph/list`](#post-graph-list) | Lists combined graphs |
| <span class="api-method api-post">POST</span> | [`/graph/{idGraph}/source`](#post-graph-idgraph-source) | Adds a series to a combined graph |
| <span class="api-method api-get">GET</span> | [`/graph/{idGraph}/source/{idGraphSource}`](#get-graph-idgraph-source-idgraphsource) | Gets a combined graph series |
| <span class="api-method api-put">PUT</span> | [`/graph/{idGraph}/source/{idGraphSource}`](#put-graph-idgraph-source-idgraphsource) | Updates a combined graph series |
| <span class="api-method api-delete">DELETE</span> | [`/graph/{idGraph}/source/{idGraphSource}`](#delete-graph-idgraph-source-idgraphsource) | Deletes a combined graph series |
| <span class="api-method api-get">GET</span> | [`/graph/{idGraph}/source/list`](#get-graph-idgraph-source-list) | Lists the series of a combined graph |
| <span class="api-method api-post">POST</span> | [`/graph/{idGraph}/source/list`](#post-graph-idgraph-source-list) | Lists the series of a combined graph |
| <span class="api-method api-post">POST</span> | [`/notification/message`](#post-notification-message) | Create a console notification |
| <span class="api-method api-get">GET</span> | [`/notification/message/{idMessage}`](#get-notification-message-idmessage) | Get one console notification |
| <span class="api-method api-put">PUT</span> | [`/notification/message/{idMessage}`](#put-notification-message-idmessage) | Update a console notification |
| <span class="api-method api-delete">DELETE</span> | [`/notification/message/{idMessage}`](#delete-notification-message-idmessage) | Delete a console notification |
| <span class="api-method api-get">GET</span> | [`/notification/message/list`](#get-notification-message-list) | List console notifications |
| <span class="api-method api-post">POST</span> | [`/notification/message/list`](#post-notification-message-list) | List console notifications |
| <span class="api-method api-post">POST</span> | [`/notification/source_user`](#post-notification-source-user) | Create or update a user notification preference |
| <span class="api-method api-get">GET</span> | [`/notification/source_user/{sourceId}/{idUser}`](#get-notification-source-user-sourceid-iduser) | Get a user notification preference |
| <span class="api-method api-put">PUT</span> | [`/notification/source_user/{sourceId}/{idUser}`](#put-notification-source-user-sourceid-iduser) | Update a user notification preference |
| <span class="api-method api-delete">DELETE</span> | [`/notification/source_user/{sourceId}/{idUser}`](#delete-notification-source-user-sourceid-iduser) | Delete a user notification preference |
| <span class="api-method api-get">GET</span> | [`/notification/source_user/list`](#get-notification-source-user-list) | List user notification preferences |
| <span class="api-method api-post">POST</span> | [`/notification/source_user/list`](#post-notification-source-user-list) | List user notification preferences |
| <span class="api-method api-get">GET</span> | [`/notification/source/{idSource}`](#get-notification-source-idsource) | Get one notification source |
| <span class="api-method api-get">GET</span> | [`/notification/source/list`](#get-notification-source-list) | List notification sources |
| <span class="api-method api-post">POST</span> | [`/notification/source/list`](#post-notification-source-list) | List notification sources |
| <span class="api-method api-get">GET</span> | [`/mail/config`](#get-mail-config) | Get the mail transport configuration without credentials |
| <span class="api-method api-post">POST</span> | [`/email/send`](#post-email-send) | Send an email through the console mail transport |

## Dashboards

API Endpoints for dashboards

### <span class="api-method api-post">POST</span> `/dashboard` { #post-dashboard }

Creates a dashboard

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idDashboard` | integer |  |  |
| `name` | string | yes |  |
| `idUser` | string |  |  |
| `idGroup` | integer |  |  |
| `internal` | boolean |  |  |
| `active` | boolean |  |  |
| `cells` | integer |  |  |
| `cellsSlideshow` | boolean |  |  |
| `dateRange` | boolean |  |  |
| `dateRangeData` | object, nullable |  |  |
| `userFullName` | string, nullable |  |  |
| `groupName` | string, nullable |  |  |
| `widgetCount` | integer |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idUser": "string",
      "idGroup": 0,
      "active": false,
      "cellsSlideshow": false,
      "dateRange": false,
      "dateRangeData": {}
    }
    ```

**Response 200**: Dashboard object

Schema: [`Dashboard`](#model-dashboard)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/dashboard/{idDashboard}` { #get-dashboard-iddashboard }

Shows a dashboard

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idDashboard` | path | integer | yes |  |

**Response 200**: Dashboard object

Schema: [`Dashboard`](#model-dashboard)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/dashboard/{idDashboard}` { #put-dashboard-iddashboard }

Updates a dashboard

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idDashboard` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idDashboard` | integer |  |  |
| `name` | string |  |  |
| `idUser` | string |  |  |
| `idGroup` | integer |  |  |
| `internal` | boolean |  |  |
| `active` | boolean |  |  |
| `cells` | integer |  |  |
| `cellsSlideshow` | boolean |  |  |
| `dateRange` | boolean |  |  |
| `dateRangeData` | object, nullable |  |  |
| `userFullName` | string, nullable |  |  |
| `groupName` | string, nullable |  |  |
| `widgetCount` | integer |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idUser": "string",
      "idGroup": 0,
      "active": false,
      "cellsSlideshow": false,
      "dateRange": false,
      "dateRangeData": {}
    }
    ```

**Response 200**: Dashboard object

Schema: [`Dashboard`](#model-dashboard)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/dashboard/{idDashboard}` { #delete-dashboard-iddashboard }

Deletes a dashboard

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idDashboard` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/dashboard/list` { #get-dashboard-list }

Lists dashboards

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: Dashboard list

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
    | `data.[].idDashboard` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].idUser` | string |  |  |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].internal` | boolean |  |  |
    | `data.[].active` | boolean |  |  |
    | `data.[].cells` | integer |  |  |
    | `data.[].cellsSlideshow` | boolean |  |  |
    | `data.[].dateRange` | boolean |  |  |
    | `data.[].dateRangeData` | object, nullable |  |  |
    | `data.[].userFullName` | string, nullable |  |  |
    | `data.[].groupName` | string, nullable |  |  |
    | `data.[].widgetCount` | integer |  |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/dashboard/list` { #post-dashboard-list }

Lists dashboards

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
| `idDashboard` | integer |  |  |
| `name` | string |  |  |
| `idUser` | string |  |  |
| `idGroup` | integer |  |  |
| `internal` | boolean |  |  |
| `active` | boolean |  |  |
| `cells` | integer |  |  |
| `cellsSlideshow` | boolean |  |  |
| `dateRange` | boolean |  |  |
| `dateRangeData` | object, nullable |  |  |
| `userFullName` | string, nullable |  |  |
| `groupName` | string, nullable |  |  |
| `widgetCount` | integer |  |  |
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
| `multipleSearch.field` | enum: `idDashboard`, `name`, `idUser`, `userFullName`, `idGroup`, `groupName`, `internal`, `active`, `cells`, `widgetCount`, `cellsSlideshow`, `dateRange` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idDashboard`, `name`, `idUser`, `userFullName`, `idGroup`, `groupName`, `internal`, `active`, `cells`, `widgetCount`, `cellsSlideshow`, `dateRange` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idUser": "string",
      "idGroup": 0,
      "active": false,
      "cellsSlideshow": false,
      "dateRange": false,
      "dateRangeData": {},
      "freeSearch": "string",
      "requestedFields": [
        "idDashboard"
      ],
      "fieldConditions": [
        {
          "field": "idDashboard",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idDashboard",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idDashboard",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Dashboard list

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
    | `data.[].idDashboard` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].idUser` | string |  |  |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].internal` | boolean |  |  |
    | `data.[].active` | boolean |  |  |
    | `data.[].cells` | integer |  |  |
    | `data.[].cellsSlideshow` | boolean |  |  |
    | `data.[].dateRange` | boolean |  |  |
    | `data.[].dateRangeData` | object, nullable |  |  |
    | `data.[].userFullName` | string, nullable |  |  |
    | `data.[].groupName` | string, nullable |  |  |
    | `data.[].widgetCount` | integer |  |  |


Error responses: `400`, `401`, `403`, `500`.

## DashboardWidgets

API Endpoints for dashboard widgets

### <span class="api-method api-post">POST</span> `/dashboard/{idDashboard}/widget` { #post-dashboard-iddashboard-widget }

Create an unconfigured or configured dashboard widget

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idDashboard` | path | integer | yes |  |

**Request body** (`application/json`): [`DashboardWidget`](#model-dashboardwidget)

**Response 200**: Dashboard widget object

Schema: [`DashboardWidget`](#model-dashboardwidget)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/dashboard/{idDashboard}/widget/{idDashboardWidget}` { #get-dashboard-iddashboard-widget-iddashboardwidget }

Show a dashboard widget

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idDashboard` | path | integer | yes |  |
| `idDashboardWidget` | path | integer | yes |  |

**Response 200**: Dashboard widget object

Schema: [`DashboardWidget`](#model-dashboardwidget)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/dashboard/{idDashboard}/widget/{idDashboardWidget}` { #put-dashboard-iddashboard-widget-iddashboardwidget }

Update a dashboard widget

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idDashboard` | path | integer | yes |  |
| `idDashboardWidget` | path | integer | yes |  |

**Request body** (`application/json`): [`DashboardWidget`](#model-dashboardwidget)

**Response 200**: Dashboard widget object

Schema: [`DashboardWidget`](#model-dashboardwidget)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/dashboard/{idDashboard}/widget/{idDashboardWidget}` { #delete-dashboard-iddashboard-widget-iddashboardwidget }

Delete a dashboard widget

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idDashboard` | path | integer | yes |  |
| `idDashboardWidget` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/dashboard/{idDashboard}/widget/list` { #get-dashboard-iddashboard-widget-list }

List dashboard widgets

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idDashboard` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Response 200**: Paginated dashboard widgets

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
    | `data.[].idDashboardWidget` | integer |  |  |
    | `data.[].idDashboard` | integer |  |  |
    | `data.[].idWidget` | integer, nullable |  |  |
    | `data.[].position` | object, nullable |  |  |
    | `data.[].options` | object, nullable |  |  |
    | `data.[].order` | integer |  |  |
    | `data.[].propWidth` | number (double) |  |  |
    | `data.[].propHeight` | number (double) |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/dashboard/{idDashboard}/widget/list` { #post-dashboard-iddashboard-widget-list }

List dashboard widgets

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idDashboard` | path | integer | yes |  |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idDashboardWidget` | integer |  |  |
| `idDashboard` | integer |  |  |
| `idWidget` | integer, nullable |  |  |
| `position` | object, nullable |  |  |
| `options` | object, nullable |  |  |
| `order` | integer |  |  |
| `propWidth` | number (double) |  |  |
| `propHeight` | number (double) |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idWidget": 0,
      "position": {},
      "options": {},
      "order": 0,
      "propWidth": 0.32,
      "propHeight": 0.32,
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

**Response 200**: Paginated dashboard widgets

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
    | `data.[].idDashboardWidget` | integer |  |  |
    | `data.[].idDashboard` | integer |  |  |
    | `data.[].idWidget` | integer, nullable |  |  |
    | `data.[].position` | object, nullable |  |  |
    | `data.[].options` | object, nullable |  |  |
    | `data.[].order` | integer |  |  |
    | `data.[].propWidth` | number (double) |  |  |
    | `data.[].propHeight` | number (double) |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Widgets

API Endpoints for widgets

### <span class="api-method api-get">GET</span> `/widget/{idWidget}` { #get-widget-idwidget }

Show widget

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idWidget` | path | integer | yes | Widget id |

**Response 200**: Widget object

??? note "Response fields (9 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idWidget` | integer |  | Id Widget |
    | `className` | string |  | Class name of the widget |
    | `uniqueName` | string |  | Unique name of the widget |
    | `description` | string, nullable |  | Description of the widget |
    | `options` | object, nullable |  | Options of the widget |
    | `page` | string |  | Page of the widget |
    | `isDashboardsAvailable` | boolean |  | Indicates if the widget is available for dashboards |
    | `isReportsAvailable` | boolean |  | Indicates if the widget is available for reports |
    | `category` | enum: `table`, `misc`, `chart` |  | Category of the widget |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/widget/list` { #get-widget-list }

List Widget

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Widget object

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
    | `data.[].idWidget` | integer |  | Id Widget |
    | `data.[].className` | string |  | Class name of the widget |
    | `data.[].uniqueName` | string |  | Unique name of the widget |
    | `data.[].description` | string, nullable |  | Description of the widget |
    | `data.[].options` | object, nullable |  | Options of the widget |
    | `data.[].page` | string |  | Page of the widget |
    | `data.[].isDashboardsAvailable` | boolean |  | Indicates if the widget is available for dashboards |
    | `data.[].isReportsAvailable` | boolean |  | Indicates if the widget is available for reports |
    | `data.[].category` | enum: `table`, `misc`, `chart` |  | Category of the widget |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/widget/list` { #post-widget-list }

List Widget

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
| `idWidget` | integer |  | Id Widget |
| `className` | string |  | Class name of the widget |
| `uniqueName` | string |  | Unique name of the widget |
| `description` | string, nullable |  | Description of the widget |
| `options` | object, nullable |  | Options of the widget |
| `page` | string |  | Page of the widget |
| `isDashboardsAvailable` | boolean |  | Indicates if the widget is available for dashboards |
| `isReportsAvailable` | boolean |  | Indicates if the widget is available for reports |
| `category` | enum: `table`, `misc`, `chart` |  | Category of the widget |
| `idWidget` |  |  |  |
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
      "className": "string",
      "uniqueName": "string",
      "description": "string",
      "options": {},
      "page": 0,
      "isDashboardsAvailable": true,
      "isReportsAvailable": false,
      "category": "table",
      "idWidget": null,
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
      "sizePage": 0,
      "limit": 0,
      "offset": 0
    }
    ```

**Response 200**: List Widget object

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
    | `data.[].idWidget` | integer |  | Id Widget |
    | `data.[].className` | string |  | Class name of the widget |
    | `data.[].uniqueName` | string |  | Unique name of the widget |
    | `data.[].description` | string, nullable |  | Description of the widget |
    | `data.[].options` | object, nullable |  | Options of the widget |
    | `data.[].page` | string |  | Page of the widget |
    | `data.[].isDashboardsAvailable` | boolean |  | Indicates if the widget is available for dashboards |
    | `data.[].isReportsAvailable` | boolean |  | Indicates if the widget is available for reports |
    | `data.[].category` | enum: `table`, `misc`, `chart` |  | Category of the widget |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Graphs

API Endpoints for combined graphs

### <span class="api-method api-post">POST</span> `/graph` { #post-graph }

Creates a combined graph

On a metaconsole serverId selects the node that owns the graph

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`Graph`](#model-graph)

**Response 200**: Combined graph object

Schema: [`Graph`](#model-graph)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/graph/{idGraph}` { #get-graph-idgraph }

Gets a combined graph

Reads the graph locally on a node. On a metaconsole serverId is required

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idGraph` | path | integer | yes | Combined graph id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Combined graph object

Schema: [`Graph`](#model-graph)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-put">PUT</span> `/graph/{idGraph}` { #put-graph-idgraph }

Updates a combined graph

On a metaconsole serverId selects the node that owns the graph

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idGraph` | path | integer | yes | Combined graph id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`Graph`](#model-graph)

**Response 200**: Combined graph object

Schema: [`Graph`](#model-graph)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-delete">DELETE</span> `/graph/{idGraph}` { #delete-graph-idgraph }

Deletes a combined graph and its sources

On a metaconsole serverId selects the node that owns the graph

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idGraph` | path | integer | yes | Combined graph id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/graph/list` { #get-graph-list }

Lists combined graphs

On a metaconsole the list aggregates every enabled node unless serverId selects specific nodes Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List of combined graphs

??? note "Response fields (29 fields)"

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
    | `data.[].idGraph` | integer |  | Id of the combined graph |
    | `data.[].idUser` | string |  | Owner user of the combined graph |
    | `data.[].serverId` | integer, nullable |  | Node that owns the combined graph when it is read from a metaconsole |
    | `data.[].name` | string |  | Name of the combined graph |
    | `data.[].description` | string, nullable |  | Description of the combined graph |
    | `data.[].period` | integer, nullable |  | Default period in seconds |
    | `data.[].width` | integer, nullable |  | Graph width |
    | `data.[].height` | integer, nullable |  | Graph height |
    | `data.[].private` | boolean, nullable |  | Only the owner can see a private graph |
    | `data.[].events` | boolean, nullable |  | Whether events are shown in the graph |
    | `data.[].stacked` | enum: `area`, `stacked_area`, `line`, `stacked_line`, `bullet_chart`, `gauge`, `hbars`, `vbars`, `pie`, `bullet_chart_threshold`, `stacked_vbars` |  | Graph rendering type |
    | `data.[].idGroup` | integer, nullable |  | Group that owns the combined graph |
    | `data.[].idGraphTemplate` | integer, nullable |  | Template the graph was created from |
    | `data.[].percentil` | boolean, nullable |  | Whether the percentile series is rendered |
    | `data.[].summatorySeries` | boolean, nullable |  | Whether the summatory series is rendered |
    | `data.[].averageSeries` | boolean, nullable |  | Whether the average series is rendered |
    | `data.[].modulesSeries` | boolean, nullable |  | Whether module series are rendered |
    | `data.[].fullscale` | boolean, nullable |  | Whether the graph is rendered with full scale |
    | `data.[].idDataTranslation` | integer, nullable |  | Data translation applied to the series |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/graph/list` { #post-graph-list }

Lists combined graphs

On a metaconsole the list aggregates every enabled node unless serverId selects specific nodes

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
| `idGraph` | integer |  | Id of the combined graph |
| `idUser` | string |  | Owner user of the combined graph |
| `serverId` | integer, nullable |  | Node that owns the combined graph when it is read from a metaconsole |
| `name` | string |  | Name of the combined graph |
| `description` | string, nullable |  | Description of the combined graph |
| `period` | integer, nullable |  | Default period in seconds |
| `width` | integer, nullable |  | Graph width |
| `height` | integer, nullable |  | Graph height |
| `private` | boolean, nullable |  | Only the owner can see a private graph |
| `events` | boolean, nullable |  | Whether events are shown in the graph |
| `stacked` | enum: `area`, `stacked_area`, `line`, `stacked_line`, `bullet_chart`, `gauge`, `hbars`, `vbars`, `pie`, `bullet_chart_threshold`, `stacked_vbars` |  | Graph rendering type |
| `idGroup` | integer, nullable |  | Group that owns the combined graph |
| `idGraphTemplate` | integer, nullable |  | Template the graph was created from |
| `percentil` | boolean, nullable |  | Whether the percentile series is rendered |
| `summatorySeries` | boolean, nullable |  | Whether the summatory series is rendered |
| `averageSeries` | boolean, nullable |  | Whether the average series is rendered |
| `modulesSeries` | boolean, nullable |  | Whether module series are rendered |
| `fullscale` | boolean, nullable |  | Whether the graph is rendered with full scale |
| `idDataTranslation` | integer, nullable |  | Data translation applied to the series |
| `idGraph` |  |  |  |
| `freeSearch` | string, nullable |  | Find text in name and description |
| `serverId` | array, nullable |  | Node identifiers to aggregate on a metaconsole |
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
| `multipleSearch.field` | enum: `idGraph`, `idUser`, `name`, `description`, `period`, `width`, `height`, `idGroup`, `idGraphTemplate`, `idDataTranslation` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idGraph`, `idUser`, `name`, `description`, `period`, `width`, `height`, `idGroup`, `idGraphTemplate`, `idDataTranslation` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "period": 0,
      "width": 0,
      "height": 0,
      "private": false,
      "events": false,
      "stacked": "area",
      "idGroup": 0,
      "percentil": false,
      "summatorySeries": false,
      "averageSeries": false,
      "modulesSeries": false,
      "fullscale": false,
      "idDataTranslation": 0,
      "idGraph": null,
      "freeSearch": "string",
      "serverId": [
        0
      ],
      "requestedFields": [
        "idGraph"
      ],
      "fieldConditions": [
        {
          "field": "idGraph",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idGraph",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idGraph",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List of combined graphs

??? note "Response fields (29 fields)"

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
    | `data.[].idGraph` | integer |  | Id of the combined graph |
    | `data.[].idUser` | string |  | Owner user of the combined graph |
    | `data.[].serverId` | integer, nullable |  | Node that owns the combined graph when it is read from a metaconsole |
    | `data.[].name` | string |  | Name of the combined graph |
    | `data.[].description` | string, nullable |  | Description of the combined graph |
    | `data.[].period` | integer, nullable |  | Default period in seconds |
    | `data.[].width` | integer, nullable |  | Graph width |
    | `data.[].height` | integer, nullable |  | Graph height |
    | `data.[].private` | boolean, nullable |  | Only the owner can see a private graph |
    | `data.[].events` | boolean, nullable |  | Whether events are shown in the graph |
    | `data.[].stacked` | enum: `area`, `stacked_area`, `line`, `stacked_line`, `bullet_chart`, `gauge`, `hbars`, `vbars`, `pie`, `bullet_chart_threshold`, `stacked_vbars` |  | Graph rendering type |
    | `data.[].idGroup` | integer, nullable |  | Group that owns the combined graph |
    | `data.[].idGraphTemplate` | integer, nullable |  | Template the graph was created from |
    | `data.[].percentil` | boolean, nullable |  | Whether the percentile series is rendered |
    | `data.[].summatorySeries` | boolean, nullable |  | Whether the summatory series is rendered |
    | `data.[].averageSeries` | boolean, nullable |  | Whether the average series is rendered |
    | `data.[].modulesSeries` | boolean, nullable |  | Whether module series are rendered |
    | `data.[].fullscale` | boolean, nullable |  | Whether the graph is rendered with full scale |
    | `data.[].idDataTranslation` | integer, nullable |  | Data translation applied to the series |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

## GraphSources

API Endpoints for combined graph series

### <span class="api-method api-post">POST</span> `/graph/{idGraph}/source` { #post-graph-idgraph-source }

Adds a series to a combined graph

On a metaconsole serverId selects the node that owns the graph

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idGraph` | path | integer | yes | Combined graph id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`GraphSource`](#model-graphsource)

**Response 200**: Combined graph source object

Schema: [`GraphSource`](#model-graphsource)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/graph/{idGraph}/source/{idGraphSource}` { #get-graph-idgraph-source-idgraphsource }

Gets a combined graph series

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idGraph` | path | integer | yes | Combined graph id |
| `idGraphSource` | path | integer | yes | Combined graph source id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Combined graph source object

Schema: [`GraphSource`](#model-graphsource)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-put">PUT</span> `/graph/{idGraph}/source/{idGraphSource}` { #put-graph-idgraph-source-idgraphsource }

Updates a combined graph series

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idGraph` | path | integer | yes | Combined graph id |
| `idGraphSource` | path | integer | yes | Combined graph source id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Request body** (`application/json`): [`GraphSource`](#model-graphsource)

**Response 200**: Combined graph source object

Schema: [`GraphSource`](#model-graphsource)

Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-delete">DELETE</span> `/graph/{idGraph}/source/{idGraphSource}` { #delete-graph-idgraph-source-idgraphsource }

Deletes a combined graph series

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idGraph` | path | integer | yes | Combined graph id |
| `idGraphSource` | path | integer | yes | Combined graph source id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-get">GET</span> `/graph/{idGraph}/source/list` { #get-graph-idgraph-source-list }

Lists the series of a combined graph

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idGraph` | path | integer | yes | Combined graph id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List of combined graph sources

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
    | `data.[].idGraphSource` | integer |  | Id of the graph source |
    | `data.[].idGraph` | integer |  | Combined graph that owns the source |
    | `data.[].serverId` | integer, nullable |  | Node that owns the source when it is read from a metaconsole |
    | `data.[].idServer` | integer, nullable |  | Stored node id used by the metaconsole renderer for this series |
    | `data.[].idAgentModule` | integer |  | Agent module rendered by the series |
    | `data.[].weight` | number (float), nullable |  | Series weight |
    | `data.[].label` | string, nullable |  | Series label |
    | `data.[].fieldOrder` | integer, nullable |  | Series order inside the graph |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/graph/{idGraph}/source/list` { #post-graph-idgraph-source-list }

Lists the series of a combined graph

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idGraph` | path | integer | yes | Combined graph id |
| `serverId` | query | integer |  | Target node id. Only available for federated resources from a metaconsole |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idGraphSource` | integer |  | Id of the graph source |
| `idGraph` | integer |  | Combined graph that owns the source |
| `serverId` | integer, nullable |  | Node that owns the source when it is read from a metaconsole |
| `idServer` | integer, nullable |  | Stored node id used by the metaconsole renderer for this series |
| `idAgentModule` | integer |  | Agent module rendered by the series |
| `weight` | number (float), nullable |  | Series weight |
| `label` | string, nullable |  | Series label |
| `fieldOrder` | integer, nullable |  | Series order inside the graph |
| `idGraphSource` |  |  |  |
| `freeSearch` | string, nullable |  | Find text in the series label |
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
| `multipleSearch.field` | enum: `idGraphSource`, `idGraph`, `idServer`, `idAgentModule`, `weight`, `label`, `fieldOrder` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idGraphSource`, `idGraph`, `idServer`, `idAgentModule`, `weight`, `label`, `fieldOrder` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgentModule": 0,
      "weight": 1,
      "label": "string",
      "fieldOrder": 0,
      "idGraphSource": null,
      "freeSearch": "string",
      "requestedFields": [
        "idGraphSource"
      ],
      "fieldConditions": [
        {
          "field": "idGraphSource",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idGraphSource",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idGraphSource",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List of combined graph sources

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
    | `data.[].idGraphSource` | integer |  | Id of the graph source |
    | `data.[].idGraph` | integer |  | Combined graph that owns the source |
    | `data.[].serverId` | integer, nullable |  | Node that owns the source when it is read from a metaconsole |
    | `data.[].idServer` | integer, nullable |  | Stored node id used by the metaconsole renderer for this series |
    | `data.[].idAgentModule` | integer |  | Agent module rendered by the series |
    | `data.[].weight` | number (float), nullable |  | Series weight |
    | `data.[].label` | string, nullable |  | Series label |
    | `data.[].fieldOrder` | integer, nullable |  | Series order inside the graph |


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

## Notifications

Notification sources, user preferences and console messages

### <span class="api-method api-post">POST</span> `/notification/message` { #post-notification-message }

Create a console notification

**Request body** (`application/json`): [`NotificationMessage`](#model-notificationmessage)

**Response 200**: Notification message

Schema: [`NotificationMessage`](#model-notificationmessage)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/notification/message/{idMessage}` { #get-notification-message-idmessage }

Get one console notification

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idMessage` | path | integer | yes |  |

**Response 200**: Notification message

Schema: [`NotificationMessage`](#model-notificationmessage)

Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/notification/message/{idMessage}` { #put-notification-message-idmessage }

Update a console notification

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idMessage` | path | integer | yes |  |

**Request body** (`application/json`): [`NotificationMessage`](#model-notificationmessage)

**Response 200**: Notification message

Schema: [`NotificationMessage`](#model-notificationmessage)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/notification/message/{idMessage}` { #delete-notification-message-idmessage }

Delete a console notification

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idMessage` | path | integer | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/notification/message/list` { #get-notification-message-list }

List console notifications

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Response 200**: List of notifications

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
    | `data.[].idMessage` | integer |  |  |
    | `data.[].idUser` | string |  |  |
    | `data.[].idSource` | integer, nullable |  |  |
    | `data.[].subject` | string |  |  |
    | `data.[].message` | string |  |  |
    | `data.[].url` | string, nullable |  |  |
    | `data.[].subtype` | string, nullable |  |  |
    | `data.[].createdAt` | integer |  |  |
    | `data.[].read` | boolean |  |  |


Error responses: `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/notification/message/list` { #post-notification-message-list }

List console notifications

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idMessage` | integer |  |  |
| `idUser` | string |  |  |
| `idSource` | integer, nullable |  |  |
| `subject` | string |  |  |
| `message` | string |  |  |
| `url` | string, nullable |  |  |
| `subtype` | string, nullable |  |  |
| `createdAt` | integer |  |  |
| `read` | boolean |  |  |
| `freeSearch` | string, nullable |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idUser": "string",
      "idSource": 0,
      "subject": "string",
      "message": "string",
      "url": "string",
      "subtype": "string",
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

**Response 200**: List of notifications

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
    | `data.[].idMessage` | integer |  |  |
    | `data.[].idUser` | string |  |  |
    | `data.[].idSource` | integer, nullable |  |  |
    | `data.[].subject` | string |  |  |
    | `data.[].message` | string |  |  |
    | `data.[].url` | string, nullable |  |  |
    | `data.[].subtype` | string, nullable |  |  |
    | `data.[].createdAt` | integer |  |  |
    | `data.[].read` | boolean |  |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/notification/source_user` { #post-notification-source-user }

Create or update a user notification preference

**Request body** (`application/json`): [`NotificationSourceUser`](#model-notificationsourceuser)

**Response 200**: Notification preference

Schema: [`NotificationSourceUser`](#model-notificationsourceuser)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/notification/source_user/{sourceId}/{idUser}` { #get-notification-source-user-sourceid-iduser }

Get a user notification preference

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `sourceId` | path | integer | yes |  |
| `idUser` | path | string | yes |  |

**Response 200**: Notification preference

Schema: [`NotificationSourceUser`](#model-notificationsourceuser)

Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/notification/source_user/{sourceId}/{idUser}` { #put-notification-source-user-sourceid-iduser }

Update a user notification preference

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `sourceId` | path | integer | yes |  |
| `idUser` | path | string | yes |  |

**Request body** (`application/json`): [`NotificationSourceUser`](#model-notificationsourceuser)

**Response 200**: Notification preference

Schema: [`NotificationSourceUser`](#model-notificationsourceuser)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/notification/source_user/{sourceId}/{idUser}` { #delete-notification-source-user-sourceid-iduser }

Delete a user notification preference

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `sourceId` | path | integer | yes |  |
| `idUser` | path | string | yes |  |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/notification/source_user/list` { #get-notification-source-user-list }

List user notification preferences

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Response 200**: List of notification preferences

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
    | `data.[].sourceId` | integer |  |  |
    | `data.[].idUser` | string |  |  |
    | `data.[].preference` | string |  |  |
    | `data.[].configured` | boolean |  |  |
    | `data.[].editable` | boolean |  |  |


Error responses: `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/notification/source_user/list` { #post-notification-source-user-list }

List user notification preferences

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `sourceId` | integer |  |  |
| `idUser` | string |  |  |
| `preference` | string |  |  |
| `configured` | boolean |  |  |
| `editable` | boolean |  |  |
| `freeSearch` | string, nullable |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "preference": "string",
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

**Response 200**: List of notification preferences

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
    | `data.[].sourceId` | integer |  |  |
    | `data.[].idUser` | string |  |  |
    | `data.[].preference` | string |  |  |
    | `data.[].configured` | boolean |  |  |
    | `data.[].editable` | boolean |  |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-get">GET</span> `/notification/source/{idSource}` { #get-notification-source-idsource }

Get one notification source

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idSource` | path | integer | yes |  |

**Response 200**: Notification source

??? note "Response fields (5 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idSource` | integer |  |  |
    | `description` | string |  |  |
    | `enabled` | boolean |  |  |
    | `userEditable` | boolean |  |  |
    | `alsoMail` | boolean |  |  |


Error responses: `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/notification/source/list` { #get-notification-source-list }

List notification sources

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Response 200**: List of notification sources

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
    | `data.[].idSource` | integer |  |  |
    | `data.[].description` | string |  |  |
    | `data.[].enabled` | boolean |  |  |
    | `data.[].userEditable` | boolean |  |  |
    | `data.[].alsoMail` | boolean |  |  |


Error responses: `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/notification/source/list` { #post-notification-source-list }

List notification sources

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idSource` | integer |  |  |
| `description` | string |  |  |
| `enabled` | boolean |  |  |
| `userEditable` | boolean |  |  |
| `alsoMail` | boolean |  |  |
| `freeSearch` | string, nullable |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
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

**Response 200**: List of notification sources

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
    | `data.[].idSource` | integer |  |  |
    | `data.[].description` | string |  |  |
    | `data.[].enabled` | boolean |  |  |
    | `data.[].userEditable` | boolean |  |  |
    | `data.[].alsoMail` | boolean |  |  |


Error responses: `400`, `401`, `403`, `500`.

## Emails

Email delivery through the console transport

### <span class="api-method api-get">GET</span> `/mail/config` { #get-mail-config }

Get the mail transport configuration without credentials

**Response 200**: Mail transport configuration

??? note "Response fields (10 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `configured` | boolean |  | Mail transport configuration without credentials. |
    | `transport` | enum: `smtp`, `oauth2` |  |  |
    | `host` | string, nullable |  |  |
    | `port` | integer, nullable |  |  |
    | `timeout` | integer, nullable |  |  |
    | `encryption` | string, nullable |  |  |
    | `fromAddress` | string, nullable |  |  |
    | `fromName` | string, nullable |  |  |
    | `oauth2` | boolean |  |  |
    | `oauthProvider` | string, nullable |  |  |


Error responses: `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/email/send` { #post-email-send }

Send an email through the console mail transport

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idUser` | string |  |  |
| `subject` | string |  |  |
| `body` | string |  |  |
| `contentType` | enum: `text/plain`, `text/html` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idUser": "string",
      "subject": "string",
      "body": "string",
      "contentType": "text/plain"
    }
    ```

**Response 200**: Email delivery result

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `sent` | boolean |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: Dashboard { #model-dashboard }

??? note "Fields (13 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idDashboard` | integer |  |  |
    | `name` | string |  |  |
    | `idUser` | string |  |  |
    | `idGroup` | integer |  |  |
    | `internal` | boolean |  |  |
    | `active` | boolean |  |  |
    | `cells` | integer |  |  |
    | `cellsSlideshow` | boolean |  |  |
    | `dateRange` | boolean |  |  |
    | `dateRangeData` | object, nullable |  |  |
    | `userFullName` | string, nullable |  |  |
    | `groupName` | string, nullable |  |  |
    | `widgetCount` | integer |  |  |


### Model: DashboardWidget { #model-dashboardwidget }

| Field | Type | Required | Description |
|---|---|---|---|
| `idDashboardWidget` | integer |  |  |
| `idDashboard` | integer |  |  |
| `idWidget` | integer, nullable |  |  |
| `position` | object, nullable |  |  |
| `options` | object, nullable |  |  |
| `order` | integer |  |  |
| `propWidth` | number (double) |  |  |
| `propHeight` | number (double) |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idWidget": 0,
      "position": {},
      "options": {},
      "order": 0,
      "propWidth": 0.32,
      "propHeight": 0.32
    }
    ```

### Model: Graph { #model-graph }

| Field | Type | Required | Description |
|---|---|---|---|
| `idGraph` | integer |  | Id of the combined graph |
| `idUser` | string |  | Owner user of the combined graph |
| `serverId` | integer, nullable |  | Node that owns the combined graph when it is read from a metaconsole |
| `name` | string |  | Name of the combined graph |
| `description` | string, nullable |  | Description of the combined graph |
| `period` | integer, nullable |  | Default period in seconds |
| `width` | integer, nullable |  | Graph width |
| `height` | integer, nullable |  | Graph height |
| `private` | boolean, nullable |  | Only the owner can see a private graph |
| `events` | boolean, nullable |  | Whether events are shown in the graph |
| `stacked` | enum: `area`, `stacked_area`, `line`, `stacked_line`, `bullet_chart`, `gauge`, `hbars`, `vbars`, `pie`, `bullet_chart_threshold`, `stacked_vbars` |  | Graph rendering type |
| `idGroup` | integer, nullable |  | Group that owns the combined graph |
| `idGraphTemplate` | integer, nullable |  | Template the graph was created from |
| `percentil` | boolean, nullable |  | Whether the percentile series is rendered |
| `summatorySeries` | boolean, nullable |  | Whether the summatory series is rendered |
| `averageSeries` | boolean, nullable |  | Whether the average series is rendered |
| `modulesSeries` | boolean, nullable |  | Whether module series are rendered |
| `fullscale` | boolean, nullable |  | Whether the graph is rendered with full scale |
| `idDataTranslation` | integer, nullable |  | Data translation applied to the series |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "period": 0,
      "width": 0,
      "height": 0,
      "private": false,
      "events": false,
      "stacked": "area",
      "idGroup": 0,
      "percentil": false,
      "summatorySeries": false,
      "averageSeries": false,
      "modulesSeries": false,
      "fullscale": false,
      "idDataTranslation": 0
    }
    ```

### Model: GraphSource { #model-graphsource }

| Field | Type | Required | Description |
|---|---|---|---|
| `idGraphSource` | integer |  | Id of the graph source |
| `idGraph` | integer |  | Combined graph that owns the source |
| `serverId` | integer, nullable |  | Node that owns the source when it is read from a metaconsole |
| `idServer` | integer, nullable |  | Stored node id used by the metaconsole renderer for this series |
| `idAgentModule` | integer |  | Agent module rendered by the series |
| `weight` | number (float), nullable |  | Series weight |
| `label` | string, nullable |  | Series label |
| `fieldOrder` | integer, nullable |  | Series order inside the graph |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgentModule": 0,
      "weight": 1,
      "label": "string",
      "fieldOrder": 0
    }
    ```

### Model: NotificationMessage { #model-notificationmessage }

| Field | Type | Required | Description |
|---|---|---|---|
| `idMessage` | integer |  |  |
| `idUser` | string |  |  |
| `idSource` | integer, nullable |  |  |
| `subject` | string |  |  |
| `message` | string |  |  |
| `url` | string, nullable |  |  |
| `subtype` | string, nullable |  |  |
| `createdAt` | integer |  |  |
| `read` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idUser": "string",
      "idSource": 0,
      "subject": "string",
      "message": "string",
      "url": "string",
      "subtype": "string"
    }
    ```

### Model: NotificationSourceUser { #model-notificationsourceuser }

| Field | Type | Required | Description |
|---|---|---|---|
| `sourceId` | integer |  |  |
| `idUser` | string |  |  |
| `preference` | string |  |  |
| `configured` | boolean |  |  |
| `editable` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "preference": "string"
    }
    ```
