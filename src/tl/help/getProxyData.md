# help.getProxyData

Get promotion info of the currently-used MTProxy

## Example

::::tabs
:::tab{title="JavaScript"}

```js
const { Api, TelegramClient } = require('telegram');
const { StringSession } = require('telegram/sessions');

const session = new StringSession('');
const client = new TelegramClient(session, apiId, apiHash, {});

(async function run() {
    const result = await client.invoke(new Api.help.getProxyData({}));
    console.log(result); // prints the result
})();
```

:::

:::tab{title="TypeScript"}

```ts
import { Api, TelegramClient } from 'telegram';
import { StringSession } from 'telegram/sessions';

const session = new StringSession('');
const client = new TelegramClient(session, apiId, apiHash, {});

(async function run() {
    const result: Api.help.ProxyData = await client.invoke(
        new Api.help.getProxyData({}),
    );
    console.log(result); // prints the result
})();
```

:::
::::

## TL schema

```txt
Method schema is available as of layer 113. Switch »
```

## Parameters

| Name | Type | Description |
| :--: | ---- | ----------- |

## Result

[help.ProxyData](https://core.telegram.org/type/help.ProxyData)

## Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

## Can bots use this method?

Yes

## Related pages
