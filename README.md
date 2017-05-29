### Facebook
##### Incoming
```
{
  "object": "page",
  "entry": [
    {
      "id": "247349599062786",
      "time": 1492541234486,
      "messaging": [
        {
          "sender": {
            "id": "1846048872078817"
          },
          "recipient": {
            "id": "247349599062786"
          },
          "timestamp": 1492541234394,
          "message": {
            "mid": "mid.$cAAC6AFgUYTphs6kk2lbgmPaOon0R",
            "seq": 3915,
            "text": "hello27"
          }
        }
      ]
    }
  ]
}

```

```
{
  "object": "page",
  "entry": [
    {
      "id": "247349599062786",
      "time": 1492543965181,
      "messaging": [
        {
          "sender": {
            "id": "247349599062786"
          },
          "recipient": {
            "id": "1846048872078817"
          },
          "timestamp": 1492543964062,
          "message": {
            "is_echo": true,
            "app_id": 276959789397329,
            "mid": "mid.$cAAC6AFgUYTphs9LLnlbgo2DBtZsK",
            "seq": 4293,
            "text": "echo text"
          }
        }
      ]
    }
  ]
}
```

##### outgoing

```
{
   "raw":{
      "access_token":"PAGE_ACCESS_TOKEN",
      "message":{
         "text":"hellow, world!"
      },
      "recipient":{
         "id":"USER_ID"
      }
   }
}
```

### Telegram
##### incoming
```
{
   "update_id":596819141,
   "message":{
      "message_id":27,
      "from":{
         "id":161696362,
         "first_name":"Kuan-Hung",
         "username":"godgunman"
      },
      "chat":{
         "id":161696362,
         "first_name":"Kuan-Hung",
         "username":"godgunman",
         "type":"private"
      },
      "date":1492511288,
      "text":"new10"
   }
} 
```

```
{
  "update_id": 596819144,
  "message": {
    "message_id": 33,
    "from": {
      "id": 161696362,
      "first_name": "Kuan-Hung",
      "username": "godgunman"
    },
    "chat": {
      "id": 161696362,
      "first_name": "Kuan-Hung",
      "username": "godgunman",
      "type": "private"
    },
    "date": 1492511686,
    "sticker": {
      "width": 512,
      "height": 512,
      "emoji": "🤔",
      "thumb": {
        "file_id": "AAQEABOeriQZAARMKj66ZEki3YI_AAIC",
        "file_size": 2888,
        "width": 128,
        "height": 128
      },
      "file_id": "CAADBAADJwEAAioAATAAAZJFQzIqdXOOAg",
      "file_size": 13076
    }
  }
}
```
##### outgoing
* [https://core.telegram.org/bots/api#sendmessage](telegram bot api)

```
  request({
    url: TELEGRAM_API_URL_ROOT + `/bot${apiToken}/sendMessage`,
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
    },
    body: {
      chat_id: chatId,
      text: '```\n' + JSON.stringify(data, null, 2) + '\n```',
      parse_mode: 'Markdown'
    },
    json: true,
  }, (error, response) => {
    if (error) return console.log(error);
    return console.log(response.body);
  });

```


### LINE
https://devdocs.line.me/en/#webhook-event-object
#### incoming
```
{
   "events":[
      {
         "type":"message",
         "replyToken":"6a37af4d99a94ce9bbe9184171398b70",
         "source":{
            "userId":"Uc76d8ae9ccd1ada4f06c4e1515d46466",
            "type":"user"
         },
         "timestamp":1492439626890,
         "message":{
            "type":"text",
            "id":"5952264121603",
            "text":"hello"
         }
      }
   ]
}
```
```
{
   "events":[
      {
         "type":"message",
         "replyToken":"cb09ce63e45e43f99a3191be83b27947",
         "source":{
            "userId":"Uc76d8ae9ccd1ada4f06c4e1515d46466",
            "type":"user"
         },
         "timestamp":1492439636888,
         "message":{
            "type":"sticker",
            "id":"5952265086769",
            "stickerId":"7740268",
            "packageId":"1190379"
         }
      }
   ]
}
```
```
{
   "events":[
      {
         "type":"message",
         "replyToken":"2a42a286a2f842668c9552c4e779ebe4",
         "source":{
            "userId":"Uc76d8ae9ccd1ada4f06c4e1515d46466",
            "type":"user"
         },
         "timestamp":1492439666056,
         "message":{
            "type":"image",
            "id":"5952267910855"
         }
      }
   ]
}
```
#### outgoing

https://devdocs.line.me/en/?shell#reply-message
```
    request({
      url: LINE_API_URL_ROOT + '/message/reply',
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        'Authorization': `Bearer ${CHANNEL_ACCESS_TOKEN}`,
      },
      body: {
        replyToken,
        messages: [{
          type: 'text',
          text: JSON.stringify(data),
        }],
      },
      json: true,
    }, (error, response) => {
      if (error) return console.log(error);
      return console.log(response.body);
    });
```
