# Display Mondial Relay address on invoice and order email

PrestaShop 1.7 core override: show the Mondial Relay pickup-point address on the invoice and in the order confirmation email.

Author: LATOUTFRANCAIS - Arnaud Merigeau - [arnaud-merigeau.fr](https://arnaud-merigeau.fr)

This repository is not a packaged module. It contains a single file, `PaymentModule.php`, which is a PrestaShop 1.7 override of the core `PaymentModule` class. A LATOUTFRANCAIS change dated 8 April 2021 looks up the Mondial Relay pickup point when the carrier name is `Mondial Relay`, then fills the delivery address placeholders used on the invoice and in the order validation email (`delivery_address1`, `delivery_city`, `delivery_postal_code`, `delivery_other`, and extra address lines when present).

## Compatibility

Written for PrestaShop 1.7. It has not been packaged or documented here for PrestaShop 8 or 9. Test on a staging shop and adapt the override if your core `PaymentModule.php` has changed.

## Installation

1. Back up your shop and the existing file, if any: `/override/classes/PaymentModule.php`.
2. Place this `PaymentModule.php` in `/override/classes/PaymentModule.php`.
3. Remove `/var/cache` (or clear the cache from the back office) so PrestaShop rebuilds the class index.
4. Place a test order with Mondial Relay and check the invoice and the order confirmation email.

If an override of `PaymentModule` already exists, do not overwrite it blindly: port the Mondial Relay block from this file into your current override.

## Notes

- This is a full copy of a core class with a small, commented change. Core upgrades can require a manual merge.
- The carrier match is the exact name `Mondial Relay`. If your carrier is named differently in the back office, update that condition.
- Review the SQL against your Mondial Relay module tables before using this on a production shop.

## Support

Questions or adaptations: [contact@arnaud-merigeau.fr](mailto:contact@arnaud-merigeau.fr)
