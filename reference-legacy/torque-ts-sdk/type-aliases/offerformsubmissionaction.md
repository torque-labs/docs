# Type Alias: OfferFormSubmissionAction

[**@torque-labs/torque-ts-sdk**](../) • **Docs**

***

[@torque-labs/torque-ts-sdk](../) / OfferFormSubmissionAction

## Type Alias: OfferFormSubmissionAction

```ts
type OfferFormSubmissionAction: {
  eventConfig: FormSubmissionAction;
  timeConfig: TimeConfig;
  type: EventType.FORM_SUBMISSION;
};
```

Form submission action bounty step requirements.

### Type declaration

| Name          | Type                        |
| ------------- | --------------------------- |
| `eventConfig` | `FormSubmissionAction`      |
| `timeConfig`? | `TimeConfig`                |
| `type`        | `EventType.FORM_SUBMISSION` |

### Defined in

[src/types/api.ts:456](https://github.com/torque-labs/torque-ts-sdk/blob/a30afeab92cb119627ec542f4c8aff2dd9faf383/src/types/api.ts#L456)
