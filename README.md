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

## CI/CD

This project uses GitHub Actions for continuous integration and deployment. The following workflows are configured:

### Tests Workflow (`.github/workflows/run-tests.yml`)
- Runs on: Push and Pull Requests
- Tests against: PHP 8.3, Laravel 11.x and 12.x
- Includes: Unit tests, coverage reports, and test artifacts
- Features:
  - Composer dependency caching for faster builds
  - Security audits with `composer audit`
  - Test result artifacts with 30-day retention
  - Code coverage reporting to Codecov

### Security & Quality Workflow (`.github/workflows/security.yml`)
- Runs on: Push and Pull Requests
- Includes:
  - Composer security audits
  - Psalm static analysis
  - Dependency vulnerability checks
  - Code quality checks
  - Composer validation

### Workflow Features
- **Caching**: Composer dependencies are cached to speed up builds
- **Timeout Protection**: Jobs have timeout limits to prevent hanging builds
- **Artifact Storage**: Test results and coverage reports are saved as artifacts
- **Security Scanning**: Automated security vulnerability detection
- **Multi-version Testing**: Tests against multiple Laravel versions for compatibility

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
