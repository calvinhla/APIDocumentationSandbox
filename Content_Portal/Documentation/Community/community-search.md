---
title: Community/community-search v20210308.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="community-community-search-community-search">Community Search</h1>
Defines the public API endpoints that are used to search communities. A community provides a way to share information, such as data streams, between customers.

	

---
## Search Streams

<a id="opIdCommunitySearch_Search Streams"></a>

Searches for streams within a community by query.

### Request
```text 
GET /api/v1/tenants/{tenantId}/communities/{communityId}/search/streams
```

<h3 id="communitysearch_search-streams-parameters">Parameters</h3>

`string tenantId`<br/>The id of the owning tenant.<br/><br/>`string communityId`<br/>The id of the community.<br/><br/>
`[optional] string query`<br/>The query. This is in the same format as used by SDS. See<br/><br/>`[optional] integer maxNamespaceResults`<br/>The maximum namespace results.<br/><br/>`[optional] integer maxTotalResults`<br/>The maximum total results.<br/><br/>

<h3 id="communitysearch_search-streams-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Returns the stream information that matches the search criteria. This is a set of objects of type `StreamSearchResult`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|None|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

### Example response body
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

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Community Administrator</li>
<li>Community Member</li>
<li>Community Moderator</li>
</ul>

# Definitions

<h2 id="tocS_ErrorResponse">ErrorResponse</h2>

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|Gets or sets Operation Id of action that caused the Error.|
|Error|string|false|true|Gets or sets the Error description.|
|Reason|string|false|true|Gets or sets the Reason for the Error.|
|Resolution|string|false|true|Gets or set the Resolution for the Error.|

