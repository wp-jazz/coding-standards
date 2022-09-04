# 📝 Coding Standards

The WordPress coding standards applied to all WP Jazz projects.

Provides a set of rulesets and extensions for:

* [EditorConfig] — Maintain consistent coding styles between different editors.
* [PHP_CodeSniffer] — PHP coding linter.
* [PHPStan] — PHP static analysis tool.
* [Psalm] — PHP static analysis tool.

> These coding standards are heavily based on, and extend,
[Human Made Coding Standards][humanmade/coding-standards].

## Installation

```sh
composer require --dev wp-jazz/coding-standards
```

This package will install supported versions of PHPCS, PHPStan, and Psalm.

See the [examples](examples) directory for boilerplate configuration files.

## Using PHPCS

Our PHPCS ruleset extends the Human Made coding standards for PHP and WordPress.

Run the following command to run the standards checks:

```sh
./vendor/bin/phpcs --standard=vendor/wp-jazz/coding-standards .
```

Or include the following in your `phpcs.xml`:

```xml
<!-- Use WP Jazz Coding Standards -->
<rule ref="Jazz" />
```

The PHPCS ruleset is based upon:

* [Human Made Coding Standards][humanmade/coding-standards]
  * [PHPCompatibilityWP]
  * [PSR-2-R]
    * [Spryker Code Sniffer][spryker/code-sniffer]
    * [Slevomat Coding Standard][slevomat/coding-standard]
  * [WordPress Coding Standards][wp-cs]
  * [WordPress VIP Coding Standards][wp-vip-cs]

With customisations, exclusions, and additions to match our style.

## Using PHPStan

Run the following command to run the static analysis:

```sh
./vendor/bin/phpstan analyze -c vendor/szepeviktor/phpstan-wordpress/extension.neon .
```

Make PHPStan find it automatically using [phpstan/extension-installer]:

```sh
composer require --dev phpstan/extension-installer
```

Or manually include it in your `phpstan.neon`:

```neon
includes:
  - vendor/szepeviktor/phpstan-wordpress/extension.neon
```

See the [szepeviktor/phpstan-wordpress] package, by Viktor Szépe,
for more information on configuring PHPStan.

## Using Psalm

```sh
./vendor/bin/psalm -c vendor/wp-jazz/coding-standards/psalm.xml.dist .
```

Use Psalm to enable the plugin:

```sh
./vendor/bin/psalm-plugin enable humanmade/psalm-plugin-wordpress
```

Or manually include it in your `psalm.xml`:

```xml
<plugins>
  <pluginClass class="PsalmWordPress\Plugin" />
</plugins>
```

See the [humanmade/psalm-plugin-wordpress] package, by Human Made,
for more information on configuring Psalm.

## Using ESLint

We recommend using the Human Made coding standards for JavaScript
which uses [ESLint].

```sh
npx install-peerdeps --dev @humanmade/eslint-config@latest
```

See the [@humanmade/eslint-config package README](https://github.com/humanmade/coding-standards/blob/master/packages/eslint-config-humanmade/readme.md)
for more information on configuring ESLint.

## Using Stylelint

We recommend using the Human Made coding standards for CSS and SCSS
which uses [Stylelint].

```sh
npm install --save-dev stylelint @humanmade/stylelint-config
```

See the [@humanmade/stylelint package README](https://github.com/humanmade/coding-standards/blob/master/packages/stylelint-config/readme.md)
for more information on configuring Stylelint.

[dealerdirect/phpcodesniffer-composer-installer]: https://github.com/PHPCSStandards/composer-installer
[EditorConfig]:                                   https://editorconfig.org/
[ESLint]:                                         https://eslint.org/
[humanmade/coding-standards]:                     https://github.com/humanmade/coding-standards
[humanmade/psalm-plugin-wordpress]:               https://github.com/humanmade/psalm-plugin-wordpress
[szepeviktor/phpstan-wordpress]:                  https://github.com/szepeviktor/phpstan-wordpress
[PHP_CodeSniffer]:                                https://github.com/squizlabs/PHP_CodeSniffer
[PHPCompatibilityWP]:                             https://github.com/PHPCompatibility/PHPCompatibilityWP
[PHPStan]:                                        https://phpstan.org/
[phpstan/extension-installer]:                    https://github.com/phpstan/extension-installer
[Psalm]:                                          https://psalm.dev/
[PSR-2-R]:                                        https://github.com/php-fig-rectified/psr2r-sniffer
[slevomat/coding-standard]:                       https://github.com/slevomat/coding-standard
[spryker/code-sniffer]:                           https://github.com/spryker/code-sniffer
[Stylelint]:                                      https://stylelint.io/
[wp-cs]:                                          https://github.com/WordPress/WordPress-Coding-Standards
[wp-vip-cs]:                                      https://github.com/Automattic/VIP-Coding-Standards
