# 🔏 Developer Gate

we have a developer gate to ensure that only trusted developers can access the feature, it can use to make some feature only for the developer.

## How to use

we add some helpers to make it easy, so in your controller method you can use this helper to check if the user is a developer or not

```php
public function index(Request $request)
{
   if(is_developer()){
    //Do THIS
   }
   
   return developer_redirect();
}
```

and it will redirect it to enter the password of the developer and you change this password just from config file.