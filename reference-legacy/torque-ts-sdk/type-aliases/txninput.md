# Type Alias: TxnInput

[**@torque-labs/torque-ts-sdk**](../) • **Docs**

***

[@torque-labs/torque-ts-sdk](../) / TxnInput

## Type Alias: TxnInput

```ts
type TxnInput: {
  data: CreateCampaignInputSchema;
  txnType: CampaignCreate;
 } | {
  data: CampaignEndInputSchema;
  txnType: CampaignEnd;
 } | {
  data: PublisherCreateInputSchema;
  txnType: PublisherCreate;
 } | {
  data: PublisherPayoutInputSchema;
  txnType: PublisherPayout;
};
```

On-chain transaction build input

### Defined in

[src/types/transactions.ts:30](https://github.com/torque-labs/torque-ts-sdk/blob/a30afeab92cb119627ec542f4c8aff2dd9faf383/src/types/transactions.ts#L30)
