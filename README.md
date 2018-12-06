# CodeIgniter-JWT-Sample

Simple Codeigniter, REST Server, JWT implementation.


**Note:** This repo is forked from [ParitoshVaidya/CodeIgniter-JWT-Sample](https://github.com/ParitoshVaidya/CodeIgniter-JWT-Sample)


Setup for existing projects
=====


You will need following files ( copy this files and place them inside your project):

**/application/config/jwt.php** <= Add **jwt_key** here

**/application/helpers/authorization_helper.php**

**/application/helpers/jwt_helper.php**

In **/application/config/autoload.php** add following...
```
$autoload['helper'] = array('url', 'form', 'jwt', "authorization");
$autoload['config'] = array('jwt');
```

That's it. You are ready. 

Configuration
=====

In your `application\config\jwt.php` file,

* `jwt_key` 

```
$config['jwt_key']	= '';
```

* **For Timeout** `token_timeout` 

```
$config['token_timeout']	= 60; // unit used here is minutes eg:- here timeout is 60 minutes
```


Add your logic to generate token, eg.

```
$tokenData = array();
$tokenData['id'] = 1; //TODO: Replace with data for token
$output['token'] = AUTHORIZATION::generateToken($tokenData);
```

Please reply, if you need additional details. Happy coding!


Run
=====

GET auth token

    URL: http://host/CodeIgniter-JWT-Sample/auth/token
    Method: GET

Check decoded token

    URL: http://host/CodeIgniter-JWT-Sample/auth/token
    Method: POST
    Header Key: Authorization
    Value: Auth token generated in GET call
    
GET auth token with **timeout**

    URL: http://host/CodeIgniter-JWT-Sample/authtimeout/token
    Method: GET

Check decoded token with **timeout**

    URL: http://host/CodeIgniter-JWT-Sample/authtimeout/token
    Method: POST
    Header Key: Authorization
    Value: Auth token generated in GET call of authtimeout controller

Project uses 
=======
[CodeIgniter] (https://www.codeigniter.com/)  
[REST Server] (https://github.com/chriskacerguis/codeigniter-restserver)  
[Reference for JWT implementation] (https://github.com/rmcdaniel/angular-codeigniter-seed)

Contact
=====
For any questions mail me paritoshvaidya@gmail.com
  
  
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://github.com/ParitoshVaidya/CodeIgniter-JWT-Sample/blob/master/license.txt)
