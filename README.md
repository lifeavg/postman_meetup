# **Postman**

## Sources

- [Postman Learning Center](https://learning.postman.com/docs/getting-started/introduction/)
- [10 Tips for Working with Postman Variables](https://blog.postman.com/10-tips-for-working-with-postman-variables/)
- [Postman Cheatsheet](https://postman-quick-reference-guide.readthedocs.io/en/latest/cheatsheet.html)

## Introduction

Postman is an API platform for building and using APIs. Postman simplifies each step of the API lifecycle and streamlines collaboration so you can create better APIs—faster.

Postman enables you to create and send API requests. Send a request to an endpoint, retrieve data from a data source, or test an API's functionality. You don't need to enter commands in a terminal or write any code. Create a new request and select Send, and the API response appears right inside Postman.

This tutorial assumes you already know basics of [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP), [JS](https://developer.mozilla.org/en-US/docs/Web/JavaScript), and [how to install Postman app](https://learning.postman.com/docs/getting-started/installation-and-updates/).

## Contents

- [General UI description](/1_general_ui_description.md)
  - [Header](/1_general_ui_description.md#Header)
    - [General settings](/1_general_ui_description.md#general-settings)
    - [Workspaces](/1_general_ui_description.md#workspaces)
  - [Footer](/1_general_ui_description.md#footer)
    - [Sync state](/1_general_ui_description.md#sync-state)
    - [Console](/1_general_ui_description.md#console)
    - [Cookie manager](/1_general_ui_description.md#cookie-manager)
  - [Left sidebar](/1_general_ui_description.md#left-sidebar)
  - [Right sidebar](/1_general_ui_description.md#right-sidebar)
- [Single request - response](/2_request.md)
  - [Method and URL](/2_request.md#method-and-url)
  - [Request parameters](/2_request.md#request-parameters)
  - [Authorization](/2_request.md#authorization)
  - [Headers](/2_request.md#headers)
  - [Body data](/2_request.md#body-data)
    - [Form data](/2_request.md#form-data)
    - [URL-encoded](/2_request.md#form-data)
    - [Raw data](/2_request.md#raw-data)
    - [Binary data](/2_request.md#binary-data)
    - [GraphQL](/2_request.md#graphql)
  - [Request Settings](/2_request.md#request-settings)
  - [Cookies](/2_request.md#cookies)
    - [Creating cookies](/2_request.md#creating-cookies)
  - [Responses](/2_request.md#responses)
    - [Network information](/2_request.md#network-information)
    - [Save Response](/2_request.md#save-response)
- [Collections](/3_collections.md)
- [Environments and variables](/4_environments_and_var_scopes.md)
  - [Variables](/4_environments_and_var_scopes.md#variables)
  - [Variable scopes](/4_environments_and_var_scopes.md#variable-scopes)
  - [Environment (/global)](/4_environments_and_var_scopes.md#environment-global)
  - [Variable scope hierarchy](/4_environments_and_var_scopes.md#variable-scope-hierarchy)
- [Random data with dynamic variables](/5_random_data.md)
- [Scripting and testing](/6_scripting_testing.md)
  - [Execution order](/6_scripting_testing.md#execution-order)
  - [Variables in scripts](/6_scripting_testing.md#variables-in-scripts)
    - [Defining variables in scripts](/6_scripting_testing.md#defining-variables-in-scripts)
    - [Accessing variables](/6_scripting_testing.md#accessing-variables)
  - [Request and response objects](/6_scripting_testing.md#request-and-response-objects)
  - [Order of requests in collection](/6_scripting_testing.md#order-of-requests-in-collection)
  - [Writing tests](/6_scripting_testing.md#writing-tests)
    - [Formatting test result messages with `pm.expect`](/6_scripting_testing.md#formatting-test-result-messages-with-pmexpect)
  - [Troubleshooting](/6_scripting_testing.md#troubleshooting)
    - [Common issues](/6_scripting_testing.md#common-issues)
