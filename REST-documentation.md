# Snippets of REST documentation 
## 1. Reference documentation of an API for a dating service
This is the documentation for a service called SoundDate, for people who care about how their dates sound, not how they look. 

This is the provided information needed to document 2 requests and the error codes:
- request for a user to upload a sound file to their own profile and 
- request to get information on sound files for another users’s profile
- error codes

### Description: Uploading a Sound File to the current User’s Profile
Here's the information from the development team:
1. The server address is https://api.sounddate.com
2. The resource is /profile/sound
3. The method is POST
4. There are three headers:
    a. Bearer has the access token. Required.
    b. Content-Type has the sound file format, which can be either audio/mpeg for mp3 files or audio/x-wav for wav files. Default is audio/mpeg.
    c. Accept has the response format, which can be application/xml or application/json. Default is JSON.
5. The POST body is the sound file
6. The sound file must be 5 minutes or shorter.
7. The response has only two elements:
    a. id: An integer, which is the ID of the new sound file
    b. length: A float, which is the length of the sound file, in seconds
8. Don’t put in a Status and Errors table. We’ll have one for the entire documentation set

### Documentation: Uploading a Sound File to the current User’s Profile

### `POST /sound`
Uploads a sound file for the user's profile.

##### URL
```POST https://api.sounddate.com/profile/sound```

##### Headers
| Header Name | Description | Required | Notes |
| ---         | ---         | ---      | ---   |
| Bearer | Access token | Required | |
| Content-Type | Contains the sound file format | Optional | `audio/mpeg` for mp3 files or `audio/x-wav` for wav files. Default is `audio/mpeg`. |
| Accept | The response format | Optional |  `application/xml` or `application/json`. Default is `application/json`.

##### POST or PUT body
The sound file
**Note**: the sound file must be 5 minutes or shorter.

##### Sample request
```
POST https://api.sounddate.com/profile/sound
Bearer: {access token}
Content-Type: audio/mpeg
Accept: application/json
{sound file}
```

##### Response
| Element | Description | Type | Notes |
| ---     | ---         | ---  | ---   |
| id | The ID of the new sound file | integer |
| length | The length of the sound file, in seconds. | float |

##### Sample response
```
{
    "id": 1234,
    "length": 20.3
}
```
### Description: Retrieving Sound File Information for a User
Here's the information from the development team:
1. The server address is https://api.sounddate.com
2. The resource is /user/{user id}/profile/sound.
3. The method is GET
4. There are two headers:
    a. Bearer has the access token. Required.
    b. Accept has the response format, which can be application/xml or application/json. Default is JSON.
5. There is one query parameter called sortOrder. This determines the order that the sound files are returned. It has four possible values:
    a. mostRecent, sorts most recent to earliest
    b. earliest, sorts earliest to most recent
    c. shortest, sorts shortest to longest
    d. longest, sorts longest to shortest
6. The sortOrder parameter is optional. The default is mostRecent.
7. Here’s a sample response:
```
{
 "soundFiles": [
 {
 "id": 23456,
 "url": "https://api.sounddate.com/profile/sound/23456.mp3",
 "length": 11.2
 },
 {
 "id": 24559,
 "url": "https://api.sounddate.com/profile/sound/24559.mp3",
 "length": 19.8
 }
 ]
}
```

### Documentation: Retrieving Sound File Information for a User
### `GET /sound`
Retrieves a list of profile sound file URLs and their lengths for the specified user.

##### URL
```GET https://api.sounddate.com/user/{userId}/profile/sound```
where `userId` is the ID of the specified user.

#### Query parameters
| Parameter | Description | Type | Required | Notes |
| ---     | ---         | ---  | ---   | --- |
| sortOrder | The order in which the sound files are returned. | string | Optional | Valid values: `mostRecent`, `earliest`, `shortest`,`longest`. Default is `mostRecent`.

**Note:**
- `mostRecent` returns the most recent sound files to the earliest.
- `earliest` returns the earliest sound files to the most recent.
- `shortest` returns the shortest sound files to longest.
- `longest` returns the longest sound files to the shortest.


##### Headers
| Header Name | Description | Required | Notes |
| ---         | ---         | ---      | ---   |
| Bearer | Access token | Required | |
| Accept | The format of the response | Optional |  `application/xml` or `application/json`. Default is `application/json`.

