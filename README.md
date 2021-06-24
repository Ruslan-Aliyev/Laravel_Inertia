# Inertia JS & Laravel

- https://inertiajs.com/
- https://www.infoq.com/news/2020/12/inertia-modern-monolith/
- https://www.youtube.com/playlist?list=PLkZU2rKh1mT8-yRt0Gr5S1ESVRZPB8fKS

Inertia.js lets you quickly build single-page React, Vue and Svelte apps using only server-side routing and controllers.

Long story short: No APIs.

## Setup

1. Preliminaries
```
composer create-project --prefer-dist laravel/laravel lara_inert
cd lara_inert
php artisan key:generate
composer require inertiajs/inertia-laravel
npm install @inertiajs/inertia @inertiajs/inertia-vue
```

2. Setup Controller
```php
namespace App\Http\Controllers;

use Illuminate\Http\Request;
use Inertia\Inertia;

class AppController extends Controller
{
    public function index()
    {
        $data = ['aaa'=>'bbb', 'ccc'=>'ddd'];

        return Inertia::render('App/Index', $data);
    }
```

3. Add to `routes/web.php`: `Route::resource('app', AppController::class);`

4. Setup root template `resources/views/app.blade.php`: https://inertiajs.com/server-side-setup#root-template

5. Might need to run on newer Laravels: https://stackoverflow.com/questions/58010053/js-app-js-file-neterr-aborted-404-not-found
```
composer require laravel/ui
php artisan ui vue --auth
```

You might still get this error and here's the solution: https://stackoverflow.com/questions/65607153/how-to-fix-the-error-you-may-need-an-appropriate-loader-to-handle-this-file-typ

6. `resources/js/app.js`: https://inertiajs.com/client-side-setup#initialize-app

7. Do your component `resources/js/Pages/App/Index.vue`

8. Run
```
npm install && npm run dev
php artisan serve
```

9. Visit http://127.0.0.1:8000/app

