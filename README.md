# GDMP Transaction Extension For OCDS

A detailed transaction extension created by the [Global Digital Marketplace](https://gds.blog.gov.uk/category/global-digital-marketplace/) from the [UK Government Digital Service](https://github.com/alphagov). The extension includes both summary transaction data and detailed information on each transaction, including unit measures, tax and item volumes. 

## Purpose

This extension was designed to support anti-corruption intiatives around the world, by allow publishers to include transaction data in any Open Contracting Initiative. Whilst transparency in contracting is a good method for preventing corruption, the Covid-19 pandemic has meant that anti-corruption initiatives have been working with limited contracting data which is insufficient to identify corruption. In this context, backwards looking Accounts Payable information, or bank statements are better suited to identifying corruption.

## Design

This extension has been designed to allow publishers to link either Accounts Payable data or Bank Statement data into the existing OCDS contract, but in addition to provide detailed reporting on every element that is usually reported in a single invoice, for instance, the extension includes the ability to record taxes, discounts and line item fees. This granular design is critical for being able to compare the price of different items and the cost of each.

## Deployment

High volumes of transaction data, e.g. a taxi contract where there might be dozens of transactions levied per day week, will likely create excessively large documents, in this instance, it may be desirable to publish the transaction data independently of the contract, but with a reference to the contract record in each document.

## Example

```json
{}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.

## Changelog

### 2020-09-26

* Initial commit


