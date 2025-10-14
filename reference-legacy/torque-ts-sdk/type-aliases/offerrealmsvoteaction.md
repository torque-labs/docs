# Type Alias: OfferRealmsVoteAction

[**@torque-labs/torque-ts-sdk**](../) • **Docs**

***

[@torque-labs/torque-ts-sdk](../) / OfferRealmsVoteAction

## Type Alias: OfferRealmsVoteAction

```ts
type OfferRealmsVoteAction: {
  eventConfig: RealmsVoteAction;
  timeConfig: TimeConfig;
  type: EventType.REALMS_VOTE;
};
```

Realms DAO vote action bounty step requirements.

### Type declaration

| Name          | Type                    |
| ------------- | ----------------------- |
| `eventConfig` | `RealmsVoteAction`      |
| `timeConfig`? | `TimeConfig`            |
| `type`        | `EventType.REALMS_VOTE` |

### Defined in

[src/types/api.ts:402](https://github.com/torque-labs/torque-ts-sdk/blob/a30afeab92cb119627ec542f4c8aff2dd9faf383/src/types/api.ts#L402)
