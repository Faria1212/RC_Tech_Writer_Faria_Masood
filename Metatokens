# Metatoken
Create metatokens for a shopper.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/checkout-test.adyen.com/v68/metaTokens` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `shopperReference` | `shopper-123"` | Required | The reference of the shopper that owns the recurring contract. |
| `merchantAccount` | `YOUR_MERCHANT_ACCOUNT"` | Required | Your merchant account. |


## Example Call

```bash
curl https://checkout-test.adyen.com/v68/metaTokens \
-H 'x-api-key: YOUR_API_KEY' \
-H 'content-type: application/json' \
-d '{
"shopperReference": "shopper-123",
"merchantAccount": "YOUR_MERCHANT_ACCOUNT"
}'
```

## Example Result

```javascript
{"merchantAccount": "YOUR_MERCHNAT_ACCOUNT",
"shopperReference": "yourShopperReference",
"metaTokenId": "9647-2876"
}
    },
    "success": true
}
```
