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
{
  "uri": "https://blahblah.uk/Notice/123456098",
  "version": "1.1",
  "extensions": [
    "https://raw.githubusercontent.com/spendnetwork/ocds_transactionDetails_extension/master/extension.json"
  ],
  "publishedDate": "2020-12-01T16:25:48Z",
  "publisher": {
    "uid": "https://beta.companieshouse.gov.uk/company/04962733",
    "uri": "https://openopps.com",
    "name": "Open Opps",
    "scheme": "Companies House"
  },
  "releases": [
    {
      "ocid": "ocds-abce-12355",
      "id": "11",
      "date": "2020-12-01T09:51:44Z",
      "tag": [
        "tender"
      ],
      "initiationType": "tender",
      "parties": [
        {
          "name": "Example company",
          "id": "GB-COH-99999999",
          "identifier": {
            "legalName": "Example company"
          },
          "address": {
            "locality": "Wetherby",
            "region": "UK",
            "countryName": "United Kingdom"
          },
          "contactPoint": {
            "email": "noreply@proactis.com"
          },
          "roles": [
            "payee"
          ],
          "details": {
            "url": "http://www.proactis.com",
            "classifications": [
              {
                "scheme": "TED_CA_TYPE",
                "id": "BODY_PUBLIC",
                "name": "Body governed by public law"
              },
              {
                "scheme": "COFOG",
                "id": "10",
                "name": "Social protection"
              }
            ]
          }
        },
        {
          "name": "Some Company Ltd.",
          "id": "GB-GOR-XX1234",
          "identifier": {
            "legalName": "Some Company Ltd."
          },
          "address": {
            "locality": "Wetherby",
            "region": "UK",
            "countryName": "United Kingdom"
          },
          "contactPoint": {
            "email": "noreply@proactis.com"
          },
          "roles": [
            "payer"
          ],
          "details": {
            "url": "http://www.proactis.com",
            "classifications": [
              {
                "scheme": "TED_CA_TYPE",
                "id": "BODY_PUBLIC",
                "name": "Body governed by public law"
              },
              {
                "scheme": "COFOG",
                "id": "10",
                "name": "Social protection"
              }
            ]
          }
        }
      ],
      "transactionDetails": [
        {
          "id": "ABC-123",
          "source": "http://www.example.com/payments/FY17",
          "purchaseOrderNumber": "20200405-2123330",
          "paymentMethod": "Purchase card",
          "description": "This is a record of a transaction of item 1 between group A and group B",
          "invoiceReceiptDate": "2017-01-01T12:30:00Z",
          "paymentDueDate": "2017-01-06T00:00:00Z",
          "paymentApprovalDate": "2017-01-03T1700:00Z",
          "paymentExecutedDate": "2017-03-20T00:00:00Z",
          "value": {
            "amount": 150000,
            "currency": "GBP"
          },
          "payer": {
            "id": "GB-GOR-XX1234",
            "name": "Some Company Ltd."
          },
          "paymentExecutor": "Joseph Bloggs",
          "paymentAuthorizers": [
            {
              "identifier": 98765432,
              "name": "Sim Kennedy"
            },
            {
              "identifier": 12345432,
              "name": "Kim Sennedy"
            }
          ],
          "payee": {
            "id": "GB-COH-99999999",
            "name": "Example company"
          },
          "taxes": [
            {
              "id": "1",
              "name": "Cat Tax",
              "rate": "0.1",
              "value": {
                "amount": 10,
                "currency": "GBP"
              }
            }
          ],
          "budgetCode": {
            "scheme": "BugdSche",
            "id": "2020-04042891",
            "description": "Highways and streetscene"
          },
          "accountCode": {
            "scheme": "AccSche",
            "id": "1234567-00-23",
            "description": "Repairs and upkeep"
          },
          "procurementClassification": {
            "scheme": "CPV",
            "id": 44000000,
            "description": "Drainage",
            "uri": "https://simap.ted.europa.eu/web/simap/cpv"
          },
          "lineItems": [
            {
              "id": "1",
              "description": "One example item",
              "unit": {
                "scheme": "UNCEFACT",
                "id": "HUR",
                "description": "Hours"
              },
              "quantity": "2",
              "value": {
                "amount": 500,
                "currency": "GBP"
              },
              "discount": {
                "description": "Discount because of reason A.",
                "rate": 0.01,
                "value": {
                  "amount": 1,
                  "currency": "GBP"
                }
              },
              "taxes": [
                {
                  "id": "123",
                  "name": "B Tax",
                  "rate": 0.1,
                  "value": {
                    "amount": 10,
                    "currency": "GBP"
                  }
                }
              ]
            }
          ]
        }
      ],
      "language": "en"
    }
  ]
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.

## Changelog

### 2020-09-26

* Initial commit


