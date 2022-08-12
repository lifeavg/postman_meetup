# General UI description

![general-overview](/images/navigating-postman-app-overview-v9.24.jpg)

All you need to make a request is:

1. Add new tab in *Workbench*
2. Input URL
3. Choose HTTP method and add *Body* or *Params* if required
4. Click *Send* button

Let's explore Postman section by section. I'll tel about most useful parts and the rest you can find in official Postman documentation.

## Header

Here you can login to your Postman account. Manage *Workspaces* and *Search* in your Postman data.

If you logged into Postman account all your data will be synced with remote Postman cloud.

> Some organizations have security guidelines that prevent team members from syncing data to the Postman cloud. In this situation, you can use Postman without an account and manually back up your data locally.

> You can delete data that's already synced to Postman by [deleting your account](https://learning.postman.com/docs/getting-started/postman-account/#deleting-your-account). Note that you must [leave all Postman teams](https://learning.postman.com/docs/collaborating-in-postman/working-with-your-team/collaboration-overview/#leaving-a-team) that you're a member of prior to deleting your account.

At first if you have no security requirements it's recommended to create Postman account and use cloud synchronization.

### General settings

![settings](/images/settings-detail-v8-9.jpg)

- **SSL certificate verification** - *Useful in some cases when tested host has problems with certificate.* Turn this off to prevent Postman from checking the validity of SSL certificates when making requests.
- **Send Postman Token header** - *Disable if you need only requeued by test set of HTTP headers.* (Recommended) Turn this on to send a random Postman token with an XMLHttpRequest. Sending a random token ensures the receiving server handles one request at a time, even when the requests send with the same parameters. The token can also aid debugging and help you distinguish between requests on the server side.
- **Automatically follow redirects** - Turn this off to prevent requests that return a 3xx series response from automatically redirecting.
- **Working directory** When you send a form-data or binary file with a request body, Postman saves a path to the file as part of the collection. The file path is relative to your working directory. Postman uses `~/Postman/files` as the default working directory. To use a different working directory, select *Choose* and then select the directory you want to use.
![working directory](/images/working-directory-web-v8-9.jpg)
- **Data** - *It's recommended to make backup from time to time* Use the Data tab to request a bulk export of Postman data or to import data. To begin the export process, select Export Data. You can choose to export your collections, environments, or both. You'll receive an email when your dump file is ready to download.

### Workspaces

Postman workspaces enable you to organize and work together on API projects. Within each workspace you can share APIs, collections, environments, and other Postman elements.

![workspaces](/images/workspace-switcher-v9.1.jpg)

Use separate *Workspace* at least for each project you work with.

When you first open Postman, you will be in your default personal workspace. You can create more workspaces for your personal use and to work with teammates. 

> Never ever use **Public** *Workspace* unless you are working with *open source* (even then better think twice).

## Footer

### Sync state

- **Offline** means that you aren't connected to the Postman servers. This may mean that your computer isn't connected to the internet.
- **Online** means that you're connected to the Postman servers and your work is either in the process of syncing or is already synced.
- **Error** means there was a syncing error while connecting to Postman. Hover over the sync state icon to see detailed information on the error.

![sync-state](/images/syncing-understanding-sync-states-v9.19.jpg)

### Console

Every request sent by Postman is logged in the console, so you can view the detail of what happened when you sent a request. This means you can use the Postman Console to help debug your requests when an API isn't behaving as you expect. Keeping the console open while you work will increase the visibility of your network calls and log messages while debugging.

![console](/images/console-pane-button.jpg)

### Cookie manager

A computer cookie is more formally known as an HTTP cookie, a web cookie, an Internet cookie, or a browser cookie. The name is a shorter version of “magic cookie,” which is a term for a packet of data that a computer receives and then sends back without changing or altering it.

A cookie typically contains two pieces of data: a unique ID for each user and a site name. Cookies enable websites to retrieve this information when you revisit them, so that they can remember you and your preferences and tailor page content for you based on this information.

![cookie-manager](/images/cookie-trash.png)

Postman's cookie manager enables you to view and edit cookies that are associated with different domains.

## Left sidebar

- **Collections** - *Usually used as one collection per service or test case.* Group your requests and examples to keep your workspace organized, to generate API documentation and API tests, and to automate request runs. *Also you can create subfolders in collection to organize requests.*
- **API** - *Useful for testing multiple versions of API and automatically generating collections from API schema.* Connect various elements of your API development and testing process to your schema, such as collections, documentation, tests, mocks, and monitors. Version APIs in and connect elements to specific versions and releases. Sync API with a remote Git repo.
- **Environments** - An environment is a set of variables (or config values) you can use in your requests. Use environments to group related sets of values together. *Use it as it named and create separate environments for 'prod', 'master', 'test-pr-nnn' e.t.c.*
- **Mock servers** - Make requests that return mock data if you do not have a production API ready, or you do not want to run your requests against real data yet. By adding a mock server to your collection and adding examples to your requests, you can simulate the behavior of a real API.
- **Monitors** - Give you continuous visibility into the health and performance of your APIs. *Almost useless for complex projects with existing automated tests.*
- **Flows** - A visual tool to create API workflows. Chain requests, handle data and create real world workflows right in your Postman workspace. *UI builder to run multiple requests one by one with some logic like which request should be run depending on response of previous.*
- **History** - Simly history of collections, requests e.t.c. you've run.

## Right sidebar

Contains Documentation (use for some notes about request/collection), Comments, Code snippets (example: `curl`), Details for Request/Collection, Folder.
