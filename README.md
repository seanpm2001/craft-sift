# Sift Plugin

A plugin for Craft CMS 3 that filters entries/categories that can be selected to only those that match a user's categories.

## Requirements

Craft CMS 3.0.0 or later.

## Installation

Install the plugin by first copying the plugin directory into a directory called `plugins` (in the Craft project path) and then add the following code to the main `composer.json` file:
```json
"repositories": [
    {
        "type": "path",
        "url": "./plugins/*"
    }
],
```
Then run the following composer command:
```
composer require putyourlightson/craft-sift
```

## Configuration

Copy the `src/config.php` config file to `craft/config` as `sift.php`, adding the category field handles to filter entries/categories by.
```php
return [
    '*' => [
        /**
         * The category field handles to filter entries/categories by
         */
        'categoryFieldHandles' => ['categoriesA', 'categoriesB'],

        /**
         * The `relatedTo` key to use for entry queries
         */
        'entryRelatedToKey' => 'targetElement',

        /**
         * The `relatedTo` key to use for category queries
         */
        'categoryRelatedToKey' => 'sourceElement',
    ],
];
```

## Fieldtype

The plugin adds a _Read-only Categories_ fieldtype that is visible to all users but that only admins can edit.

## License

This plugin is licensed for free under the MIT License.

<small>Created by [PutYourLightsOn](https://putyourlightson.com/).</small>
