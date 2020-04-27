# Okta Workflows

This repo is a collection of flowpacks exported from Okta Workflows. 

## oktaGetForCapiaWithPagination.flopack

This flowpack supports pagination for the `Okta - Custom API Action` card by parsing the Link header from the Okta API's response headers.

`[Okta] custom GET with pagination` is a recursive flow, so you will need to replace the dummy call to `[export placeholder]` and wire up the `Flow Control - Call Flow` card.

Inputs to `[Okta] custom GET with pagination`:
- **maxPages**: maximum number of "pages" to request from the API. This can be helpful in throttling your requests.
- **relativeUrl**: this is the relative url for the Okta API endpoint you are calling. It can include request parameters for search, filtering, etc.
- **pageNumber**: this is the page number of the current iteration. *Do not use this*. This value is passed in to the flow during the recursive call.
- **items**: this is the cumulative list of response items from the API call up to the current page. *Do not use this*. This value is passed into the flow during the recursive call. 