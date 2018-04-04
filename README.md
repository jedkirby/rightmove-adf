# RightmoveADF

PHP library for the Rightmove Real Time Property Datafeed.

## Install

### Prerequisites

To use this package, you need to:
* Be running PHP 5.4 or above
* Be using composer (if you want to follow the installation guide)
* Rightmove will provide you with a PEM certificate/password and Network ID to use in the requests. You should also have a Branch ID.

Note that this package's dependencies will also be installed. Check the `composer.json` file from the repository if you want to see what these are before using it.

### Installation using Composer

To install with Composer:

```sh
composer require jedkirby/rightmove-adf
```

Or add to a composer.json file:

```json
"require": {
	"jedkirby/rightmove-adf" : "1.*"
}
```

## Usage

### Using the Examples

Examples are provided. It's recommended that you setup one of the examples to see how to interact with the library before continuing.

* Install this package using composer as outlined above.
* create a directory for your project for example `public_html`

```
mkdir public_html
```

* copy the example code to the new `public_html` directory

```
cp -R vendor/jedkirby/rightmove-adf/examples/ public_html/
```

* copy the config file to a working Version

```
cp public_html/config.php.example public_html/config.php
```

* Edit the config file with your settings. You'll need to have a .pem file form RightMove with your Real Time Data Feed key in it, as well as your network and branch information.
* run the local web server

```
cd public_html

php -S localhost:8000
```

*  run one of the example files from you browser (eg  `http://localhost:8080/getBranchPropertyList.php`)

### Available Methods

All values that you set in the configuration will be checked against what the API expects and return exceptions if the wrong data type is set.

All 13 of the v1.2.3 API endpoints are supported.

- SendProperty [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/sendProperty.php)]
- RemoveProperty [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/removeProperty.php)]
- GetBranchPropertyList [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/getBranchPropertyList.php)]
- AddPremiumListing [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/addPremiumListing.php)]
- AddFeaturedProperty [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/addFeaturedProperty.php)]
- RemoveFeaturedProperty [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/removeFeaturedProperty.php)]
- GetPropertyPerformance [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/getPropertyPerformance.php)]
- GetBranchPerformance [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/getBranchPerformance.php)]
- GetBrandEmails [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/getBrandEmails.php)]
- GetBranchEmails [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/getBranchEmails.php)]
- GetBrandPhoneLeads [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/getBrandPhoneLeads.php)]
- GetBranchPhoneLeads [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/getBranchPhoneLeads.php)]
- GetPropertyEmails [[Example](https://github.com/jedkirby/rightmoveADF/blob/master/examples/getPropertyEmails.php)]


## Todo

- Add in a pre-send validation check for required fields.

## Known Issues

- The rightmove media crawler doesn't work over [Lets Encrypt](https://letsencrypt.org/) https and will just return an MED_00001 error.
