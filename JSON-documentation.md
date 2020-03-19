## Simple song

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