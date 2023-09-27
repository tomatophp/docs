# 🔁 Index Request

this method returns view or JsonResponse based on the request type. and we get the request type by check if the route has `splade` middleware or not.

this method accept some arguments:

- `request` the request object
- `model` the model you want to get
- `view` the view you want to return
- `table` the table class you want to use
- `data` the data you want to pass to the view
- `api` if you want to return JsonResponse or not
- `resource` resource class to resource your returned data
- `query` if you want to add some query to the model
- `filters` if you want to add some filters to the table

```php
public function index(Request $request): View|JsonResponse
{
    return Tomato::index(
        request: $request, //Required
        model: $this->model, //Required
        view: 'users.index', 
        table: \App\Tables\UserTable::class,
        data: [
            'name' => 'john doe',
        ],
        api: true,
        resource: UserResource::class,
        query: User::query()->where('is_activated',true),
        filters: [
            'is_activated',
        ],
    );
}
```