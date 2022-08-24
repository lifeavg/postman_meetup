# Useful tricks

Some collections with examples of useful scripts

## Switching HTTP/HTTPS

First check URL of requests and collection variables.

Then try `NoProtocol` request and check *console*

Url is: `http://example.com/`

Then try `VarProtocol` request with empty `protocol` variable and then set it to `https://`

[Example collection](/collections/HTTP-S.postman_collection.json)

## Environment protection

The case is when you want to protect some environments from destructive requests.

Check pre-request scripts in collection requests and global variables.

Then try requests with `PROD` environment and any other.

[Collection](/collections/AccessValidation.postman_collection.json)
[Environment](/collections/PROD.postman_environment.json)
[Globals](/collections/workspace.postman_globals.json)

## Cookie change

Check pre-request script

[Collection](/collections/ChangeCookie.postman_collection.json)

## Request iteration

Inspect scripts in requests and use collection runner, selecting only one request to run.

[Collection](/collections/IterateinRun.postman_collection.json)

![collection-runner](/images/collection-runner.jpg)

## HTML response parsing

Check *Tests* script.

[Collection](/collections/ParseHtmlResponse.postman_collection.json)

## [Many other examples by Postman team](https://www.postman.com/postman/workspace/postman-answers/request/3407886-06011115-e3cf-4711-926c-55a417d530f1)