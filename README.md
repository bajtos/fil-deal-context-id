# fil-deal-context-id
Calculate IPNI ContextID for Filecoin StorageMarket deals

## Conclusion: this is not feasible

See https://github.com/filecoin-station/fil-deal-context-id/pull/1#discussion_r1415561688:

It turns out that Boost computes the Context ID from `market.ClientDealProposal` containing two fields: `Proposal` and `ClientSignature` ([source code](https://github.com/filecoin-project/boost/blob/ca748c3c6916449524921efc8389f9b3898361fe/indexprovider/wrapper.go#L168-L172), see also the screenshot below).

Unfortunately, the data provided in `StateMarketDeals.json.zst` by Glif (presumably a snapshot of Lotus’ method [StateMarketDeals](https://lotus.filecoin.io/reference/lotus/state/#statemarketdeals)) contains only the `Proposal` but not the `ClientSignature`.

<img width="874" alt="Screenshot 2024-02-14 at 15 36 29" src="https://github.com/filecoin-station/fil-deal-context-id/assets/1140553/52c992e2-7cc7-4058-bc64-e5200fb6e518">
