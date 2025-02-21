# messages.EditChatAdmin

Make a user admin in a [legacy group](https://core.telegram.org/api/channel).

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
    new Api.messages.EditChatAdmin({
      chatId: 43,
      userId: "username",
      isAdmin: false,
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
    new Api.messages.EditChatAdmin({
      chatId: 43,
      userId: "username",
      isAdmin: false,
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|    Name     | Type                                                  | Description               |
| :---------: | ----------------------------------------------------- | ------------------------- |
| **chatId**  | [int](https://core.telegram.org/type/int)             | The ID of the group       |
| **userId**  | [InputUser](https://core.telegram.org/type/InputUser) | The user to make admin    |
| **isAdmin** | [Bool](https://core.telegram.org/type/Bool)           | Whether to make him admin |

## Result

[Bool](https://core.telegram.org/type/Bool)

## Possible errors

| Code | Type                 | Description                                    |
| :--: | -------------------- | ---------------------------------------------- |
| 400  | CHAT_ID_INVALID      | The provided chat id is invalid                |
| 400  | PEER_ID_INVALID      | The provided peer id is invalid                |
| 400  | USER_ID_INVALID      | The provided user ID is invalid                |
| 400  | USER_NOT_PARTICIPANT | You're not a member of this supergroup/channel |

## Can bots use this method?

No

## Related pages

#### [Channels](https://core.telegram.org/api/channel)

How to handle channels, supergroups, groups, and what's the difference between them.
