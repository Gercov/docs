# messages.DeleteHistory

Delete the history of a [supergroup](https://core.telegram.org/api/channel)

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
    new Api.messages.DeleteHistory({
      peer: "username",
      maxId: 0,
      justClear: true,
      revoke: true,
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

  const result: Api.messages.AffectedHistory = await client.invoke(
    new Api.messages.DeleteHistory({
      peer: "username",
      maxId: 0,
      justClear: true,
      revoke: true,
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|    Name     | Type                                                        | Description                                                                       |
| :---------: | ----------------------------------------------------------- | --------------------------------------------------------------------------------- |
| **channel** | [InputChannel](https://core.telegram.org/type/InputChannel) | [Supergroup](https://core.telegram.org/api/channel) whose history must be deleted |
|  **maxId**  | [int](https://core.telegram.org/type/int)                   | ID of message **up to which** the history must be deleted                         |

## Result

[Bool](https://core.telegram.org/type/Bool)

## Possible errors

| Code | Type            | Description                                |
| :--: | --------------- | ------------------------------------------ |
| 400  | CHANNEL_INVALID | The provided channel is invalid            |
| 400  | CHANNEL_PRIVATE | You haven't joined this channel/supergroup |

## Can bots use this method?

No

## Related pages

#### [Channels](https://core.telegram.org/api/channel)

How to handle channels, supergroups, groups, and what's the difference between them.
