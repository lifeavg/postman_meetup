# Making requests

- Each request could be opened in a new tab.
- Each request could be saved into collection.

Let's explore request configuration step by step.

![request](/images/first-request-sent-v9-4.jpg)

## Method and URL

At least to make a request you need to choose `HTTP method` from the dropdown list of standard methods or *just put cursor on method name and input any method name you need*.

![custom-method](/images/custom-method.png)

Next input resource URL (`http://test.domain`) and click *Send* button.

To save your request for later use just click *Save* button, choose name (you could change it later by right click), and chose an existing collection or create a new one.
Later you could move requests between collections just by *drag and drop* request from one collection to another.

If you click dropdown menu od *Send* button you can download response data and save it on your PC.

![save-download](/images/send-download.png)

> *For HTTP requests* don't add `http://` to requests, Postman will add `http` protocol automatically. Add protocol only if you need `https://` *(Further in 'Variables' section will be explained how to use 'host' variable to change protocol in one place for entire collection)*

## Request parameters

You can send path and query parameters with your requests using the URL field and the Params tab.

Query parameters are appended to the end of the request URL, following `?` and listed in key value pairs, separated by `&` using the following syntax: `?id=1&type=new`

Path parameters form part of the request URL, and are referenced using placeholders preceded by `:` as in the following example: `/customer/:id`

![request-parameters](/images/request-parameters.png)

URL from screenshot will be generated to: `https://www.google.com/search?q=searchby`

You can use the *Bulk Edit* option if you prefer to enter your parameters in plain text instead of using the request builder.

![bulk-edit](/images/bulk-edit.png)

## Authorization

Some APIs require auth details. Authentication involves confirming the identity of the client sending a request, and authorization involves confirming that the client has permission to carry out the endpoint operation. Open the Authorization tab to configure your access details.

Postman will automatically include your auth details in the relevant part of the request, for example in Headers.

![authorization](/images/aythorization.png)

Just choose one you need and follow the instructions.

