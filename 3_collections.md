# Collections

There are several ways to create a new collection:

- Select **Collections** in the sidebar, then select **+**.
![new-collection](/images/new-collection.jpg)
- Select **New**, then select **Collection**.
- Select **Home** in the Postman header. Select **Create New**, then select **Collection**.

Once you have created a new collection, you can customize and configure it:

> **Pre-request Script**, **Variables** and **Tests** are described later in separate chapters.

- Select the edit icon Edit icon to give your new collection a name.
- You can optionally specify a description for your collection. Select the documentation icon Documentation icon , then select the edit icon Edit icon to write your description. This description will appear in its documentation and in the workspace when anyone opens it.
- Select **Authorization** to configure authorization details for the collection.
- Select **Pre-request Script** to define a pre-request script for your collection, which will run before requests are sent to the server.
- Select **Tests** to define a test script for your collection, which will run after a response is received.
- Select **Variables** to define values for collection variables to share across all requests in the collection.
- [Adding requests to a collection](https://learning.postman.com/docs/sending-requests/intro-to-collections/#adding-requests-to-a-collection)
- Adding folders to a collection: *(You can also add sub-folders to create extra levels of nesting for the collection's requests and examples.)*

  1. Select the *More actions icon* next to the collection name or right click the collection.
  2. Select **Add folder**.

> Each folder and subfolder also has **Authorization**, **Pre-request Script** and **Tests** tabs, so you can group requests py this parameters.

![collection-details](/images/collection-details.jpg)

As if you have **Authorization** settings for entire collection it's good to group requests to same APIs with same credentials in one collection and set **Authorization** settings for entire collection or folder. Then just select option **Inherit auth from parent** (usually default) in **Authorization** tab of each separate request.

> By now you might think that it's good idea to store two copies of API in one collection and separate folders for *production* and *test* if you have different credentials - it's NOT. For this purposes we will use **Variables** and **Environments**.

To `Run` entire collection of requests one by one you can use [Collection Runner](https://learning.postman.com/docs/running-collections/intro-to-collection-runs/)

![collection-runner](/images/collection-runner.jpg)

## Collection from API

You can import an existing API schema into your API. API schemas can be imported from a local file or directory, a URL, raw text, a code repository, or an API gateway. And generate test collection from this schema.

To import your API specifications into Postman:

1. From the sidebar, select *APIs*, then select *Import*.

  ![import-api](/images/import-api.png)

2. On *Import* tab select file or paste a link to address field of file explorer window (on some systems cold be unavailable)
3. And follow next steps.

Or create/paste API definition schema:

1. From the sidebar, select *APIs*, then select *Import*.
2. On *Create* tab select *type* and *format* of API schema.
3. And follow next steps.
4. Then open *definition* tab.

  ![api-definition](/images/api-definition.png)

4. Paste/create API schema and *Save* it
5. Generate collection from the API

![save-api](/images/save-api.jpg)
