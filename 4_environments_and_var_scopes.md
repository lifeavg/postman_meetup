# Environments and variables

## Variables

**Variables** enable you to store and reuse values in Postman. By storing a value as a variable, you can reference it throughout your collections, environments, requests, and test scripts. **Variables** help you work efficiently, collaborate with teammates, and set up dynamic workflows.

A **variable** is a symbolic representation of data that enables you to access a value without having to enter it manually wherever you need it. This can be useful if you are using the same values in multiple places. **Variables** make your requests more flexible and readable, by abstracting the detail away.

For example, if you have the same URL in more than one request, but the URL might change later, you can store the URL in a variable base_url and reference it in your requests using `{{base_url}}`. If the URL changes, you can change the **variable** value and it will be reflected throughout your collection, wherever you've used the variable name.

Another example. How collection variables are rendered on request execution.

![variable-example](/images/var-exmpl.png)

In request we *use* this variables next way.

![request-variables](/images/request-variables.png)

On *Send* click request will be rendered to: `https://www.google.com/search?q=find%20it`

**Initial and Current values.** By default the current value will copy the initial value.

- The **Initial Value** is synced to your account using the Postman servers. It's shared with any collaborators who have access to the environment.
- The **Current Value** is used in your local instance of Postman, and is never synced to your account or shared with your team unless you choose to persist it (make *Initial*).

## Variable scopes

Postman supports variables at different scopes, allowing you to tailor your processing to a variety of development, testing, and collaboration tasks. Scopes in Postman relate to the different contexts that your requests run in, and different variable scopes are suited to different tasks.

In order from broadest to narrowest, these scopes are: global, collection, environment, data, and local.

- **Global variables** enable you to access data between *collections*, *requests*, test *scripts*, and *environments*. Global variables are available throughout a *workspace*. Since global variables have the broadest scope available in Postman, they're well-suited for testing and prototyping. In later development phases, use more specific scopes. *(Edit in the same place as environments.*
- **Collection variables** are available throughout the requests in a *collection* and are independent of environments. Collection variables don't change based on the selected *environment*. Collection variables are suitable if you're using a single environment, for example for auth or URL details. *(Store here variables you will use in this particular collection and only.)*
- **Environment variables** enable you to scope your work to different *environments*, for example *local development* versus *testing* or *production*. *One environment can be active at a time.* If you have a single environment, using collection variables can be more efficient, but environments enable you to specify role-based access levels. *(Great place for host names, access tokens, base path to service e.t.c.)*

> For now just remember that **Data variables**, **Local variables** are exist.

- **Data variables** come from external CSV and JSON files to define data sets you can use when running collections with Newman or the Collection Runner. Data variables have current values, which don't persist beyond request or collection runs.
- **Local variables** are temporary variables that are accessed in your *request scripts*. Local variable values are *scoped to a single request* or *collection run*, and are no longer available when the run is complete. Local variables are suitable if you need a value to override all other variable scopes but don't want the value to persist once execution has ended.

## Environment (/global)

Postman displays the active environment in the environment selector, located in the top right of the workbench.

You can access all environments from Environments in the sidebar.

To view environment/global variables:

1. Select Environments in the sidebar.
2. Select the environment you want to inspect variables for.

To add a new environment variable:

1. Select *Add* a new variable, and enter a name for the variable.
2. Select a *Type* for the new variable.

    > Use *Secret* type for credentials to prevent occasional account leaks on screenshots and video calls.

3. Add an *Initial Value*, and if you choose, a *Current Value*.
4. Select *Save* icon to confirm your changes.

Choose **Environment**: select required in top right corner dropdown list.

![choose-environment](/images/choose-environment.png)

## Variable scope hierarchy

Similar to working with variables in other programming languages, Postman resolves scopes according to a variable scope hierarchy. Using variables within specific scopes allows you to reuse values efficiently.

![variable-scope-hierarchy](/images/image1-2.webp)

So if you have variable with same name in different scopes first Postman will use value from `data` scope if it present there, then `local` and so on to `global`.

**Global variables** are commonly used to capture ephemeral states. C**ollection variables** are best for values that are meant to be reused within the current collection. **Environment variables** are frequently used across multiple server environments – like development, staging, and production. For example, an endpoint using the variable `{{url}}` could easily switch between a development  value of dev.`myapp.com` or a production value of `myapp.com`.
