# Scripting and testing

Tests confirm that your API is working as expected. You can also use test code to aid the debugging process when something goes wrong with your API project.

You can add JavaScript code to execute during two events in the flow:

- Before a request is sent to the server, as a **pre-request script** under the Pre-request Script tab.
- After a response is received, as a **test script** under the Tests tab.

More appropriate to name it **pre-request** and **post-request with tests**.

You will carry out most of the Postman JavaScript API functionality using `pm.*`, which provides access to request and response data, and variables.

## Execution order

In Postman, the script execution order for a single request looks like this:

![execution-order-request](/images/req-resp.png)

For every request in a collection, scripts will execute in the following order:

![execution-order-scripts](/images/execOrder.png)

According to schemas for collections with multiple requests scripts are executed next way:

1st request:

1. collection pre-request script
2. folder pre-request script
3. *request one* pre-request
4. *request one*
5. *response one*
6. collection test script
7. folder test script
8. *request one* test script
9. collection pre-request script
10. folder pre-request script
11. *request two* pre-request
12. *request two*
13. *response two*
14. collection test script
15. ...

## Variables in scripts

### Defining variables in scripts

You can `.set` variables programmatically in your request scripts.

| Method | Use-case | Example |
| ------ | -------- | ------- |
| `pm.globals` | Use to define a global variable. | `pm.globals.set("variable_key", "variable_value");` |
| `pm.collectionVariables` | Use to define a collection variable. | `pm.collectionVariables.set("variable_key", "variable_value");` |
| `pm.environment` | Use to define an environment variable in the currently selected environment. | `pm.environment.set("variable_key", "variable_value");` |
| data variables | Can only be set from a CSV or a JSON file. |
| `pm.variables` | Use to define a local variable. | `pm.variables.set("variable_key", "variable_value");` |
| `unset` | You can use unset to remove a variable. | `pm.environment.unset("variable_key");` |
| `replaceIn` | To use dynamic variables in pre-request or test scripts | `pm.variables.replaceIn('{{$randomFirstName}}')` |

### Accessing variables

You can retrieve the current value of a variable in your scripts using the object representing the scope level and the `.get` method:

| Use-case | Example |
| -------- | ------- |
| global variable | `pm.globals.get("variable_key");` |
| collection variable | `pm.collectionVariables.get("variable_key");` |
| environment variable | `pm.environment.get("variable_key");` |
| data variables | `pm.iterationData.get('myVariable);` |
| at any scope including local. ([variable scope hierarchy])(/4_environments_and_var_scopes.md#variable-scope-hierarchy) | `pm.variables.get("variable_key");` |

Also before accessing you can check if variable exists with `.has` function:

``` js
pm.variables.has(variableName:String):function → Boolean
```

Or get all available as object containing all variables with their values in the current scope. Based on the order of precedence, this will contain variables from multiple scopes.

``` js
pm.variables.toObject():function → Object
```

## Request and response objects

A variety of methods provide access to request and response data in Postman scripts, including `pm.request`, `pm.response`, `pm.info`, and `pm.cookies`. Additionally you can send requests using `pm.sendRequest`.

- [Request](https://learning.postman.com/docs/writing-scripts/script-references/postman-sandbox-api-reference/#scripting-with-request-data)
- [Response](https://learning.postman.com/docs/writing-scripts/script-references/postman-sandbox-api-reference/#scripting-with-response-data)
- [Request info](https://learning.postman.com/docs/writing-scripts/script-references/postman-sandbox-api-reference/#scripting-with-request-info)
- [Cookies](https://learning.postman.com/docs/writing-scripts/script-references/postman-sandbox-api-reference/#scripting-with-request-cookies)
- [Sending requests from scripts](https://learning.postman.com/docs/writing-scripts/script-references/postman-sandbox-api-reference/#sending-requests-from-scripts) - This allows you to execute logic in the background if you are carrying out computation or sending multiple requests at the same time without waiting for each to complete. *(Remember that this requests are asynchronous and could be executed not in the order you defined)*

## Order of requests in collection

Typically when you start a collection run, Postman runs all requests in the same order they appear in your collection. Requests in folders are executed first, followed by any requests in the root of the collection.

In the Collection Runner, you have the option to change the order of the requests before starting a run. However, instead of manually changing the request order each time you run the collection, you can automate this behavior using the `postman.setNextRequest()` function.

- Run the specified request after this one (the request name as defined in the collection, for example "Get customers"):

``` js
postman.setNextRequest(requestName:String):Function
```

Run the specified request after this one (the request ID returned by `pm.info.requestId`):

``` js
postman.setNextRequest(requestId:String):Function
```
