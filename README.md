# GDMP Transaction Extension For OCDS

A detailed transaction extension created by the [Global Digital Marketplace](https://gds.blog.gov.uk/category/global-digital-marketplace/) from the [UK Government Digital Service](https://github.com/alphagov). The extension includes both summary transaction data and detailed information on each transaction, including unit measures, tax and item volumes. 

## Purpose

This extension was designed to support anti-corruption intiatives around the world, by allow publishers to include transaction data in any Open Contracting Initiative. Whilst transparency in contracting is a good method for preventing corruption, the Covid-19 pandemic has meant that anti-corruption initiatives have been working with limited contracting data which is insufficient to identify corruption. In this context, backwards looking Accounts Payable information, or bank statements are better suited to identifying corruption.

## Design

This extension has been designed to allow publishers to link either Accounts Payable data or Bank Statement data into the existing OCDS contract, but in addition to provide detailed reporting on every element that is usually reported in a single invoice, for instance, the extension includes the ability to record taxes, discounts and line item fees. This granular design is critical for being able to compare the price of different items and the cost of each.

## Example

```json
{
    "id": "m75-junctions-4-to-5-smart-motorway",
    "updated": "2018-12-10T15:53:00Z",
    "title": "M75 Junctions 4 to 5 upgrade smart motorway",
    "description": "Upgrading the 5km stretch of the M75 near Birmingham Airport, between junction 4 near Patcham and junction 5 at Windlesham, to an all-lane running smart motorway.",
    "status": "completed",
    "period": {
        "startDate": "2016-01-01T00:00:00Z",
        "endDate": "2018-12-10T00:00:00Z",
        "durationInDays": 1074
    },
    "sector": [
        "transport",
        "transport.road"
    ],
    "type": "construction",
    "assetLifetime": {
        "startDate": "2018-07-01T00:00:00Z",
        "endDate": "2040-07-01T00:00:00Z",
        "durationInDays": 8027
    },
    "locations": [
       {
            "id": "001",
            "description": "M75 J4 Patcham Interchange",
            "geometry": {
                "type": "Point",
                "coordinates": [
                    52.2571843,
                    -0.1163333
                ]
            },
            "gazetteer": {
                "scheme": "GEONAMES",
                "identifiers": [
                    "2657507"
                ]
            },
            "address": {
                "streetAddress": "Patcham Interchange, New Road",
                "locality": "Patcham",
                "region": "Westshire",
                "postalCode": "WS20 5TV",
                "countryName": "UK"
            },
            "uri": "https://www.openstreetmap.org/node/202995"
        },
       {
            "id": "002",
            "description": "M75 J5 Windlesham interchange",
            "geometry": {
                "type": "Point",
                "coordinates": [
                    52.1373584,
                    -0.1198955
                ]
            },
            "gazetteer": {
                "scheme": "osm",
                "identifiers": []
            },
            "address": {
                "streetAddress": "Windlesham Interchange, Old Road",
                "locality": "Windlesham",
                "region": "Westshire",
                "postalCode": "WS21 6RZ",
                "countryName": "UK"
            },
            "uri": "https://www.openstreetmap.org/node/1638915385"
        }
    ],
    "budget": {
        "amount": {
            "amount": 40000000,
            "currency": "GBP"
        },
        "approvalDate": "2015-06-24T00:00:00Z",
        "budgetBreakdown": [
           {
                "id": "1",
                "description": "2016 budget allocation",
                "amount": {
                    "amount": 10000000,
                    "currency": "GBP"
                },
                "period": {
                    "startDate": "2016-01-01T00:00:00Z",
                    "endDate": "2016-12-31T00:00:00Z"
                },
                "sourceParty": {
                    "name": "Motorways UK",
                    "id": "GB-GOR-XX1234"
                }
            },
           {
                "id": "2",
                "description": "2017 budget allocation",
                "amount": {
                    "amount": 20000000,
                    "currency": "GBP"
                },
                "period": {
                    "startDate": "2017-01-01T00:00:00Z",
                    "endDate": "2017-12-31T00:00:00Z"
                },
                "sourceParty": {
                    "name": "Motorways UK",
                    "id": "GB-GOR-XX1234"
                }
            },
           {
                "id": "3",
                "description": "2018 budget allocation",
                "amount": {
                    "amount": 10000000,
                    "currency": "GBP"
                },
                "period": {
                    "startDate": "2018-01-01T00:00:00Z",
                    "endDate": "2018-12-31T00:00:00Z"
                },
                "sourceParty": {
                    "name": "Motorways UK",
                    "id": "GB-GOR-XX1234"
                }
            }
        ]
    },
    "parties": [
       {
            "name": "Motorways UK",
            "id": "GB-GOR-XX1234",
            "identifier": {
                "scheme": "GB-GOR",
                "legalName": "Motorways UK",
                "id": "XX1234",
                "uri": "https://government-organisation.register.gov.uk/records/XX1234"
            },
            "address": {
                "postalCode": "LL55 4NY",
                "countryName": "UK",
                "streetAddress": "8 Mountain Walk",
                "region": "Westshire",
                "locality": "Patcham"
            },
            "people": [{
                "title": "Mrs",
                "name": "Sarah Russell",
                "email": "EX12345@motorwaysuk.gov.uk",
                "telephone": "+44 0123 456 7890",
                "faxNumber": "+44 0123 456 7891",
                "identifier": {
                    "scheme": "",
                    "id": "",
                    "uri": ""
                },
                "businessFunction": [{
                    "type": "authority",
                    "classification": {
                        "scheme": "",
                        "id": "",
                        "uri": ""
                    },
                    "jobTitle": "Motorways Manager",
                    "period": {
                        "startDate": ""
                    },
                    "documents": [{
                        "id": "",
                        "docType": "regulatoryDocument",
                        "url": "",
                    }]
                }]
            },
            {
                "title": "Mr",
                "name": "Tim Kennedy",
                "email": "tim@motorwaysuk.gov.uk",
                "telephone": "+44 0123 456 7890",
                "faxNumber": "+44 0123 456 7891",
                "identifier": {
                    "scheme": "",
                    "id": 98765432,
                    "uri": ""
                },
                "businessFunction": [{
                    "type": "authority",
                    "classification": {
                        "scheme": "",
                        "id": "FIN",
                        "uri": ""
                    },
                    "jobTitle": "Finance Manager",
                    "period": {
                        "startDate": ""
                    },
                    "documents": [{
                        "id": "",
                        "docType": "regulatoryDocument",
                        "url": "",
                    }]
                }]
            },
            {
                "title": "Mr",
                "name": "Ian Marshall",
                "email": "ian@motorwaysuk.gov.uk",
                "telephone": "+44 0123 456 7890",
                "faxNumber": "+44 0123 456 7891",
                "identifier": {
                    "scheme": "",
                    "id": 12345678,
                    "uri": ""
                },
                "businessFunction": [{
                    "type": "authority",
                    "classification": {
                        "scheme": "",
                        "id": "FIN",
                        "uri": ""
                    },
                    "jobTitle": "Finance Officer",
                    "period": {
                        "startDate": ""
                    },
                    "documents": [{
                        "id": "",
                        "docType": "regulatoryDocument",
                        "url": "",
                    }]
                }]
            }],
            "roles": [
                "procuringEntity",
                "buyer",
                "administrativeEntity"
            ]
        },
       {
            "name": "A1 Expert Smart Moto Design",
            "id": "GB-COH-11111111",
            "identifier": {
                "scheme": "GB-COH",
                "id": "11111111",
                "legalName": "A1 Expert Smart Moto Design Ltd",
                "uri": "https://beta.companieshouse.gov.uk/company/11111111"
            },
            "address": {
                "streetAddress": "Farm Grove, Prince Road",
                "locality": "Patcham",
                "region": "Westshire",
                "postalCode": "WS18 5BW",
                "countryName": "UK"
            },
            "contactPoint": {
                "name": "Kim Designer",
                "email": "kim.designerd@a1expertsmart.com",
                "telephone": "+44 0123 456 7890",
                "url": "https://www.example.com"
            },
            "roles": [
                "supplier"
            ]
        },
       {
            "name": "Expert Motorway Supervisors Ltd",
            "id": "GB-COH-22222222",
            "identifier": {
                "scheme": "GB-COH",
                "id": "22222222",
                "legalName": "Expert Motorway Supervisors Ltd",
                "uri": "https://beta.companieshouse.gov.uk/company/22222222"
            },
            "address": {
                "streetAddress": "9 Seaview Road",
                "locality": "London",
                "region": "London",
                "postalCode": "SE1 1EZ",
                "countryName": "UK"
            },
            "people": [{
                "title": "Ms",
                "name": "Mollie Kent",
                "email": "mollie@expertmotorways.co.uk",
                "telephone": "+44 0123 456 7890",
                "faxNumber": "+44 0123 456 7891",
                "identifier": {
                    "scheme": "",
                    "id": 88888888,
                    "uri": ""
                },
                "businessFunction": [{
                    "type": "supplier",
                    "classification": {
                        "scheme": "",
                        "id": "MAR",
                        "uri": ""
                    },
                    "jobTitle": "Marketing Manager",
                    "period": {
                        "startDate": ""
                    },
                    "documents": [{
                        "id": "",
                        "docType": "regulatoryDocument",
                        "url": "",
                    }]
                }]
            }],
            "roles": [
                "supplier"
            ]
        },
       {
            "name": "Concrete Motorways Construction",
            "id": "GB-COH-33333333",
            "identifier": {
                "scheme": "GB-COH",
                "id": "GB-COH-33333333",
                "legalName": "Concrete Motorways Construction Ltd",
                "uri": "https://beta.companieshouse.gov.uk/company/33333333"
            },
            "address": {
                "streetAddress": "5 Example Grove",
                "locality": "London",
                "region": "London",
                "postalCode": "SW1A 1AA",
                "countryName": "UK"
            },
            "people": [{
                "title": "Ms",
                "name": "Ahmet Bristol",
                "email": "ahmet@concrete-motorways.co.uk",
                "telephone": "+44 0123 456 7890",
                "faxNumber": "+44 0123 456 7891",
                "identifier": {
                    "scheme": "",
                    "id": 00000000,
                    "uri": ""
                },
                "businessFunction": [{
                    "type": "supplier",
                    "classification": {
                        "scheme": "",
                        "id": "MAR",
                        "uri": ""
                    },
                    "jobTitle": "Head of Regional Business Development (South East Region)",
                    "period": {
                        "startDate": ""
                    },
                    "documents": [{
                        "id": "",
                        "docType": "regulatoryDocument",
                        "url": "",
                    }]
                }]
            }],
            "roles": [
                "supplier"
            ]
        }
    ],
    "documents": [
       {
            "id": "consultation-1234",
            "documentType": "x_consultationResponses",
            "title": "M75 Junction 4 to 5 Smart Motorway. Summary of Statutory Instrument consultation responses",
            "description": "Summary of Statutory Instrument consultation responses",
            "url": "https://example.com/he/M75-junctions-4-to-5-smart-motorway/results/M75J4-5responsereportforstatutoryinstrument-pbamendsjune18.pdf",
            "datePublished": "2016-05-01T00:00:00Z",
            "dateModified": "2016-05-11T00:00:00Z",
            "format": "application/pdf",
            "language": "en",
            "author": "Fred Consulter"
        },
       {
            "id": "environmental-impact-5678-r4",
            "documentType": "environmentalImpact",
            "title": "Environmental Study Report",
            "description": "An Environmental Study Report into the M75 Junction 4 to 5 Smart Motorway Upgrade",
            "url": "http://example.com/roads/road-projects/M75+junctions+4+to+5++smart+motorway/M75+J4-5SM+Environmental+Study+Report.pdf",
            "datePublished": "2016-02-10T00:00:00Z",
            "dateModified": "2016-12-15T00:00:00Z",
            "format": "application/pdf",
            "author": "Jane Environment, Environment Motorway Consultants Ltd."
        },
       {
            "id": "budget-approval-5678",
            "documentType": "budgetApproval",
            "title": "Approval of Budget for M75 J4-5 upgrade",
            "description": "A full budget approval document for the M75 J4-5 upgrade with budgeting for design, build and supervision.",
            "url": "http://example.com/roads/road-projects/M75+unctions+4+to+5+budget+approval.pdf",
            "datePublished": "2015-10-01T00:00:00Z",
            "dateModified": "2018-03-01T00:00:00Z",
            "format": "application/pdf",
            "author": "UK Motorways Budget Agency",
            "pageStart": "55",
            "pageEnd": "60",
            "accessDetails": "Documents can be inspected in the Motoways UK Example Archive or users can register for free to access."
        }
    ],
    "contractingProcesses": [
       {
            "id": "ocds-a1b1c1-a410a80d-adc8-11e6-9901-0019b9f3037b",
            "summary": {
                "ocid": "ocds-a1b1c1-a410a80d-adc8-11e6-9901-0019b9f3037b",
                "externalReference": "2016-SMP-M75-J4_J5-design",
                "nature": [
                    "design"
                ],
                "title": "Smart Motorway Design M75 J4-5",
                "description": "Design of Smart Motorway upgrade M75 J4-5",
                "status": "closed",
                "tender": {
                    "procurementMethod": "limited",
                    "procurementMethodDetails": "Restricted procedure",
                    "costEstimate": {
                        "amount": 2000000,
                        "currency": "GBP"
                    },
                    "numberOfTenderers": 3,
                    "procuringEntity": {
                        "name": "Motorways UK",
                        "id": "GB-GOR-XX1234"
                    }
                },
                "suppliers": [
                   {
                        "name": "A1 Expert Smart Moto Design",
                        "id": "GB-COH-11111111"
                    }
                ],
                "contractValue": {
                    "amount": 1950000,
                    "currency": "GBP"
                },
                "contractPeriod": {
                    "startDate": "2016-06-01T00:00:00Z",
                    "endDate": "2017-07-07T00:00:00Z"
                },
                "finalValue": {
                    "amount": 1950000,
                    "currency": "GBP"
                },
                "documents": [
                   {
                        "id": "a1b1c1-tender-doc-001",
                        "documentType": "tenderNotice",
                        "title": "M72 improvements at J4-5: Tender Notice",
                        "description": "A tender notice for the design of improvements to M75 J4-5",
                        "url": "https://example.com/Published/a1b1c1-design-001.html",
                        "datePublished": "2018-12-10T16:45:00Z",
                        "format": "text/html",
                        "author": "Motorways UK"
                    }
                ]
            },
            "releases": [
               {
                    "id": "ocds-cdf-pc10008",
                    "date": "2016-04-01T00:00:00Z",
                    "tag": "tender",
                    "url": "https://www.example.com/releases/ocds-cdf-pc10008.json"
                },
               {
                    "id": "ocds-cdf-pc10009",
                    "date": "2016-06-01T15:49:19Z",
                    "tag": "award",
                    "url": "https://www.example.com/releases/ocds-cdf-pc10009.json"
                }
            ]
        },
       {
            "id": "ocds-a1b1c1-370ad85a-097f-4b8c-adf8-09d840c7c48b",
            "summary": {
                "ocid": "ocds-a1b1c1-370ad85a-097f-4b8c-adf8-09d840c7c48b",
                "externalReference": "2016-SMP-M75-J4_J5-supervision",
                "nature": [
                    "supervision"
                ],
                "title": "Commercial Management and Assurance for the Motorways Upgrade Programme M75 J4-5",
                "description": "Specialist Professional and Technical Services Framework: Commercial Management and Assurance for the Motorways Upgrade Programme M75 J4-5",
                "status": "closed",
                "tender": {
                    "procurementMethod": "limited",
                    "procurementMethodDetails": "Framework",
                    "costEstimate": {
                        "amount": 5000000,
                        "currency": "GBP"
                    },
                    "numberOfTenderers": 5,
                    "procuringEntity": {
                        "name": "Motorways UK",
                        "id": "GB-GOR-XX1234"
                    },
                    "administrativeEntity": {
                        "name": "Motorways UK",
                        "id": "GB-GOR-XX1234"
                    }
                },
                "suppliers": [
                   {
                        "name": "Expert Motorway Supervisors",
                        "id": "GB-COH-22222222"
                    }
                ],
                "contractValue": {
                    "amount": 4900000,
                    "currency": "GBP"
                },
                "contractPeriod": {
                    "startDate": "2017-02-24T00:00:00Z",
                    "endDate": "2018-10-10T00:00:00Z"
                },
                "finalValue": {
                    "amount": 4900000,
                    "currency": "GBP"
                },
                "documents": [
                   {
                        "id": "a1b1c1-spats-2-033-completion",
                        "documentType": "completionCertificate",
                        "title": "Completion Certificate for supervision",
                        "description": "A completion certificate for Expert Motorway Supervisors supervision of M75 J4-5",
                        "url": "https://example.com/Published/a1b1c1-spats-2-033-completion.html",
                        "datePublished": "2018-12-10T16:45:00Z",
                        "format": "text/html"
                    }
                ],
                "transactions": [{
			        "id": "ABC-123",
			        "source": "http://www.example.com/payments/FY17",
			        "purchaseOrderNumber": "20200405-2123330",
			        "paymentMethod": "Purchase card",
			        "description": "description for transaction",
			        "keyDates": {
			        	"invoiceReceiptDate": "2017-01-01T12:30:00Z",
			          	"paymentDueDate": "2017-01-06T00:00:00Z",
			          	"paymentApprovalDate": "2017-01-03T1700:00Z",
			          	"paymentExecutedDate": "2017-03-20T00:00:00Z"
			        },
			        "value": {
			          "amount": 150000,
			          "currency": "GBP"
			        },
			        "payer": {
			          "id": "GB-GOR-XX1234",
			          "executor": {
			            "identifier": 12345678,
                        "name": "Ian Makgill"
			          },
			          "authorised": [{
			          	"identifier": 98765432,
                        "name": "Sim Kennedy"
			          }]
			        },
			        "payee": {
			          "id": "GB-COH-99999999",
			          "name": "Example company"
			        },
			        "tax": [{
			          "name": "name of tax applied",
			          "rate": {
			          	"application": "percentage",
			          	"amount": 10
			      	  },
			          "value": {
			            "amount": 10,
			            "currency": "GBP"
			          }
			        }],
			        "budgetCode": {
			          "id": "2020-04042891",
			          "description": "Highways and streetscene"
			      	},
			        "accountCode": {
			          "id":"1234567-00-23",
			          "description": "Repairs and upkeep"	
			        },
			        "procurementClassification": {
			          "scheme": "CPV",
			          "id": 44000000,
			          "description": "Drainage",
			          "uri": "https://simap.ted.europa.eu/web/simap/cpv"
			        },
                    "lineItems": [{
                      "lineDescription": "string describing each item",
                      "unit": {
                        "scheme": "UNCEFACT",
                        "id": "HUR",
                        "name": "Hours",
                      },
                      "priceSpecification": {
                        "value": {
                            "amount": 250,
                            "currency": "GBP",
                        },
                        "quantity": {
                          "value": 2,
                          "unitCode": "HUR"
                        },
                      },
                      "value": {
                        "amount": 500,
                        "currency": "GBP"
                      },
                      "discount": {
                        "name": "name of discount",
                        "rate": {
                            "application":"percentage",
                            "amount": 0,
                        "value": {
                          "amount": 500,
                          "currency": "GBP"
                        }
                      },
                      "tax": [{
                        "name": "name of tax applied",
                        "rate": {
                            "application": "percentage",
                            "amount": 10
                        },
                        "value": {
                            "amount": 10,
                            "currency": "GBP"
                        }
                      }],
                    },
    			  }],
    			}],
                "releases": [
               {
                    "id": "ocds-a1b1c1-spats-2-033e",
                    "date": "2017-03-02T17:14:37Z",
                    "tag": "tender",
                    "url": "https://example.com/releases/ex-a1b1c1--033e.json"
                },
               {
                    "id": "ocds-a1b1c1-spats-2-033f",
                    "date": "2017-05-02T17:14:37Z",
                    "tag": "award",
                    "url": "https://example.com/releases/ex-a1b1c1--033f.json"
                },
               {
                    "id": "ocds-a1b1c1-spats-2-033g",
                    "date": "2017-07-02T17:14:37Z",
                    "tag": "implementation",
                    "url": "https://example.com/Published/releases/ex-a1b1c1--033g.json"
                },
               {
                    "id": "ocds-a1b1c1-spats-2-033h",
                    "date": "2018-12-10T14:45:00Z",
                    "tag": "contractTermination",
                    "url": "https://example.com/releases/ex-a1b1c1--033h.json"
                }
            ],
    	   
            "id": "ocds-a1b1c1-c9b14c18-adc8-11e6-9901-0019b9f3037b",
            "summary": {
                "ocid": "ocds-a1b1c1-c9b14c18-adc8-11e6-9901-0019b9f3037b",
                "externalReference": "2016-SMP-M75-J4_J5-construction",
                "nature": [
                    "construction"
                ],
                "title": "Smart Motorways Programme - Construction - Package 3 - M75 J8 - 10",
                "description": "Collaborative Delivery Framework (CDF) - Lot 3B - Construction  £10 to  £50m",
                "status": "closed",
                "tender": {
                    "procurementMethod": "limited",
                    "procurementMethodDetails": "Restricted procedure",
                    "costEstimate": {
                        "amount": 33000000,
                        "currency": "GBP"
                    },
                    "numberOfTenderers": 4,
                    "procuringEntity": {
                        "name": "Motorways UK",
                        "id": "GB-GOR-XX1234"
                    }
                },
                "suppliers": [
                   {
                        "name": "Concrete Motorways Construction",
                        "id": "GB-COH-33333333"
                    }
                ],
                "contractValue": {
                    "amount": 29000000,
                    "currency": "GBP"
                },
                "contractPeriod": {
                    "startDate": "2017-07-07T00:00:00Z",
                    "endDate": "2018-07-01T00:00:00Z"
                },
                "finalValue": {
                    "amount": 35250000,
                    "currency": "GBP"
                },
                "documents": [
                   {
                        "id": "a1b1c1-construction-excavation-report",
                        "documentType": "physicalProgressReport",
                        "title": "Report on construction excavation",
                        "description": "A report on the construction at Junction 5 where excavation damaged a watercourse.",
                        "url": "https://example.com/Published/a1b1c1-construction-monitoring.html",
                        "datePublished": "2018-02-01T00:00:00Z",
                        "dateModified": "2018-02-11T00:00:00Z",
                        "format": "text/html",
                        "language": "en",
                        "accessDetails": "Register for document access.",
                        "author": "Motorways UK"
                    },
                   {
                        "id": "a1b1c1-construction-completion",
                        "documentType": "comletionCertificate",
                        "title": "Completion certificate for construction at M75 J4-5 upgrade",
                        "description": "Completion certificate for the construction upgrading motorway M75 Junctions 4-5.",
                        "url": "https://example.com/Published/a1b1c1-construction-completion.html",
                        "datePublished": "2018-12-10T00:00:00Z",
                        "format": "text/html",
                        "language": "en",
                        "accessDetails": "Register for document access.",
                        "author": "Motorways UK"
                    }
                ],
                "modifications": [
                   {
                        "id": "m27-4-5-construction-modification-001",
                        "date": "2018-04-01T15:15:00Z",
                        "description": "Construction extended for 5 months",
                        "rationale": "Excavation damaged a watercourse. Construction extended for repairs.",
                        "type": "duration",
                        "releaseID": "ocds-a1b1c1-c9b14c18-adc8-11e6-9901-0019b9f3037b-cdfpc3b005",
                        "oldContractPeriod": {
                            "startDate": "2017-07-07T00:00:00Z",
                            "endDate": "2018-07-01T00:00:00Z"
                        },
                        "newContractPeriod": {
                            "startDate": "2017-07-07T00:00:00Z",
                            "endDate": "2018-12-01T00:00:00Z"
                        }
                    },
                   {
                        "id": "m27-4-5-construction-modification-002",
                        "date": "2018-04-01T15:15:00Z",
                        "description": "Construction scope extended to include repairing a watercourse",
                        "rationale": "Excavation damaged a watercourse. Construction scope extended for repairs.",
                        "type": "scope",
                        "releaseID": "ocds-a1b1c1-c9b14c18-adc8-11e6-9901-0019b9f3037b-cdfpc3b0015"
                    },
                   {
                        "id": "m27-4-5-construction-modification-003",
                        "date": "2018-04-01T15:15:00Z",
                        "description": "Contract value increased from 29000000 to 35250000 to include repairing a watercourse",
                        "rationale": "Excavation damaged a watercourse. Construction budget extended for repairs.",
                        "type": "value",
                        "releaseID": "ocds-a1b1c1-c9b14c18-adc8-11e6-9901-0019b9f3037b-cdfpc3b0015",
                        "oldContractValue": {
                            "amount": 29000000,
                            "currency": "GBP"
                        },
                        "newContractValue": {
                            "amount": 35250000,
                            "currency": "GBP"
                        }
                    }
                ]
            },
            "releases": [
               {
                    "id": "ocds-a1b1c1-c9b14c18-adc8-11e6-9901-0019b9f3037b-cdfpc3b0011",
                    "date": "2015-09-16T15:12:32Z",
                    "tag": "tender",
                    "url": "https://example.com/Published/releases/5553-b55.json"
                },
               {
                    "id": "ocds-a1b1c1-c9b14c18-adc8-11e6-9901-0019b9f3037b-cdfpc3b0012",
                    "date": "2015-12-16T15:15:00Z",
                    "tag": "award",
                    "url": "https://example.com/Published/releases/5553-b56.json"
                },
               {
                    "id": "ocds-a1b1c1-c9b14c18-adc8-11e6-9901-0019b9f3037b-cdfpc3b0013",
                    "date": "2015-12-16T15:15:00Z",
                    "tag": "contract",
                    "url": "https://example.com/Published/releases/5553-b57.json"
                },
               {
                    "id": "ocds-a1b1c1-c9b14c18-adc8-11e6-9901-0019b9f3037b-cdfpc3b0014",
                    "date": "2015-12-16T15:15:00Z",
                    "tag": "implementation",
                    "url": "https://example.com/Published/releases/5553-b58.json"
                },
               {
                    "id": "ocds-a1b1c1-c9b14c18-adc8-11e6-9901-0019b9f3037b-cdfpc3b0015",
                    "date": "2018-04-01T15:15:00Z",
                    "tag": "implementationUpdate",
                    "url": "https://example.com/Published/releases/5553-b59.json"
                },
               {
                    "id": "ocds-a1b1c1-c9b14c18-adc8-11e6-9901-0019b9f3037b-cdfpc3b0016",
                    "date": "2018-12-10T09:15:00Z",
                    "tag": "contractTermination",
                    "url": "https://example.com/Published/releases/5553-b60.json"
                }
            ]
        }
    ],
    "completion": {
        "endDate": "2018-12-10T00:00:00Z",
        "endDateDetails": "Construction was delayed due to excavation problems when a watercourse was damaged.",
        "finalValue": {
            "amount": 42100000,
            "currency": "GBP"
        },
        "finalValueDetails": "Budget increase due to construction delay.",
        "finalScope": "Upgrade of Junctions 4 and 5 and repairs to the watercourse at Junction 5.",
        "finalScopeDetails": "Scope was expanded to include repairs to a watercourse damaged during construction excavation."
    }
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.

## Changelog

### 2020-09-26

* Initial commit


