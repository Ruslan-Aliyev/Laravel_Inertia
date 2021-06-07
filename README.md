# Inertia JS & Laravel

- https://inertiajs.com/
- https://www.infoq.com/news/2020/12/inertia-modern-monolith/
- https://www.youtube.com/playlist?list=PLkZU2rKh1mT8-yRt0Gr5S1ESVRZPB8fKS

Long story short: No APIs.

## Setup

```
composer create-project --prefer-dist laravel/laravel lara_inert
cd lara_inert
php artisan key:generate
composer require inertiajs/inertia-laravel
npm install @inertiajs/inertia @inertiajs/inertia-vue
```