# 🔁 Store Request

this method returns RedirectResponse or JsonResponse based on the request type. and we get the request type by check if the route has `splade` middleware or not.

this method accept some arguments:

* `request` the request object
* `model` the model you want to get
* `validation` the validation rules you want to use
* `message` the message you want to return with the response
* `validationError` the message you want to return if the validation failed
* `redirect` the redirect route you want to redirect to
* `hasMedia` if you want to get the media of the model or not
* `collection [array]` the media collection you want to get as array take true if it's multi or false if it's single
* `api` if you want to return JsonResponse or not

```php
public function store(Request $request): RedirectResponse|JsonResponse
{
    $response = Tomato::store(
        request: $request, //Required
        model: \App\Models\User::class, //Required
        validation: [
            'name' => 'required|string|max:255',
            'email' => 'required|string|email|max:255|unique:users',
        ],
        message: __('User created successfully'),
        validationError: __('Error When Try To Store User'),
        redirect: 'admin.users.index',
        hasMedia: true,
        collection: [
            'avatar' => false,
            'gallery' => true
        ],
        api: true,
    );

    if($response instanceof JsonResponse){
        return $response;
    }

    return $response->redirect;
}
```
