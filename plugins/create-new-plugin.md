# 🏗️ Create New Plugin

from v1.2 you can create a new plugin by just using GUI it will generate a new module for you with a module.json file ready to use for our plugins system, and you can use our plugin generator feature to build a full migration and CRUD operation with GUI! without any code.

### Add Required Plugins

you can add required plugins to make the plugin active only if the other module is active you can do that by adding the `required` to `module.json` file like this

```json
{
    "required": ['EcommerceTheme']
}
```

