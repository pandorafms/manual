# Reports

Report designs, pages, widgets, templates and data sources.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-post">POST</span> | [`/report/design`](#post-report-design) | Creates a new report design |
| <span class="api-method api-get">GET</span> | [`/report/design/{idReportDesign}`](#get-report-design-idreportdesign) | Show report design |
| <span class="api-method api-put">PUT</span> | [`/report/design/{idReportDesign}`](#put-report-design-idreportdesign) | Updates a Report Design |
| <span class="api-method api-delete">DELETE</span> | [`/report/design/{idReportDesign}`](#delete-report-design-idreportdesign) | Deletes a report design object. |
| <span class="api-method api-get">GET</span> | [`/report/design/list`](#get-report-design-list) | List Report Design |
| <span class="api-method api-post">POST</span> | [`/report/design/list`](#post-report-design-list) | List Report Design |
| <span class="api-method api-get">GET</span> | [`/report/design/{idReportDesign}/history`](#get-report-design-idreportdesign-history) | Gets the current history entry for a report design |
| <span class="api-method api-post">POST</span> | [`/report/design/{idReportDesign}/history`](#post-report-design-idreportdesign-history) | Pushes a new history entry for a report design |
| <span class="api-method api-put">PUT</span> | [`/report/design/{idReportDesign}/history`](#put-report-design-idreportdesign-history) | Moves the history cursor (undo/redo) for a report design |
| <span class="api-method api-delete">DELETE</span> | [`/report/design/{idReportDesign}/history`](#delete-report-design-idreportdesign-history) | Deletes all history entries for a report design and user |
| <span class="api-method api-get">GET</span> | [`/report/design/{idReportDesign}/history/list`](#get-report-design-idreportdesign-history-list) | List history entries for a report design |
| <span class="api-method api-post">POST</span> | [`/report/design/{idReportDesign}/history/list`](#post-report-design-idreportdesign-history-list) | List history entries for a report design |
| <span class="api-method api-post">POST</span> | [`/report/design/{idReportDesign}/report`](#post-report-design-idreportdesign-report) | Creates a new report entry |
| <span class="api-method api-get">GET</span> | [`/report/design/{idReportDesign}/report/{idReportDesignReport}`](#get-report-design-idreportdesign-report-idreportdesignreport) | Show report details |
| <span class="api-method api-put">PUT</span> | [`/report/design/{idReportDesign}/report/{idReportDesignReport}`](#put-report-design-idreportdesign-report-idreportdesignreport) | Updates a report entry |
| <span class="api-method api-delete">DELETE</span> | [`/report/design/{idReportDesign}/report/{idReportDesignReport}`](#delete-report-design-idreportdesign-report-idreportdesignreport) | Deletes a report entry. |
| <span class="api-method api-get">GET</span> | [`/report/design/{idReportDesign}/report/list`](#get-report-design-idreportdesign-report-list) | List Report |
| <span class="api-method api-post">POST</span> | [`/report/design/{idReportDesign}/report/list`](#post-report-design-idreportdesign-report-list) | List Report |
| <span class="api-method api-post">POST</span> | [`/report/design/{idReportDesign}/template`](#post-report-design-idreportdesign-template) | Creates a new report design template |
| <span class="api-method api-get">GET</span> | [`/report/design/{idReportDesign}/template/{idReportDesignTemplate}`](#get-report-design-idreportdesign-template-idreportdesigntemplate) | Show report design template |
| <span class="api-method api-put">PUT</span> | [`/report/design/{idReportDesign}/template/{idReportDesignTemplate}`](#put-report-design-idreportdesign-template-idreportdesigntemplate) | Updates a report design template |
| <span class="api-method api-delete">DELETE</span> | [`/report/design/{idReportDesign}/template/{idReportDesignTemplate}`](#delete-report-design-idreportdesign-template-idreportdesigntemplate) | Deletes a report design template object. |
| <span class="api-method api-get">GET</span> | [`/report/design/{idReportDesign}/template/list`](#get-report-design-idreportdesign-template-list) | List report design templates |
| <span class="api-method api-post">POST</span> | [`/report/design/{idReportDesign}/template/list`](#post-report-design-idreportdesign-template-list) | List report design templates |
| <span class="api-method api-post">POST</span> | [`/report/design/{idReportDesign}/page`](#post-report-design-idreportdesign-page) | Creates a new report design page |
| <span class="api-method api-get">GET</span> | [`/report/design/{idReportDesign}/page/{idReportDesignPage}`](#get-report-design-idreportdesign-page-idreportdesignpage) | Show report design page details |
| <span class="api-method api-put">PUT</span> | [`/report/design/{idReportDesign}/page/{idReportDesignPage}`](#put-report-design-idreportdesign-page-idreportdesignpage) | Updates a Report Design Page |
| <span class="api-method api-delete">DELETE</span> | [`/report/design/{idReportDesign}/page/{idReportDesignPage}`](#delete-report-design-idreportdesign-page-idreportdesignpage) | Deletes a report design page. |
| <span class="api-method api-get">GET</span> | [`/report/design/{idReportDesign}/page/list`](#get-report-design-idreportdesign-page-list) | List Report Design Pages |
| <span class="api-method api-post">POST</span> | [`/report/design/{idReportDesign}/page/list`](#post-report-design-idreportdesign-page-list) | List Report Design Pages |
| <span class="api-method api-post">POST</span> | [`/report/design/{idReportDesign}/page/{idReportDesignPage}/widget`](#post-report-design-idreportdesign-page-idreportdesignpage-widget) | Creates a new report design page widget |
| <span class="api-method api-get">GET</span> | [`/report/design/{idReportDesign}/page/{idReportDesignPage}/widget/{idReportDesignPageWidget}`](#get-report-design-idreportdesign-page-idreportdesignpage-widget-idreportdesignpagewidget) | Show report design page widget details |
| <span class="api-method api-put">PUT</span> | [`/report/design/{idReportDesign}/page/{idReportDesignPage}/widget/{idReportDesignPageWidget}`](#put-report-design-idreportdesign-page-idreportdesignpage-widget-idreportdesignpagewidget) | Updates a Report Design Page Widget |
| <span class="api-method api-delete">DELETE</span> | [`/report/design/{idReportDesign}/page/{idReportDesignPage}/widget/{idReportDesignPageWidget}`](#delete-report-design-idreportdesign-page-idreportdesignpage-widget-idreportdesignpagewidget) | Deletes a report design page widget. |
| <span class="api-method api-get">GET</span> | [`/report/design/{idReportDesign}/page/{idReportDesignPage}/widget/list`](#get-report-design-idreportdesign-page-idreportdesignpage-widget-list) | List Report Design Page Widgets |
| <span class="api-method api-post">POST</span> | [`/report/design/{idReportDesign}/page/{idReportDesignPage}/widget/list`](#post-report-design-idreportdesign-page-idreportdesignpage-widget-list) | List Report Design Page Widgets |
| <span class="api-method api-post">POST</span> | [`/report/dataSource`](#post-report-datasource) | Creates a new report data source |
| <span class="api-method api-get">GET</span> | [`/report/dataSource/{idReportDataSource}`](#get-report-datasource-idreportdatasource) | Show report data source |
| <span class="api-method api-put">PUT</span> | [`/report/dataSource/{idReportDataSource}`](#put-report-datasource-idreportdatasource) | Updates a report data source |
| <span class="api-method api-delete">DELETE</span> | [`/report/dataSource/{idReportDataSource}`](#delete-report-datasource-idreportdatasource) | Deletes a report data source. |
| <span class="api-method api-get">GET</span> | [`/report/dataSource/list`](#get-report-datasource-list) | List Report data sources |
| <span class="api-method api-post">POST</span> | [`/report/dataSource/list`](#post-report-datasource-list) | List Report data sources |
| <span class="api-method api-post">POST</span> | [`/report/dataSource/{idReportDataSource}/agent`](#post-report-datasource-idreportdatasource-agent) | Creates a new report dataSource agent |
| <span class="api-method api-get">GET</span> | [`/report/dataSource/{idReportDataSource}/agent/{idReportDataSourceAgent}`](#get-report-datasource-idreportdatasource-agent-idreportdatasourceagent) | Show report dataSource agent details |
| <span class="api-method api-put">PUT</span> | [`/report/dataSource/{idReportDataSource}/agent/{idReportDataSourceAgent}`](#put-report-datasource-idreportdatasource-agent-idreportdatasourceagent) | Updates a report dataSource agent |
| <span class="api-method api-delete">DELETE</span> | [`/report/dataSource/{idReportDataSource}/agent/{idReportDataSourceAgent}`](#delete-report-datasource-idreportdatasource-agent-idreportdatasourceagent) | Deletes a report dataSource agent. |
| <span class="api-method api-get">GET</span> | [`/report/dataSource/{idReportDataSource}/agent/list`](#get-report-datasource-idreportdatasource-agent-list) | List report dataSource agents |
| <span class="api-method api-post">POST</span> | [`/report/dataSource/{idReportDataSource}/agent/list`](#post-report-datasource-idreportdatasource-agent-list) | List report dataSource agents |
| <span class="api-method api-post">POST</span> | [`/report/dataSource/{idReportDataSource}/group`](#post-report-datasource-idreportdatasource-group) | Creates a new report data source group |
| <span class="api-method api-get">GET</span> | [`/report/dataSource/{idReportDataSource}/group/{idReportDataSourceGroup}`](#get-report-datasource-idreportdatasource-group-idreportdatasourcegroup) | Show report data source group details |
| <span class="api-method api-put">PUT</span> | [`/report/dataSource/{idReportDataSource}/group/{idReportDataSourceGroup}`](#put-report-datasource-idreportdatasource-group-idreportdatasourcegroup) | Updates a report data source group |
| <span class="api-method api-delete">DELETE</span> | [`/report/dataSource/{idReportDataSource}/group/{idReportDataSourceGroup}`](#delete-report-datasource-idreportdatasource-group-idreportdatasourcegroup) | Deletes a report data source group. |
| <span class="api-method api-get">GET</span> | [`/report/dataSource/{idReportDataSource}/group/list`](#get-report-datasource-idreportdatasource-group-list) | List report data source groups |
| <span class="api-method api-post">POST</span> | [`/report/dataSource/{idReportDataSource}/group/list`](#post-report-datasource-idreportdatasource-group-list) | List report data source groups |

## ReportDesigns

API Endpoints for report designs

### <span class="api-method api-post">POST</span> `/report/design` { #post-report-design }

Creates a new report design

**Request body** (`application/json`): [`ReportDesign`](#model-reportdesign)

**Response 200**: Report design object

Schema: [`ReportDesign`](#model-reportdesign)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/design/{idReportDesign}` { #get-report-design-idreportdesign }

Show report design

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |

**Response 200**: Report design object

Schema: [`ReportDesign`](#model-reportdesign)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/report/design/{idReportDesign}` { #put-report-design-idreportdesign }

Updates a Report Design

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |

**Request body** (`application/json`): [`ReportDesign`](#model-reportdesign)

**Response 200**: Report design object

Schema: [`ReportDesign`](#model-reportdesign)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/report/design/{idReportDesign}` { #delete-report-design-idreportdesign }

Deletes a report design object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/design/list` { #get-report-design-list }

List Report Design

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Report Design object

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
    | `data.[].idReportDesign` | integer |  | Id ReportDesign |
    | `data.[].name` | string |  | Name of the reportDesign |
    | `data.[].idGroup` | integer, nullable |  | Id of the group to which the report design belongs |
    | `data.[].description` | string, nullable |  | Description of the reportDesign |
    | `data.[].pagesDefaultDirection` | enum: `vertical`, `horizontal` |  | Default direction of the pages in the report design, either vertical or horizontal |
    | `data.[].isPdfCoverRender` | boolean, nullable |  | Indicates if the PDF cover is rendered in the report design |
    | `data.[].isPdfIndexRender` | boolean, nullable |  | Indicates if the PDF index is rendered in the report design |
    | `data.[].isPdfHeaderRender` | boolean, nullable |  | Indicates if the PDF header is rendered in the report design |
    | `data.[].isPdfFooterRender` | boolean, nullable |  | Indicates if the PDF footer is rendered in the report design |
    | `data.[].pdfHeader` | string, nullable |  | PDF header content of the report design |
    | `data.[].pdfCover` | string, nullable |  | PDF cover content of the report design |
    | `data.[].pdfFooter` | string, nullable |  | PDF footer content of the report design |
    | `data.[].createdAt` | number |  | Creation timestamp of the report design |
    | `data.[].updatedAt` | number |  | Last update timestamp of the report design |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/report/design/list` { #post-report-design-list }

List Report Design

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
| `idReportDesign` | integer |  | Id ReportDesign |
| `name` | string |  | Name of the reportDesign |
| `idGroup` | integer, nullable |  | Id of the group to which the report design belongs |
| `description` | string, nullable |  | Description of the reportDesign |
| `pagesDefaultDirection` | enum: `vertical`, `horizontal` |  | Default direction of the pages in the report design, either vertical or horizontal |
| `isPdfCoverRender` | boolean, nullable |  | Indicates if the PDF cover is rendered in the report design |
| `isPdfIndexRender` | boolean, nullable |  | Indicates if the PDF index is rendered in the report design |
| `isPdfHeaderRender` | boolean, nullable |  | Indicates if the PDF header is rendered in the report design |
| `isPdfFooterRender` | boolean, nullable |  | Indicates if the PDF footer is rendered in the report design |
| `pdfHeader` | string, nullable |  | PDF header content of the report design |
| `pdfCover` | string, nullable |  | PDF cover content of the report design |
| `pdfFooter` | string, nullable |  | PDF footer content of the report design |
| `createdAt` | number |  | Creation timestamp of the report design |
| `updatedAt` | number |  | Last update timestamp of the report design |
| `idReportDesign` |  |  |  |
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
      "idGroup": 0,
      "description": "string",
      "pagesDefaultDirection": "vertical",
      "isPdfCoverRender": false,
      "isPdfIndexRender": false,
      "isPdfHeaderRender": false,
      "isPdfFooterRender": false,
      "pdfHeader": "string",
      "pdfCover": "string",
      "pdfFooter": "string",
      "createdAt": 0,
      "updatedAt": 0,
      "idReportDesign": null,
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

**Response 200**: List Report Design object

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
    | `data.[].idReportDesign` | integer |  | Id ReportDesign |
    | `data.[].name` | string |  | Name of the reportDesign |
    | `data.[].idGroup` | integer, nullable |  | Id of the group to which the report design belongs |
    | `data.[].description` | string, nullable |  | Description of the reportDesign |
    | `data.[].pagesDefaultDirection` | enum: `vertical`, `horizontal` |  | Default direction of the pages in the report design, either vertical or horizontal |
    | `data.[].isPdfCoverRender` | boolean, nullable |  | Indicates if the PDF cover is rendered in the report design |
    | `data.[].isPdfIndexRender` | boolean, nullable |  | Indicates if the PDF index is rendered in the report design |
    | `data.[].isPdfHeaderRender` | boolean, nullable |  | Indicates if the PDF header is rendered in the report design |
    | `data.[].isPdfFooterRender` | boolean, nullable |  | Indicates if the PDF footer is rendered in the report design |
    | `data.[].pdfHeader` | string, nullable |  | PDF header content of the report design |
    | `data.[].pdfCover` | string, nullable |  | PDF cover content of the report design |
    | `data.[].pdfFooter` | string, nullable |  | PDF footer content of the report design |
    | `data.[].createdAt` | number |  | Creation timestamp of the report design |
    | `data.[].updatedAt` | number |  | Last update timestamp of the report design |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/design/{idReportDesign}/history` { #get-report-design-idreportdesign-history }

Gets the current history entry for a report design

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |

**Response 200**: Report design history object

Schema: [`ReportDesignHistory`](#model-reportdesignhistory)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/report/design/{idReportDesign}/history` { #post-report-design-idreportdesign-history }

Pushes a new history entry for a report design

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |

**Request body** (`application/json`): [`ReportDesignHistory`](#model-reportdesignhistory)

**Response 200**: Report design history object

Schema: [`ReportDesignHistory`](#model-reportdesignhistory)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/report/design/{idReportDesign}/history` { #put-report-design-idreportdesign-history }

Moves the history cursor (undo/redo) for a report design

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |

**Request body** (`application/json`): [`ReportDesignHistory`](#model-reportdesignhistory)

**Response 200**: Report design history object

Schema: [`ReportDesignHistory`](#model-reportdesignhistory)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/report/design/{idReportDesign}/history` { #delete-report-design-idreportdesign-history }

Deletes all history entries for a report design and user

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/design/{idReportDesign}/history/list` { #get-report-design-idreportdesign-history-list }

List history entries for a report design

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List ReportDesignHistory object

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
    | `data.[].idReportDesignHistory` | integer |  | Id ReportDesignHistory |
    | `data.[].idReportDesign` | integer |  | Id of the report design this history entry belongs to |
    | `data.[].idUser` | string |  | Id of the user who owns this history stack |
    | `data.[].sequence` | integer |  | Position in the undo/redo stack (0-based) |
    | `data.[].state` | array of object |  | Serialised builder state snapshot |
    | `data.[].isCurrent` | boolean |  | Whether this entry is the current cursor position |
    | `data.[].isSavedCheckpoint` | boolean |  | Whether this entry corresponds to the last explicit save |
    | `data.[].createdAt` | number |  | Creation timestamp of the history entry |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/report/design/{idReportDesign}/history/list` { #post-report-design-idreportdesign-history-list }

List history entries for a report design

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDesignHistory` | integer |  | Id ReportDesignHistory |
| `idReportDesign` | integer |  | Id of the report design this history entry belongs to |
| `idUser` | string |  | Id of the user who owns this history stack |
| `sequence` | integer |  | Position in the undo/redo stack (0-based) |
| `state` | array of object |  | Serialised builder state snapshot |
| `isCurrent` | boolean |  | Whether this entry is the current cursor position |
| `isSavedCheckpoint` | boolean |  | Whether this entry corresponds to the last explicit save |
| `createdAt` | number |  | Creation timestamp of the history entry |
| `idReportDesignHistory` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in idUser field. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "sequence": 0,
      "state": [
        {}
      ],
      "isCurrent": false,
      "isSavedCheckpoint": false,
      "idReportDesignHistory": null,
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

**Response 200**: List ReportDesignHistory object

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
    | `data.[].idReportDesignHistory` | integer |  | Id ReportDesignHistory |
    | `data.[].idReportDesign` | integer |  | Id of the report design this history entry belongs to |
    | `data.[].idUser` | string |  | Id of the user who owns this history stack |
    | `data.[].sequence` | integer |  | Position in the undo/redo stack (0-based) |
    | `data.[].state` | array of object |  | Serialised builder state snapshot |
    | `data.[].isCurrent` | boolean |  | Whether this entry is the current cursor position |
    | `data.[].isSavedCheckpoint` | boolean |  | Whether this entry corresponds to the last explicit save |
    | `data.[].createdAt` | number |  | Creation timestamp of the history entry |


Error responses: `400`, `401`, `403`, `404`, `500`.

## ReportDesignReports

API Endpoints for report design reports

### <span class="api-method api-post">POST</span> `/report/design/{idReportDesign}/report` { #post-report-design-idreportdesign-report }

Creates a new report entry

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |

**Request body** (`application/json`): [`ReportDesignReport`](#model-reportdesignreport)

**Response 200**: Report object

Schema: [`ReportDesignReport`](#model-reportdesignreport)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/design/{idReportDesign}/report/{idReportDesignReport}` { #get-report-design-idreportdesign-report-idreportdesignreport }

Show report details

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignReport` | path | integer | yes | Report id |

**Response 200**: Report object

Schema: [`ReportDesignReport`](#model-reportdesignreport)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/report/design/{idReportDesign}/report/{idReportDesignReport}` { #put-report-design-idreportdesign-report-idreportdesignreport }

Updates a report entry

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignReport` | path | integer | yes | Report id |

**Request body** (`application/json`): [`ReportDesignReport`](#model-reportdesignreport)

**Response 200**: Report object

Schema: [`ReportDesignReport`](#model-reportdesignreport)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/report/design/{idReportDesign}/report/{idReportDesignReport}` { #delete-report-design-idreportdesign-report-idreportdesignreport }

Deletes a report entry.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignReport` | path | integer | yes | Report id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/design/{idReportDesign}/report/list` { #get-report-design-idreportdesign-report-list }

List Report

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Report object

??? note "Response fields (31 fields)"

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
    | `data.[].idReportDesignReport` | integer |  | Id Report |
    | `data.[].idReportDesign` | integer |  | Id of the parent report design |
    | `data.[].idReportDesignTemplate` | integer, nullable |  | Id of the report design template |
    | `data.[].owner` | string, nullable |  | Owner of the report |
    | `data.[].fileName` | string, nullable |  | Generated file name |
    | `data.[].idGroup` | integer, nullable |  | Id of the group |
    | `data.[].description` | string, nullable |  | Description of the report |
    | `data.[].idReportDataSource` | integer, nullable |  | Id of the report data source |
    | `data.[].dateRange` | array, nullable |  | Date range configuration |
    | `data.[].reportType` | enum: `HTML`, `PDF`, `JSON`, `CSV` |  | Report output type |
    | `data.[].notify` | boolean |  | Whether to notify on completion |
    | `data.[].sendByEmail` | boolean |  | Whether to send the report by email |
    | `data.[].emailTargets` | array, nullable |  | List of email targets |
    | `data.[].emailSubject` | string |  | Email subject |
    | `data.[].emailBody` | string |  | Email body |
    | `data.[].status` | enum: `PENDING`, `COMPLETED`, `FAILED` |  | Generation status |
    | `data.[].progress` | array, nullable |  | Progress data |
    | `data.[].errorMessage` | string, nullable |  | Error message if generation failed |
    | `data.[].queuedAt` | number |  | Queued timestamp |
    | `data.[].createdAt` | number |  | Creation timestamp |
    | `data.[].completedAt` | number, nullable |  | Completion timestamp |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/report/design/{idReportDesign}/report/list` { #post-report-design-idreportdesign-report-list }

List Report

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDesignReport` | integer |  | Id Report |
| `idReportDesign` | integer |  | Id of the parent report design |
| `idReportDesignTemplate` | integer, nullable |  | Id of the report design template |
| `owner` | string, nullable |  | Owner of the report |
| `fileName` | string, nullable |  | Generated file name |
| `idGroup` | integer, nullable |  | Id of the group |
| `description` | string, nullable |  | Description of the report |
| `idReportDataSource` | integer, nullable |  | Id of the report data source |
| `dateRange` | array, nullable |  | Date range configuration |
| `reportType` | enum: `HTML`, `PDF`, `JSON`, `CSV` |  | Report output type |
| `notify` | boolean |  | Whether to notify on completion |
| `sendByEmail` | boolean |  | Whether to send the report by email |
| `emailTargets` | array, nullable |  | List of email targets |
| `emailSubject` | string |  | Email subject |
| `emailBody` | string |  | Email body |
| `status` | enum: `PENDING`, `COMPLETED`, `FAILED` |  | Generation status |
| `progress` | array, nullable |  | Progress data |
| `errorMessage` | string, nullable |  | Error message if generation failed |
| `queuedAt` | number |  | Queued timestamp |
| `createdAt` | number |  | Creation timestamp |
| `completedAt` | number, nullable |  | Completion timestamp |
| `idReportDesignReport` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in owner, file_name and email_subject fields. |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idReportDesignTemplate": 0,
      "owner": "string",
      "fileName": "string",
      "idGroup": 0,
      "description": "string",
      "idReportDataSource": 0,
      "dateRange": [
        "string"
      ],
      "reportType": "HTML",
      "notify": false,
      "sendByEmail": false,
      "emailTargets": [
        "string"
      ],
      "emailSubject": "string",
      "emailBody": "string",
      "errorMessage": "string",
      "idReportDesignReport": null,
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

**Response 200**: List Report object

??? note "Response fields (31 fields)"

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
    | `data.[].idReportDesignReport` | integer |  | Id Report |
    | `data.[].idReportDesign` | integer |  | Id of the parent report design |
    | `data.[].idReportDesignTemplate` | integer, nullable |  | Id of the report design template |
    | `data.[].owner` | string, nullable |  | Owner of the report |
    | `data.[].fileName` | string, nullable |  | Generated file name |
    | `data.[].idGroup` | integer, nullable |  | Id of the group |
    | `data.[].description` | string, nullable |  | Description of the report |
    | `data.[].idReportDataSource` | integer, nullable |  | Id of the report data source |
    | `data.[].dateRange` | array, nullable |  | Date range configuration |
    | `data.[].reportType` | enum: `HTML`, `PDF`, `JSON`, `CSV` |  | Report output type |
    | `data.[].notify` | boolean |  | Whether to notify on completion |
    | `data.[].sendByEmail` | boolean |  | Whether to send the report by email |
    | `data.[].emailTargets` | array, nullable |  | List of email targets |
    | `data.[].emailSubject` | string |  | Email subject |
    | `data.[].emailBody` | string |  | Email body |
    | `data.[].status` | enum: `PENDING`, `COMPLETED`, `FAILED` |  | Generation status |
    | `data.[].progress` | array, nullable |  | Progress data |
    | `data.[].errorMessage` | string, nullable |  | Error message if generation failed |
    | `data.[].queuedAt` | number |  | Queued timestamp |
    | `data.[].createdAt` | number |  | Creation timestamp |
    | `data.[].completedAt` | number, nullable |  | Completion timestamp |


Error responses: `400`, `401`, `403`, `404`, `500`.

## ReportDesignTemplates

API Endpoints for report design templates

### <span class="api-method api-post">POST</span> `/report/design/{idReportDesign}/template` { #post-report-design-idreportdesign-template }

Creates a new report design template

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |

**Request body** (`application/json`): [`ReportDesignTemplate`](#model-reportdesigntemplate)

**Response 200**: ReportDesignTemplate object

Schema: [`ReportDesignTemplate`](#model-reportdesigntemplate)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/design/{idReportDesign}/template/{idReportDesignTemplate}` { #get-report-design-idreportdesign-template-idreportdesigntemplate }

Show report design template

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignTemplate` | path | integer | yes | ReportDesignTemplate id |

**Response 200**: ReportDesignTemplate object

Schema: [`ReportDesignTemplate`](#model-reportdesigntemplate)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/report/design/{idReportDesign}/template/{idReportDesignTemplate}` { #put-report-design-idreportdesign-template-idreportdesigntemplate }

Updates a report design template

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignTemplate` | path | integer | yes | ReportDesignTemplate id |

**Request body** (`application/json`): [`ReportDesignTemplate`](#model-reportdesigntemplate)

**Response 200**: ReportDesignTemplate object

Schema: [`ReportDesignTemplate`](#model-reportdesigntemplate)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/report/design/{idReportDesign}/template/{idReportDesignTemplate}` { #delete-report-design-idreportdesign-template-idreportdesigntemplate }

Deletes a report design template object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignTemplate` | path | integer | yes | ReportDesignTemplate id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/design/{idReportDesign}/template/list` { #get-report-design-idreportdesign-template-list }

List report design templates

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List report design templates object

??? note "Response fields (30 fields)"

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
    | `data.[].idReportDesignTemplate` | integer |  | Id design template |
    | `data.[].idReportDesign` | integer |  | Id of the report design to which this template belongs |
    | `data.[].owner` | string |  | User id owner of this template |
    | `data.[].name` | string |  | Name of the template |
    | `data.[].idGroup` | integer, nullable |  | Group id |
    | `data.[].description` | string, nullable |  | Description |
    | `data.[].idReportDataSource` | integer, nullable |  | Id of the report data source |
    | `data.[].dateRange` | array, nullable |  | Date range configuration |
    | `data.[].reportType` | enum: `HTML`, `PDF`, `JSON`, `CSV` |  | Report output type |
    | `data.[].scheduled` | enum: `NO`, `DAILY`, `WEEKLY`, `MONTHLY` |  | Scheduling frequency |
    | `data.[].lastGenerationTimestamp` | number, nullable |  | Timestamp of last generation |
    | `data.[].nextGenerationTimestamp` | number, nullable |  | Timestamp of next scheduled generation |
    | `data.[].enabled` | boolean |  | Whether this template is enabled |
    | `data.[].notify` | boolean |  | Whether to send notifications |
    | `data.[].sendByEmail` | boolean |  | Whether to send the report by email |
    | `data.[].emailTargets` | array, nullable |  | List of email addresses to send the report to |
    | `data.[].emailSubject` | string |  | Email subject |
    | `data.[].emailBody` | string |  | Email body |
    | `data.[].createdAt` | number |  | Creation timestamp of the report design template |
    | `data.[].updatedAt` | number |  | Last update timestamp of the report design template |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/report/design/{idReportDesign}/template/list` { #post-report-design-idreportdesign-template-list }

List report design templates

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDesignTemplate` | integer |  | Id design template |
| `idReportDesign` | integer |  | Id of the report design to which this template belongs |
| `owner` | string |  | User id owner of this template |
| `name` | string |  | Name of the template |
| `idGroup` | integer, nullable |  | Group id |
| `description` | string, nullable |  | Description |
| `idReportDataSource` | integer, nullable |  | Id of the report data source |
| `dateRange` | array, nullable |  | Date range configuration |
| `reportType` | enum: `HTML`, `PDF`, `JSON`, `CSV` |  | Report output type |
| `scheduled` | enum: `NO`, `DAILY`, `WEEKLY`, `MONTHLY` |  | Scheduling frequency |
| `lastGenerationTimestamp` | number, nullable |  | Timestamp of last generation |
| `nextGenerationTimestamp` | number, nullable |  | Timestamp of next scheduled generation |
| `enabled` | boolean |  | Whether this template is enabled |
| `notify` | boolean |  | Whether to send notifications |
| `sendByEmail` | boolean |  | Whether to send the report by email |
| `emailTargets` | array, nullable |  | List of email addresses to send the report to |
| `emailSubject` | string |  | Email subject |
| `emailBody` | string |  | Email body |
| `createdAt` | number |  | Creation timestamp of the report design template |
| `updatedAt` | number |  | Last update timestamp of the report design template |
| `idReportDesignTemplate` |  |  |  |
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
      "owner": "string",
      "name": "string",
      "idGroup": 0,
      "description": "string",
      "idReportDataSource": 0,
      "dateRange": [],
      "reportType": "HTML",
      "scheduled": "NO",
      "lastGenerationTimestamp": 0,
      "nextGenerationTimestamp": 0,
      "enabled": false,
      "notify": false,
      "sendByEmail": false,
      "emailTargets": [],
      "emailSubject": "string",
      "emailBody": "string",
      "createdAt": 0,
      "updatedAt": 0,
      "idReportDesignTemplate": null,
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

**Response 200**: List report design templates object

??? note "Response fields (30 fields)"

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
    | `data.[].idReportDesignTemplate` | integer |  | Id design template |
    | `data.[].idReportDesign` | integer |  | Id of the report design to which this template belongs |
    | `data.[].owner` | string |  | User id owner of this template |
    | `data.[].name` | string |  | Name of the template |
    | `data.[].idGroup` | integer, nullable |  | Group id |
    | `data.[].description` | string, nullable |  | Description |
    | `data.[].idReportDataSource` | integer, nullable |  | Id of the report data source |
    | `data.[].dateRange` | array, nullable |  | Date range configuration |
    | `data.[].reportType` | enum: `HTML`, `PDF`, `JSON`, `CSV` |  | Report output type |
    | `data.[].scheduled` | enum: `NO`, `DAILY`, `WEEKLY`, `MONTHLY` |  | Scheduling frequency |
    | `data.[].lastGenerationTimestamp` | number, nullable |  | Timestamp of last generation |
    | `data.[].nextGenerationTimestamp` | number, nullable |  | Timestamp of next scheduled generation |
    | `data.[].enabled` | boolean |  | Whether this template is enabled |
    | `data.[].notify` | boolean |  | Whether to send notifications |
    | `data.[].sendByEmail` | boolean |  | Whether to send the report by email |
    | `data.[].emailTargets` | array, nullable |  | List of email addresses to send the report to |
    | `data.[].emailSubject` | string |  | Email subject |
    | `data.[].emailBody` | string |  | Email body |
    | `data.[].createdAt` | number |  | Creation timestamp of the report design template |
    | `data.[].updatedAt` | number |  | Last update timestamp of the report design template |


Error responses: `400`, `401`, `403`, `404`, `500`.

## ReportDesignPages

API Endpoints for report design pages

### <span class="api-method api-post">POST</span> `/report/design/{idReportDesign}/page` { #post-report-design-idreportdesign-page }

Creates a new report design page

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |

**Request body** (`application/json`): [`ReportDesignPage`](#model-reportdesignpage)

**Response 200**: Report design page object

Schema: [`ReportDesignPage`](#model-reportdesignpage)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/design/{idReportDesign}/page/{idReportDesignPage}` { #get-report-design-idreportdesign-page-idreportdesignpage }

Show report design page details

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignPage` | path | integer | yes | Report design page id |

**Response 200**: Report design page object

Schema: [`ReportDesignPage`](#model-reportdesignpage)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/report/design/{idReportDesign}/page/{idReportDesignPage}` { #put-report-design-idreportdesign-page-idreportdesignpage }

Updates a Report Design Page

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignPage` | path | integer | yes | Report design page id |

**Request body** (`application/json`): [`ReportDesignPage`](#model-reportdesignpage)

**Response 200**: Report design page object

Schema: [`ReportDesignPage`](#model-reportdesignpage)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/report/design/{idReportDesign}/page/{idReportDesignPage}` { #delete-report-design-idreportdesign-page-idreportdesignpage }

Deletes a report design page.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignPage` | path | integer | yes | Report design page id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/design/{idReportDesign}/page/list` { #get-report-design-idreportdesign-page-list }

List Report Design Pages

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Report Design Pages object

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
    | `data.[].idReportDesignPage` | integer |  | Id ReportDesignPage |
    | `data.[].idReportDesign` | integer, nullable |  | Id of the report design to which the page belongs |
    | `data.[].position` | integer |  | Position of the report design page |
    | `data.[].pagesDirection` | enum: `vertical`, `horizontal` |  | Direction of the pages in the report design page, either vertical or horizontal |
    | `data.[].createdAt` | number |  | Creation timestamp of the report design page |
    | `data.[].updatedAt` | number |  | Last update timestamp of the report design page |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/report/design/{idReportDesign}/page/list` { #post-report-design-idreportdesign-page-list }

List Report Design Pages

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDesignPage` | integer |  | Id ReportDesignPage |
| `idReportDesign` | integer, nullable |  | Id of the report design to which the page belongs |
| `position` | integer |  | Position of the report design page |
| `pagesDirection` | enum: `vertical`, `horizontal` |  | Direction of the pages in the report design page, either vertical or horizontal |
| `createdAt` | number |  | Creation timestamp of the report design page |
| `updatedAt` | number |  | Last update timestamp of the report design page |
| `idReportDesignPage` |  |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "position": 1,
      "pagesDirection": "vertical",
      "idReportDesignPage": null,
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

**Response 200**: List Report Design Pages object

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
    | `data.[].idReportDesignPage` | integer |  | Id ReportDesignPage |
    | `data.[].idReportDesign` | integer, nullable |  | Id of the report design to which the page belongs |
    | `data.[].position` | integer |  | Position of the report design page |
    | `data.[].pagesDirection` | enum: `vertical`, `horizontal` |  | Direction of the pages in the report design page, either vertical or horizontal |
    | `data.[].createdAt` | number |  | Creation timestamp of the report design page |
    | `data.[].updatedAt` | number |  | Last update timestamp of the report design page |


Error responses: `400`, `401`, `403`, `404`, `500`.

## ReportDesignPageWidgets

API Endpoints for report design page widgets

### <span class="api-method api-post">POST</span> `/report/design/{idReportDesign}/page/{idReportDesignPage}/widget` { #post-report-design-idreportdesign-page-idreportdesignpage-widget }

Creates a new report design page widget

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignPage` | path | integer | yes | Report design page id |

**Request body** (`application/json`): [`ReportDesignPageWidget`](#model-reportdesignpagewidget)

**Response 200**: Report design page object

Schema: [`ReportDesignPageWidget`](#model-reportdesignpagewidget)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/design/{idReportDesign}/page/{idReportDesignPage}/widget/{idReportDesignPageWidget}` { #get-report-design-idreportdesign-page-idreportdesignpage-widget-idreportdesignpagewidget }

Show report design page widget details

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignPage` | path | integer | yes | Report design page id |
| `idReportDesignPageWidget` | path | integer | yes | Report design page widget id |

**Response 200**: Report design page object

Schema: [`ReportDesignPageWidget`](#model-reportdesignpagewidget)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/report/design/{idReportDesign}/page/{idReportDesignPage}/widget/{idReportDesignPageWidget}` { #put-report-design-idreportdesign-page-idreportdesignpage-widget-idreportdesignpagewidget }

Updates a Report Design Page Widget

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignPage` | path | integer | yes | Report design page id |
| `idReportDesignPageWidget` | path | integer | yes | Report design page widget id |

**Request body** (`application/json`): [`ReportDesignPageWidget`](#model-reportdesignpagewidget)

**Response 200**: Report design page object

Schema: [`ReportDesignPageWidget`](#model-reportdesignpagewidget)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/report/design/{idReportDesign}/page/{idReportDesignPage}/widget/{idReportDesignPageWidget}` { #delete-report-design-idreportdesign-page-idreportdesignpage-widget-idreportdesignpagewidget }

Deletes a report design page widget.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignPage` | path | integer | yes | Report design page id |
| `idReportDesignPageWidget` | path | integer | yes | Report design page widget id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/design/{idReportDesign}/page/{idReportDesignPage}/widget/list` { #get-report-design-idreportdesign-page-idreportdesignpage-widget-list }

List Report Design Page Widgets

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignPage` | path | integer | yes | Report design page id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Report Design Page Widgets object

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
    | `data.[].idReportDesignPageWidget` | integer |  | Id ReportDesignPageWidget |
    | `data.[].idWidget` | integer |  | Id of the widget associated to the report design page widget |
    | `data.[].idReportDesignPage` | integer |  | Id of the report design page to which the widget belongs |
    | `data.[].position` |  |  | Position of the report design page widget |
    | `data.[].position.x` |  |  |  |
    | `data.[].position.y` |  |  |  |
    | `data.[].position.w` |  |  |  |
    | `data.[].position.h` |  |  |  |
    | `data.[].options` |  |  | Options of the report design page widget |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/report/design/{idReportDesign}/page/{idReportDesignPage}/widget/list` { #post-report-design-idreportdesign-page-idreportdesignpage-widget-list }

List Report Design Page Widgets

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDesign` | path | integer | yes | Report design id |
| `idReportDesignPage` | path | integer | yes | Report design page id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDesignPageWidget` | integer |  | Id ReportDesignPageWidget |
| `idWidget` | integer |  | Id of the widget associated to the report design page widget |
| `idReportDesignPage` | integer |  | Id of the report design page to which the widget belongs |
| `position` |  |  | Position of the report design page widget |
| `position.x` |  |  |  |
| `position.y` |  |  |  |
| `position.w` |  |  |  |
| `position.h` |  |  |  |
| `options` |  |  | Options of the report design page widget |
| `idReportDesignPageWidget` |  |  |  |
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
      "position": [
        "string"
      ],
      "options": [],
      "idReportDesignPageWidget": null,
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

**Response 200**: List Report Design Page Widgets object

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
    | `data.[].idReportDesignPageWidget` | integer |  | Id ReportDesignPageWidget |
    | `data.[].idWidget` | integer |  | Id of the widget associated to the report design page widget |
    | `data.[].idReportDesignPage` | integer |  | Id of the report design page to which the widget belongs |
    | `data.[].position` |  |  | Position of the report design page widget |
    | `data.[].position.x` |  |  |  |
    | `data.[].position.y` |  |  |  |
    | `data.[].position.w` |  |  |  |
    | `data.[].position.h` |  |  |  |
    | `data.[].options` |  |  | Options of the report design page widget |


Error responses: `400`, `401`, `403`, `404`, `500`.

## ReportDataSources

API Endpoints for report data sources

### <span class="api-method api-post">POST</span> `/report/dataSource` { #post-report-datasource }

Creates a new report data source

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDataSource` | integer |  | Id ReportDataSource |
| `name` | string |  | Name of the report data source |
| `idGroup` | integer, nullable |  | Id of the group to which the report data source belongs |
| `description` | string, nullable |  | Description of the report data source |
| `allGroup` | boolean |  | Indicates if the report data source applies to all groups |
| `groupsRecursion` | boolean |  | Indicates if the report data source applies recursively to groups |
| `wildcardAgents` | array, nullable |  | List of wildcard agents associated with the report data source |
| `wildcardGroups` | array, nullable |  | List of wildcard groups associated with the report data source |
| `createdAt` | number |  | Creation timestamp of the report data source |
| `updatedAt` | number |  | Last update timestamp of the report data source |
| `idGroup` | integer | yes |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idGroup": 0,
      "description": "string",
      "allGroup": false,
      "groupsRecursion": false,
      "wildcardAgents": [
        "string"
      ],
      "wildcardGroups": [
        "string"
      ],
      "createdAt": 0,
      "updatedAt": 0
    }
    ```

**Response 200**: Report data source object

Schema: [`ReportDataSource`](#model-reportdatasource)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/dataSource/{idReportDataSource}` { #get-report-datasource-idreportdatasource }

Show report data source

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |

**Response 200**: Report data source object

Schema: [`ReportDataSource`](#model-reportdatasource)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/report/dataSource/{idReportDataSource}` { #put-report-datasource-idreportdatasource }

Updates a report data source

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |

**Request body** (`application/json`): [`ReportDataSource`](#model-reportdatasource)

**Response 200**: Report data source object

Schema: [`ReportDataSource`](#model-reportdatasource)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/report/dataSource/{idReportDataSource}` { #delete-report-datasource-idreportdatasource }

Deletes a report data source.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/dataSource/list` { #get-report-datasource-list }

List Report data sources

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List ReportDataSource object

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
    | `data.[].idReportDataSource` | integer |  | Id ReportDataSource |
    | `data.[].name` | string |  | Name of the report data source |
    | `data.[].idGroup` | integer, nullable |  | Id of the group to which the report data source belongs |
    | `data.[].description` | string, nullable |  | Description of the report data source |
    | `data.[].allGroup` | boolean |  | Indicates if the report data source applies to all groups |
    | `data.[].groupsRecursion` | boolean |  | Indicates if the report data source applies recursively to groups |
    | `data.[].wildcardAgents` | array, nullable |  | List of wildcard agents associated with the report data source |
    | `data.[].wildcardGroups` | array, nullable |  | List of wildcard groups associated with the report data source |
    | `data.[].createdAt` | number |  | Creation timestamp of the report data source |
    | `data.[].updatedAt` | number |  | Last update timestamp of the report data source |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/report/dataSource/list` { #post-report-datasource-list }

List Report data sources

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
| `idReportDataSource` | integer |  | Id ReportDataSource |
| `name` | string |  | Name of the report data source |
| `idGroup` | integer, nullable |  | Id of the group to which the report data source belongs |
| `description` | string, nullable |  | Description of the report data source |
| `allGroup` | boolean |  | Indicates if the report data source applies to all groups |
| `groupsRecursion` | boolean |  | Indicates if the report data source applies recursively to groups |
| `wildcardAgents` | array, nullable |  | List of wildcard agents associated with the report data source |
| `wildcardGroups` | array, nullable |  | List of wildcard groups associated with the report data source |
| `createdAt` | number |  | Creation timestamp of the report data source |
| `updatedAt` | number |  | Last update timestamp of the report data source |
| `idReportDataSource` |  |  |  |
| `freeSearch` | string, nullable |  | Find word in name fields. |
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
      "description": "string",
      "allGroup": false,
      "groupsRecursion": false,
      "wildcardAgents": [
        "string"
      ],
      "wildcardGroups": [
        "string"
      ],
      "createdAt": 0,
      "updatedAt": 0,
      "idReportDataSource": null,
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

**Response 200**: List ReportDataSource object

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
    | `data.[].idReportDataSource` | integer |  | Id ReportDataSource |
    | `data.[].name` | string |  | Name of the report data source |
    | `data.[].idGroup` | integer, nullable |  | Id of the group to which the report data source belongs |
    | `data.[].description` | string, nullable |  | Description of the report data source |
    | `data.[].allGroup` | boolean |  | Indicates if the report data source applies to all groups |
    | `data.[].groupsRecursion` | boolean |  | Indicates if the report data source applies recursively to groups |
    | `data.[].wildcardAgents` | array, nullable |  | List of wildcard agents associated with the report data source |
    | `data.[].wildcardGroups` | array, nullable |  | List of wildcard groups associated with the report data source |
    | `data.[].createdAt` | number |  | Creation timestamp of the report data source |
    | `data.[].updatedAt` | number |  | Last update timestamp of the report data source |


Error responses: `400`, `401`, `403`, `404`, `500`.

## ReportDataSourceAgents

API Endpoints for report data source agents

### <span class="api-method api-post">POST</span> `/report/dataSource/{idReportDataSource}/agent` { #post-report-datasource-idreportdatasource-agent }

Creates a new report dataSource agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |

**Request body** (`application/json`): [`ReportDataSourceAgent`](#model-reportdatasourceagent)

**Response 200**: Report data source agent object

Schema: [`ReportDataSourceAgent`](#model-reportdatasourceagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/dataSource/{idReportDataSource}/agent/{idReportDataSourceAgent}` { #get-report-datasource-idreportdatasource-agent-idreportdatasourceagent }

Show report dataSource agent details

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |
| `idReportDataSourceAgent` | path | integer | yes | Report data source agent id |

**Response 200**: Report data source agent object

Schema: [`ReportDataSourceAgent`](#model-reportdatasourceagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/report/dataSource/{idReportDataSource}/agent/{idReportDataSourceAgent}` { #put-report-datasource-idreportdatasource-agent-idreportdatasourceagent }

Updates a report dataSource agent

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |
| `idReportDataSourceAgent` | path | integer | yes | Report data source agent id |

**Request body** (`application/json`): [`ReportDataSourceAgent`](#model-reportdatasourceagent)

**Response 200**: Report data source agent object

Schema: [`ReportDataSourceAgent`](#model-reportdatasourceagent)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/report/dataSource/{idReportDataSource}/agent/{idReportDataSourceAgent}` { #delete-report-datasource-idreportdatasource-agent-idreportdatasourceagent }

Deletes a report dataSource agent.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |
| `idReportDataSourceAgent` | path | integer | yes | Report data source agent id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/dataSource/{idReportDataSource}/agent/list` { #get-report-datasource-idreportdatasource-agent-list }

List report dataSource agents

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List report data source agents object

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
    | `data.[].idReportDataSourceAgent` | integer |  | Id ReportDataSourceAgent |
    | `data.[].idReportDataSource` | integer |  | Id of the report data source to which the agent belongs |
    | `data.[].idAgent` | integer |  | Id of the agent linked to the report data source |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/report/dataSource/{idReportDataSource}/agent/list` { #post-report-datasource-idreportdatasource-agent-list }

List report dataSource agents

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDataSourceAgent` | integer |  | Id ReportDataSourceAgent |
| `idReportDataSource` | integer |  | Id of the report data source to which the agent belongs |
| `idAgent` | integer |  | Id of the agent linked to the report data source |
| `idReportDataSourceAgent` |  |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": 0,
      "idReportDataSourceAgent": null,
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

**Response 200**: List report data source agents object

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
    | `data.[].idReportDataSourceAgent` | integer |  | Id ReportDataSourceAgent |
    | `data.[].idReportDataSource` | integer |  | Id of the report data source to which the agent belongs |
    | `data.[].idAgent` | integer |  | Id of the agent linked to the report data source |


Error responses: `400`, `401`, `403`, `404`, `500`.

## ReportDataSourceGroups

API Endpoints for report data source groups

### <span class="api-method api-post">POST</span> `/report/dataSource/{idReportDataSource}/group` { #post-report-datasource-idreportdatasource-group }

Creates a new report data source group

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |

**Request body** (`application/json`): [`ReportDataSourceGroup`](#model-reportdatasourcegroup)

**Response 200**: Report design dataSource group object

Schema: [`ReportDataSourceGroup`](#model-reportdatasourcegroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/dataSource/{idReportDataSource}/group/{idReportDataSourceGroup}` { #get-report-datasource-idreportdatasource-group-idreportdatasourcegroup }

Show report data source group details

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |
| `idReportDataSourceGroup` | path | integer | yes | Report design dataSource group id |

**Response 200**: Report design dataSource group object

Schema: [`ReportDataSourceGroup`](#model-reportdatasourcegroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/report/dataSource/{idReportDataSource}/group/{idReportDataSourceGroup}` { #put-report-datasource-idreportdatasource-group-idreportdatasourcegroup }

Updates a report data source group

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |
| `idReportDataSourceGroup` | path | integer | yes | Report design dataSource group id |

**Request body** (`application/json`): [`ReportDataSourceGroup`](#model-reportdatasourcegroup)

**Response 200**: Report design dataSource group object

Schema: [`ReportDataSourceGroup`](#model-reportdatasourcegroup)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/report/dataSource/{idReportDataSource}/group/{idReportDataSourceGroup}` { #delete-report-datasource-idreportdatasource-group-idreportdatasourcegroup }

Deletes a report data source group.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |
| `idReportDataSourceGroup` | path | integer | yes | Report design dataSource group id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/report/dataSource/{idReportDataSource}/group/list` { #get-report-datasource-idreportdatasource-group-list }

List report data source groups

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List report data source groups object

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
    | `data.[].idReportDataSourceGroup` | integer |  | Id ReportDataSourceGroup |
    | `data.[].idReportDataSource` | integer |  | Id of the report design dataSource to which the group belongs |
    | `data.[].idGroup` | integer |  | Id of the group linked to the report design dataSource |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/report/dataSource/{idReportDataSource}/group/list` { #post-report-datasource-idreportdatasource-group-list }

List report data source groups

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idReportDataSource` | path | integer | yes | Report data source id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDataSourceGroup` | integer |  | Id ReportDataSourceGroup |
| `idReportDataSource` | integer |  | Id of the report design dataSource to which the group belongs |
| `idGroup` | integer |  | Id of the group linked to the report design dataSource |
| `idReportDataSourceGroup` |  |  |  |
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroup": 0,
      "idReportDataSourceGroup": null,
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

**Response 200**: List report data source groups object

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
    | `data.[].idReportDataSourceGroup` | integer |  | Id ReportDataSourceGroup |
    | `data.[].idReportDataSource` | integer |  | Id of the report design dataSource to which the group belongs |
    | `data.[].idGroup` | integer |  | Id of the group linked to the report design dataSource |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: ReportDataSource { #model-reportdatasource }

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDataSource` | integer |  | Id ReportDataSource |
| `name` | string |  | Name of the report data source |
| `idGroup` | integer, nullable |  | Id of the group to which the report data source belongs |
| `description` | string, nullable |  | Description of the report data source |
| `allGroup` | boolean |  | Indicates if the report data source applies to all groups |
| `groupsRecursion` | boolean |  | Indicates if the report data source applies recursively to groups |
| `wildcardAgents` | array, nullable |  | List of wildcard agents associated with the report data source |
| `wildcardGroups` | array, nullable |  | List of wildcard groups associated with the report data source |
| `createdAt` | number |  | Creation timestamp of the report data source |
| `updatedAt` | number |  | Last update timestamp of the report data source |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idGroup": 0,
      "description": "string",
      "allGroup": false,
      "groupsRecursion": false,
      "wildcardAgents": [
        "string"
      ],
      "wildcardGroups": [
        "string"
      ],
      "createdAt": 0,
      "updatedAt": 0
    }
    ```

### Model: ReportDataSourceAgent { #model-reportdatasourceagent }

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDataSourceAgent` | integer |  | Id ReportDataSourceAgent |
| `idReportDataSource` | integer |  | Id of the report data source to which the agent belongs |
| `idAgent` | integer |  | Id of the agent linked to the report data source |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idAgent": 0
    }
    ```

### Model: ReportDataSourceGroup { #model-reportdatasourcegroup }

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDataSourceGroup` | integer |  | Id ReportDataSourceGroup |
| `idReportDataSource` | integer |  | Id of the report design dataSource to which the group belongs |
| `idGroup` | integer |  | Id of the group linked to the report design dataSource |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroup": 0
    }
    ```

### Model: ReportDesign { #model-reportdesign }

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDesign` | integer |  | Id ReportDesign |
| `name` | string |  | Name of the reportDesign |
| `idGroup` | integer, nullable |  | Id of the group to which the report design belongs |
| `description` | string, nullable |  | Description of the reportDesign |
| `pagesDefaultDirection` | enum: `vertical`, `horizontal` |  | Default direction of the pages in the report design, either vertical or horizontal |
| `isPdfCoverRender` | boolean, nullable |  | Indicates if the PDF cover is rendered in the report design |
| `isPdfIndexRender` | boolean, nullable |  | Indicates if the PDF index is rendered in the report design |
| `isPdfHeaderRender` | boolean, nullable |  | Indicates if the PDF header is rendered in the report design |
| `isPdfFooterRender` | boolean, nullable |  | Indicates if the PDF footer is rendered in the report design |
| `pdfHeader` | string, nullable |  | PDF header content of the report design |
| `pdfCover` | string, nullable |  | PDF cover content of the report design |
| `pdfFooter` | string, nullable |  | PDF footer content of the report design |
| `createdAt` | number |  | Creation timestamp of the report design |
| `updatedAt` | number |  | Last update timestamp of the report design |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "idGroup": 0,
      "description": "string",
      "pagesDefaultDirection": "vertical",
      "isPdfCoverRender": false,
      "isPdfIndexRender": false,
      "isPdfHeaderRender": false,
      "isPdfFooterRender": false,
      "pdfHeader": "string",
      "pdfCover": "string",
      "pdfFooter": "string",
      "createdAt": 0,
      "updatedAt": 0
    }
    ```

### Model: ReportDesignHistory { #model-reportdesignhistory }

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDesignHistory` | integer |  | Id ReportDesignHistory |
| `idReportDesign` | integer |  | Id of the report design this history entry belongs to |
| `idUser` | string |  | Id of the user who owns this history stack |
| `sequence` | integer |  | Position in the undo/redo stack (0-based) |
| `state` | array of object |  | Serialised builder state snapshot |
| `isCurrent` | boolean |  | Whether this entry is the current cursor position |
| `isSavedCheckpoint` | boolean |  | Whether this entry corresponds to the last explicit save |
| `createdAt` | number |  | Creation timestamp of the history entry |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "sequence": 0,
      "state": [
        {}
      ],
      "isCurrent": false,
      "isSavedCheckpoint": false
    }
    ```

### Model: ReportDesignPage { #model-reportdesignpage }

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDesignPage` | integer |  | Id ReportDesignPage |
| `idReportDesign` | integer, nullable |  | Id of the report design to which the page belongs |
| `position` | integer |  | Position of the report design page |
| `pagesDirection` | enum: `vertical`, `horizontal` |  | Direction of the pages in the report design page, either vertical or horizontal |
| `createdAt` | number |  | Creation timestamp of the report design page |
| `updatedAt` | number |  | Last update timestamp of the report design page |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "position": 1,
      "pagesDirection": "vertical"
    }
    ```

### Model: ReportDesignPageWidget { #model-reportdesignpagewidget }

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDesignPageWidget` | integer |  | Id ReportDesignPageWidget |
| `idWidget` | integer |  | Id of the widget associated to the report design page widget |
| `idReportDesignPage` | integer |  | Id of the report design page to which the widget belongs |
| `position` |  |  | Position of the report design page widget |
| `position.x` |  |  |  |
| `position.y` |  |  |  |
| `position.w` |  |  |  |
| `position.h` |  |  |  |
| `options` |  |  | Options of the report design page widget |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idWidget": 0,
      "position": [
        "string"
      ],
      "options": []
    }
    ```

### Model: ReportDesignReport { #model-reportdesignreport }

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDesignReport` | integer |  | Id Report |
| `idReportDesign` | integer |  | Id of the parent report design |
| `idReportDesignTemplate` | integer, nullable |  | Id of the report design template |
| `owner` | string, nullable |  | Owner of the report |
| `fileName` | string, nullable |  | Generated file name |
| `idGroup` | integer, nullable |  | Id of the group |
| `description` | string, nullable |  | Description of the report |
| `idReportDataSource` | integer, nullable |  | Id of the report data source |
| `dateRange` | array, nullable |  | Date range configuration |
| `reportType` | enum: `HTML`, `PDF`, `JSON`, `CSV` |  | Report output type |
| `notify` | boolean |  | Whether to notify on completion |
| `sendByEmail` | boolean |  | Whether to send the report by email |
| `emailTargets` | array, nullable |  | List of email targets |
| `emailSubject` | string |  | Email subject |
| `emailBody` | string |  | Email body |
| `status` | enum: `PENDING`, `COMPLETED`, `FAILED` |  | Generation status |
| `progress` | array, nullable |  | Progress data |
| `errorMessage` | string, nullable |  | Error message if generation failed |
| `queuedAt` | number |  | Queued timestamp |
| `createdAt` | number |  | Creation timestamp |
| `completedAt` | number, nullable |  | Completion timestamp |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idReportDesignTemplate": 0,
      "owner": "string",
      "fileName": "string",
      "idGroup": 0,
      "description": "string",
      "idReportDataSource": 0,
      "dateRange": [
        "string"
      ],
      "reportType": "HTML",
      "notify": false,
      "sendByEmail": false,
      "emailTargets": [
        "string"
      ],
      "emailSubject": "string",
      "emailBody": "string",
      "errorMessage": "string"
    }
    ```

### Model: ReportDesignTemplate { #model-reportdesigntemplate }

| Field | Type | Required | Description |
|---|---|---|---|
| `idReportDesignTemplate` | integer |  | Id design template |
| `idReportDesign` | integer |  | Id of the report design to which this template belongs |
| `owner` | string |  | User id owner of this template |
| `name` | string |  | Name of the template |
| `idGroup` | integer, nullable |  | Group id |
| `description` | string, nullable |  | Description |
| `idReportDataSource` | integer, nullable |  | Id of the report data source |
| `dateRange` | array, nullable |  | Date range configuration |
| `reportType` | enum: `HTML`, `PDF`, `JSON`, `CSV` |  | Report output type |
| `scheduled` | enum: `NO`, `DAILY`, `WEEKLY`, `MONTHLY` |  | Scheduling frequency |
| `lastGenerationTimestamp` | number, nullable |  | Timestamp of last generation |
| `nextGenerationTimestamp` | number, nullable |  | Timestamp of next scheduled generation |
| `enabled` | boolean |  | Whether this template is enabled |
| `notify` | boolean |  | Whether to send notifications |
| `sendByEmail` | boolean |  | Whether to send the report by email |
| `emailTargets` | array, nullable |  | List of email addresses to send the report to |
| `emailSubject` | string |  | Email subject |
| `emailBody` | string |  | Email body |
| `createdAt` | number |  | Creation timestamp of the report design template |
| `updatedAt` | number |  | Last update timestamp of the report design template |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "owner": "string",
      "name": "string",
      "idGroup": 0,
      "description": "string",
      "idReportDataSource": 0,
      "dateRange": [],
      "reportType": "HTML",
      "scheduled": "NO",
      "lastGenerationTimestamp": 0,
      "nextGenerationTimestamp": 0,
      "enabled": false,
      "notify": false,
      "sendByEmail": false,
      "emailTargets": [],
      "emailSubject": "string",
      "emailBody": "string",
      "createdAt": 0,
      "updatedAt": 0
    }
    ```
