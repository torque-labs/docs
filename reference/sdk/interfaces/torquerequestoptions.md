# TorqueRequestOptions

[**@torque-labs/sdk**](../)

***

[@torque-labs/sdk](../) / TorqueRequestOptions

## Interface: TorqueRequestOptions

Defined in: [sdk/src/utils/requests.ts:9](https://github.com/torque-labs/monorepo/blob/2ebf07140779767733d669c69d4b6e369a4193c3/packages/sdk/src/utils/requests.ts#l9)

Interface for the Torque SDK request options

### Properties

| Property   | Type                                           | Description                             |
| ---------- | ---------------------------------------------- | --------------------------------------- |
| `apiKey?`  | `string`                                       | The API key for the request             |
| `body?`    | `unknown`                                      | The body of the request (if applicable) |
| `headers?` | `HeadersInit`                                  | The headers for the request             |
| `method`   | `"POST"` \| `"GET"` \| `"PATCH"` \| `"DELETE"` | The HTTP method of the request          |
| `token?`   | `string`                                       | The auth token for the request          |
| `url`      | `string`                                       | The URL of the request                  |