##### Sample request
```
GET https://api.sounddate.com/user/1234/profile/sound?sortOrder=shortest
Bearer: {access token}
Accept: application/json
```
##### Response
| Element | Description | Type | Notes |
| --- | --- | --- | ---|
| soundFiles | List of sound file information. Top element. | array | |
| &nbsp; &nbsp; &nbsp; id | The ID of the sound file. | integer | |
| &nbsp; &nbsp; &nbsp; url | The URL of the sound file. | string | |
| &nbsp; &nbsp; &nbsp; length | The length of the sound file in seconds. | float | |

##### Sample response
```
{
 "soundFiles": [
 {
 "id": 23456,
 "url": "https://api.sounddate.com/profile/sound/23456.mp3",
 "length": 11.2
 },
 {
 "id": 24559,
 "url": "https://api.sounddate.com/profile/sound/24559.mp3",
 "length": 19.8
 }
 ]
}
```

### Description: Status Codes and Errors
Here's the information from the development team:
1. 200, success for both POST and GET
2. 401, access token is no good
3. 413, sound file that was POSTed was too long

### Documentation: Status Codes and Errors
| Code | Description | Notes
| --- | --- | --- |
| 200 | OK | Success |
| 401 | Unauthorized | The access token is invalid. |
| 413 | Request entity too large | The uploaded sound file was longer than 5 minutes.|


## 2. Snippets of reference documentation from an API for sharing and printing photos

Here's the information from the development team:

#### 1. Document the methods and URL of API requests for managing an online photo album
- The server location is https://phantasticfoto.com/api/v1/
- The resource name is album.
- An album is a collection of images.
- You can create an album with POST, retrieve it with GET, update it with PUT, and delete it with DELETE.
- For GET, PUT, and DELETE, specify the album ID after the resource
- You can also get a list of all albums with GET where you don't specify the ID.
- Also, you can print an album using the endpoint album/print and a POST method.

#### 2. Document headers for the request that uploads a photo
- The format for the photo is specified with the Content-Type header. Valid values are: image/jpeg, image/png, and image/gif. Default is image/jpeg.
- The format of the returned data is specified with the Accept header. Valid values are: application/json and application/xml. Default is application/json.
- The authorization token is specified with a query parameter, so you don't need a header for that.
- The server address is https://phantasticFoto/api/v1/
- The method is POST and the resource is photo

#### 3. Document status codes
- 200 Success.
- 401 The access token is not valid for this resource.
- 403 The number of API requests per month has been exceeded.
- 404 The resource name or ID is not valid.


#### Documentation: 

**Retrieve an album**
Returns data about the specified collection of images.
```
GET https://phantasticfoto.com/api/v1/album/{album ID}
```
where `{album ID}` is the id of the album

**Create an Album**
Creates a new collection of images.
``` 
POST https://phantasticfoto.com/api/v1/album
```

**Update an Album**
Updates an existing collection of images.
```
PUT https://phantasticfoto.com/api/v1/album/{album ID}
```
where `{album ID}` is the ID of the album to update.

**Delete an Album**
Deletes a collection of images.
```
DELETE https://phantasticfoto.com/api/v1/album/{album ID}
```
where `{album ID}` is the ID of the album to delete.

**Retrieve a List of All Albums**
Returns a list of all albums.
```
GET https://phantasticfoto.com/api/v1/album 
```

**Print an Album**
Sends an album to be printed.
```
POST https://phantasticfoto.com/api/v1/album/print/{album ID}
```
where `{album ID}` is the ID of the album to be printed.

**Headers**
|  Header Name | Description | Required | Values |
| ---          | ---         | ---      | ---    |
| Content-Type | The format of the photo. | Optional | Valid values are: `image/jpeg`, `image/png`, and `image/gif`. Default is `image/jpeg` |
| Accept | The format of the returned data. | Optional | `application/json` and `application/xml`. Default is `application/json`|

**Sample request**
This example request uploads a photo in JPEG format and returns data in JSON format. 
```
POST "https://phantasticFoto/api/v1/photo"
Content-Type image/jpeg
Accept: application/json
POST body is a photo
```

**Status and error codes**
| Code | Description | Notes
| --- | --- | --- |
| 200 | OK | Success |
| 401 | Unauthorized | The access token is not valid for this resource. |
| 403 | Forbidden | The number of API requests per month has been exceeded.|
| 404 | Not found | The resource name or ID is not valid. |

