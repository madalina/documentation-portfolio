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
*Notes:*
- *time is GMT.*
- *location is optional. The default is an empty string.*
- *reminder is optional. The default is 10 minutes.*
- *invitees is optional. The default is an empty array.*

#### Documentation example
##### Meeting request
Represents a request for a meeting in a calendar.
<table>
   <thead>
        <tr>
            <th colspan=2>Element</th>
            <th>Description</th>
            <th>Type</th>
            <th>Required</th>
            <th>Notes</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td colspan=2>meeting</td>
            <td>Top level</td>
            <td>string</td>
            <td>Required</td>
            <td />
        </tr>
        <tr>
            <td></td>
            <td>time</td>
            <td>The time of the meeting</td>
            <td>meeting object</td>
            <td>Required</td>
            <td>Time is GMT. Format is YYYY-MM-DD HH:MM:SS. </td>
        </tr>
        <tr>
            <td></td>
            <td>duration</td>
            <td>The duration of the meeting in minutes</td>
            <td>number</td>
            <td>Required</td>
            <td>Example: 60 </td>
        </tr>
        <tr>
            <td></td>
            <td>location</td>
            <td>The location of the meeting </td>
            <td>string</td>
            <td>Optional</td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td>description</td>
            <td>The description of the meeting </td>
            <td>string</td>
            <td>Required</td>
            <td>Default: ""</td>
        </tr>
        <tr>
            <td></td>
            <td>reminder</td>
            <td>A reminder for the meeting in minutes</td>
            <td>number</td>
            <td>Optional</td>
            <td>Default: 10</td>
        </tr>
        <tr>
            <td></td>
            <td>invitees</td>
            <td>List of invitees emails</td>
            <td>array</td>
            <td>Optional</td>
            <td>Default: []</td>
        </tr>
    </tbody>
</table>

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
<table>
   <thead>
        <tr>
            <th colspan=2>Element</th>
            <th>Description</th>
            <th>Type</th>
            <th>Required</th>
            <th>Notes</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td colspan=2>comment</td>
            <td>Top level</td>
            <td>comment data object</td>
            <td>Required</td>
            <td />
        </tr>
        <tr>
            <td></td>
            <td>userId</td>
            <td>The id of the user making the comment</td>
            <td>string</td>
            <td>Required</td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td>discussionId</td>
            <td>The ID of the discussion that is being commented on</td>
            <td>number</td>
            <td>Required</td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td>time</td>
            <td>The time the comment was posted </td>
            <td>string</td>
            <td>Optional</td>
            <td>Time is GMT. Format is YYYY-MM-DD HH:MM:SS. Default is the time the comment is received by the server.</td>
        </tr>
        <tr>
            <td></td>
            <td>text</td>
            <td>The text of the comment </td>
            <td>string</td>
            <td>Required</td>
            <td></td>
        </tr>
    </tbody>
</table>


## 3. Describing a song

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
