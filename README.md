# Mailgun metrics for Laravel Nova dashboard.

[![Latest Version on Packagist](https://img.shields.io/packagist/v/palpalani/nova-mailgun-metrics.svg?style=flat-square)](https://packagist.org/packages/palpalani/nova-mailgun-metrics)
[![GitHub Tests Action Status](https://img.shields.io/github/workflow/status/palpalani/nova-mailgun-metrics/run-tests?label=tests)](https://github.com/palpalani/nova-mailgun-metrics/actions?query=workflow%3ATests+branch%3Amaster)
[![Total Downloads](https://img.shields.io/packagist/dt/palpalani/nova-mailgun-metrics.svg?style=flat-square)](https://packagist.org/packages/palpalani/nova-mailgun-metrics)


Provides most useful cards for Mailgun.

## Installation

You can install the package via composer:

```bash
composer require palpalani/nova-mailgun-metrics
```

You can publish and run the migrations with:

```bash
php artisan vendor:publish --provider="PalPalani\NovaMailgunMetrics\NovaMailgunMetricsServiceProvider" --tag="nova-mailgun-metrics-migrations"
php artisan migrate
```

You can publish the config file with:
```bash
php artisan vendor:publish --provider="PalPalani\NovaMailgunMetrics\NovaMailgunMetricsServiceProvider" --tag="nova-mailgun-metrics-config"
```

This is the contents of the published config file:

```php
return [
    return [
        'api_key' => env('MAILGUN_API_KEY'),
        'domain' => env('MAILGUN_DOMAIN'),
        'cache' => env('MAILGUN_CACHE', 5),
    ];
];
```

## Testing

```bash
composer test
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Contributing

Please see [CONTRIBUTING](.github/CONTRIBUTING.md) for details.

## Security Vulnerabilities

Please review [our security policy](../../security/policy) on how to report security vulnerabilities.

## Credits

- [palPalani](https://github.com/palpalani)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
