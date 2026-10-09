---
title: Installation
editLink: true
---

# Installation
<!-- 
**Mall** can be found on the official [Winter CMS Marketplace](https://wintercms.com/plugin/offline-mall). 



## Using Marketplace

The easiest way to install **Mall** is via the official Marketplace. There you can add the plugin to 
your project and install it by executing the following artisan command in the root directory of your 
website:

```sh
php artisan project:sync
```

During this installation, all dependencies are downloaded and installed automatically.
-->

## Manual Installation
<!-- 
You can install **Mall** also manually like any other WinterCMS plugin. However, make sure that you 
install the dependencies up-front. Visit the root directory of your WinterCMS website and execute 
the following commands

```sh
php artisan plugin:install Winter.User
php artisan plugin:install Winter.Location
php artisan plugin:install Winter.Translate
php artisan plugin:install Winter.Mall
```

You can also use composer to install the plugins, however, keep in mind that you've to install 
and migrate the dependent packages first before installing and migrating Mall itself.
-->
You can use composer to install the plugins, however, keep in mind that you've to install 
and migrate the dependent packages first before installing and migrating Mall itself.

```sh
composer require winter/user-plugin
composer require winter/location-plugin
composer require winter/translate-plugin
```

```sh
php artisan migrate
```

```sh
composer require winter/wn-mall-plugin
```

```sh
php artisan migrate
```
<!-- 
Both ways will automatically install all composer packages required by the **Mall** plugin, at least 
on WinterCMS v3 installations. 
-->


## Optional Dependencies

Certain features of the **Mall** plugin requires you to install additional composer packages to 
make everything work. 

| Feature                      | Package |
| ---------------------------- | ------- |
| File-Based Index             | [`offline/jsonq`](https://packagist.org/packages/offline/jsonq)<br />[`tmarois/filebase`](https://packagist.org/packages/tmarois/filebase) |
| Google Merchant Feed         | [`vitalybaev/google-merchant-feed`](https://packagist.org/packages/vitalybaev/google-merchant-feed) |
| PostFinance Payment Provider | [`bummzack/omnipay-postfinance`](https://packagist.org/packages/bummzack/omnipay-postfinance) |


Simple use the following command in the root directory of your WinterCMS website to install the 
desired package.

```sh
composer require <$package_name>
```

## Check your Installation

After you successfully installed all plugins and packages, you can run the `mall:check` artisan 
command to validate your installation. 

**Don't panic!** After the initial installation there will be some items that are marked as FAIL. 
This is because we didn't configure the plugin yet.

```sh
php artisan mall:check
```

::: tip
You can run this command at any time in the future to make sure everything is set up correctly.
:::


## Seed initial data

Since version 3.1, **Mall** no longer inserts any data automatically during the installation. You 
can use the following command to seed the initial data, as happened before.

```sh
php artisan plugin:seed Winter.Mall Winter\Mall\Updates\Seeders\MallSeeder
```

However, we **highly recommend** using the following command instead, which allows you to customize 
the desired data.

```sh
php artisan mall:seed --help
```

::: danger
Please note that this command **deletes** all existing store data and resets all setting. You should 
therefore not run this command on an already configured installations.
:::

You can also simple reset the whole **Mall** installation by running the following command.

```sh
php artisan plugin:refresh Winter.Mall
```


## Setup Demo-Theme

We also provide a simple demonstration theme to make getting started with our **Mall** plugin as 
easy as possible. 
<!-- 
You can find this theme on the official [Winter CMS Marketplace](https://wintercms.com/theme/offline-oc-mall-theme) 
as well as on [GitHub](https://github.com/wintercms/wn-mall-theme).

To install the theme, make sure you've installed the dependent packages first

```sh
php artisan plugin:install Winter.Pages
php artisan plugin:install OFFLINE.SiteSearch
```

After that, you can download and extract the theme inside the `themes/mall` folder of your 
WinterCMS website and select it as your active theme.
-->
