# 🔍 Search

<figure><img src="../../.gitbook/assets/Screenshot from 2024-01-18 17-07-19.png" alt=""><figcaption></figcaption></figure>

on some views we need to get data from APIs and view it as Object!, and that's what this component does when you search it does a query on the remote URL and returns with an array of objects that you can select any object and it's filled with the object not just the ID

you can use it like this

```markup
<x-tomato-search
    :remote-url="route('admin.orders.user')"
    remote-root="data"
    name="account_id"
    placeholder="{{__('Select Account')}}"
    label="{{__('Account')}}"
/>
<div v-if="form.errors.account_id"
     class="text-danger-500 mt-2 text-xs font-chakra flex gap-2 mb-[6px]">
    <p v-text="form.errors.account_id"> </p>
</div>
<div v-if="form.account_id">
    <div class="text-lg font-bold mt-2">
        @{{form.account_id.name}}
    </div>
    <div class="text-sm">
        @{{form.account_id.email}}
    </div>
    <div class="text-sm">
        @{{form.account_id.phone}}
    </div>
    <div class="text-sm">
        @{{form.account_id.address}}
    </div>
    <div class="text-sm">
        @{{form.account_id.zip}} @{{form.account_id.city}}
    </div>
    <div class="text-sm">
        @{{form.account_id.country?form.account_id.country.name:''}}
    </div>
</div>
```
