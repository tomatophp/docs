# 🔁 Get Request

this method returns view or JsonResponse based on the request type. and we get the request type by check if the route has `splade` middleware or not.

this method accept some arguments:

* `model` the model you want to get
* `view` the view you want to return
* `data` the data you want to pass to the view
* `hasMedia` if you want to get the media of the model or not
* `collection [array]` the media collection you want to get as array take true if it's multi or false if it's single
* `attach [array]` to attach some data to the model
* `api` if you want to return JsonResponse or not
* `resource` resource class to resource your returned data
* `query` if you want to add some query to the model

```php
public function show(\App\Models\User $model): View|JsonResponse
{
    return Tomato::get(
        model: $model, //Required
        view: 'users.show', //Required
        data: [
            'name' => 'john doe',
        ],
        hasMedia: true,
        collection: [
            'avatar' => false,
            'gallery' => true
        ],
        attach: [
            'roles' => $model->roles,
        ],
        api: true,
        resource: UserResource::class,
        query: User::query()->where('is_activated',true)
    );
}
```
