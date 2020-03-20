## 1. An API for sharing and printing photos

Document the method and URL of API requests for creating an online photo album. Here's the information from the development team:
- The server location is https://phantasticfoto.com/api/v1/
- The resource name is album.
- An album is a collection of images.
- You can create an album with POST, retrieve it with GET, update it with PUT, and delete it with DELETE.
- For GET, PUT, and DELETE, specify the album ID after the resource
- You can also get a list of all albums with GET where you don't specify the ID.
- Also, you can print an album using the endpoint album/print and a POST method.


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


