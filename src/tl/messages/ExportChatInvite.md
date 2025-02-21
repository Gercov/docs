# messages.ExportChatInvite

Export an invite link for a chat

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
    new Api.messages.ExportChatInvite({
      peer: "username",
      legacyRevokePermanent: true,
      expireDate: 43,
      usageLimit: 43,
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

  const result: Api.ExportedChatInvite = await client.invoke(
    new Api.messages.ExportChatInvite({
      peer: "username",
      legacyRevokePermanent: true,
      expireDate: 43,
      usageLimit: 43,
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|   Name   | Type                                                  | Description |
| :------: | ----------------------------------------------------- | ----------- |
| **peer** | [InputPeer](https://core.telegram.org/type/InputPeer) | Chat        |

## Result

[ExportedChatInvite](https://core.telegram.org/type/ExportedChatInvite)

## Possible errors

| Code | Type                 | Description                                  |
| :--: | -------------------- | -------------------------------------------- |
| 400  | CHANNEL_PRIVATE      | You haven't joined this channel/supergroup   |
| 400  | CHAT_ADMIN_REQUIRED  | You must be an admin in this chat to do this |
| 400  | CHAT_ID_INVALID      | The provided chat id is invalid              |
| 403  | CHAT_WRITE_FORBIDDEN | You can't write in this chat                 |
| 400  | PEER_ID_INVALID      | The provided peer id is invalid              |

## Can bots use this method?

Yes

## Related pages
