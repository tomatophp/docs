# 🔁 Destroy Request

this method returns RedirectResponse or JsonResponse based on the request type. and we get the request type by check if the route has `splade` middleware or not.

this method accept some arguments:

* `model` the model you want to get
* `message` the message you want to return with the response
* `redirect` the redirect route you want to redirect to
* `api` if you want to return JsonResponse or not

```php
public function destroy(\App\Models\User $model): RedirectResponse|JsonResponse
{
    $response = Tomato::destroy(
        model: $model, //Required
        message: __('User deleted successfully'), //Required
        redirect: 'admin.users.index',
    );

    if($response instanceof JsonResponse){
        return $response;
    }

    return $response->redirect;
}
```
