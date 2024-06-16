# PHP Date Localization With IntlDateFormatter

This PHP script localizes date formatting based on specified locales and formats. It uses the `IntlDateFormatter` class to format dates according to various international conventions.

## Prerequisites

- PHP installed on your system.
- The `intl` extension enabled in PHP.
- The required locales installed on your system. On a Debian-based system, you can install them using:
  ```sh
  sudo apt-get install locale-all
  ```
  or
```sh
  sudo apt-get install locale-all
 ```

### `localize` Function

```php
/**
 * Returns a localized date based on format and locale
 * @param DateTime $date the date to format
 * @param string $format the format mask
 * @param string|null $locale
 * @return string
 */
function localize(DateTime $date, string $format, ?string $locale = 'en_EN'): string
{
    $formatter = new \IntlDateFormatter($locale, 0, 0);
    $formatter->setPattern($format);
    return $formatter->format($date);
}
```

### Format pattern

IntlDateFormatter does not share format patterns with date(). A comprehensive list of formats can be found here https://unicode-org.github.io/icu/userguide/format_parse/datetime/

This function takes a `DateTime` object, a date format string, and an optional locale string. It uses the `IntlDateFormatter` class to format the date according to the specified locale and format.

### Example Output

```sh
The time in Afar (Djibouti) with format 'date_default' is 2023-06-16
The time in Thai (Thailand) with format MMMM Y is มิถุนายน 2024
The time in Tibetan (China) with format Y-MM-dd is 2024-06-16
...


## Acknowledgements

This script makes use of the `IntlDateFormatter` class from the PHP `intl` extension for handling localized date formatting.
```