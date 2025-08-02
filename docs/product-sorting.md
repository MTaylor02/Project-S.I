# Product Sorting API

## Overview

The Product Sorting API is a crucial aspect of our suite of services. This endpoint allows for sorting of our products in various ways, in order to help the end-user find the products they are searching for.

## Features

**POST** /products/sort/price

### Sorting by Price

This feature allows products to be sorted by price, in ascending or descending fashion. In other words, by least or most expensive. “id” notes the product id used for identifying our products, “name” is the product name that is displayed to the end-user, and “price” is the price of the product.

> order: "asc" (low → high) or "desc" (high → low)

**Request Body**

```json
{
  "order": "asc"
}
```

**Response Body**

```json
{
  "products": [
    {
      "id": "string",
      "name": "string",
      "price": 0.00
    }
  ]
}
```

**POST** /products/sort/availability

### Sorting by Availability

This feature allows products to be sorted by availability by utilizing a feature flag of true or false. If the flag is set to true, it will return in stock products first in a list or results. If flag is set to false, it will show out of stock products first.

> inStockFirst: true to list in-stock items before out-of-stock; false to reverse

**Request Body**

```json
{
  "inStockFirst": true
}
```

**Response Body**

```json
{
  "products": [
    {
      "id": "string",
      "name": "string",
      "inStock": true
    }
  ]
}
```

**POST** /products/sort/shipping

### Sort by Shipping Method

This feature allows products to be sorted by shipping method, allowing end-users to sort products by the method in which they ship, potentially allowing them to receive products in a shorter window of time.

> methodPriority: array of shipping methods in desired sort order

**Request Body**

```json
{
  "methodPriority": ["express", "standard", "economy"]
}
```

**Response Body**

```json
{
  "products": [
    {
      "id": "string",
      "name": "string",
      "shippingMethod": "express"
    }
  ]
}
```

> All responses return a single top-level products array.
> Each product object only includes the fields relevant to the sort.
> You can combine these into one more generic endpoint  /products/sort by making the request schema a union of these.
