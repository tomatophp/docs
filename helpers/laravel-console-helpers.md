---
description: tons of helper you need for you artisan command line application
---

# 🍕 Laravel Console Helpers

<figure><img src="../.gitbook/assets/screenshot (1).png" alt=""><figcaption></figcaption></figure>

## Installation

```bash
composer require tomatophp/console-helpers
```

## Usage

we have Traits that you can use in your artisan command class

### Run PHP Command

you can run direct php command like this

```php
use TomatoPHP\ConsoleHelpers\Traits\RunCommand;

class MyCommand extends Command{
    use RunCommand;
}
```

```php
$this->phpCommand('echo "welcome";');
```

### Run Yarn Command

you can run direct yarn commands like this

```php
use TomatoPHP\ConsoleHelpers\Traits\RunCommand;

class MyCommand extends Command{
    use RunCommand;
}
```

```php
$this->yarnCommand('echo "welcome";');
```

**NOTE**

you can update the yarn path from the config file.

### Run Artisan Command

you can direct run the artisan command by using this method

```php
use TomatoPHP\ConsoleHelpers\Traits\RunCommand;

class MyCommand extends Command{
    use RunCommand;
}
```

```php
$this->artisanCommand('migrate');
```

### Handle Stubs File Template

you can handle stubs file templates and copy change or add new data by using this method

```php
use TomatoPHP\ConsoleHelpers\Traits\HandleStubs;

class MyCommand extends Command{
    use HandleStubs;
}
```

```php
$this->generateStubs(
    __DIR__ . "/stubs/SettingsClass.stub",
    "Modules/Base/Settings/MainSettings.php",
    [
        "settingName" => "site_url",
        "moduleName" => "Base",
        "settingField" => Str::lower("site_url")
    ],
    [
        "Modules/Base/Settings/"
    ]
);
```

### Handel Modules Actions

this command is working with [laravel-modules](https://nwidart.com/laravel-modules/v6/introduction) you can activate all modules or stop all modules or actively selected modules by this method

```php
use TomatoPHP\ConsoleHelpers\Traits\HandleModules;

class MyCommand extends Command{
    use HandleModules;
}
```

```php
$this->activeAllModules();
```

```php
$this->stopAllModules();
```

this method takes 2 parameters first is the module name and the second is the active/stop bool by default is true

```php
$this->activeModule("Base");
```

## Changelog

Please see [CHANGELOG](https://github.com/tomatophp/console-helpers/blob/master/CHANGELOG.md) for more information on what has changed recently.

## Credits

* [Fady Mondy](https://github.com/3x1io)

## License

The MIT License (MIT). Please see [License File](https://github.com/tomatophp/console-helpers/blob/master/LICENSE.md) for more information.
