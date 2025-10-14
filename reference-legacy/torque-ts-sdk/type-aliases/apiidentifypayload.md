# Type Alias: ApiIdentifyPayload

[**@torque-labs/torque-ts-sdk**](../) • **Docs**

***

[@torque-labs/torque-ts-sdk](../) / ApiIdentifyPayload

## Type Alias: ApiIdentifyPayload

```ts
type ApiIdentifyPayload: {
  payload: {
     expirationTime: string;
     issuedAt: string;
     statement: string;
    };
};
```

Payload returned from the API as a sample payload for sign in.

### Type declaration

| Name                     | Type                                                                         |
| ------------------------ | ---------------------------------------------------------------------------- |
| `payload`                | { `expirationTime`: `string`; `issuedAt`: `string`; `statement`: `string`; } |
| `payload.expirationTime` | `string`                                                                     |
| `payload.issuedAt`       | `string`                                                                     |
| `payload.statement`      | `string`                                                                     |

### Defined in

[src/types/api.ts:226](https://github.com/torque-labs/torque-ts-sdk/blob/a30afeab92cb119627ec542f4c8aff2dd9faf383/src/types/api.ts#L226)
