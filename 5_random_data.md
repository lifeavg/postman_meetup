# Random data with dynamic variables

Postman uses the [faker library](https://www.npmjs.com/package/@faker-js/faker) to generate sample data, including random names, addresses, email addresses, and much more. You can use these pre-defined variables multiple times to return different values per request.

You can *use* these variables *like any other variable in Postman.* Their values are *generated at the time of execution* and their names start with a $ symbol, for example `$guid` or `$timestamp`.

[Complete list](https://learning.postman.com/docs/writing-scripts/script-references/variables-list/) in Postman official guide.

![random-variable](/images/random-var.png)
