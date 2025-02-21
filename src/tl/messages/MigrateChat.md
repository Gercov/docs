# messages.MigrateChat

Turn a [legacy group into a supergroup](https://core.telegram.org/api/channel)

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
    new Api.messages.MigrateChat({
      chatId: 43,
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

  const result: Api.Updates = await client.invoke(
    new Api.messages.MigrateChat({
      chatId: 43,
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|    Name    | Type                                      | Description             |
| :--------: | ----------------------------------------- | ----------------------- |
| **chatId** | [int](https://core.telegram.org/type/int) | Legacy group to migrate |

## Result

[Updates](https://core.telegram.org/type/Updates)

## Possible errors

| Code | Type                | Description                                  |
| :--: | ------------------- | -------------------------------------------- |
| 403  | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this |
| 400  | CHAT_ID_INVALID     | The provided chat id is invalid              |
| 400  | PEER_ID_INVALID     | The provided peer id is invalid              |

## Can bots use this method?

No

## Related pages

#### [Channels](https://core.telegram.org/api/channel)

How to handle channels, supergroups, groups, and what's the difference between them.
