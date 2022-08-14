---
label: Product API Sync
icon: sync
order: 3
---

These sections provide the necessary information required to **CREATE**, **UPDATE** and **DELETE** products on the Grocerly system allowing you to synchronise your products.

> Please view the [Product Units](units.md) and [Product Categories](categories.md) pages for a full list of all available product units and categories.

---

#### Create a new product

+++ Request

```js [!badge variant="primary" text="POST"] /supermarket/products
{
  barcode: 'XXXXXX', // Must be unique
  name: 'Heinz Ketchup',
  price: 200, // In cents - Translates to 2 euro
  categoryId: 'XXXXXX', // View the Product Categories page for a full list of all possible categories
  inStock: true, // Whether an item is in stock
  unit: 'GRAM', // View the Product Units page for a full list of all possible units
  weight: 100,
  isWeighed: false, //  Set to true if the product can be sold based on weight. Defaults to false if not provided
  image?: File, // (Optional) Buffer Array
}
```

+++ Response

```js
{
  success: true,
}
```

+++

---

#### Update an existing product

+++ Request

```js [!badge variant="warning" text="PUT"] /supermarket/products/:PRODUCT_BARCODE:
{
  name: 'Another Ketchup',
  price: 400, // In cents - Translates to 4 euro
  inStock: true, // Whether an item is in stock
  image?: File, // (Optional) Buffer Array
}
```

+++ Response

```js
{
  success: true,
}
```

+++

---

#### Delete a product

+++ Request

```js [!badge variant="danger" text="DELETE"] /supermarket/products/:PRODUCT_ID:
// Empty body
```

+++ Response

```js
{
  success: true,
}
```

+++

---