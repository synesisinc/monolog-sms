# SMS Monolog Handler
[![Latest Version](https://img.shields.io/github/release/tylercd100/monolog-sms.svg?style=flat-square)](https://github.com/tylercd100/monolog-sms/releases)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![Build Status](https://travis-ci.org/tylercd100/monolog-sms.svg?branch=master)](https://travis-ci.org/tylercd100/monolog-sms)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/tylercd100/monolog-sms/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/tylercd100/monolog-sms/?branch=master)
[![Code Coverage](https://scrutinizer-ci.com/g/tylercd100/monolog-sms/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/tylercd100/monolog-sms/?branch=master)
[![Dependency Status](https://www.versioneye.com/user/projects/56f3252c35630e0029db0187/badge.svg?style=flat)](https://www.versioneye.com/user/projects/56f3252c35630e0029db0187)
[![Total Downloads](https://img.shields.io/packagist/dt/tylercd100/monolog-sms.svg?style=flat-square)](https://packagist.org/packages/tylercd100/monolog-sms)

A Monolog Handler for SMS messaging services

Currently supported
- [Plivo](https://www.plivo.com/)
- [Twilio](https://www.twilio.com/)

## Installation

Install via [composer](https://getcomposer.org/) - In the terminal:
```bash
composer require synesisinc/monolog-sms dev-master
```

## Usage
For Plivo:
```php
use Tylercd100\Monolog\Handler\PlivoHandler;

$handler = new PlivoHandler($token,$auth_id,$fromPhoneNumber,$toPhoneNumber);
$logger  = new Monolog\Logger('plivo.example');
$logger->pushHandler($handler);
$logger->addCritical("Foo Bar!");
```

For Twilio:
```php
use Tylercd100\Monolog\Handler\TwilioHandler;

$handler = new TwilioHandler($secret,$sid,$fromPhoneNumber,$toPhoneNumber);
$logger  = new Monolog\Logger('twilio.example');
$logger->pushHandler($handler);
$logger->addCritical("Foo Bar!");
```
