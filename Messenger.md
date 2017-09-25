# Messenger

## Incoming

- [Content Types](#content-type)
   - [Text](#text)
   - [Audio](#audio)
   - [Image](#image)
   - [Video](#video)
   - [File](#file)
- [Templates](#templates)
- [Buttons](#buttons)
- [Quick Replies](#quick-replies)
- [Sender Actions](#sender-actions)

### Content Types

- [Text](#text)
- [Audio](#audio)
- [Image](#image)
- [Video](#video)
- [File](#file)

#### Text
```json
{
  "object": "page",
  "entry": [
    {
      "id": "247349599062786",
      "time": 1492541234486,
      "messaging": [
        {
          "recipient":{
            "id":"USER_ID"
          },
          "message":{
            "text":"hello, world!"
          }
        }
      ]
    }
  ]
}
```

#### Audio
```json
{
  "object": "page",
  "entry": [
    {
      "id": "247349599062786",
      "time": 1492541234486,
      "messaging": [
         {
            "recipient":{
               "id":"USER_ID"
            },
            "message":{
               "attachment":{
                  "type":"audio",
                  "payload":{
                    "url":"https://petersapparel.com/bin/clip.mp3"
                  }
               }
            }
         }
      ]
    }
  ]
}
```

#### Image
```json
{
  "object": "page",
  "entry": [
    {
      "id": "247349599062786",
      "time": 1492541234486,
      "messaging": [
         {
            "recipient":{
               "id":"USER_ID"
            },
            "message":{
               "attachment":{
                  "type":"image",
                  "payload":{
                     "url":"https://petersapparel.com/img/shirt.png"
                  }
               }
            }
         }
      ]
    }
  ]
}
```

#### Video
```json
{
  "object": "page",
  "entry": [
    {
      "id": "247349599062786",
      "time": 1492541234486,
      "messaging": [
         {
            "recipient":{
               "id":"USER_ID"
            },
            "message":{
               "attachment":{
                  "type":"video",
                  "payload":{
                    "url":"https://petersapparel.com/bin/clip.mp4"
                  }
               }
            }
         }
      ]
    }
  ]
}
```

#### File
```json
{
  "object": "page",
  "entry": [
    {
      "id": "247349599062786",
      "time": 1492541234486,
      "messaging": [
         {
            "recipient":{
               "id":"USER_ID"
            },
            "message":{
               "attachment":{
                  "type":"file",
                  "payload":{
                     "url":"https://petersapparel.com/bin/report.pdf"
                  }
               }
            }
         }
      ]
    }
  ]
}
```


### Templates

```json
{
  "object": "page",
  "entry": [
    {
      "id": "247349599062786",
      "time": 1492541234486,
      "messaging": [
         {
            "recipient":{
               "id":"USER_ID"
            },
            "message":{
               "attachment":{
                  "type":"template",
                  "payload":{
                     "template_type":"button",
                     "text":"What do you want to do next?",
                     "buttons":[
                        {
                           "type":"web_url",
                           "url":"https://www.messenger.com",
                           "title":"Visit Messenger"
                        },
                        {
                           "type":"web_url",
                           "url":"https://www.messenger.com",
                           "title":"Visit Messenger"
                        }
                     ]
                  }
               }

            }
         }
      ]
    }
  ]
}
```

### Buttons
```json
{
  "object": "page",
  "entry": [
    {
      "id": "247349599062786",
      "time": 1492541234486,
      "messaging": [
         {
            "recipient":{
               "id":"USER_ID"
            },
            "message":{
               "buttons":[
                  {
                     "type":"web_url",
                     "url":"https://petersfancyapparel.com/criteria_selector",
                     "title":"Select Criteria",
                     "webview_height_ratio": "full",
                     "messenger_extensions": true,  
                     "fallback_url": "https://petersfancyapparel.com/fallback"
                  }
               ]
            }
         }
      ]
    }
  ]
}
```

### Quick Replies

```json
{
  "object": "page",
  "entry": [
    {
      "id": "247349599062786",
      "time": 1492541234486,
      "messaging": [
         {
            "recipient":{
               "id":"USER_ID"
            },
            "message":{
               "quick_replies":[
                  {
                     "content_type":"text",
                     "title":"Red",
                     "image_url":"http://example.com/img/red.png",
                     "payload":"DEVELOPER_DEFINED_PAYLOAD_FOR_PICKING_RED"
                  }
               ]
            }
         }
      ]
    }
  ]
}
```

### Sender Actions

```json
{
  "object": "page",
  "entry": [
    {
      "id": "247349599062786",
      "time": 1492541234486,
      "messaging": [
         {
            "recipient":{
               "id":"USER_ID"
            },
            "sender_action":"typing_on"
         }
      ]
    }
  ]
}
```

