---
description: Using The Blue Terra Contract Metadata in Your Apps
---

# 🦾 Neighbour API

As with all Solana NFTs, both on-chain and off-chain metadata is easily queryable. To get the `contract` data defined in the `Blue Terra Token Metadata Standard` we can simply request our off-chain metadata from Arweave.&#x20;

To make it easier to query the contract metadata embedded within your NFT, we have created   the `neighbour-api`. The `neighbour-api`contains useful set for the Blue Terra community using drawing from public data. For now, we will make public a single http get endpoint for obtaining `Blue Terra Token Metadata Standard` data.

* `v1/contract` - Gets JSON contract data.

In the future, the `neighbour api` will be expanded to include additional public details about Blue Terra plots and extra endpoints to discover for example the token addresses of your neighbors or a given plot's distance to the ocean.

## I. `contract`

* url: `https://neighbour-api.blueterra.land/v1/contract`
* method: `POST`
* params: `{"mint": <Blue_Terra_Mint>}`

The following is an example query for the Blue Terra Land-As-NFT contract data for our FTX 1 of 1 using `curl` and `python.`

{% tabs %}
{% tab title="curl" %}


### Curl

```bash
curl -X POST \
    "https://neighbour-api.blueterra.land/v1/contract?mint=A6ymjkFB85t51ftqGCXYjZ5cetXsZ5GE9YapdtteteJF"
```
{% endtab %}

{% tab title="python" %}


### Python

```python
import requests

def get_contract_from_mint(mint: str):
    response = requests.post(
        url="https://neighbour-api.blueterra.land/v1/contract",
        params={"mint": mint})
    if response.status_code == 200:
        return response.json()
    raise Exception("Request Failed. Non 200 Status Code")

if __name__ == "__main__":
    mint = "A6ymjkFB85t51ftqGCXYjZ5cetXsZ5GE9YapdtteteJF" # FTX 1 of 1 Token
    print(get_contract_from_mint(mint))
```
{% endtab %}
{% endtabs %}

Here is a sample of the response body from the `neighbour-api` requests above.&#x20;

```json
{
    "success":true,
    "contract":
        {
            "name":"Blue Terra Leasing Agreement",
            "uri":"https://leases.blueterra.land/0/ftx",
            "type":"Perpetual Lease",
            "description":"A Blue Terra NFT allows its holder the right to claim the Blue Terra plot of land specified in the uri field.",
            "created":"2022-02-25 05:25:20.574631"
        }
}
```
