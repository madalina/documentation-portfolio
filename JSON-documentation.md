## 1. Describing a meeting request
#### Original requirements
```
{
 "meeting" : {
    "time": "2015-09-01 10:00",
    "duration": 60,
    "description": "2016 Strategic Planning Meeting",
    "location": "Building 23, Room 206",
    "reminder": 15,
    "invitees": ["michael@example.com", "thelma@example.com", "david@example.com", "leon@example.com"]
             }
}
```
_Notes:
• time is GMT.
• location is optional. The default is an empty string.
• reminder is optional. The default is 10 minutes.
• invitees is optional. The default is an empty array._

#### Meeting request
Represents a request for a meeting in a calendar.
| Element | Description | Type | Required | Notes |
| ---     | ---         | ---  | --- | --- |
| meeting | Top level | meeting object | Required | |
| &nbsp; &nbsp; &nbsp; time | The time of the meeting | string | Required |Time is GMT. Format is `YYYY-MM-DD HH:MM:SS`. |
| &nbsp; &nbsp; &nbsp; duration | The duration of the meeting in minutes | number | Required | Example: `60` |
| &nbsp; &nbsp; &nbsp; description | The description of the meeting | string | Required | |
| &nbsp; &nbsp; &nbsp; location | The location of the meeting | string | Optional | Default: `""` |
| &nbsp; &nbsp; &nbsp; reminder | A reminder for the meeting in minutes | number | Optional | Default: `10` |
| &nbsp; &nbsp; &nbsp; invitees | List of invitees emails | array | Optional | Default: `[]` |



## 2. Describing a menu
#### Original menu JSON
```
{
"menu": [ 
   {  "header": "File",
    "items": [
        {"id": "Open", "label": "Open"},
        {"id": "New", "label": "New"},
        {"id": "Close", "label": "Close"}
    ] },
   { "header": "View",
    "items": [
        {"id": "ZoomIn", "label": "Zoom In"},
        {"id": "ZoomOut", "label": "Zoom Out"},
        {"id": "OriginalView", "label": "Original View"}
   ]}
]}
```
#### Menu description
| Element | Description | Type |
| ---     | ---         | ---  |
| menu | Top level | array of menu items |
| &nbsp; &nbsp; &nbsp; header | The name of the header | string |
| &nbsp; &nbsp; &nbsp; items | A list of menu items in the header menu | array of menu items |
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; id | The id of the menu item | string |
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; label | The label that is displayed in the user interface | string |

## 3. Describing a comment object
#### JSON comment example
```
{
   "comment":  {
      "userId": "pgruenbaum",
      "discussionId": 964564445654,
      "time": "2015-02-28 10:04:32",
      "text": "Well said, Barbara!"
   }
}
```
#### Documentation example
| Element | Description | Type | Required | Notes |
| ---     | ---         | ---  | --- | --- |
| comment | Top level | comment data object | Required | |
| &nbsp; &nbsp; &nbsp; userId | The id of the user making the comment | string | Required | |
| &nbsp; &nbsp; &nbsp; discussionId | The ID of the discussion that is being commented on | number | Required | |
| &nbsp; &nbsp; &nbsp; time | The time the comment was posted | string | Optional |Time is GMT. Format is YYYY-MM-DD HH:MM:SS. Default is the time the comment is received by the server. |
| &nbsp; &nbsp; &nbsp; text | The text of the comment | string | Required | |

## Describing a song

#### JSON song Example
```
{
"song":
   {
      "title": "Hey Jude",
      "artist": "The Beatles",
      "musicians": 
         ["John Lennon", "Paul McCartney", 
             "George Harrison", "Ringo Starr"]
   }
}
```

#### Documentation example

Element | Description | Type | Notes
------ | ---------- | --- | ----
song | Top level | song data type 
&nbsp;&nbsp;&nbsp;title | Song title | string
&nbsp;&nbsp;&nbsp;artist | Artist name | string
&nbsp;&nbsp;&nbsp;musicians | A list of musicians playing the song | array of string
