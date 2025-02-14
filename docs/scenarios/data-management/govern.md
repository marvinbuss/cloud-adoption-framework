---
title: Data summary and maturity model for Azure
description: Understand the concept of data governance in the cloud and for Azure.
author: BrianBlanchard
ms.author: brblanch
ms.date: 02/01/2020
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: scenario
ms.custom: e2e-data-management, think-tank
---

# Data summary and maturity model for Azure

The key to successful data governance is to break down structured data into data entities and data subject areas. Then use a data governance solution to surround the specific data entities and data subject areas with people, processes, policies, and technology. This solution will help govern the lifecycle of these data entities. Establishing a common business vocabulary in a business glossary within a data catalog can help.

The data catalog is critical technology. You can't govern data if you don't know where the data is or what it means. Data catalog software provides automatic data discovery, automatic profiling to determine its quality, and automatic sensitive data detection. It also helps map disparate data to your common vocabulary data names and definitions in the catalog business glossary to understand what data means.

Creating data governance classification schemes such as the examples shown in [Data confidentiality classification scheme](./govern-requirements.md#data-confidentiality-classification-scheme) and [data retention classification scheme](./govern-requirements.md#data-retention-classification-scheme) provide different levels of governance classification. These schemas must be defined in the data catalog. At this point, policies and rules can be created in the data catalog and associated with different levels of governance classification.

It should then be possible to label (or tag) data attributes in the business glossary with confidentiality and retention classes to specify how to govern it. And because the data catalog already knows the mappings of physical data attributes in different data stores to attributes in business glossary, then labeling an attribute in the glossary automatically determines how to govern data mapped to it in underlying data stores. Multiple technologies that integrate with the data catalog can then access this metadata to consistently enforce these policies and rules across all data stores in a distributed data landscape. The exact same governance classification labels can also be applied to unstructured data.

Master data entities are critical because this data is so widely shared. It's also frequently associated with documents. For example, a customer and an invoice, a supplier and a contract, an asset and an operating manual. That's why master data values, such as supplier name, can be used to tag related documents to ensure that relationships between structured and unstructured data is preserved.

When you use the common vocabulary data entities defined in the data catalog and the mappings discovered, it's possible to create pipelines using data fabric to create trusted data assets. These assets can be published in a data marketplace for all to share. The key point about data governance is that there are methods here to get your data under control and once trusted, to then use it to drive value. Success will be determined by how well you organize and collaborate to do it. This Microsoft data governance guide is provided to assist so you can systematically use people, processes, policies, and technology to get your data into a trusted well-governed state to eradicate data quality problems and the impact they have, uphold privacy, secure access, and drive business value.

## Data governance maturity model

When you look at the data governance challenge, you might wonder how mature you are for covering all aspects across your data landscape. To assess it, the following data governance maturity model is provided.

## People

| Ungoverned | Stage 1 | Stage 2 | Fully governed |
|--|--|--|--|
| No stakeholder executive sponsor | Stakeholder sponsor in place | Stakeholder sponsor in place | Stakeholder sponsor in place |
| No roles and responsibilities | Roles and responsibilities defined | Roles and responsibilities defined | Roles and responsibilities defined |
| No data governance control board | Data governance control board in place but no ability | Data governance control board in place with data | Data governance control board in place with data |
| No data governance working groups | No data governance working groups | Some data governance working groups in place | All data governance working groups in place |
| No data owners accountable for data | No data owners accountable for data | Some data owners in place | All data owners in place |
| No data stewards appointed with responsibility for data quality | Some data stewards in place for data quality but scope too broad, for example, whole dept | Data stewards in place and assigned to data governance working groups for specific data | Data stewards in place assigned to data governance working groups for specific data |
| No one accountable for data privacy | No one accountable for data privacy | Chief privacy officer accountable for privacy (no tools) | Chief privacy officer accountable for privacy with tools |
| No one accountable for access security | IT accountable for access security | IT security accountable for access security | IT security accountable for access security and responsible for enforcing privacy |
| No one to produce trusted data assets | Data publisher identified and accountable for producing trusted data | Data publisher identified and accountable for producing trusted data | Data publisher identified and accountable for producing trusted data |
| No SMEs identified for data entities | Some SMEs identified but not engaged | SMEs identified and in data governance working groups | SMEs identified and in data governance working group |

## Process

| Ungoverned | Stage 1 | Stage 2 | Fully governed |
|--|--|--|--|
| No common business vocabulary | Common biz vocabulary started in a glossary | Common business vocabulary established | Common business vocabulary complete |
| No way to know where data is located, its data quality or if it's sensitive data | Data catalog auto data discovery, profiling and sensitive data detection on some systems | Data catalog auto data discovery, profiling and sensitive data detection on all structured data | Data catalog auto data discovery, profiling and sensitive data detection on structured and unstructured in all systems w/ full auto tagging |
| No process to govern authoring or maintenance of policies and rules | Governance of data access security policy authoring and maintenance on some systems | Governance of data access security, privacy, and retention policy authoring and maintenance | Governance of data access security, privacy, and retention policy authoring and maintenance |
| No way to enforce policies and rules | Piecemeal enforcement of data access security policies and rules across systems with no catalog integration | Enforcement of data access security and privacy policies and rules across systems with catalog integration | Enforcement of data access security, privacy, and retention policies and rules across all systems |
| No processes to monitor data quality, data privacy, or data access security | Some ability to monitor data quality <br> Some ability to monitor privacy (for example, queries) | Monitoring and stewardship of data quality and data privacy on core systems with DBMS masking | Monitoring and stewardship of data quality and data privacy on all systems with dynamic masking |
| No availability of fully trusted data assets | Dev started on a small set of trusted data assets using data fabric software | Several core trusted data assets created using data fabric | Continuous delivery of trusted data assets with enterprise data marketplace |
| No way to know whether a policy violation occurred or process to act if it did | Data access security violation detection in some systems | Data access security violation detection in all systems | Data access security violation detection in all systems |
| No vulnerability testing process | Limited vulnerability testing process | Vulnerability testing process on all systems | Vulnerability testing process on all systems |
| No common process for master data creation, maintenance, and sync | MDM with common master data CRUD and sync processes for single entity | MDM with common master data CRUD and sync processes for some data entities | MDM with common master data CRUD and sync processes for all master data entities complete |

## Policies

| Ungoverned | Stage 1 | Stage 2 | Fully governed |
|--|--|--|--|
| No data governance classification schemes on confidentiality and retention | Data governance classification scheme for confidentiality | Data governance classification scheme for both confidentiality and retention | Data governance classification scheme for both confidentiality and retention |
| No policies and rules to govern data quality | Policies and rules to govern data quality started in common vocabulary in business glossary | Policies and rules to govern data quality defined in common vocabulary in catalog biz glossary | Policies and rules to govern data quality defined in common vocabulary in catalog biz glossary |
| No policies and rules to govern data access security | Some policies and rules to govern data access security created in different technologies | Policies and rules to govern data access security and data privacy consolidated in the data catalog using classification scheme | Policies and rules to govern data access security, data privacy, and retention consolidated in the data catalog using classification schemes and enforced everywhere |
| No policies and rules to govern data privacy | Some policies and rules to govern data privacy | Policies and rules to govern data access security and data privacy consolidated in the data catalog using classification scheme | Policies and rules to govern data access security, data privacy, and retention consolidated in the data catalog using classification schemes and enforced everywhere |
| No policies and rules to govern data retention | No policies and rules to govern data retention | Some policies and rules to govern data retention | Policies and rules to govern data access security, data privacy, and retention consolidated in the data catalog using classification schemes and enforced everywhere |
| No policies and rules to govern master data maintenance | Policies and rules to govern master data maintenance for a single master data entity | Policies and rules to govern master data maintenance for some master data entities | Policies and rules to govern master data maintenance for all master data entities |

## Technology

| Ungoverned | Stage 1 | Stage 2 | Fully governed |
|--|--|--|--|
| No data catalog with auto data discovery, profiling and sensitive data detection | Data catalog with auto data discovery, profiling and sensitive data detection purchased | Data catalog with auto data discovery, profiling and sensitive data detection purchased | Data catalog with auto data discovery, profiling and sensitive data detection purchased |
| No data fabric software with multicloud edge and datacenter connectivity | Data fabric software with multicloud edge and datacenter connectivity and catalog integration purchased | Data fabric software with multicloud edge and datacenter connectivity and catalog integration purchased | Data fabric software with multicloud edge and datacenter connectivity and catalog integration purchased |
| No metadata lineage | Metadata lineage available in data catalog on trusted assets being developed using fabric | Metadata lineage available in data catalog on trusted assets being developed using fabric | Metadata lineage available in data catalog on trusted assets being developed using fabric |
| No data stewardship tools | Data stewardship tools available as part of the data fabric software | Data stewardship tools available as part of the data fabric software | Data stewardship tools available as part of the data fabric software |
| No data access security tool | Data access security in multiple technologies | Data access security in multiple technologies | Data access security enforced in all systems |
| No data privacy enforcement software | No data privacy enforcement software | Data privacy enforcement in some database management systems | Data privacy enforcement in all data stores |
| No master data management system | Single entity master data management system | Multientity master data management system | Multientity master data management system |

## Next steps

[Requirements for governing data in a modern enterprise](./govern-requirements.md)