For more detail on implementing different types of auth in your Postman requests, check out [Authorizing requests](https://learning.postman.com/docs/sending-requests/requests/).

*In case you have not found any required one `API Key` usually saves situation. You can manually input key name and value, and choose the place where Postman will add your credentials.*

![api-key](/images/api-key.png)

## Headers

Some APIs require you to send particular headers along with requests, typically to provide additional metadata about the operation you are performing. You can set these up in the Headers tab. Enter any key-value pairs you need and Postman will send them along with your request. As you enter text, Postman prompts you with common options you can use to autocomplete your setup, such as Content-Type.

![headers](/images/presets-v9.jpg)

You can save commonly used headers together in a header preset. In the *Headers* tab, select *Presets*, and choose *Manage Presets*. Add each preset by providing a name, and entering the key plus value. Select *Add* and your preset will be available in the *Presets dropdown list*. Selecting the preset will autopopulate the fields in your request headers.

**Autogenerated headers**: Postman will automatically add certain headers to your requests based on your request selections and settings. Select hidden at the top of the headers tab for information about what Postman will send with your request.

> Please, DON'T ADD `AUTHORIZATION`, `COOKIES` or anything else *you have special tab/option for* manually to headers or request parameters, or anywhere else. Except you know what you're doing.

## Body data

The Body tab in Postman allows you to specify the data you need to send with a request. You can send various different types of body data to suit your API.

You will need to send body data with requests whenever you need to add or update structured data. For example, if you're sending a request to add a new customer to a database, you might include the customer details in `JSON`. Typically you will use body data with `PUT`, `POST`, and `PATCH` requests.

*By default*, Postman will select **None** — leave it selected if you don't need to send a body with your request.

![body-data](/images/form-data-v9.jpg)

### Form data

Website forms often send data to APIs as `multipart/form-data`. You can replicate this in Postman using the `form-data` *Body* tab. Form data allows you to send key-value pairs, and specify the content type.

> Remember to save files to current `Working directory`.

### URL-encoded

URL-encoded data uses the same encoding as URL parameters. If your API requires url-encoded data, select `x-www-form-urlencoded` in the *Body* tab of your request. Enter your key-value pairs to send with the request and Postman will encode them before sending.

### Raw data

You can use `raw` body data to send anything you can enter as text. Use the `raw` tab, and the type dropdown list to indicate the format of your data (`Text`, `JavaScript`, `JSON`, `HTML`, or `XML`) and Postman will enable syntax-highlighting as well as appending the relevant headers to your request.

> You can set a content type header manually if you need to override the one Postman sends automatically.

> To beautify your XML or JSON, select the text in the editor and then select ⌘+Option+B or Ctrl+Alt+B or click Button un top right corner of input area.

### Binary data

You can use `binary` data to send information you can't enter manually in the Postman editor with your request body, such as image, audio, and video files (you can also send text files).

> Remember to save files to current `Working directory`.

### GraphQL

You can send *GraphQL* queries with your Postman requests by selecting the `GraphQL` tab in the request *Body*. Enter your code in the `Query` area and any variables in the `GraphQL Variables` section.

Check out [Using GraphQL](https://learning.postman.com/docs/sending-requests/graphql/graphql/) for more information on GraphQL, including how to enable Autocomplete powered by Postman API schemas.

## Request Settings

You can configure a variety of settings for Postman requests using the request Settings tab. These allow you to apply non-standard logic to your requests.

Most useful are:

- **Automatically follow redirects** (ON by default)
- **Encode URL automatically** (ON by default) - Postman parses and encodes your request URL to maximize the chances of a successful API call. Postman encodes the characters in your URL and maps them to a representation that your API is most likely to accept. The Postman URL processor optimizes the chance of your request being effectively processed by the wide range of server implementations in use.

    > The processor is turned on by default in Postman, but you can turn off encoding if you are working with an unusual server implementation. 

- **Disable cookie jar** - to disable using cookies for particular request

## Cookies

Postman's *cookie manager* enables you to view and edit cookies that are associated with different *domains*. You can manually create cookies for a domain, or you can [capture cookies](https://learning.postman.com/docs/sending-requests/capturing-request-data/syncing-cookies/) using the *Postman proxy* or *Postman Interceptor*. You can then use the cookies stored in the cookie jar when sending requests in Postman.

![cookies](/images/cookies-link.jpg)

### Creating cookies

To add a new cookie for a domain, select *+ Add Cookie*. A pre-generated cookie string compliant with [HTTP State Management](https://datatracker.ietf.org/doc/html/rfc6265#section-4.1) standards is created.

```csv
<cookieName>=<cookieValue>; path=/; domain=.domain.com; HttpOnly; Secure; Expires=Tue, 19 Jan 2038 03:14:07 GMT;
```

Postman supports the following attributes:

- **cookieName**, **cookieValue** - The name of the cookie and the value stored in it.
- **Domain** - The domain Postman will send the cookie to.
- **Path** - The URL path that the cookie is restricted to. If the path is /, the cookie will be sent to all requests in the specified domain.
- **HttpOnly** - If present, the cookie won't be accessible to the client-side scripts run on the page (for example, with document.cookie in JavaScript). The cookie will only be added to the cookie header in requests that are made. This field doesn't have an effect on Postman's behavior.
- **Secure** - If present, the cookie is only sent when the URL begins with https:// and won't be sent over an insecure connection.
- **Expires** - The time after which the cookie will expire and not be sent by Postman.

## Responses

The Postman *Body* tab gives you several tools to help you understand the response quickly. You can view the body in one of four views: *Pretty*, *Raw*, *Preview*, and *Visualize*.

> Finding items in responses - To open the search bar, select the search icon Search icon in the results pane. You can also place your cursor in the response and select ⌘+F or Ctrl+F. This option isn't available in a response's Preview or Visualize views.

Note that if the response's Content-Type header indicates that the response is an image, Postman will detect and render the image automatically.

![response](/images/response-pretty-view.jpg)

> Forcing `JSON` formatting. For Postman to automatically format the body, the response must have the appropriate `Content-Type` header. If you receive a response with a different `Content-Type` header, you can force formatting through `JSON`. In the Postman header, select the settings icon *Settings* icon , then select *Settings*. In the *General* tab, select `JSON` from the Language detection dropdown.

- **Response code** - Postman displays the response code returned by the API. Hover over the response code to get a short description of the code and what it means.
- **Response time** - Postman automatically calculates the time in milliseconds it took for the response to arrive from the server. This information can be useful for some preliminary performance testing. Hover over the response time for a graph with information on how long each event in the process took.

### Network information

Postman displays network information when your API returns a response. Hover over the network icon Network information icon to get the local and remote IP addresses for the request you sent.

When you make an https request, the network icon includes a padlock. When you hover over the icon, the network information will show additional information including certificate verification details.

![network-information](/images/https-network-info-response.jpg)