# Product Display API

## Overview

The Product Display API is a crucial aspect of our suite of services. This endpoint allows for the display of product information on each page that an end-user navigates to. For example, a product page may have information such as dimensions or weight attributed to it.

## Features

**POST** /products/detail

### Product Details

This feature allows product information to be displayed on a product page. The minimum information that is required includes the standard fields contained within the Product Sort API, as well as images of the product. This feature returns the full details for that product, including pricing, availability, available shipping options, and image URLs.

> You can extend the product object with any other fields you need (e.g. weight, dimensions, custom attributes, etc.) but this gives the core you’ll display when someone selects an item.
>

**Request Body**

```json

{
  "productId": "string"
}
```

**Response Body**

```json
{
  "product": {
    "id": "string",
    "name": "string",
    "description": "string",
    "price": 0.00,
    "inStock": true,
    "shippingMethods": ["standard", "express"],
    "images": ["https://…/img1.jpg", "https://…/img2.jpg"]
  }
}

```
