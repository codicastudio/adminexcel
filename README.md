![banner-nova](https://user-images.githubusercontent.com/7728097/57463952-16783a80-727c-11e9-87f7-94aae5284bfc.jpg)



<h3 align="center">Supercharge your Laravel Nova resource exports</h3>

<h4 align="center">
  <a href="https://docs.laravel-excel.com/nova/1.1/getting-started/">Quickstart</a>
  <span> · </span>
  <a href="https://docs.laravel-excel.com/nova/1.1/">Documentation</a>
  <span> · </span>
  <a href="https://docs.laravel-excel.com/blog/">Blog</a>
  <span> · </span>
  <a href="https://docs.laravel-excel.com/3.1/getting-started/contributing.html">Contributing</a>
  <span> · </span>
  <a href="https://docs.laravel-excel.com/3.1/getting-started/support.html">Support</a>
</h4>

## ✨ Features

- **Easily export resources to Excel.** Supercharge your Nova resources and export them directly to an Excel or CSV document. Exporting has never been so easy.

- **Supercharged resource exports.** Export resources with automatic chunking for better performance. You provide us the query, we handle the performance. Exporting even larger resources? No worries, Laravel Nova Excel has your back. You can queue your exports so all of this happens in the background.

- **Export based on filters and selection.** Select or filter only certain resources and export only those to Excel!

- **Export lenses.** Got custom lenses defined? When exporting from a lens, it will use the query of the lens to determine which data needs to be exported!

## :rocket: 5 minutes quick start

:bulb: Require this package in the `composer.json` of your Laravel project. This will download the package and Laravel-Excel.

```
composer require maatwebsite/laravel-nova-excel
```

:muscle: Go to your resource. As example we'll use the `app/Nova/User.php`. Add `DownloadExcel` action to your `actions()` list.

```php
<?php

namespace App\Nova;

use Illuminate\Http\Request;
use Maatwebsite\LaravelNovaExcel\Actions\DownloadExcel;

class User extends Resource
{
    /**
     * The model the resource corresponds to.
     *
     * @var string
     */
    public static $model = 'App\\User';
    
    // Other default resource methods
    
    /**
     * Get the actions available for the resource.
     *
     * @param  \Illuminate\Http\Request $request
     *
     * @return array
     */
    public function actions(Request $request)
    {
        return [
            new DownloadExcel,
        ];
    }
}
```
