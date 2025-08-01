# Product Compatibility API

## Overview

The Product Compatibility endpoint is unique in that it is an entirely end-user driven feature. In our online catalog, end-users can input their desired system specifications in order to get results tailored to their specific equipment. For example: If an end-user owns an AM4 Motherboard and CPU, they can further add their RAM, and PSU Wattage in order to sort for products that are not only compatible with their system, but fit within their power constraints. This will prevent them from ordering parts that are either incompatible, or unsafe for their current power needs.

## Features

**POST** /products/sort/cpu

## Sorting by CPU Compatibility

This feature allows products to be sorted by CPU details for compatibility, in ascending or descending fashion. In other words, by least or most expensive. The end-user will enter this into a dialog box prior to searching. This pre-processing of information allows the search to be focused on a particular platform, displaying those results first.

**Request Body**
'{
  "make": "string",
  "model": "string",
  "manufacturer": "string"
}'

Response Body

**POST** /products/sort/ram

This feature helps the end-user narrow down even further with regards to their own system. Depending on the CPU, the end-user will be bound to a few choices. DDR3, DDR4, or DDR5 for modern systems.

RAM modules sorted with matching ramType first; each item shows its DDR generation.

DDR2 and DDR RAM modules are not valid entries, as they are not available to purchase. ECC (Error Correcting) RAM modules do not have a specific field, but will still appear in search results with each respective generation. This will be available in a future version.
