# Metatokens

A metatoken is a collection of the shopper’s existing tokens, ordered based on how likely they will lead to a successful payment (based on our machine learning algorithm). This enables retrying the payment using the token with the highest probability of succeeding first. We first try the payment using the highest-ranking token. If this fails, we retry the payment using the second-ranking token (under the same meta-token), etc.
DEV-53788 functionality was built to utilize alternate tokens (possibly across different shops) for the same shopper.

## Benefit
•	Allows tokens to be shared across multiple shops under the same company.
•	The pilot is estimated to have a 5 - 15% increase in failed tokenized payments being recovered by use of meta tokens. 



## MetaTokens Endpoint
Creates metatokens for a shopper.

Use the details below to set up your request.

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

Other possible responses:

404 - The event was not found
500 - Unexpected server error
