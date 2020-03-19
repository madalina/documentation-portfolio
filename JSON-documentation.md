## Describing a song

JSON Example:
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

Documentation example:

Element | Description | Type | Notes
------ | ---------- | --- | ----
song | Top level | song data type 
&nbsp;&nbsp;&nbsp;title | Song title | string
&nbsp;&nbsp;&nbsp;artist | Artist name | string
&nbsp;&nbsp;&nbsp;musicians | A list of musicians playing the song | array of string

## Describing a menu
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

| Element | Description | Type |
| ---     | ---         | ---  |
| menu | Top level | array of menu items |
| &nbsp; &nbsp; &nbsp; header | The name of the header | string |
| &nbsp; &nbsp; &nbsp; items | A list of menu items in the header menu | array of menu items |
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; id | The id of the menu item | string |
| &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; label | The label that is displayed in the user interface | string |

## Describing a comment object
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

| Element | Description | Type | Required | Notes |
| ---     | ---         | ---  | --- | --- |
| comment | Top level | comment data object | Required | |
| &nbsp; &nbsp; &nbsp; userId | The id of the user making the comment | string | Required | |
| &nbsp; &nbsp; &nbsp; discussionId | The ID of the discussion that is being commented on | number | Required | |
| &nbsp; &nbsp; &nbsp; time | The time the comment was posted | string | Optional |Time is GMT. Format is YYYY-MM-DD HH:MM:SS. Default is the time the comment is received by the server. |
| &nbsp; &nbsp; &nbsp; text | The text of the comment | string | Required | |
