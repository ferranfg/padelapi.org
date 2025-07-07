## About the Padel API

Learn how to access, authenticate with, and use the [Padel API](https://en.fantasypadeltour.com/docs) by **Fantasy Padel Tour**.

### Authentication

The **Padel API** uses API tokens to authenticate requests. These are provided to you on your [API Tokens](https://en.fantasypadeltour.com/user/api-tokens) management page.

To authenticate, you need to include an `Authorization` header in all of your requests. In this header, you must state that you're using an API token (similar to [HTTP basic access authentication](https://en.wikipedia.org/wiki/Basic_access_authentication)).

For example:

```curl
curl -i -X GET \
  'https://fantasypadeltour.com/api/seasons' \
  -H 'Authorization: Bearer YOUR_API_TOKEN_HERE'
```

Either if the API key isn't valid, or you don't provide an `Authorization` header at all, you'll receive a `401` status code as response

### Pagination

Several endpoints return paginated results.

By default, the **Padel API** only returns the first 15 results for those endpoints. You can use optional query parameters to increase or decrease the number of results.

| Parameter  | Description                                        |
|------------|----------------------------------------------------|
| `per_page` | Number of results to return per page (default: 15) |
| `page`     | Page number to retrieve                            |

### Status Codes

The **Padel API** uses conventional [HTTP response codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) to indicate whether a request was successful (`2XX` codes) or resulted in an error (`4XX` and `5XX` codes).