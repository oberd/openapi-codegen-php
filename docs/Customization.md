# Customization

## Customizing templates

The code and documentation are generated from jMustache templates available in `resources/dev/elastic-openapi-codegen-php/src/main/resources/elastic-php-client` :

Generated file   | Template file      | Description
---------------- | -------------------| ----------------------
`Client.php`     | `Client.mustache ` | The main client class.
`Endpoint/*.php` | `api.mustache `    | One generated class for each path/operation in the OpenAPI spec file.
`README.md`      | `README.mustache ` | A base skeleton for documentation. This templates include several others (`readme_faq.mustache`, `readme_usage.mustache`...) allowing to override only parts of it.

To override a template, copy it into the `resources/api/templates` directory of your project and apply modification on the copied files.


## Output Directory

To override the output directory, you can pass an absolute path as the first parameter to the build script. For example:

```bash
# Output to src directory
./vendor/bin/elastic-openapi-codegen.sh "$PWD/src"
```

Make sure you configure your composer.json accordingly!

```json
{
    ...
    "psr-4": {
        "Fancy\\Client\\" : "src/"
    }
}
```