# Collections

File collections and the agents they are assigned to.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-post">POST</span> | [`/collection/{idCollection}/apply`](#post-collection-idcollection-apply) | Generate or regenerate the collection ZIP and MD5 |
| <span class="api-method api-post">POST</span> | [`/collection`](#post-collection) | Create a collection and its directory |
| <span class="api-method api-get">GET</span> | [`/collection/{idCollection}`](#get-collection-idcollection) | Get local collection metadata |
| <span class="api-method api-put">PUT</span> | [`/collection/{idCollection}`](#put-collection-idcollection) | Partially update collection metadata |
| <span class="api-method api-delete">DELETE</span> | [`/collection/{idCollection}`](#delete-collection-idcollection) | Remove collection files and agent configuration references |
| <span class="api-method api-get">GET</span> | [`/collection/list`](#get-collection-list) | List local collections using query filters |
| <span class="api-method api-post">POST</span> | [`/collection/list`](#post-collection-list) | List local collections using advanced filters |
| <span class="api-method api-get">GET</span> | [`/collection/{idCollection}/file`](#get-collection-idcollection-file) | Read collection text file content for editing |
| <span class="api-method api-post">POST</span> | [`/collection/{idCollection}/file`](#post-collection-idcollection-file) | Create a text file or an empty file in a collection |
| <span class="api-method api-put">PUT</span> | [`/collection/{idCollection}/file`](#put-collection-idcollection-file) | Replace text content of an existing collection file |
| <span class="api-method api-delete">DELETE</span> | [`/collection/{idCollection}/file`](#delete-collection-idcollection-file) | Delete a collection file |
| <span class="api-method api-post">POST</span> | [`/collection/{idCollection}/folder`](#post-collection-idcollection-folder) | Create a collection folder |
| <span class="api-method api-delete">DELETE</span> | [`/collection/{idCollection}/folder`](#delete-collection-idcollection-folder) | Delete an empty collection folder |
| <span class="api-method api-get">GET</span> | [`/collection/{idCollection}/file/download`](#get-collection-idcollection-file-download) | Download collection file bytes |
| <span class="api-method api-get">GET</span> | [`/collection/{idCollection}/file/list`](#get-collection-idcollection-file-list) | Browse collection files and folders |
| <span class="api-method api-post">POST</span> | [`/collection/{idCollection}/file/list`](#post-collection-idcollection-file-list) | Browse collection content with JSON options |
| <span class="api-method api-post">POST</span> | [`/collection/{idCollection}/file/upload`](#post-collection-idcollection-file-upload) | Upload a file or extract a ZIP into a collection folder |
| <span class="api-method api-get">GET</span> | [`/collection/{idCollection}/agent/list`](#get-collection-idcollection-agent-list) | List agents assigned to a collection |
| <span class="api-method api-post">POST</span> | [`/collection/{idCollection}/agent/list`](#post-collection-idcollection-agent-list) | List assigned agents with JSON options |

## Collections

API Endpoints for synchronized file collections

### <span class="api-method api-post">POST</span> `/collection/{idCollection}/apply` { #post-collection-idcollection-apply }

Generate or regenerate the collection ZIP and MD5

Requires at least one file in the collection. An empty collection returns HTTP 400:
Collection has no files to apply. Queues package distribution on the management metaconsole.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |

**Request body** (`application/json`)


**Response 200**: Collection metadata

Schema: [`Collection`](#model-collection)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/collection` { #post-collection }

Create a collection and its directory

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idCollection` | integer |  |  |
| `name` | string |  |  |
| `shortName` | string |  | Immutable after creation. Empty or omitted generates fc_<timestamp>. |
| `idGroup` | integer |  |  |
| `description` | string, nullable |  |  |
| `status` | enum: `0`, `1` |  | Persisted status: 0 pending apply, 1 applied. Updating metadata sets 1 as in the console. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "shortName": "string",
      "idGroup": 0,
      "description": "string"
    }
    ```

**Response 200**: Collection metadata

Schema: [`Collection`](#model-collection)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/collection/{idCollection}` { #get-collection-idcollection }

Get local collection metadata

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |

**Response 200**: Collection metadata

Schema: [`Collection`](#model-collection)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/collection/{idCollection}` { #put-collection-idcollection }

Partially update collection metadata

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |

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

**Response 200**: Collection metadata

Schema: [`Collection`](#model-collection)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/collection/{idCollection}` { #delete-collection-idcollection }

Remove collection files and agent configuration references

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |

**Response 200**: Collection deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/collection/list` { #get-collection-list }

List local collections using query filters

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `freeSearch` | query | string |  |  |

**Response 200**: ACL-scoped collection list

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
    | `data.[].idCollection` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].shortName` | string |  | Immutable after creation. Empty or omitted generates fc_<timestamp>. |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].status` | enum: `0`, `1` |  | Persisted status: 0 pending apply, 1 applied. Updating metadata sets 1 as in the console. |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/collection/list` { #post-collection-list }

List local collections using advanced filters

Body filters override query filters. Both totals use the same group ACL scope.

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
| `idCollection` | integer |  |  |
| `name` | string |  |  |
| `shortName` | string |  |  |
| `idGroup` | integer |  |  |
| `description` | string, nullable |  |  |
| `status` | enum: `0`, `1` |  |  |
| `freeSearch` | string, nullable |  | Search name, shortName and description. |
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
| `multipleSearch.field` | enum: `idCollection`, `name`, `shortName`, `idGroup`, `description`, `status` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idCollection`, `name`, `shortName`, `idGroup`, `description`, `status` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idCollection"
      ],
      "fieldConditions": [
        {
          "field": "idCollection",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "idCollection": 0,
      "name": "string",
      "shortName": "string",
      "idGroup": 0,
      "description": "string",
      "status": 0,
      "freeSearch": "string",
      "multipleSearch": {
        "field": "idCollection",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idCollection",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: ACL-scoped collection list

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
    | `data.[].idCollection` | integer |  |  |
    | `data.[].name` | string |  |  |
    | `data.[].shortName` | string |  | Immutable after creation. Empty or omitted generates fc_<timestamp>. |
    | `data.[].idGroup` | integer |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].status` | enum: `0`, `1` |  | Persisted status: 0 pending apply, 1 applied. Updating metadata sets 1 as in the console. |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/collection/{idCollection}/file` { #get-collection-idcollection-file }

Read collection text file content for editing

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |
| `path` | query | string | yes | Path relative to this collection, never an absolute server path |

**Response 200**: Text file with content and line-ending compatibility

??? note "Response fields (10 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idCollection` | integer |  |  |
    | `path` | string |  | Relative to this collection |
    | `name` | string |  |  |
    | `type` | enum: `file`, `folder` |  |  |
    | `size` | integer |  |  |
    | `modifiedAt` | integer |  |  |
    | `permissions` | string |  |  |
    | `status` | enum: `0`, `1` |  |  |
    | `content` | string |  |  |
    | `compatibility` | enum: `unix`, `windows` |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/collection/{idCollection}/file` { #post-collection-idcollection-file }

Create a text file or an empty file in a collection

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `path` | string | yes |  |
| `content` | string |  |  |
| `permissions` | string |  |  |
| `overwrite` | boolean |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "path": "plugins/check.sh",
      "content": "string",
      "permissions": "0755",
      "overwrite": false
    }
    ```

**Response 200**: Collection file or folder metadata

Schema: [`CollectionFileEntry`](#model-collectionfileentry)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/collection/{idCollection}/file` { #put-collection-idcollection-file }

Replace text content of an existing collection file

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `path` | string | yes |  |
| `content` | string | yes |  |
| `permissions` | string |  |  |
| `compatibility` | enum: `unix`, `windows` |  | Omit to preserve submitted line endings |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "path": "string",
      "content": "string",
      "permissions": "string",
      "compatibility": "unix"
    }
    ```

**Response 200**: Collection file or folder metadata

Schema: [`CollectionFileEntry`](#model-collectionfileentry)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/collection/{idCollection}/file` { #delete-collection-idcollection-file }

Delete a collection file

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |
| `path` | query | string | yes | Path relative to this collection, never an absolute server path |

**Response 200**: Deleted entry metadata

Schema: [`CollectionDeletedEntry`](#model-collectiondeletedentry)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/collection/{idCollection}/folder` { #post-collection-idcollection-folder }

Create a collection folder

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `path` | string | yes |  |
| `recursive` | boolean |  |  |
| `permissions` | string |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "path": "plugins/linux",
      "recursive": false,
      "permissions": "string"
    }
    ```

**Response 200**: Collection file or folder metadata

Schema: [`CollectionFileEntry`](#model-collectionfileentry)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/collection/{idCollection}/folder` { #delete-collection-idcollection-folder }

Delete an empty collection folder

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |
| `path` | query | string | yes | Path relative to this collection, never an absolute server path |

**Response 200**: Deleted entry metadata

Schema: [`CollectionDeletedEntry`](#model-collectiondeletedentry)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/collection/{idCollection}/file/download` { #get-collection-idcollection-file-download }

Download collection file bytes

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |
| `path` | query | string | yes | Path relative to this collection, never an absolute server path |

**Response 200**: File download

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/collection/{idCollection}/file/list` { #get-collection-idcollection-file-list }

Browse collection files and folders

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |
| `folder` | query | string |  |  |
| `page` | query | integer |  |  |
| `sizePage` | query | integer |  |  |
| `sortField` | query | enum: `name`, `type`, `size`, `modifiedAt` |  |  |
| `sortDirection` | query | enum: `ASC`, `DESC` |  |  |
| `freeSearch` | query | string |  |  |

**Response 200**: Collection folder contents

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
    | `data.[].idCollection` | integer |  |  |
    | `data.[].path` | string |  | Relative to this collection |
    | `data.[].name` | string |  |  |
    | `data.[].type` | enum: `file`, `folder` |  |  |
    | `data.[].size` | integer |  |  |
    | `data.[].modifiedAt` | integer |  |  |
    | `data.[].permissions` | string |  |  |
    | `data.[].status` | enum: `0`, `1` |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/collection/{idCollection}/file/list` { #post-collection-idcollection-file-list }

Browse collection content with JSON options

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `folder` | string |  |  |
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `sortField` | enum: `name`, `type`, `size`, `modifiedAt` |  |  |
| `sortDirection` | enum: `ASC`, `DESC` |  |  |
| `freeSearch` | string |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "folder": "string",
      "page": 0,
      "sizePage": 50,
      "sortField": "name",
      "sortDirection": "ASC",
      "freeSearch": "string"
    }
    ```

**Response 200**: Collection folder contents

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
    | `data.[].idCollection` | integer |  |  |
    | `data.[].path` | string |  | Relative to this collection |
    | `data.[].name` | string |  |  |
    | `data.[].type` | enum: `file`, `folder` |  |  |
    | `data.[].size` | integer |  |  |
    | `data.[].modifiedAt` | integer |  |  |
    | `data.[].permissions` | string |  |  |
    | `data.[].status` | enum: `0`, `1` |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/collection/{idCollection}/file/upload` { #post-collection-idcollection-file-upload }

Upload a file or extract a ZIP into a collection folder

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |

**Request body** (`multipart/form-data`)

| Field | Type | Required | Description |
|---|---|---|---|
| `file` | string (binary) | yes |  |
| `folder` | string |  |  |
| `decompress` | boolean |  | Extract a ZIP instead of storing it. Uploaded and total extracted bytes obey collection_max_size. |
| `overwrite` | boolean |  |  |
| `permissions` | string |  |  |

**Response 200**: Uploaded file metadata or extracted entries

??? note "Response fields (21 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idCollection` | integer |  |  |
    | `path` | string |  | Relative to this collection |
    | `name` | string |  |  |
    | `type` | enum: `file`, `folder` |  |  |
    | `size` | integer |  |  |
    | `modifiedAt` | integer |  |  |
    | `permissions` | string |  |  |
    | `status` | enum: `0`, `1` |  |  |
    | `idCollection` | integer |  |  |
    | `folder` | string |  |  |
    | `decompress` | boolean |  |  |
    | `status` | enum: `0` |  |  |
    | `data` | array of object |  |  |
    | `data.[].idCollection` | integer |  |  |
    | `data.[].path` | string |  | Relative to this collection |
    | `data.[].name` | string |  |  |
    | `data.[].type` | enum: `file`, `folder` |  |  |
    | `data.[].size` | integer |  |  |
    | `data.[].modifiedAt` | integer |  |  |
    | `data.[].permissions` | string |  |  |
    | `data.[].status` | enum: `0`, `1` |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

## CollectionAgents

Agents assigned to a collection

### <span class="api-method api-get">GET</span> `/collection/{idCollection}/agent/list` { #get-collection-idcollection-agent-list }

List agents assigned to a collection

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |
| `serverId` | query | integer |  | Required on metaconsole, omitted on nodes |
| `page` | query | integer |  |  |
| `sizePage` | query | integer |  |  |
| `freeSearch` | query | string |  |  |
| `sortField` | query | enum: `name`, `alias`, `idAgent` |  |  |
| `sortDirection` | query | enum: `ASC`, `DESC` |  |  |

**Response 200**: Agents with an active collection directive

??? note "Response fields (63 fields)"

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


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

### <span class="api-method api-post">POST</span> `/collection/{idCollection}/agent/list` { #post-collection-idcollection-agent-list }

List assigned agents with JSON options

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idCollection` | path | integer | yes |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `page` | integer |  |  |
| `sizePage` | integer |  |  |
| `freeSearch` | string |  |  |
| `sortField` | enum: `name`, `alias`, `idAgent` |  |  |
| `sortDirection` | enum: `ASC`, `DESC` |  |  |
| `serverId` | integer |  | Required on a metaconsole; collection ID belongs to that node. Omit on nodes. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "page": 0,
      "sizePage": 50,
      "freeSearch": "string",
      "sortField": "name",
      "sortDirection": "ASC",
      "serverId": 0
    }
    ```

**Response 200**: Agents with an active collection directive

??? note "Response fields (63 fields)"

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


Error responses: `400`, `401`, `403`, `404`, `500`, `502`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: Collection { #model-collection }

??? note "Fields (6 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idCollection` | integer |  |  |
    | `name` | string |  |  |
    | `shortName` | string |  | Immutable after creation. Empty or omitted generates fc_<timestamp>. |
    | `idGroup` | integer |  |  |
    | `description` | string, nullable |  |  |
    | `status` | enum: `0`, `1` |  | Persisted status: 0 pending apply, 1 applied. Updating metadata sets 1 as in the console. |


### Model: CollectionDeletedEntry { #model-collectiondeletedentry }

??? note "Fields (9 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idCollection` | integer |  |  |
    | `path` | string |  | Relative to this collection |
    | `name` | string |  |  |
    | `type` | enum: `file`, `folder` |  |  |
    | `size` | integer |  |  |
    | `modifiedAt` | integer |  |  |
    | `permissions` | string |  |  |
    | `status` | enum: `0`, `1` |  |  |
    | `deleted` | boolean |  |  |


### Model: CollectionFileEntry { #model-collectionfileentry }

??? note "Fields (8 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idCollection` | integer |  |  |
    | `path` | string |  | Relative to this collection |
    | `name` | string |  |  |
    | `type` | enum: `file`, `folder` |  |  |
    | `size` | integer |  |  |
    | `modifiedAt` | integer |  |  |
    | `permissions` | string |  |  |
    | `status` | enum: `0`, `1` |  |  |
