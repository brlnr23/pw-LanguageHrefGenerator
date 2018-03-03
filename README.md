# LanguageHrefGenerator

Generates <link> tags with hreflang support for multi-language sites. 

## What is hreflang?
hreflang is an attribute to tell search engines which URL targets which language and country. It is used to reference the same page content in other languages. Aditionally it can be used to target URLs with the same language to different countries (e.g. English for the UK and English for the US)

Additional information can be found here: https://support.google.com/webmasters/answer/189077?hl=en


## Requirements
* Processwire 2.8.21, 3.0.21 or above
* [LanguageSupport](https://modules.processwire.com/modules/language-support/) module must be installed


## Installation and setup
* Install the module with one [of these methods](https://modules.processwire.com/install-uninstall/)
* Once the installation is done, open each language page (Setup > Languages) and add the proper language code
  * set the [language code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for the language
  * (optionally) set the [country code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) for the country


## Usage

Call the module in the <head> section in all of your pages like this:
`echo wire("modules")->get("LanguageHrefGenerator")->generateMarkup($page);`


The generated output will look like this (assuming that English is your default language):

    <link rel="alternate" hreflang="en" href="http://www.example.com/" />
    <link rel="alternate" hreflang="x-default" href="http://www.example.com/" />
    <link rel="alternate" hreflang="de" href="http://www.example.com/de/" />
    <link rel="alternate" hreflang="fr" href="http://www.example.com/fr/" />
    <link rel="alternate" hreflang="de-CH" href="http://www.example.com/dech/" />
    <link rel="alternate" hreflang="de-AT" href="http://www.example.com/deat/" />


## Additional information

The default language represents also the x-default hreflang - means the default language targets all audiences where no separate language/country exists.

* List of language codes: https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes
* List of country codes: https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2


### Additional information about hreflang
* https://www.rebelytics.com/multiple-hreflang-tags-one-url/
* https://www.rebelytics.com/hreflang-canonical/
