# TorqueContextValue

[**@torque-labs/react**](../)

***

[@torque-labs/react](../) / TorqueContextValue

## Interface: TorqueContextValue

Defined in: [react/src/context.tsx:11](https://github.com/torque-labs/monorepo/blob/2ebf07140779767733d669c69d4b6e369a4193c3/packages/react/src/context.tsx#L11)

The TorqueContextValue interface defines the value of the TorqueContext.

### Properties

| Property                   | Type                                                                           | Description                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------- |
| `authenticate`             | (`authInput`?: `TorqueAuthInput`, `signInUrl`?: `string`) => `Promise`<`void`> | Authenticates the user with the Torque SDK                                      |
| `connectModalOpen`         | `boolean`                                                                      | The state of the connect modal                                                  |
| `currentUser?`             | `UserWithConnectedAccounts`                                                    | The current user                                                                |
| `isAuthenticated`          | `boolean`                                                                      | Flag indicating if the user is authenticated. (same as initialized)             |
| `isLoading`                | `boolean`                                                                      | Whether the Torque SDK is loading                                               |
| `isVerified`               | `boolean`                                                                      | Flag indicating if the user is verified                                         |
| `logout`                   | (`disconnect`?: `boolean`) => `Promise`<`void`>                                | Logout the user from the Torque SDK                                             |
| `setConnectModalOpen`      | `Dispatch`<`SetStateAction`<`boolean`>>                                        | Set the visibility of the wallet connect modal                                  |
| `setUseTransactionForAuth` | `Dispatch`<`SetStateAction`<`boolean`>>                                        | Set the flag whether to use transactions for authentication                     |
| `torque`                   | `TorqueSDK`                                                                    | The Torque SDK instance                                                         |
| `useTransactionForAuth`    | `boolean`                                                                      | Flag to set if the user should use transactions for authentication (eg. Ledger) |
| `wallet?`                  | `Adapter` \| `PrivySolanaWallet`                                               | The wallet adapter instance                                                     |
