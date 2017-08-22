# Methods

## init

Initializes the chat window.

```js
import { init } from "@livechat/livechat-visitor-api";

const visitorApi = init({
    license: 123,
    group: 0,
})
```

#### Parameters:

| param   | type   | description              |
| ------- | ------ | ------------------------ |
| license | number | LiveChat license number  |
| group   | number | Group number (default: 0) |

## sendMessage

Sends a message.

```js
visitorApi.sendMessage({
    text: "Hello",
    customId: 123423215
})
    .then((response) => {
        console.log(response)
    })
    .catch((error) => {
        console.log(error)
    })
```

#### Parameters:

| param    | type   | description          |
| -------- | ------ | -------------------- |
| text     | string | Visitor message text |
| customId | string | Message custom id    |

#### Errors:

| type             | reason                               |
| ---------------- | ------------------------------------ |
| connection       | "Request failed"                     |
| missing argument | "Missing text or customId parameter" |

## sendFile - not implemented yet

Enables [file sharing](https://www.livechatinc.com/features/chat-tools/#File-sharing) through the chat window.

```js
visitorApi.sendFile({
    file: FileObject,
    customId: 123423215
})
    .then((response) => {
        console.log(response.status)
    })
    .catch((error) => {
        console.log(error)
    })
```

#### Parameters:

| param      | type   | description    |
| ---------- | ------ | -------------- |
| file       | file   | File to upload |
| customId   | string | custom file id |


## rateChat - not implemented yet

Enables [chat ratings](https://www.livechatinc.com/features/getting-feedback/#Chat-ratings).

```js
visitorApi.rateChat({
    rate: "good",
    comment: "Agent helped me a lot!"
})
```

#### Parameters:

| param   | type                      | description                  |
| ------- | ------------------------- | ---------------------------- |
| rate    | "good" \| "bad" \| "none" | Rate type                    |
| comment | string                    | Rate comment text (optional) |



## markMessageAsSeen - not implemented yet

Marks a message as Seen.

Learn more about LiveChat delivery statuses [here](https://www.livechatinc.com/features/chat-tools/#Delivery-status).

```js
visitorApi.markMessageAsSeen({
    messageId: "123123123",
})
```

#### Parameters:

| param     | type   | description                        |
| --------- | ------ | ---------------------------------- |
| messageId | string | Id of message to be marked as seen |



## setSneakPeek - not implemented yet

Enables [sneak peeks](https://www.livechatinc.com/features/chat-tools/#Message-sneak-peak) to see what the visitor is typing in before they actually send the message.

```js
visitorApi.setSneakPeek({
    message: "Hello, I woul",
})
```

#### Parameters:

| param   | type   | description                |
| ------- | ------ | -------------------------- |
| message | string | Current message input text |

**Note:** Sneak peek won't be sent every time you call a function. It will be throttled (i.e. sent not earlier than 300ms after the last sneak peek request).


## forwardChatTranscript - not implemented yet

Sends [chat transcripts](https://www.livechatinc.com/features/chat-tools/#Chat-tools-other-features) to the specified email address when the chat is ended.

```js
visitorApi.forwardChatTranscript({
    email: "test@livechatinc.com",
})
```

#### Parameters:

| param | type   | description                                                                |
| ----- | ------ | -------------------------------------------------------------------------- |
| email | string | Email that will automatically receive a transcript when a chat is finished |


## sendTicketForm - not implemented yet

Gathers the [data](https://www.livechatinc.com/features/engaging-customers/#Ticket-form) collected from a customer.

```js
visitorApi.sendTicketForm(form)
```


## sendPrechatForm - not implemented yet

Collects the pre-chat form information (it will be visible during the chat and in the archives).

```js
visitorApi.sendPrechatForm(form)
```

## sendPostchatForm - not implemented yet

Collects the [post-chat form](https://www.livechatinc.com/features/getting-feedback/#Post-chat-surveys) information (it will be visible in the archives).

```js
visitorApi.sendPostchatForm(form)
```


## getVisitorData - not implemented yet

Collects the [visitor information](https://www.livechatinc.com/features/chat-tools/#Visitor-information).

```js

const visitorData = visitorApi.getVisitorData()
```

#### Returned value: 

| param            | type   | description                                                               |
| ---------------- | ------ | ------------------------------------------------------------------------- |
| name             | string | Visitor's name                                                            |
| email            | string | Visitor's email address                                                   |
| pageUrl          | string | Visitor's currently visiting website URL                                  |
| pageTitle        | string | Visitor's currently visiting website title                                |
| customProperties | object | Visitor's additional data object (custom properties) |

## setVisitorData
```js
visitorApi.setVisitorData({
    name: "Wynton Marsalis",
    email: "test@livechatinc.com",
    pageUrl: 'http://example.org/pricing',
    pageTitle: 'Pricing'
})
```

#### Parameters:

| param            | type   | description                                                               |
| ---------------- | ------ | ------------------------------------------------------------------------- |
| name             | string | Visitor's name                                                            |
| email            | string | Visitor's email address                                                   |
| url              | string | Visitor's currently visiting website URL                                  |
| customProperties | object | Not implemented yet: Visitor's additional data object (custom properties) |

#### Errors:

| type             | reason                                         |
| ---------------- | ---------------------------------------------- |
| missing argument | "Missing name, email, url or customProperties" |

