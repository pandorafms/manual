# Users and access

Authentication and tokens, users, profiles, groups and tags, and the audit log.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

## Endpoints

| Method | Endpoint | Summary |
|---|---|---|
| <span class="api-method api-post">POST</span> | [`/token`](#post-token) | Creates a new tokens |
| <span class="api-method api-get">GET</span> | [`/token/{id}`](#get-token-id) | show tokens |
| <span class="api-method api-put">PUT</span> | [`/token/{id}`](#put-token-id) | Updates an token |
| <span class="api-method api-delete">DELETE</span> | [`/token/{id}`](#delete-token-id) | Deletes an token object. |
| <span class="api-method api-get">GET</span> | [`/token/list`](#get-token-list) | List tokens |
| <span class="api-method api-post">POST</span> | [`/token/list`](#post-token-list) | List tokens |
| <span class="api-method api-post">POST</span> | [`/auth/login`](#post-auth-login) | Validates credentials and opens a session |
| <span class="api-method api-post">POST</span> | [`/auth/login/mfa`](#post-auth-login-mfa) | Completes the login with the second factor |
| <span class="api-method api-post">POST</span> | [`/auth/logout`](#post-auth-logout) | Revokes the current session |
| <span class="api-method api-get">GET</span> | [`/ping`](#get-ping) | ping |
| <span class="api-method api-post">POST</span> | [`/auth/refresh`](#post-auth-refresh) | Rotates the session pair |
| <span class="api-method api-post">POST</span> | [`/user`](#post-user) | Creates a new users |
| <span class="api-method api-get">GET</span> | [`/user/{idUser}`](#get-user-iduser) | show users |
| <span class="api-method api-put">PUT</span> | [`/user/{idUser}`](#put-user-iduser) | Updates an user |
| <span class="api-method api-delete">DELETE</span> | [`/user/{idUser}`](#delete-user-iduser) | Deletes an user object. |
| <span class="api-method api-get">GET</span> | [`/user/{idUser}/login`](#get-user-iduser-login) | show user when login process |
| <span class="api-method api-get">GET</span> | [`/user/list`](#get-user-list) | List user |
| <span class="api-method api-post">POST</span> | [`/user/list`](#post-user-list) | List user |
| <span class="api-method api-post">POST</span> | [`/user/{idUser}/notify`](#post-user-iduser-notify) | Send an email to a system user |
| <span class="api-method api-post">POST</span> | [`/user/2fa/bulk/disable`](#post-user-2fa-bulk-disable) | Disable the two-factor authentication of several users |
| <span class="api-method api-post">POST</span> | [`/user/2fa/disable/all`](#post-user-2fa-disable-all) | Disable the two-factor authentication of all users |
| <span class="api-method api-post">POST</span> | [`/user/{idUser}/2fa/disable`](#post-user-iduser-2fa-disable) | Disable the two-factor authentication of a user |
| <span class="api-method api-get">GET</span> | [`/user/{idUser}/2fa`](#get-user-iduser-2fa) | Show whether a user has two-factor authentication enabled |
| <span class="api-method api-post">POST</span> | [`/user/{idUser}/2fa/reset`](#post-user-iduser-2fa-reset) | Create or rotate the two-factor authentication secret of a user |
| <span class="api-method api-post">POST</span> | [`/user/{idUser}/profile/{idProfile}`](#post-user-iduser-profile-idprofile) | Create user profile |
| <span class="api-method api-get">GET</span> | [`/user/{idUser}/profiles/{idUserProfile}`](#get-user-iduser-profiles-iduserprofile) | show data field user profile |
| <span class="api-method api-delete">DELETE</span> | [`/user/{idUser}/profiles/{idUserProfile}`](#delete-user-iduser-profiles-iduserprofile) | Deletes user profile. |
| <span class="api-method api-get">GET</span> | [`/user/{idUser}/profiles`](#get-user-iduser-profiles) | List user profiles |
| <span class="api-method api-post">POST</span> | [`/user/{idUser}/profiles`](#post-user-iduser-profiles) | List user profiles |
| <span class="api-method api-post">POST</span> | [`/profile`](#post-profile) | Creates a new profiles |
| <span class="api-method api-get">GET</span> | [`/profile/{idProfile}`](#get-profile-idprofile) | Show profile |
| <span class="api-method api-put">PUT</span> | [`/profile/{idProfile}`](#put-profile-idprofile) | Updates an profile |
| <span class="api-method api-delete">DELETE</span> | [`/profile/{idProfile}`](#delete-profile-idprofile) | Deletes an profile object. |
| <span class="api-method api-get">GET</span> | [`/profile/list`](#get-profile-list) | List profiles |
| <span class="api-method api-post">POST</span> | [`/profile/list`](#post-profile-list) | List profiles |
| <span class="api-method api-post">POST</span> | [`/group`](#post-group) | Creates a new groups |
| <span class="api-method api-get">GET</span> | [`/group/{idGroup}`](#get-group-idgroup) | Show group |
| <span class="api-method api-put">PUT</span> | [`/group/{idGroup}`](#put-group-idgroup) | Updates an group |
| <span class="api-method api-delete">DELETE</span> | [`/group/{idGroup}`](#delete-group-idgroup) | Deletes an group object. |
| <span class="api-method api-get">GET</span> | [`/group/list`](#get-group-list) | List groups |
| <span class="api-method api-post">POST</span> | [`/group/list`](#post-group-list) | List groups |
| <span class="api-method api-post">POST</span> | [`/tag`](#post-tag) | Creates a new tags |
| <span class="api-method api-get">GET</span> | [`/tag/{idTag}`](#get-tag-idtag) | Show tag |
| <span class="api-method api-put">PUT</span> | [`/tag/{idTag}`](#put-tag-idtag) | Updates an tag |
| <span class="api-method api-delete">DELETE</span> | [`/tag/{idTag}`](#delete-tag-idtag) | Deletes an tag object. |
| <span class="api-method api-get">GET</span> | [`/tag/list`](#get-tag-list) | List tags |
| <span class="api-method api-post">POST</span> | [`/tag/list`](#post-tag-list) | List tags |
| <span class="api-method api-get">GET</span> | [`/audit/log/{idSession}`](#get-audit-log-idsession) | Get one audit log entry and its extended data |
| <span class="api-method api-get">GET</span> | [`/audit/log/list`](#get-audit-log-list) | List audit log entries with query filters |
| <span class="api-method api-post">POST</span> | [`/audit/log/list`](#post-audit-log-list) | List audit log entries with body filters |

## Authentication

API Endpoints of authentication

### <span class="api-method api-post">POST</span> `/token` { #post-token }

Creates a new tokens

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idToken` | integer |  | Id Token |
| `label` | string |  | label of the token |
| `uuid` | string, nullable |  | uuid of the token |
| `idUser` | string, nullable |  | Owner user id. Optional for user authentication; required when credentials have no associated user. |
| `validity` | string, nullable |  | Date until which tocken is valid, if it is void it will never expire |
| `lastUsage` | string, nullable |  | last_usage of the token |
| `isPandoraAi` | boolean |  | Whether this is a Pandora AI token. AI tokens are created and managed by the console. |
| `tokenType` | enum: `access`, `refresh`, `mfa` |  | Credential type. Only access tokens work on the general API. |
| `sessionId` | string, nullable |  | Groups the access and refresh rows of the same session. |
| `isMobile` | boolean, nullable |  | Mobile session (filterable; the list excludes them by default). |
| `deviceInfo` | object, nullable |  | Client metadata: device id, platform, app version, ip, locale, timezone, screen. |
| `sessionExpiresAt` | string, nullable |  | Absolute session limit (login + 7 days). |
| `isPandoraAi` | enum: `False` |  | Only false is accepted when creating a token through the API. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "label": "string",
      "idUser": "string",
      "validity": "2023-02-21 08:34:16",
      "isPandoraAi": false,
      "tokenType": "access",
      "sessionId": "string",
      "isMobile": false,
      "deviceInfo": {},
      "sessionExpiresAt": "string"
    }
    ```

**Response 200**: Incidence type object

Schema: [`Token`](#model-token)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/token/{id}` { #get-token-id }

show tokens

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | Token id |

**Response 200**: Incidence type object

Schema: [`Token`](#model-token)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/token/{id}` { #put-token-id }

Updates an token

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | Token id |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idToken` | integer |  | Id Token |
| `label` | string |  | label of the token |
| `uuid` | string, nullable |  | uuid of the token |
| `idUser` | string, nullable |  | Owner user id. Optional for user authentication; required when credentials have no associated user. |
| `validity` | string, nullable |  | Date until which tocken is valid, if it is void it will never expire |
| `lastUsage` | string, nullable |  | last_usage of the token |
| `isPandoraAi` | boolean |  | Whether this is a Pandora AI token. AI tokens are created and managed by the console. |
| `tokenType` | enum: `access`, `refresh`, `mfa` |  | Credential type. Only access tokens work on the general API. |
| `sessionId` | string, nullable |  | Groups the access and refresh rows of the same session. |
| `isMobile` | boolean, nullable |  | Mobile session (filterable; the list excludes them by default). |
| `deviceInfo` | object, nullable |  | Client metadata: device id, platform, app version, ip, locale, timezone, screen. |
| `sessionExpiresAt` | string, nullable |  | Absolute session limit (login + 7 days). |
| `isPandoraAi` | boolean |  | Console-managed flag. This field is rejected in update requests. |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "label": "string",
      "idUser": "string",
      "validity": "2023-02-21 08:34:16",
      "isPandoraAi": true,
      "tokenType": "access",
      "sessionId": "string",
      "isMobile": false,
      "deviceInfo": {},
      "sessionExpiresAt": "string"
    }
    ```

**Response 200**: Incidence type object

Schema: [`Token`](#model-token)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/token/{id}` { #delete-token-id }

Deletes an token object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `id` | path | integer | yes | Token id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/token/list` { #get-token-list }

List tokens

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Incidence object

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
    | `data.[].idToken` | integer |  | Id Token |
    | `data.[].label` | string |  | label of the token |
    | `data.[].uuid` | string, nullable |  | uuid of the token |
    | `data.[].idUser` | string, nullable |  | Owner user id. Optional for user authentication; required when credentials have no associated user. |
    | `data.[].validity` | string, nullable |  | Date until which tocken is valid, if it is void it will never expire |
    | `data.[].lastUsage` | string, nullable |  | last_usage of the token |
    | `data.[].isPandoraAi` | boolean |  | Whether this is a Pandora AI token. AI tokens are created and managed by the console. |
    | `data.[].tokenType` | enum: `access`, `refresh`, `mfa` |  | Credential type. Only access tokens work on the general API. |
    | `data.[].sessionId` | string, nullable |  | Groups the access and refresh rows of the same session. |
    | `data.[].isMobile` | boolean, nullable |  | Mobile session (filterable; the list excludes them by default). |
    | `data.[].deviceInfo` | object, nullable |  | Client metadata: device id, platform, app version, ip, locale, timezone, screen. |
    | `data.[].sessionExpiresAt` | string, nullable |  | Absolute session limit (login + 7 days). |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/token/list` { #post-token-list }

List tokens

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
| `idToken` | integer |  | Id Token |
| `label` | string |  | label of the token |
| `uuid` | string, nullable |  | uuid of the token |
| `idUser` | string, nullable |  | Owner user id. Optional for user authentication; required when credentials have no associated user. |
| `validity` | string, nullable |  | Date until which tocken is valid, if it is void it will never expire |
| `lastUsage` | string, nullable |  | last_usage of the token |
| `isPandoraAi` | boolean |  | Whether this is a Pandora AI token. AI tokens are created and managed by the console. |
| `tokenType` | enum: `access`, `refresh`, `mfa` |  | Credential type. Only access tokens work on the general API. |
| `sessionId` | string, nullable |  | Groups the access and refresh rows of the same session. |
| `isMobile` | boolean, nullable |  | Mobile session (filterable; the list excludes them by default). |
| `deviceInfo` | object, nullable |  | Client metadata: device id, platform, app version, ip, locale, timezone, screen. |
| `sessionExpiresAt` | string, nullable |  | Absolute session limit (login + 7 days). |
| `idToken` |  |  |  |
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
| `multipleSearch.field` | enum: `idToken`, `label`, `idUser`, `validity`, `lastUsage`, `isPandoraAi`, `tokenType`, `sessionId`, `isMobile`, `sessionExpiresAt` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idToken`, `label`, `idUser`, `validity`, `lastUsage`, `isPandoraAi`, `tokenType`, `sessionId`, `isMobile`, `sessionExpiresAt` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "label": "string",
      "idUser": "string",
      "validity": "2023-02-21 08:34:16",
      "isPandoraAi": true,
      "tokenType": "access",
      "sessionId": "string",
      "isMobile": false,
      "deviceInfo": {},
      "sessionExpiresAt": "string",
      "idToken": null,
      "freeSearch": "string",
      "requestedFields": [
        "idToken"
      ],
      "fieldConditions": [
        {
          "field": "idToken",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idToken",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idToken",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List Incidence object

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
    | `data.[].idToken` | integer |  | Id Token |
    | `data.[].label` | string |  | label of the token |
    | `data.[].uuid` | string, nullable |  | uuid of the token |
    | `data.[].idUser` | string, nullable |  | Owner user id. Optional for user authentication; required when credentials have no associated user. |
    | `data.[].validity` | string, nullable |  | Date until which tocken is valid, if it is void it will never expire |
    | `data.[].lastUsage` | string, nullable |  | last_usage of the token |
    | `data.[].isPandoraAi` | boolean |  | Whether this is a Pandora AI token. AI tokens are created and managed by the console. |
    | `data.[].tokenType` | enum: `access`, `refresh`, `mfa` |  | Credential type. Only access tokens work on the general API. |
    | `data.[].sessionId` | string, nullable |  | Groups the access and refresh rows of the same session. |
    | `data.[].isMobile` | boolean, nullable |  | Mobile session (filterable; the list excludes them by default). |
    | `data.[].deviceInfo` | object, nullable |  | Client metadata: device id, platform, app version, ip, locale, timezone, screen. |
    | `data.[].sessionExpiresAt` | string, nullable |  | Absolute session limit (login + 7 days). |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/auth/login` { #post-auth-login }

Validates credentials and opens a session

Public endpoint (ACL still applies). Returns an access token and sets the refresh token in an HttpOnly cookie. If the account has two-factor authentication, returns status=mfa_required and a short-lived mfa_token instead of tokens.

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `id_user` | string | yes |  |
| `password` | string (password) | yes |  |
| `isMobile` | boolean |  |  |
| `deviceInfo` | object, nullable |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "id_user": "admin",
      "password": "string",
      "isMobile": false,
      "deviceInfo": {}
    }
    ```

**Response 200**: Session created or second factor required

??? note "Response fields (5 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `status` | string |  |  |
    | `access_token` | string |  |  |
    | `access_expires_in` | integer |  |  |
    | `session_expires_at` | string |  |  |
    | `id_user` | string |  |  |


Error responses: `401`, `403`, `429`.

### <span class="api-method api-post">POST</span> `/auth/login/mfa` { #post-auth-login-mfa }

Completes the login with the second factor

Public endpoint. Exchanges the mfa_token from /auth/login plus the 6-digit code for the session pair. Five wrong codes invalidate the mfa_token.

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `mfa_token` | string | yes |  |
| `code` | string | yes |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "mfa_token": "string",
      "code": "123456"
    }
    ```

**Response 200**: Session created

??? note "Response fields (5 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `status` | string |  |  |
    | `access_token` | string |  |  |
    | `access_expires_in` | integer |  |  |
    | `session_expires_at` | string |  |  |
    | `id_user` | string |  |  |


Error responses: `401`, `403`, `429`.

### <span class="api-method api-post">POST</span> `/auth/logout` { #post-auth-logout }

Revokes the current session

Deletes the access and refresh tokens of the session and clears the refresh cookie. Accepts the refresh cookie, so it also works when the access token has expired. Other sessions of the user stay open.

**Response 200**: Session revoked

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `status` | string |  |  |


Error responses: `401`.

### <span class="api-method api-get">GET</span> `/ping` { #get-ping }

ping

**Response 200**: API availability, authentication and version information

??? note "Response fields (6 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `valid` | boolean | yes | Whether the supplied authentication token is valid |
    | `version` | string | yes | Pandora FMS version |
    | `build` | string | yes | Pandora FMS build identifier |
    | `lts_name` | string | yes | Long-term support release name; empty when not applicable |
    | `current_package` | string | yes | Currently installed package number |
    | `MR` | string | yes | Installed minor release identifier |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/auth/refresh` { #post-auth-refresh }

Rotates the session pair

Public endpoint authenticated with the HttpOnly refresh cookie. Invalidates the previous access and refresh tokens and sets a new cookie. The session window slides on every refresh and ends after REFRESH_TTL without activity.

**Response 200**: New session pair

??? note "Response fields (5 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `status` | string |  |  |
    | `access_token` | string |  |  |
    | `access_expires_in` | integer |  |  |
    | `session_expires_at` | string |  |  |
    | `id_user` | string |  |  |


Error responses: `401`, `403`.

## Users

API Endpoints of users

### <span class="api-method api-post">POST</span> `/user` { #post-user }

Creates a new users

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `idUser` | string |  | Id user |
| `fullName` | string, nullable |  | Full name |
| `firstName` | string, nullable |  | First name |
| `lastName` | string, nullable |  | Last name |
| `middleName` | string, nullable |  | Middle name |
| `password` | string, nullable |  |  |
| `passwordValidate` | string, nullable |  |  |
| `oldPassword` | string, nullable |  | Only administrator users will not have to confirm the old password |
| `comments` | string, nullable |  | Comments for user |
| `lastConnect` | integer, nullable |  | User last connect utimestamp |
| `registered` | integer, nullable |  | User registration Unix timestamp |
| `email` | string, nullable |  | User email address |
| `phone` | string, nullable |  | User phone number |
| `isAdmin` | boolean |  | User is administrator |
| `language` | enum: `catalonian`, `english`, `spanish`, `french`, `japanese`, `russian`, `chinese` |  | User section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
| `timezone` | string, nullable |  | User timezone, https://www.php.net/manual/en/datetimezone.listidentifiers.php |
| `blockSize` | integer, nullable |  | User default block pagination size |
| `idSkin` | integer, nullable |  | User id skin |
| `disabled` | boolean |  | Disabling this user |
| `shortcut` | integer, nullable |  | User shortcut |
| `shortcutData` | string, nullable |  | User shorcut data |
| `section` | enum: `default`, `visual_console`, `event_list`, `group_view`, `group_view`, `tactical_view`, `alert_detail`, `external_link`, `other`, `dashboard` |  | User section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
| `dataSection` | string, nullable |  | User section data |
| `metaconsoleSection` | enum: `default`, `visual_console`, `event_list`, `group_view`, `group_view`, `tactical_view`, `alert_detail`, `external_link`, `other`, `dashboard` |  | User Metaconsole section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
| `metaconsoleDataSection` | string, nullable |  | User metaconsole section data |
| `forceChangePass` | boolean |  | Force the user to change the password on next login |
| `lastPassChange` | string, nullable |  | Date of last password change |
| `lastFailedLogin` | string, nullable |  | Date of last login failure |
| `failedAttempt` | integer |  | Number of failed login attempts by a user |
| `loginBlocked` | boolean |  | Blocked user |
| `metaconsoleAccess` | string, nullable |  | User metaconsole access |
| `notLogin` | boolean |  | The user with no access authorization can only access the API. |
| `localUser` | boolean |  | The user with local authentication enabled will always use local authentication. |
| `metaconsoleAgentsManager` | integer, nullable |  | Agents manager |
| `metaconsoleAccessNode` | integer, nullable |  | Access node |
| `strictAcl` | boolean |  | User with ACL strict |
| `idFilter` | integer, nullable |  | Assign a specific filter for user |
| `sessionTime` | integer, nullable |  | This is defined in minutes. If you want a permanent session, introduce -1 in this field. |
| `defaultEventFilter` | integer, nullable |  | Assign a specific filter in events for user |
| `metaconsoleDefaultEventFilter` | integer, nullable |  | Assign a specific filter in events for user metaconsole |
| `showTipsStartup` | boolean |  | User show tips startup |
| `autorefreshWhiteList` | string |  | User pages autorefresh |
| `timeAutorefresh` | integer |  | Interval of autorefresh of the elements, by default they are 30 seconds, needing to enable the autorefresh first |
| `defaultCustomView` | integer, nullable |  | default custom view for user |
| `ehorusUserLevelUser` | string |  | user access ehorus whit user name |
| `ehorusUserLevelPass` | string |  | user access ehorus whit user token |
| `ehorusUserLevelEnabled` | boolean |  | User access ehorus level |
| `itsmUserLevelUser` | string |  | user access ITSM whit user name |
| `itsmUserLevelPass` | string |  | user access ITSM whit user token |
| `apiToken` | string |  | Api key |
| `allowedIpActive` | boolean |  | User allowed ip active |
| `allowedIpList` | string, nullable |  | User allowed Ip List |
| `sessionMaxTimeExpire` | integer, nullable |  | user expire session time |
| `authTokenSecret` | string |  | Auth token |
| `twoFactorEnabled` | boolean |  | Whether the user has a TOTP secret in this console |
| `permanentlyBlockedAttempts` | integer |  | Number of bloked login attempts by a user |
| `permanentlyBlocked` | boolean |  | Blocked user permanently |
| `fullName` | string | yes |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idUser": "string",
      "fullName": "string",
      "firstName": "string",
      "lastName": "string",
      "middleName": "string",
      "password": "password",
      "passwordValidate": "password",
      "oldPassword": "oldPassword",
      "comments": "The user is allergic",
      "email": "nobody@samplecompany.com",
      "phone": "555-555-555",
      "isAdmin": "false",
      "language": "catalonian",
      "timezone": "string",
      "blockSize": "20",
      "idSkin": 0,
      "disabled": false,
      "shortcut": 0,
      "shortcutData": "string",
      "section": "default",
      "dataSection": "string",
      "metaconsoleSection": "default",
      "metaconsoleDataSection": "string",
      "forceChangePass": false,
      "metaconsoleAccess": "string",
      "notLogin": false,
      "localUser": false,
      "metaconsoleAgentsManager": 0,
      "metaconsoleAccessNode": 0,
      "strictAcl": false,
      "idFilter": 0,
      "sessionTime": 0,
      "defaultEventFilter": 0,
      "metaconsoleDefaultEventFilter": 0,
      "showTipsStartup": true,
      "autorefreshWhiteList": "string",
      "timeAutorefresh": 0,
      "defaultCustomView": 0,
      "ehorusUserLevelUser": "string",
      "ehorusUserLevelPass": "string",
      "ehorusUserLevelEnabled": false,
      "itsmUserLevelUser": "string",
      "itsmUserLevelPass": "string",
      "allowedIpActive": false,
      "allowedIpList": "string",
      "sessionMaxTimeExpire": 0,
      "permanentlyBlocked": false
    }
    ```

**Response 200**: User object

Schema: [`User`](#model-user)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/user/{idUser}` { #get-user-iduser }

show users

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes | User id |

**Response 200**: User object

Schema: [`User`](#model-user)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/user/{idUser}` { #put-user-iduser }

Updates an user

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes | User id |

**Request body** (`application/json`): [`User`](#model-user)

**Response 200**: User object

Schema: [`User`](#model-user)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/user/{idUser}` { #delete-user-iduser }

Deletes an user object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes | User id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/user/{idUser}/login` { #get-user-iduser-login }

show user when login process

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes | User id |
| `password` | query | string | yes | User password |

**Response 200**: User object

Schema: [`User`](#model-user)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/user/list` { #get-user-list }

List user

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Incidence object

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
    | `data.[].idUser` | string |  | Id user |
    | `data.[].fullName` | string, nullable |  | Full name |
    | `data.[].firstName` | string, nullable |  | First name |
    | `data.[].lastName` | string, nullable |  | Last name |
    | `data.[].middleName` | string, nullable |  | Middle name |
    | `data.[].password` | string, nullable |  |  |
    | `data.[].passwordValidate` | string, nullable |  |  |
    | `data.[].oldPassword` | string, nullable |  | Only administrator users will not have to confirm the old password |
    | `data.[].comments` | string, nullable |  | Comments for user |
    | `data.[].lastConnect` | integer, nullable |  | User last connect utimestamp |
    | `data.[].registered` | integer, nullable |  | User registration Unix timestamp |
    | `data.[].email` | string, nullable |  | User email address |
    | `data.[].phone` | string, nullable |  | User phone number |
    | `data.[].isAdmin` | boolean |  | User is administrator |
    | `data.[].language` | enum: `catalonian`, `english`, `spanish`, `french`, `japanese`, `russian`, `chinese` |  | User section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
    | `data.[].timezone` | string, nullable |  | User timezone, https://www.php.net/manual/en/datetimezone.listidentifiers.php |
    | `data.[].blockSize` | integer, nullable |  | User default block pagination size |
    | `data.[].idSkin` | integer, nullable |  | User id skin |
    | `data.[].disabled` | boolean |  | Disabling this user |
    | `data.[].shortcut` | integer, nullable |  | User shortcut |
    | `data.[].shortcutData` | string, nullable |  | User shorcut data |
    | `data.[].section` | enum: `default`, `visual_console`, `event_list`, `group_view`, `group_view`, `tactical_view`, `alert_detail`, `external_link`, `other`, `dashboard` |  | User section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
    | `data.[].dataSection` | string, nullable |  | User section data |
    | `data.[].metaconsoleSection` | enum: `default`, `visual_console`, `event_list`, `group_view`, `group_view`, `tactical_view`, `alert_detail`, `external_link`, `other`, `dashboard` |  | User Metaconsole section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
    | `data.[].metaconsoleDataSection` | string, nullable |  | User metaconsole section data |
    | `data.[].forceChangePass` | boolean |  | Force the user to change the password on next login |
    | `data.[].lastPassChange` | string, nullable |  | Date of last password change |
    | `data.[].lastFailedLogin` | string, nullable |  | Date of last login failure |
    | `data.[].failedAttempt` | integer |  | Number of failed login attempts by a user |
    | `data.[].loginBlocked` | boolean |  | Blocked user |
    | `data.[].metaconsoleAccess` | string, nullable |  | User metaconsole access |
    | `data.[].notLogin` | boolean |  | The user with no access authorization can only access the API. |
    | `data.[].localUser` | boolean |  | The user with local authentication enabled will always use local authentication. |
    | `data.[].metaconsoleAgentsManager` | integer, nullable |  | Agents manager |
    | `data.[].metaconsoleAccessNode` | integer, nullable |  | Access node |
    | `data.[].strictAcl` | boolean |  | User with ACL strict |
    | `data.[].idFilter` | integer, nullable |  | Assign a specific filter for user |
    | `data.[].sessionTime` | integer, nullable |  | This is defined in minutes. If you want a permanent session, introduce -1 in this field. |
    | `data.[].defaultEventFilter` | integer, nullable |  | Assign a specific filter in events for user |
    | `data.[].metaconsoleDefaultEventFilter` | integer, nullable |  | Assign a specific filter in events for user metaconsole |
    | `data.[].showTipsStartup` | boolean |  | User show tips startup |
    | `data.[].autorefreshWhiteList` | string |  | User pages autorefresh |
    | `data.[].timeAutorefresh` | integer |  | Interval of autorefresh of the elements, by default they are 30 seconds, needing to enable the autorefresh first |
    | `data.[].defaultCustomView` | integer, nullable |  | default custom view for user |
    | `data.[].ehorusUserLevelUser` | string |  | user access ehorus whit user name |
    | `data.[].ehorusUserLevelPass` | string |  | user access ehorus whit user token |
    | `data.[].ehorusUserLevelEnabled` | boolean |  | User access ehorus level |
    | `data.[].itsmUserLevelUser` | string |  | user access ITSM whit user name |
    | `data.[].itsmUserLevelPass` | string |  | user access ITSM whit user token |
    | `data.[].apiToken` | string |  | Api key |
    | `data.[].allowedIpActive` | boolean |  | User allowed ip active |
    | `data.[].allowedIpList` | string, nullable |  | User allowed Ip List |
    | `data.[].sessionMaxTimeExpire` | integer, nullable |  | user expire session time |
    | `data.[].authTokenSecret` | string |  | Auth token |
    | `data.[].twoFactorEnabled` | boolean |  | Whether the user has a TOTP secret in this console |
    | `data.[].permanentlyBlockedAttempts` | integer |  | Number of bloked login attempts by a user |
    | `data.[].permanentlyBlocked` | boolean |  | Blocked user permanently |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/user/list` { #post-user-list }

List user

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
| `idUser` | string |  | Id user |
| `fullName` | string, nullable |  | Full name |
| `firstName` | string, nullable |  | First name |
| `lastName` | string, nullable |  | Last name |
| `middleName` | string, nullable |  | Middle name |
| `password` | string, nullable |  |  |
| `passwordValidate` | string, nullable |  |  |
| `oldPassword` | string, nullable |  | Only administrator users will not have to confirm the old password |
| `comments` | string, nullable |  | Comments for user |
| `lastConnect` | integer, nullable |  | User last connect utimestamp |
| `registered` | integer, nullable |  | User registration Unix timestamp |
| `email` | string, nullable |  | User email address |
| `phone` | string, nullable |  | User phone number |
| `isAdmin` | boolean |  | User is administrator |
| `language` | enum: `catalonian`, `english`, `spanish`, `french`, `japanese`, `russian`, `chinese` |  | User section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
| `timezone` | string, nullable |  | User timezone, https://www.php.net/manual/en/datetimezone.listidentifiers.php |
| `blockSize` | integer, nullable |  | User default block pagination size |
| `idSkin` | integer, nullable |  | User id skin |
| `disabled` | boolean |  | Disabling this user |
| `shortcut` | integer, nullable |  | User shortcut |
| `shortcutData` | string, nullable |  | User shorcut data |
| `section` | enum: `default`, `visual_console`, `event_list`, `group_view`, `group_view`, `tactical_view`, `alert_detail`, `external_link`, `other`, `dashboard` |  | User section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
| `dataSection` | string, nullable |  | User section data |
| `metaconsoleSection` | enum: `default`, `visual_console`, `event_list`, `group_view`, `group_view`, `tactical_view`, `alert_detail`, `external_link`, `other`, `dashboard` |  | User Metaconsole section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
| `metaconsoleDataSection` | string, nullable |  | User metaconsole section data |
| `forceChangePass` | boolean |  | Force the user to change the password on next login |
| `lastPassChange` | string, nullable |  | Date of last password change |
| `lastFailedLogin` | string, nullable |  | Date of last login failure |
| `failedAttempt` | integer |  | Number of failed login attempts by a user |
| `loginBlocked` | boolean |  | Blocked user |
| `metaconsoleAccess` | string, nullable |  | User metaconsole access |
| `notLogin` | boolean |  | The user with no access authorization can only access the API. |
| `localUser` | boolean |  | The user with local authentication enabled will always use local authentication. |
| `metaconsoleAgentsManager` | integer, nullable |  | Agents manager |
| `metaconsoleAccessNode` | integer, nullable |  | Access node |
| `strictAcl` | boolean |  | User with ACL strict |
| `idFilter` | integer, nullable |  | Assign a specific filter for user |
| `sessionTime` | integer, nullable |  | This is defined in minutes. If you want a permanent session, introduce -1 in this field. |
| `defaultEventFilter` | integer, nullable |  | Assign a specific filter in events for user |
| `metaconsoleDefaultEventFilter` | integer, nullable |  | Assign a specific filter in events for user metaconsole |
| `showTipsStartup` | boolean |  | User show tips startup |
| `autorefreshWhiteList` | string |  | User pages autorefresh |
| `timeAutorefresh` | integer |  | Interval of autorefresh of the elements, by default they are 30 seconds, needing to enable the autorefresh first |
| `defaultCustomView` | integer, nullable |  | default custom view for user |
| `ehorusUserLevelUser` | string |  | user access ehorus whit user name |
| `ehorusUserLevelPass` | string |  | user access ehorus whit user token |
| `ehorusUserLevelEnabled` | boolean |  | User access ehorus level |
| `itsmUserLevelUser` | string |  | user access ITSM whit user name |
| `itsmUserLevelPass` | string |  | user access ITSM whit user token |
| `apiToken` | string |  | Api key |
| `allowedIpActive` | boolean |  | User allowed ip active |
| `allowedIpList` | string, nullable |  | User allowed Ip List |
| `sessionMaxTimeExpire` | integer, nullable |  | user expire session time |
| `authTokenSecret` | string |  | Auth token |
| `twoFactorEnabled` | boolean |  | Whether the user has a TOTP secret in this console |
| `permanentlyBlockedAttempts` | integer |  | Number of bloked login attempts by a user |
| `permanentlyBlocked` | boolean |  | Blocked user permanently |
| `twoFactorEnabled` | boolean, nullable |  | Filter users by whether they have a TOTP secret stored in this console. true returns only users with two-factor authentication enabled, false only users without it; omit the field for no filter. |
| `freeSearch` | string, nullable |  | Find word in fullname and comments fields. |
| `multipleSearchString` | object |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
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
| `multipleSearch.field` | enum: `idUser`, `fullName`, `firstName`, `lastName`, `middleName`, `comments`, `lastConnect`, `registered`, `email`, `phone`, `isAdmin`, `language`, `timezone`, `idSkin`, `disabled`, `forceChangePass`, `loginBlocked`, `notLogin`, `localUser`, `strictAcl` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idUser`, `fullName`, `firstName`, `lastName`, `middleName`, `comments`, `lastConnect`, `registered`, `email`, `phone`, `isAdmin`, `language`, `timezone`, `idSkin`, `disabled`, `forceChangePass`, `loginBlocked`, `notLogin`, `localUser`, `strictAcl` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idUser": "string",
      "fullName": "string",
      "firstName": "string",
      "lastName": "string",
      "middleName": "string",
      "password": "password",
      "passwordValidate": "password",
      "oldPassword": "oldPassword",
      "comments": "The user is allergic",
      "email": "nobody@samplecompany.com",
      "phone": "555-555-555",
      "isAdmin": "false",
      "language": "catalonian",
      "timezone": "string",
      "blockSize": "20",
      "idSkin": 0,
      "disabled": false,
      "shortcut": 0,
      "shortcutData": "string",
      "section": "default",
      "dataSection": "string",
      "metaconsoleSection": "default",
      "metaconsoleDataSection": "string",
      "forceChangePass": false,
      "metaconsoleAccess": "string",
      "notLogin": false,
      "localUser": false,
      "metaconsoleAgentsManager": 0,
      "metaconsoleAccessNode": 0,
      "strictAcl": false,
      "idFilter": 0,
      "sessionTime": 0,
      "defaultEventFilter": 0,
      "metaconsoleDefaultEventFilter": 0,
      "showTipsStartup": true,
      "autorefreshWhiteList": "string",
      "timeAutorefresh": 0,
      "defaultCustomView": 0,
      "ehorusUserLevelUser": "string",
      "ehorusUserLevelPass": "string",
      "ehorusUserLevelEnabled": false,
      "itsmUserLevelUser": "string",
      "itsmUserLevelPass": "string",
      "allowedIpActive": false,
      "allowedIpList": "string",
      "sessionMaxTimeExpire": 0,
      "permanentlyBlocked": false,
      "twoFactorEnabled": false,
      "freeSearch": "string",
      "multipleSearchString": {
        "field": "idUser",
        "data": [
          "string"
        ]
      },
      "requestedFields": [
        "idUser"
      ],
      "fieldConditions": [
        {
          "field": "idUser",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idUser",
        "data": [
          0
        ]
      }
    }
    ```

**Response 200**: List Incidence object

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
    | `data.[].idUser` | string |  | Id user |
    | `data.[].fullName` | string, nullable |  | Full name |
    | `data.[].firstName` | string, nullable |  | First name |
    | `data.[].lastName` | string, nullable |  | Last name |
    | `data.[].middleName` | string, nullable |  | Middle name |
    | `data.[].password` | string, nullable |  |  |
    | `data.[].passwordValidate` | string, nullable |  |  |
    | `data.[].oldPassword` | string, nullable |  | Only administrator users will not have to confirm the old password |
    | `data.[].comments` | string, nullable |  | Comments for user |
    | `data.[].lastConnect` | integer, nullable |  | User last connect utimestamp |
    | `data.[].registered` | integer, nullable |  | User registration Unix timestamp |
    | `data.[].email` | string, nullable |  | User email address |
    | `data.[].phone` | string, nullable |  | User phone number |
    | `data.[].isAdmin` | boolean |  | User is administrator |
    | `data.[].language` | enum: `catalonian`, `english`, `spanish`, `french`, `japanese`, `russian`, `chinese` |  | User section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
    | `data.[].timezone` | string, nullable |  | User timezone, https://www.php.net/manual/en/datetimezone.listidentifiers.php |
    | `data.[].blockSize` | integer, nullable |  | User default block pagination size |
    | `data.[].idSkin` | integer, nullable |  | User id skin |
    | `data.[].disabled` | boolean |  | Disabling this user |
    | `data.[].shortcut` | integer, nullable |  | User shortcut |
    | `data.[].shortcutData` | string, nullable |  | User shorcut data |
    | `data.[].section` | enum: `default`, `visual_console`, `event_list`, `group_view`, `group_view`, `tactical_view`, `alert_detail`, `external_link`, `other`, `dashboard` |  | User section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
    | `data.[].dataSection` | string, nullable |  | User section data |
    | `data.[].metaconsoleSection` | enum: `default`, `visual_console`, `event_list`, `group_view`, `group_view`, `tactical_view`, `alert_detail`, `external_link`, `other`, `dashboard` |  | User Metaconsole section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
    | `data.[].metaconsoleDataSection` | string, nullable |  | User metaconsole section data |
    | `data.[].forceChangePass` | boolean |  | Force the user to change the password on next login |
    | `data.[].lastPassChange` | string, nullable |  | Date of last password change |
    | `data.[].lastFailedLogin` | string, nullable |  | Date of last login failure |
    | `data.[].failedAttempt` | integer |  | Number of failed login attempts by a user |
    | `data.[].loginBlocked` | boolean |  | Blocked user |
    | `data.[].metaconsoleAccess` | string, nullable |  | User metaconsole access |
    | `data.[].notLogin` | boolean |  | The user with no access authorization can only access the API. |
    | `data.[].localUser` | boolean |  | The user with local authentication enabled will always use local authentication. |
    | `data.[].metaconsoleAgentsManager` | integer, nullable |  | Agents manager |
    | `data.[].metaconsoleAccessNode` | integer, nullable |  | Access node |
    | `data.[].strictAcl` | boolean |  | User with ACL strict |
    | `data.[].idFilter` | integer, nullable |  | Assign a specific filter for user |
    | `data.[].sessionTime` | integer, nullable |  | This is defined in minutes. If you want a permanent session, introduce -1 in this field. |
    | `data.[].defaultEventFilter` | integer, nullable |  | Assign a specific filter in events for user |
    | `data.[].metaconsoleDefaultEventFilter` | integer, nullable |  | Assign a specific filter in events for user metaconsole |
    | `data.[].showTipsStartup` | boolean |  | User show tips startup |
    | `data.[].autorefreshWhiteList` | string |  | User pages autorefresh |
    | `data.[].timeAutorefresh` | integer |  | Interval of autorefresh of the elements, by default they are 30 seconds, needing to enable the autorefresh first |
    | `data.[].defaultCustomView` | integer, nullable |  | default custom view for user |
    | `data.[].ehorusUserLevelUser` | string |  | user access ehorus whit user name |
    | `data.[].ehorusUserLevelPass` | string |  | user access ehorus whit user token |
    | `data.[].ehorusUserLevelEnabled` | boolean |  | User access ehorus level |
    | `data.[].itsmUserLevelUser` | string |  | user access ITSM whit user name |
    | `data.[].itsmUserLevelPass` | string |  | user access ITSM whit user token |
    | `data.[].apiToken` | string |  | Api key |
    | `data.[].allowedIpActive` | boolean |  | User allowed ip active |
    | `data.[].allowedIpList` | string, nullable |  | User allowed Ip List |
    | `data.[].sessionMaxTimeExpire` | integer, nullable |  | user expire session time |
    | `data.[].authTokenSecret` | string |  | Auth token |
    | `data.[].twoFactorEnabled` | boolean |  | Whether the user has a TOTP secret in this console |
    | `data.[].permanentlyBlockedAttempts` | integer |  | Number of bloked login attempts by a user |
    | `data.[].permanentlyBlocked` | boolean |  | Blocked user permanently |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/user/{idUser}/notify` { #post-user-iduser-notify }

Send an email to a system user

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes |  |

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


Error responses: `400`, `401`, `403`, `404`, `422`, `502`, `500`.

### <span class="api-method api-post">POST</span> `/user/2fa/bulk/disable` { #post-user-2fa-bulk-disable }

Disable the two-factor authentication of several users

Best-effort operation. Per-user errors do not abort the rest. Administrator only.

**Request body** (`application/json`)


??? example "Example generated from the schema (placeholder values)"

    ```json
    [
      "string"
    ]
    ```

**Response 200**: Per-user results

??? note "Response fields (8 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `successCount` | integer |  |  |
    | `errorCount` | integer |  |  |
    | `results` | array of object |  |  |
    | `results.[].idUser` | string |  |  |
    | `results.[].success` | boolean |  |  |
    | `results.[].status` | integer |  |  |
    | `results.[].changed` | boolean |  |  |
    | `results.[].error` | string |  |  |


Error responses: `400`, `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/user/2fa/disable/all` { #post-user-2fa-disable-all }

Disable the two-factor authentication of all users

Deletes every console-local TOTP secret. Administrator only.

**Response 200**: All two-factor authentication secrets disabled

??? note "Response fields (2 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `successCount` | integer |  |  |
    | `errorCount` | integer |  |  |


Error responses: `401`, `403`, `500`.

### <span class="api-method api-post">POST</span> `/user/{idUser}/2fa/disable` { #post-user-iduser-2fa-disable }

Disable the two-factor authentication of a user

Deletes the console-local TOTP secret. Idempotent and local to this console.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes | User id |

**Request body** (`application/json`): [`UserTwoFactorAuthAction`](#model-usertwofactorauthaction)

**Response 200**: Two-factor authentication disabled

Schema: [`UserTwoFactorAuth`](#model-usertwofactorauth)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/user/{idUser}/2fa` { #get-user-iduser-2fa }

Show whether a user has two-factor authentication enabled

Reads the console-local tuser_double_auth table. The TOTP secret is never returned.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes | User id |

**Response 200**: Two-factor authentication status

Schema: [`UserTwoFactorAuth`](#model-usertwofactorauth)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/user/{idUser}/2fa/reset` { #post-user-iduser-2fa-reset }

Create or rotate the two-factor authentication secret of a user

Immediately activates a console-local TOTP secret. Returned only in this response.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes | User id |

**Request body** (`application/json`): [`UserTwoFactorAuthAction`](#model-usertwofactorauthaction)

**Response 200**: Two-factor authentication secret rotated

Schema: [`UserTwoFactorAuth`](#model-usertwofactorauth)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/user/{idUser}/profile/{idProfile}` { #post-user-iduser-profile-idprofile }

Create user profile

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes | User id |
| `idProfile` | path | integer | yes | Profile id |

**Request body** (`application/json`): [`UserProfile`](#model-userprofile)

**Response 200**: User Profile type object

Schema: [`UserProfile`](#model-userprofile)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/user/{idUser}/profiles/{idUserProfile}` { #get-user-iduser-profiles-iduserprofile }

show data field user profile

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes | User id |
| `idUserProfile` | path | integer | yes | User profile id |

**Response 200**: User Profile type object

Schema: [`UserProfile`](#model-userprofile)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/user/{idUser}/profiles/{idUserProfile}` { #delete-user-iduser-profiles-iduserprofile }

Deletes user profile.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes | User id |
| `idUserProfile` | path | integer | yes | User profile id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/user/{idUser}/profiles` { #get-user-iduser-profiles }

List user profiles

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes | User id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List data profiles user object

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
    | `data.[].idUserProfile` | integer |  | Id user profile |
    | `data.[].idUser` | string |  | Id User |
    | `data.[].idProfile` | integer |  | Id Profile |
    | `data.[].idGroup` | integer |  | Id Group |
    | `data.[].isNoHierarchy` | boolean, nullable |  | No hierarchy |
    | `data.[].assignedBy` | string |  | Create user profile by |
    | `data.[].idPolicy` | integer |  | Id Policy |
    | `data.[].tags` | array, nullable |  | Tags to which a user belongs |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/user/{idUser}/profiles` { #post-user-iduser-profiles }

List user profiles

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idUser` | path | string | yes | User id |
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Request body** (`application/json`): [`UserProfile`](#model-userprofile)

**Response 200**: List data profiles user object

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
    | `data.[].idUserProfile` | integer |  | Id user profile |
    | `data.[].idUser` | string |  | Id User |
    | `data.[].idProfile` | integer |  | Id Profile |
    | `data.[].idGroup` | integer |  | Id Group |
    | `data.[].isNoHierarchy` | boolean, nullable |  | No hierarchy |
    | `data.[].assignedBy` | string |  | Create user profile by |
    | `data.[].idPolicy` | integer |  | Id Policy |
    | `data.[].tags` | array, nullable |  | Tags to which a user belongs |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Profiles

API Endpoints of profiles

### <span class="api-method api-post">POST</span> `/profile` { #post-profile }

Creates a new profiles

**Request body** (`application/json`): [`Profile`](#model-profile)

**Response 200**: Profile object

Schema: [`Profile`](#model-profile)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/profile/{idProfile}` { #get-profile-idprofile }

Show profile

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idProfile` | path | integer | yes | Profile id |

**Response 200**: Profile object

Schema: [`Profile`](#model-profile)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/profile/{idProfile}` { #put-profile-idprofile }

Updates an profile

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idProfile` | path | integer | yes | Profile id |

**Request body** (`application/json`): [`Profile`](#model-profile)

**Response 200**: Profile object

Schema: [`Profile`](#model-profile)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/profile/{idProfile}` { #delete-profile-idprofile }

Deletes an profile object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idProfile` | path | integer | yes | Profile id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/profile/list` { #get-profile-list }

List profiles

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Incidence object

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
    | `data.[].idProfile` | integer |  | Id Profile |
    | `data.[].name` | string |  | Name of the profile |
    | `data.[].isAgentView` | boolean, nullable |  | Agent Read |
    | `data.[].isAgentEdit` | boolean, nullable |  | Agent Write |
    | `data.[].isAlertEdit` | boolean, nullable |  | Alert write |
    | `data.[].isUserManagement` | boolean, nullable |  | User Management |
    | `data.[].isDbManagement` | boolean, nullable |  | Database Management |
    | `data.[].isAlertManagement` | boolean, nullable |  | Alert Management |
    | `data.[].isPandoraManagement` | boolean, nullable |  | Pandora Management |
    | `data.[].isReportView` | boolean, nullable |  | Report view |
    | `data.[].isReportEdit` | boolean, nullable |  | Report Edit |
    | `data.[].isReportManagement` | boolean, nullable |  | Report Management |
    | `data.[].isEventView` | boolean, nullable |  | Event Read |
    | `data.[].isEventEdit` | boolean, nullable |  | Event write |
    | `data.[].isEventManagement` | boolean, nullable |  | Event Management |
    | `data.[].isAgentDisable` | boolean, nullable |  | Agent Disable |
    | `data.[].isMapView` | boolean, nullable |  | Map Read |
    | `data.[].isMapEdit` | boolean, nullable |  | Map Write |
    | `data.[].isMapManagement` | boolean, nullable |  | Map Management |
    | `data.[].isVconsoleView` | boolean, nullable |  | Visual console Read |
    | `data.[].isVconsoleEdit` | boolean, nullable |  | Visual console Write |
    | `data.[].isVconsoleManagement` | boolean, nullable |  | Visual console Management |
    | `data.[].isNetworkConfigView` | boolean, nullable |  | Network config read |
    | `data.[].isNetworkConfigEdit` | boolean, nullable |  | Network config Write |
    | `data.[].isNetworkConfigManagement` | boolean, nullable |  | Network config Management |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/profile/list` { #post-profile-list }

List profiles

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
| `idProfile` | integer |  | Id Profile |
| `name` | string |  | Name of the profile |
| `isAgentView` | boolean, nullable |  | Agent Read |
| `isAgentEdit` | boolean, nullable |  | Agent Write |
| `isAlertEdit` | boolean, nullable |  | Alert write |
| `isUserManagement` | boolean, nullable |  | User Management |
| `isDbManagement` | boolean, nullable |  | Database Management |
| `isAlertManagement` | boolean, nullable |  | Alert Management |
| `isPandoraManagement` | boolean, nullable |  | Pandora Management |
| `isReportView` | boolean, nullable |  | Report view |
| `isReportEdit` | boolean, nullable |  | Report Edit |
| `isReportManagement` | boolean, nullable |  | Report Management |
| `isEventView` | boolean, nullable |  | Event Read |
| `isEventEdit` | boolean, nullable |  | Event write |
| `isEventManagement` | boolean, nullable |  | Event Management |
| `isAgentDisable` | boolean, nullable |  | Agent Disable |
| `isMapView` | boolean, nullable |  | Map Read |
| `isMapEdit` | boolean, nullable |  | Map Write |
| `isMapManagement` | boolean, nullable |  | Map Management |
| `isVconsoleView` | boolean, nullable |  | Visual console Read |
| `isVconsoleEdit` | boolean, nullable |  | Visual console Write |
| `isVconsoleManagement` | boolean, nullable |  | Visual console Management |
| `isNetworkConfigView` | boolean, nullable |  | Network config read |
| `isNetworkConfigEdit` | boolean, nullable |  | Network config Write |
| `isNetworkConfigManagement` | boolean, nullable |  | Network config Management |
| `idProfile` |  |  |  |
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
| `multipleSearch.field` | enum: `idProfile`, `name`, `isAgentView`, `isAgentEdit`, `isAlertEdit`, `isUserManagement`, `isDbManagement`, `isAlertManagement`, `isPandoraManagement`, `isReportView`, `isReportEdit`, `isReportManagement`, `isEventView`, `isEventEdit`, `isEventManagement`, `isAgentDisable`, `isMapView`, `isMapEdit`, `isMapManagement`, `isVconsoleView`, `isVconsoleEdit`, `isVconsoleManagement`, `isNetworkConfigView`, `isNetworkConfigEdit`, `isNetworkConfigManagement` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idProfile`, `name`, `isAgentView`, `isAgentEdit`, `isAlertEdit`, `isUserManagement`, `isDbManagement`, `isAlertManagement`, `isPandoraManagement`, `isReportView`, `isReportEdit`, `isReportManagement`, `isEventView`, `isEventEdit`, `isEventManagement`, `isAgentDisable`, `isMapView`, `isMapEdit`, `isMapManagement`, `isVconsoleView`, `isVconsoleEdit`, `isVconsoleManagement`, `isNetworkConfigView`, `isNetworkConfigEdit`, `isNetworkConfigManagement` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "isAgentView": false,
      "isAgentEdit": false,
      "isAlertEdit": false,
      "isUserManagement": false,
      "isDbManagement": false,
      "isAlertManagement": false,
      "isPandoraManagement": false,
      "isReportView": false,
      "isReportEdit": false,
      "isReportManagement": false,
      "isEventView": false,
      "isEventEdit": false,
      "isEventManagement": false,
      "isAgentDisable": false,
      "isMapView": false,
      "isMapEdit": false,
      "isMapManagement": false,
      "isVconsoleView": false,
      "isVconsoleEdit": false,
      "isVconsoleManagement": false,
      "isNetworkConfigView": false,
      "isNetworkConfigEdit": false,
      "isNetworkConfigManagement": false,
      "idProfile": null,
      "freeSearch": "string",
      "requestedFields": [
        "idProfile"
      ],
      "fieldConditions": [
        {
          "field": "idProfile",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idProfile",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idProfile",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List Incidence object

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
    | `data.[].idProfile` | integer |  | Id Profile |
    | `data.[].name` | string |  | Name of the profile |
    | `data.[].isAgentView` | boolean, nullable |  | Agent Read |
    | `data.[].isAgentEdit` | boolean, nullable |  | Agent Write |
    | `data.[].isAlertEdit` | boolean, nullable |  | Alert write |
    | `data.[].isUserManagement` | boolean, nullable |  | User Management |
    | `data.[].isDbManagement` | boolean, nullable |  | Database Management |
    | `data.[].isAlertManagement` | boolean, nullable |  | Alert Management |
    | `data.[].isPandoraManagement` | boolean, nullable |  | Pandora Management |
    | `data.[].isReportView` | boolean, nullable |  | Report view |
    | `data.[].isReportEdit` | boolean, nullable |  | Report Edit |
    | `data.[].isReportManagement` | boolean, nullable |  | Report Management |
    | `data.[].isEventView` | boolean, nullable |  | Event Read |
    | `data.[].isEventEdit` | boolean, nullable |  | Event write |
    | `data.[].isEventManagement` | boolean, nullable |  | Event Management |
    | `data.[].isAgentDisable` | boolean, nullable |  | Agent Disable |
    | `data.[].isMapView` | boolean, nullable |  | Map Read |
    | `data.[].isMapEdit` | boolean, nullable |  | Map Write |
    | `data.[].isMapManagement` | boolean, nullable |  | Map Management |
    | `data.[].isVconsoleView` | boolean, nullable |  | Visual console Read |
    | `data.[].isVconsoleEdit` | boolean, nullable |  | Visual console Write |
    | `data.[].isVconsoleManagement` | boolean, nullable |  | Visual console Management |
    | `data.[].isNetworkConfigView` | boolean, nullable |  | Network config read |
    | `data.[].isNetworkConfigEdit` | boolean, nullable |  | Network config Write |
    | `data.[].isNetworkConfigManagement` | boolean, nullable |  | Network config Management |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Groups

API Endpoints of Groups

### <span class="api-method api-post">POST</span> `/group` { #post-group }

Creates a new groups

**Request body** (`application/json`): [`Group`](#model-group)

**Response 200**: Group object

Schema: [`Group`](#model-group)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/group/{idGroup}` { #get-group-idgroup }

Show group

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idGroup` | path | integer | yes | Group id |

**Response 200**: Group object

Schema: [`Group`](#model-group)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/group/{idGroup}` { #put-group-idgroup }

Updates an group

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idGroup` | path | integer | yes | Group id |

**Request body** (`application/json`): [`Group`](#model-group)

**Response 200**: Group object

Schema: [`Group`](#model-group)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/group/{idGroup}` { #delete-group-idgroup }

Deletes an group object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idGroup` | path | integer | yes | Group id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/group/list` { #get-group-list }

List groups

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Groups Object

??? note "Response fields (27 fields)"

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
    | `data.[].idGroup` | integer |  | Id group |
    | `data.[].name` | string, nullable |  | Name group |
    | `data.[].icon` | string, nullable |  | Path icon, by default: without-group@groups.svg |
    | `data.[].parent` | integer, nullable |  | Id Group parent |
    | `data.[].parentName` | string, nullable |  | name group parent |
    | `data.[].hasChild` | boolean, nullable |  | Group has child |
    | `data.[].isPropagate` | boolean |  | Group propagate |
    | `data.[].isAlertEnabled` | boolean |  | Group is alert enabled |
    | `data.[].customId` | string, nullable |  | Custom id |
    | `data.[].idSkin` | integer, nullable |  | Id skin |
    | `data.[].description` | string, nullable |  | Description |
    | `data.[].contact` | string, nullable |  | Contact |
    | `data.[].other` | string, nullable |  | Other things |
    | `data.[].password` | string, nullable |  |  |
    | `data.[].maxAgents` | integer |  | Maximum number of agents per group |
    | `data.[].enableVisualSetting` | boolean |  | Enable group visual settings |
    | `data.[].visualSettings` | string, nullable |  | Group visual settings |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/group/list` { #post-group-list }

List groups

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
| `idGroup` | integer |  | Id group |
| `name` | string, nullable |  | Name group |
| `icon` | string, nullable |  | Path icon, by default: without-group@groups.svg |
| `parent` | integer, nullable |  | Id Group parent |
| `parentName` | string, nullable |  | name group parent |
| `hasChild` | boolean, nullable |  | Group has child |
| `isPropagate` | boolean |  | Group propagate |
| `isAlertEnabled` | boolean |  | Group is alert enabled |
| `customId` | string, nullable |  | Custom id |
| `idSkin` | integer, nullable |  | Id skin |
| `description` | string, nullable |  | Description |
| `contact` | string, nullable |  | Contact |
| `other` | string, nullable |  | Other things |
| `password` | string, nullable |  |  |
| `maxAgents` | integer |  | Maximum number of agents per group |
| `enableVisualSetting` | boolean |  | Enable group visual settings |
| `visualSettings` | string, nullable |  | Group visual settings |
| `idGroup` |  |  |  |
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
| `multipleSearch.field` | enum: `idGroup`, `name`, `icon`, `parent`, `isPropagate`, `isAlertEnabled`, `customId`, `idSkin`, `description`, `contact`, `other`, `maxAgents`, `enableVisualSetting`, `visualSettings` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idGroup`, `name`, `icon`, `parent`, `isPropagate`, `isAlertEnabled`, `customId`, `idSkin`, `description`, `contact`, `other`, `maxAgents`, `enableVisualSetting`, `visualSettings` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "icon": "string",
      "parent": 0,
      "isPropagate": "false",
      "isAlertEnabled": "true",
      "customId": "string",
      "idSkin": 0,
      "description": "string",
      "contact": "string",
      "other": "string",
      "password": "string",
      "maxAgents": 0,
      "enableVisualSetting": false,
      "visualSettings": "string",
      "idGroup": null,
      "freeSearch": "string",
      "requestedFields": [
        "idGroup"
      ],
      "fieldConditions": [
        {
          "field": "idGroup",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idGroup",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idGroup",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List Groups Object

??? note "Response fields (27 fields)"

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
    | `data.[].idGroup` | integer |  | Id group |
    | `data.[].name` | string, nullable |  | Name group |
    | `data.[].icon` | string, nullable |  | Path icon, by default: without-group@groups.svg |
    | `data.[].parent` | integer, nullable |  | Id Group parent |
    | `data.[].parentName` | string, nullable |  | name group parent |
    | `data.[].hasChild` | boolean, nullable |  | Group has child |
    | `data.[].isPropagate` | boolean |  | Group propagate |
    | `data.[].isAlertEnabled` | boolean |  | Group is alert enabled |
    | `data.[].customId` | string, nullable |  | Custom id |
    | `data.[].idSkin` | integer, nullable |  | Id skin |
    | `data.[].description` | string, nullable |  | Description |
    | `data.[].contact` | string, nullable |  | Contact |
    | `data.[].other` | string, nullable |  | Other things |
    | `data.[].password` | string, nullable |  |  |
    | `data.[].maxAgents` | integer |  | Maximum number of agents per group |
    | `data.[].enableVisualSetting` | boolean |  | Enable group visual settings |
    | `data.[].visualSettings` | string, nullable |  | Group visual settings |


Error responses: `400`, `401`, `403`, `404`, `500`.

## Tags

API Endpoints of tags

### <span class="api-method api-post">POST</span> `/tag` { #post-tag }

Creates a new tags

**Request body** (`application/json`): [`Tag`](#model-tag)

**Response 200**: Tag object

Schema: [`Tag`](#model-tag)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/tag/{idTag}` { #get-tag-idtag }

Show tag

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idTag` | path | integer | yes | Tag id |

**Response 200**: Tag object

Schema: [`Tag`](#model-tag)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-put">PUT</span> `/tag/{idTag}` { #put-tag-idtag }

Updates an tag

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idTag` | path | integer | yes | Tag id |

**Request body** (`application/json`): [`Tag`](#model-tag)

**Response 200**: Tag object

Schema: [`Tag`](#model-tag)

Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-delete">DELETE</span> `/tag/{idTag}` { #delete-tag-idtag }

Deletes an tag object.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idTag` | path | integer | yes | Tag id |

**Response 200**: Successfully deleted

??? note "Response fields (1 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `result` | string |  |  |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-get">GET</span> `/tag/list` { #get-tag-list }

List tags

Supports pagination, sorting, and filters through query parameters.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |

**Response 200**: List Incidence object

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
    | `data.[].idTag` | integer |  | Id Tag |
    | `data.[].name` | string |  | Name of the tag |
    | `data.[].description` | string, nullable |  | Description of the tag |
    | `data.[].url` | string, nullable |  | Url of the tag |
    | `data.[].mail` | string, nullable |  | Email address associated with the tag |
    | `data.[].phone` | string, nullable |  | Phone of the tag |
    | `data.[].previousName` | string, nullable |  | Previous name of the tag |


Error responses: `400`, `401`, `403`, `404`, `500`.

### <span class="api-method api-post">POST</span> `/tag/list` { #post-tag-list }

List tags

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
| `idTag` | integer |  | Id Tag |
| `name` | string |  | Name of the tag |
| `description` | string, nullable |  | Description of the tag |
| `url` | string, nullable |  | Url of the tag |
| `mail` | string, nullable |  | Email address associated with the tag |
| `phone` | string, nullable |  | Phone of the tag |
| `previousName` | string, nullable |  | Previous name of the tag |
| `idTag` |  |  |  |
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
| `multipleSearch.field` | enum: `idTag`, `name`, `description`, `url`, `mail`, `phone` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idTag`, `name`, `description`, `url`, `mail`, `phone` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "url": "string",
      "mail": "string",
      "phone": "string",
      "idTag": null,
      "freeSearch": "string",
      "requestedFields": [
        "idTag"
      ],
      "fieldConditions": [
        {
          "field": "idTag",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "multipleSearch": {
        "field": "idTag",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idTag",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: List Incidence object

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
    | `data.[].idTag` | integer |  | Id Tag |
    | `data.[].name` | string |  | Name of the tag |
    | `data.[].description` | string, nullable |  | Description of the tag |
    | `data.[].url` | string, nullable |  | Url of the tag |
    | `data.[].mail` | string, nullable |  | Email address associated with the tag |
    | `data.[].phone` | string, nullable |  | Phone of the tag |
    | `data.[].previousName` | string, nullable |  | Previous name of the tag |


Error responses: `400`, `401`, `403`, `404`, `500`.

## AuditLogs

Read-only system audit log and extended data

### <span class="api-method api-get">GET</span> `/audit/log/{idSession}` { #get-audit-log-idsession }

Get one audit log entry and its extended data

Requires PM. serverId is required on a metaconsole and reads one node; it must
be omitted on a standalone console. Returns decoded text, structured JSON extended data,
and the stored hash status without modifying any record.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `idSession` | path | integer (int64) | yes | Audit log session id |
| `serverId` | query | integer |  | Node id. Required on a metaconsole; omitted on a standalone console |

**Response 200**: Audit log entry

??? note "Response fields (16 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idSession` | integer (int64) |  |  |
    | `serverId` | integer, nullable |  | Origin node; null for the local console |
    | `idUser` | string, nullable |  |  |
    | `sourceIp` | string |  |  |
    | `action` | string |  |  |
    | `description` | string, nullable |  |  |
    | `timestamp` | integer (int64) |  | UTC epoch seconds from utimestamp |
    | `date` | string (date-time) |  | ISO 8601 UTC value derived from timestamp |
    | `aiSession` | string, nullable |  | Pandora AI correlation identifier; this endpoint does not read the AI audit |
    | `extendedData` | array of object |  | Omitted when requestedFields is supplied; use GET or an unprojected LIST |
    | `extendedData.[].idExtended` | integer |  |  |
    | `extendedData.[].idSession` | integer (int64) |  |  |
    | `extendedData.[].format` | enum: `json`, `text` |  |  |
    | `extendedData.[].data` |  |  |  |
    | `extendedData.[].hash` | string |  |  |
    | `extendedData.[].hashValid` | boolean |  |  |


Error responses: `400`, `401`, `403`, `404`, `502`, `503`, `504`, `500`.

### <span class="api-method api-get">GET</span> `/audit/log/list` { #get-audit-log-list }

List audit log entries with query filters

Requires PM. Default last 24h. serverId is required on a metaconsole and reads
one node; it must be omitted on a standalone console. Simple text, user and date filters are
published in query. POST exposes the full filter body. Public sizePage is 1000; the requested
page window cannot exceed 10000. sortField accepts timestamp, date or idSession. Omit
requestedFields to include extended data.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Node id. Required on a metaconsole; omitted on a standalone console |
| `idSession` | query | integer (int64) |  |  |
| `idUser` | query | string, nullable |  |  |
| `sourceIp` | query | string, nullable |  |  |
| `action` | query | string, nullable |  |  |
| `description` | query | string, nullable |  |  |
| `timestamp` | query | integer (int64) |  |  |
| `aiSession` | query | string, nullable |  |  |
| `freeSearch` | query | string, nullable |  |  |
| `startDate` | query | string (date-time), nullable |  |  |
| `endDate` | query | string (date-time), nullable |  |  |

**Response 200**: Audit log list

??? note "Response fields (28 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `startDate` | string (date-time) |  |  |
    | `endDate` | string (date-time) |  |  |
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
    | `data.[].idSession` | integer (int64) |  |  |
    | `data.[].serverId` | integer, nullable |  | Origin node; null for the local console |
    | `data.[].idUser` | string, nullable |  |  |
    | `data.[].sourceIp` | string |  |  |
    | `data.[].action` | string |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].timestamp` | integer (int64) |  | UTC epoch seconds from utimestamp |
    | `data.[].date` | string (date-time) |  | ISO 8601 UTC value derived from timestamp |
    | `data.[].aiSession` | string, nullable |  | Pandora AI correlation identifier; this endpoint does not read the AI audit |
    | `data.[].extendedData` | array of object |  | Omitted when requestedFields is supplied; use GET or an unprojected LIST |
    | `data.[].extendedData.[].idExtended` | integer |  |  |
    | `data.[].extendedData.[].idSession` | integer (int64) |  |  |
    | `data.[].extendedData.[].format` | enum: `json`, `text` |  |  |
    | `data.[].extendedData.[].data` |  |  |  |
    | `data.[].extendedData.[].hash` | string |  |  |
    | `data.[].extendedData.[].hashValid` | boolean |  |  |


Error responses: `400`, `401`, `403`, `502`, `503`, `504`, `500`.

### <span class="api-method api-post">POST</span> `/audit/log/list` { #post-audit-log-list }

List audit log entries with body filters

Same semantics as GET. Body filters override query filters. serverId is a
single node identifier, required on a metaconsole and forbidden on a standalone console.
Pagination and sorting are accepted as query parameters. Omit requestedFields to include
extended data; when requestedFields is present extendedData is not returned.

**Parameters**

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `page` | query | integer |  | Zero-based page index. 0 selects the first page. |
| `sizePage` | query | integer |  | Size page |
| `sortField` | query | string |  | sort field |
| `sortDirection` | query | enum: `ASC`, `DESC` |  | sort direction |
| `serverId` | query | integer |  | Node id. Required on a metaconsole; omitted on a standalone console |
| `idSession` | query | integer (int64) |  |  |
| `idUser` | query | string, nullable |  |  |
| `sourceIp` | query | string, nullable |  |  |
| `action` | query | string, nullable |  |  |
| `description` | query | string, nullable |  |  |
| `timestamp` | query | integer (int64) |  |  |
| `aiSession` | query | string, nullable |  |  |
| `freeSearch` | query | string, nullable |  |  |
| `startDate` | query | string (date-time), nullable |  |  |
| `endDate` | query | string (date-time), nullable |  |  |

**Request body** (`application/json`)

| Field | Type | Required | Description |
|---|---|---|---|
| `requestedFields` | array, nullable |  | Optional list of API field names to include in the SQL SELECT. Field names must be valid fields of the concrete filter schema. The legacy fields property is still accepted for backwards compatibility. |
| `fieldConditions` | array, nullable |  | Advanced conditions joined with AND. Field names must be valid fields of the concrete filter schema. |
| `page` | integer, nullable |  | Zero-based page index. 0 selects the first page; omission or null uses the first page. |
| `sizePage` | integer, nullable |  | Items per page. Cannot be combined with limit or offset. |
| `limit` | integer, nullable |  | Offset-mode row limit; zero returns no rows. Incompatible with page/sizePage. |
| `offset` | integer, nullable |  | Rows to skip; zero by default. Without limit, returns the rest. Incompatible with page/sizePage. |
| `page` | integer, nullable |  |  |
| `sizePage` | integer, nullable |  |  |
| `limit` | integer, nullable |  |  |
| `offset` | integer, nullable |  |  |
| `sortField` | enum: `timestamp`, `date`, `idSession` |  |  |
| `sortDirection` | enum: `ASC`, `DESC` |  |  |
| `idSession` | integer (int64), nullable |  |  |
| `idUser` | string, nullable |  |  |
| `sourceIp` | string, nullable |  |  |
| `action` | string, nullable |  |  |
| `description` | string, nullable |  |  |
| `timestamp` | integer (int64), nullable |  |  |
| `aiSession` | string, nullable |  |  |
| `freeSearch` | string, nullable |  |  |
| `startDate` | string (date-time), nullable |  |  |
| `endDate` | string (date-time), nullable |  |  |
| `serverId` | integer, nullable |  | Node identifier. Required when reading from a metaconsole |
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
| `multipleSearch.field` | enum: `idSession`, `idUser`, `sourceIp`, `action`, `description`, `timestamp`, `aiSession` |  |  |
| `multipleSearchString` |  |  |  |
| `multipleSearchString.field` | string, nullable |  | Field to search of query |
| `multipleSearchString.data` | array, nullable |  | Values to search of query IN() |
| `multipleSearchString.field` | enum: `idSession`, `idUser`, `sourceIp`, `action`, `description`, `timestamp`, `aiSession` |  |  |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "requestedFields": [
        "idSession"
      ],
      "fieldConditions": [
        {
          "field": "idSession",
          "operator": "like",
          "value": "capacity"
        }
      ],
      "page": 0,
      "sizePage": 0,
      "limit": 0,
      "offset": 0,
      "sortField": "timestamp",
      "sortDirection": "ASC",
      "idSession": 0,
      "idUser": "string",
      "sourceIp": "string",
      "action": "string",
      "description": "string",
      "timestamp": 0,
      "aiSession": "string",
      "freeSearch": "string",
      "startDate": "string",
      "endDate": "string",
      "serverId": 0,
      "multipleSearch": {
        "field": "idSession",
        "data": [
          0
        ]
      },
      "multipleSearchString": {
        "field": "idSession",
        "data": [
          "string"
        ]
      }
    }
    ```

**Response 200**: Audit log list

??? note "Response fields (28 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `startDate` | string (date-time) |  |  |
    | `endDate` | string (date-time) |  |  |
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
    | `data.[].idSession` | integer (int64) |  |  |
    | `data.[].serverId` | integer, nullable |  | Origin node; null for the local console |
    | `data.[].idUser` | string, nullable |  |  |
    | `data.[].sourceIp` | string |  |  |
    | `data.[].action` | string |  |  |
    | `data.[].description` | string, nullable |  |  |
    | `data.[].timestamp` | integer (int64) |  | UTC epoch seconds from utimestamp |
    | `data.[].date` | string (date-time) |  | ISO 8601 UTC value derived from timestamp |
    | `data.[].aiSession` | string, nullable |  | Pandora AI correlation identifier; this endpoint does not read the AI audit |
    | `data.[].extendedData` | array of object |  | Omitted when requestedFields is supplied; use GET or an unprojected LIST |
    | `data.[].extendedData.[].idExtended` | integer |  |  |
    | `data.[].extendedData.[].idSession` | integer (int64) |  |  |
    | `data.[].extendedData.[].format` | enum: `json`, `text` |  |  |
    | `data.[].extendedData.[].data` |  |  |  |
    | `data.[].extendedData.[].hash` | string |  |  |
    | `data.[].extendedData.[].hashValid` | boolean |  |  |


Error responses: `400`, `401`, `403`, `502`, `503`, `504`, `500`.

## Models

Schemas used by more than one operation on this page. Those you send are open and have an example; those you receive are collapsed.

### Model: Group { #model-group }

| Field | Type | Required | Description |
|---|---|---|---|
| `idGroup` | integer |  | Id group |
| `name` | string, nullable |  | Name group |
| `icon` | string, nullable |  | Path icon, by default: without-group@groups.svg |
| `parent` | integer, nullable |  | Id Group parent |
| `parentName` | string, nullable |  | name group parent |
| `hasChild` | boolean, nullable |  | Group has child |
| `isPropagate` | boolean |  | Group propagate |
| `isAlertEnabled` | boolean |  | Group is alert enabled |
| `customId` | string, nullable |  | Custom id |
| `idSkin` | integer, nullable |  | Id skin |
| `description` | string, nullable |  | Description |
| `contact` | string, nullable |  | Contact |
| `other` | string, nullable |  | Other things |
| `password` | string, nullable |  |  |
| `maxAgents` | integer |  | Maximum number of agents per group |
| `enableVisualSetting` | boolean |  | Enable group visual settings |
| `visualSettings` | string, nullable |  | Group visual settings |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "icon": "string",
      "parent": 0,
      "isPropagate": "false",
      "isAlertEnabled": "true",
      "customId": "string",
      "idSkin": 0,
      "description": "string",
      "contact": "string",
      "other": "string",
      "password": "string",
      "maxAgents": 0,
      "enableVisualSetting": false,
      "visualSettings": "string"
    }
    ```

### Model: Profile { #model-profile }

| Field | Type | Required | Description |
|---|---|---|---|
| `idProfile` | integer |  | Id Profile |
| `name` | string |  | Name of the profile |
| `isAgentView` | boolean, nullable |  | Agent Read |
| `isAgentEdit` | boolean, nullable |  | Agent Write |
| `isAlertEdit` | boolean, nullable |  | Alert write |
| `isUserManagement` | boolean, nullable |  | User Management |
| `isDbManagement` | boolean, nullable |  | Database Management |
| `isAlertManagement` | boolean, nullable |  | Alert Management |
| `isPandoraManagement` | boolean, nullable |  | Pandora Management |
| `isReportView` | boolean, nullable |  | Report view |
| `isReportEdit` | boolean, nullable |  | Report Edit |
| `isReportManagement` | boolean, nullable |  | Report Management |
| `isEventView` | boolean, nullable |  | Event Read |
| `isEventEdit` | boolean, nullable |  | Event write |
| `isEventManagement` | boolean, nullable |  | Event Management |
| `isAgentDisable` | boolean, nullable |  | Agent Disable |
| `isMapView` | boolean, nullable |  | Map Read |
| `isMapEdit` | boolean, nullable |  | Map Write |
| `isMapManagement` | boolean, nullable |  | Map Management |
| `isVconsoleView` | boolean, nullable |  | Visual console Read |
| `isVconsoleEdit` | boolean, nullable |  | Visual console Write |
| `isVconsoleManagement` | boolean, nullable |  | Visual console Management |
| `isNetworkConfigView` | boolean, nullable |  | Network config read |
| `isNetworkConfigEdit` | boolean, nullable |  | Network config Write |
| `isNetworkConfigManagement` | boolean, nullable |  | Network config Management |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "isAgentView": false,
      "isAgentEdit": false,
      "isAlertEdit": false,
      "isUserManagement": false,
      "isDbManagement": false,
      "isAlertManagement": false,
      "isPandoraManagement": false,
      "isReportView": false,
      "isReportEdit": false,
      "isReportManagement": false,
      "isEventView": false,
      "isEventEdit": false,
      "isEventManagement": false,
      "isAgentDisable": false,
      "isMapView": false,
      "isMapEdit": false,
      "isMapManagement": false,
      "isVconsoleView": false,
      "isVconsoleEdit": false,
      "isVconsoleManagement": false,
      "isNetworkConfigView": false,
      "isNetworkConfigEdit": false,
      "isNetworkConfigManagement": false
    }
    ```

### Model: Tag { #model-tag }

| Field | Type | Required | Description |
|---|---|---|---|
| `idTag` | integer |  | Id Tag |
| `name` | string |  | Name of the tag |
| `description` | string, nullable |  | Description of the tag |
| `url` | string, nullable |  | Url of the tag |
| `mail` | string, nullable |  | Email address associated with the tag |
| `phone` | string, nullable |  | Phone of the tag |
| `previousName` | string, nullable |  | Previous name of the tag |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "name": "string",
      "description": "string",
      "url": "string",
      "mail": "string",
      "phone": "string"
    }
    ```

### Model: Token { #model-token }

??? note "Fields (12 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idToken` | integer |  | Id Token |
    | `label` | string |  | label of the token |
    | `uuid` | string, nullable |  | uuid of the token |
    | `idUser` | string, nullable |  | Owner user id. Optional for user authentication; required when credentials have no associated user. |
    | `validity` | string, nullable |  | Date until which tocken is valid, if it is void it will never expire |
    | `lastUsage` | string, nullable |  | last_usage of the token |
    | `isPandoraAi` | boolean |  | Whether this is a Pandora AI token. AI tokens are created and managed by the console. |
    | `tokenType` | enum: `access`, `refresh`, `mfa` |  | Credential type. Only access tokens work on the general API. |
    | `sessionId` | string, nullable |  | Groups the access and refresh rows of the same session. |
    | `isMobile` | boolean, nullable |  | Mobile session (filterable; the list excludes them by default). |
    | `deviceInfo` | object, nullable |  | Client metadata: device id, platform, app version, ip, locale, timezone, screen. |
    | `sessionExpiresAt` | string, nullable |  | Absolute session limit (login + 7 days). |


### Model: User { #model-user }

| Field | Type | Required | Description |
|---|---|---|---|
| `idUser` | string |  | Id user |
| `fullName` | string, nullable |  | Full name |
| `firstName` | string, nullable |  | First name |
| `lastName` | string, nullable |  | Last name |
| `middleName` | string, nullable |  | Middle name |
| `password` | string, nullable |  |  |
| `passwordValidate` | string, nullable |  |  |
| `oldPassword` | string, nullable |  | Only administrator users will not have to confirm the old password |
| `comments` | string, nullable |  | Comments for user |
| `lastConnect` | integer, nullable |  | User last connect utimestamp |
| `registered` | integer, nullable |  | User registration Unix timestamp |
| `email` | string, nullable |  | User email address |
| `phone` | string, nullable |  | User phone number |
| `isAdmin` | boolean |  | User is administrator |
| `language` | enum: `catalonian`, `english`, `spanish`, `french`, `japanese`, `russian`, `chinese` |  | User section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
| `timezone` | string, nullable |  | User timezone, https://www.php.net/manual/en/datetimezone.listidentifiers.php |
| `blockSize` | integer, nullable |  | User default block pagination size |
| `idSkin` | integer, nullable |  | User id skin |
| `disabled` | boolean |  | Disabling this user |
| `shortcut` | integer, nullable |  | User shortcut |
| `shortcutData` | string, nullable |  | User shorcut data |
| `section` | enum: `default`, `visual_console`, `event_list`, `group_view`, `group_view`, `tactical_view`, `alert_detail`, `external_link`, `other`, `dashboard` |  | User section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
| `dataSection` | string, nullable |  | User section data |
| `metaconsoleSection` | enum: `default`, `visual_console`, `event_list`, `group_view`, `group_view`, `tactical_view`, `alert_detail`, `external_link`, `other`, `dashboard` |  | User Metaconsole section, the available sections are: default, visual_console, event_list, group_view, group_view, tactical_view, alert_detail, external_link, other, dashboard |
| `metaconsoleDataSection` | string, nullable |  | User metaconsole section data |
| `forceChangePass` | boolean |  | Force the user to change the password on next login |
| `lastPassChange` | string, nullable |  | Date of last password change |
| `lastFailedLogin` | string, nullable |  | Date of last login failure |
| `failedAttempt` | integer |  | Number of failed login attempts by a user |
| `loginBlocked` | boolean |  | Blocked user |
| `metaconsoleAccess` | string, nullable |  | User metaconsole access |
| `notLogin` | boolean |  | The user with no access authorization can only access the API. |
| `localUser` | boolean |  | The user with local authentication enabled will always use local authentication. |
| `metaconsoleAgentsManager` | integer, nullable |  | Agents manager |
| `metaconsoleAccessNode` | integer, nullable |  | Access node |
| `strictAcl` | boolean |  | User with ACL strict |
| `idFilter` | integer, nullable |  | Assign a specific filter for user |
| `sessionTime` | integer, nullable |  | This is defined in minutes. If you want a permanent session, introduce -1 in this field. |
| `defaultEventFilter` | integer, nullable |  | Assign a specific filter in events for user |
| `metaconsoleDefaultEventFilter` | integer, nullable |  | Assign a specific filter in events for user metaconsole |
| `showTipsStartup` | boolean |  | User show tips startup |
| `autorefreshWhiteList` | string |  | User pages autorefresh |
| `timeAutorefresh` | integer |  | Interval of autorefresh of the elements, by default they are 30 seconds, needing to enable the autorefresh first |
| `defaultCustomView` | integer, nullable |  | default custom view for user |
| `ehorusUserLevelUser` | string |  | user access ehorus whit user name |
| `ehorusUserLevelPass` | string |  | user access ehorus whit user token |
| `ehorusUserLevelEnabled` | boolean |  | User access ehorus level |
| `itsmUserLevelUser` | string |  | user access ITSM whit user name |
| `itsmUserLevelPass` | string |  | user access ITSM whit user token |
| `apiToken` | string |  | Api key |
| `allowedIpActive` | boolean |  | User allowed ip active |
| `allowedIpList` | string, nullable |  | User allowed Ip List |
| `sessionMaxTimeExpire` | integer, nullable |  | user expire session time |
| `authTokenSecret` | string |  | Auth token |
| `twoFactorEnabled` | boolean |  | Whether the user has a TOTP secret in this console |
| `permanentlyBlockedAttempts` | integer |  | Number of bloked login attempts by a user |
| `permanentlyBlocked` | boolean |  | Blocked user permanently |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idUser": "string",
      "fullName": "string",
      "firstName": "string",
      "lastName": "string",
      "middleName": "string",
      "password": "password",
      "passwordValidate": "password",
      "oldPassword": "oldPassword",
      "comments": "The user is allergic",
      "email": "nobody@samplecompany.com",
      "phone": "555-555-555",
      "isAdmin": "false",
      "language": "catalonian",
      "timezone": "string",
      "blockSize": "20",
      "idSkin": 0,
      "disabled": false,
      "shortcut": 0,
      "shortcutData": "string",
      "section": "default",
      "dataSection": "string",
      "metaconsoleSection": "default",
      "metaconsoleDataSection": "string",
      "forceChangePass": false,
      "metaconsoleAccess": "string",
      "notLogin": false,
      "localUser": false,
      "metaconsoleAgentsManager": 0,
      "metaconsoleAccessNode": 0,
      "strictAcl": false,
      "idFilter": 0,
      "sessionTime": 0,
      "defaultEventFilter": 0,
      "metaconsoleDefaultEventFilter": 0,
      "showTipsStartup": true,
      "autorefreshWhiteList": "string",
      "timeAutorefresh": 0,
      "defaultCustomView": 0,
      "ehorusUserLevelUser": "string",
      "ehorusUserLevelPass": "string",
      "ehorusUserLevelEnabled": false,
      "itsmUserLevelUser": "string",
      "itsmUserLevelPass": "string",
      "allowedIpActive": false,
      "allowedIpList": "string",
      "sessionMaxTimeExpire": 0,
      "permanentlyBlocked": false
    }
    ```

### Model: UserProfile { #model-userprofile }

| Field | Type | Required | Description |
|---|---|---|---|
| `idUserProfile` | integer |  | Id user profile |
| `idUser` | string |  | Id User |
| `idProfile` | integer |  | Id Profile |
| `idGroup` | integer |  | Id Group |
| `isNoHierarchy` | boolean, nullable |  | No hierarchy |
| `assignedBy` | string |  | Create user profile by |
| `idPolicy` | integer |  | Id Policy |
| `tags` | array, nullable |  | Tags to which a user belongs |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "idGroup": 0,
      "isNoHierarchy": false,
      "idPolicy": 0,
      "tags": [
        {
          "idTags": 0
        }
      ]
    }
    ```

### Model: UserTwoFactorAuth { #model-usertwofactorauth }

??? note "Fields (6 fields)"

    | Field | Type | Required | Description |
    |---|---|---|---|
    | `idUser` | string |  | Console user identifier |
    | `twoFactorEnabled` | boolean |  | Whether the user has a stored TOTP secret |
    | `consoleTwoFactorEnabled` | boolean |  | Whether two-factor authentication is enabled in the console |
    | `changed` | boolean, nullable |  | Whether the operation changed the stored state |
    | `secret` | string, nullable |  | New TOTP secret. Only present in the reset response. |
    | `provisioningUri` | string, nullable |  | otpauth provisioning URI. Only present in the reset response. |


### Model: UserTwoFactorAuthAction { #model-usertwofactorauthaction }

| Field | Type | Required | Description |
|---|---|---|---|
| `reason` | string, nullable |  | Optional reason stored in the audit log |

??? example "Example generated from the schema (placeholder values)"

    ```json
    {
      "reason": "string"
    }
    ```
