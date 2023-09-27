# 🔁 JSON Request

this method return only json response of the model to make it easy to access it with `x-splade-select` or `x-tomato-admin-select`

this method accept some arguments:

* `request` the request object
* `model` the model you want to get
* `data` the data you want to pass to the view
* `paginate` if you want to paginate the response or not
* `query` if you want to add some query to the model
* `filters` if you want to add some filters to the table

```php
public function api(Request $request): JsonResponse
{
    return Tomato::json(
        request: $request, //Required
        model: \App\Models\User::class, //Required
        data: [
            'name' => 'john doe',
        ],
        paginate: 10,
        query: User::query()->where('is_activated',true),
        filters: [
            'is_activated',
        ],
    );
}
```
