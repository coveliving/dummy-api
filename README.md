# Dummy Cove API

This documentation explains the basic capabilities of the API server that should be enough to implement all basic requirements. However, if you need more features, please, check the [full documentation](https://github.com/typicode/json-server#routes).

## Endpoint

`https://my-json-server.typicode.com/coveliving/dummy-api`

## Methods

### Get all listings

`GET /listings`

Returnes an array of listings. Each listing belongs to a building.

### Get listing

`GET /listings/1`

### Get all buildings

`GET /buidlings`

### Get building

`GET /buildings/1`

## Filtering

Filtering by any field (including nested) is supported:

```
GET /listings?bed=queen
GET /listings?discount.amount=300
GET /buildings?id=1&id=2
```

Operators `gte`, `lte` are also supported:

```
GET /listings?price_gte=2000
```

To exclude a value use `ne`:

```
GET /listings?discount.percent_ne=null
```

## Sorting

Sort entities using `_sort` and `_order`:

```
GET /listings?_sort=price&_order=asc
GET /buildings/1/listings?_sort=discount.amount&_order=desc
```

## Relationships

Include children resources using `_embed`:

```
GET /buildings?_embed=listings
```

Include parent resource using `_expand`:

```
GET /listings?_expand=building
```

## Misc

Images are stored at https://imgur.com/a/bHUVkVf.
