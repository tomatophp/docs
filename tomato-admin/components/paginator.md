# ⏸ Paginator

<figure><img src="../../.gitbook/assets/Screenshot from 2024-01-18 17-51-42.png" alt=""><figcaption></figcaption></figure>

if you try to use the default Laravel paginator you will find out that it does not have an SPA links component so we create another one with the replacement of \<a> tages to be \<x-splade-link> you can use it like this

```markup
{!! $users->links('tomato-admin::components.pagination') !!}
```
