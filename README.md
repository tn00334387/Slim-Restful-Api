Restful API with Slim Framework
===

## Slimtest.zip
---
A project that contains a basic GET/POST/DELETE api.

* index.html : Call the request for GET/POST/DELETE method and refresh the server by html-form .
* slim_api.php : Define GET/POST/DELETE's function get()/post()/delete()
    * get() : Query the message. You can query a message by using the GET method to get the id parameter from the URL /{id}/hello , or query it by /all to get all the messages.
    * post() : Add a message. It can add the corresponding message by getting the $_POST['id'] parameter in the POST method of the html-form.
    * delete() : Delete a message. because html-form can not directly support the DELETE method, so through the post method and give its DELETE attribute as a request to call. It will through the URL {id} / hello to get the id parameter to delete.
* message.php : Define a message Class. The class is used as the data structure of the message, and uses the $_SESSION of the server as the database. It defines the find()/create()/delete() function to call the slim_api.php.
* clear.php : Clear all messages in the server.

## Slimtest_cache.zip
---
A project that contains a Http-cache GET/POST/DELETE api.

### Explain :  

Here, Etag is selected as the cache method, in which a unique id is given in the callback() of the api to cache the result of the response. When there is a Request, it will check whether it is the same Etag to obtain the cached value and directly return it, no need to visit the server to get the information.
