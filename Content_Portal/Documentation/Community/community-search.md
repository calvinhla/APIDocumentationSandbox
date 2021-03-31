---
title: Community/community-search v20210330.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Community Search
Defines the public API endpoints that are used to search communities. A community provides a way to share information, such as data streams, between customers.

## Search Streams2

<a id="opIdCommunitySearch_Search Streams2"></a>

Searches for streams within a community by query.

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/communities/{communityId}/search/streams
?query={query}&maxNamespaceResults={maxNamespaceResults}&maxTotalResults={maxTotalResults}
```

#### Parameters

`string tenantId`
<br/>The id of the owning tenant.<br/><br/>`string communityId`
<br/>The id of the community.<br/><br/>
`[optional] string query`
<br/>The query. This is in the same format as used by SDS. See<br/><br/>`[optional] integer maxNamespaceResults`
<br/>The maximum namespace results.<br/><br/>`[optional] integer maxTotalResults`
<br/>The maximum total results.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Returns the stream information that matches the search criteria. This is a set of objects of type `StreamSearchResult`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|None|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

#### Example response body
> 400 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Account Administrator</li>
<li>Community Administrator</li>
<li>Community Member</li>
<li>Community Moderator</li>
</ul>

---

## Search Streams

<a id="opIdCommunitySearch_Search Streams"></a>

Searches for streams within a community by query.

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/search/communities/{communityId}/streams
?query={query}&maxNamespaceResults={maxNamespaceResults}&maxTotalResults={maxTotalResults}
```

#### Parameters

`string tenantId`
<br/>The id of the owning tenant.<br/><br/>`string communityId`
<br/>The id of the community.<br/><br/>
`[optional] string query`
<br/>The query. This is in the same format as used by SDS. See<br/><br/>`[optional] integer maxNamespaceResults`
<br/>The maximum namespace results.<br/><br/>`[optional] integer maxTotalResults`
<br/>The maximum total results.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Returns the stream information that matches the search criteria. This is a set of objects of type `StreamSearchResult`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|None|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

#### Example response body
> 400 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Account Administrator</li>
<li>Community Administrator</li>
<li>Community Member</li>
<li>Community Moderator</li>
</ul>

---
# Definitions

## ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|Gets or sets Operation Id of action that caused the Error.|
|Error|string|false|true|Gets or sets the Error description.|
|Reason|string|false|true|Gets or sets the Reason for the Error.|
|Resolution|string|false|true|Gets or set the Resolution for the Error.|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string"
}

```

---

