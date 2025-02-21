# account.SetAccountTTL

Set account self-destruction period

## Example

::::tabs
:::tab{title="JavaScript"}

```js
const { Api, TelegramClient } = require("telegram");
const { StringSession } = require("telegram/sessions");

const session = new StringSession(""); // You should put your string session here
const client = new TelegramClient(session, apiId, apiHash, {});

(async function run() {
  await client.connect(); // This assumes you have already authenticated with .start()

  const result = await client.invoke(
    new Api.account.SetAccountTTL({
      ttl: new Api.AccountDaysTTL({
        days: 43,
      }),
    })
  );
  console.log(result); // prints the result
})();
```

:::

:::tab{title="TypeScript"}

```ts
import { Api, TelegramClient } from "telegram";
import { StringSession } from "telegram/sessions";

const session = new StringSession(""); // You should put your string session here
const client = new TelegramClient(session, apiId, apiHash, {});

(async function run() {
  await client.connect(); // This assumes you have already authenticated with .start()

  const result: Api.Bool = await client.invoke(
    new Api.account.SetAccountTTL({
      ttl: new Api.AccountDaysTTL({
        days: 43,
      }),
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|  Name   | Type                                                            | Description          |
| :-----: | --------------------------------------------------------------- | -------------------- |
| **ttl** | [AccountDaysTTL](https://core.telegram.org/type/AccountDaysTTL) | Time to live in days |

## Result

[Bool](https://core.telegram.org/type/Bool)

## Possible errors

| Code | Type             | Description                 |
| :--: | ---------------- | --------------------------- |
| 400  | TTL_DAYS_INVALID | The provided TTL is invalid |

## Can bots use this method?

No

## Related pages
