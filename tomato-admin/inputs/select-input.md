# ⚡ Select Input

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

because of some limits of `x-splade-select` you develop a new component using [vue-multiselect](https://vue-multiselect.js.org/) this new component has features:

* Load data from APIs
* Search Sync with API
* Pagination support with load more button
* Auto Fill Selected Data from API

you can use this select input like `x-splade-select`

```markup
<x-tomato-admin-select 
    :label="__('Developer id')" 
    :placeholder="__('Developer id')" 
    name="developer_id"
    remote-url="{{route('admin.users.api')}}" 
    remote-root="data" 
    option-label=name.en 
    option-value="id" 
    type="relation" 
    query-by="name" 
    paginated
/>
```

`:type` is the type of select it can be select / relation

`:query-by` is the name of the request key sent when searching

`:paginated` is a bool for options of pagination
