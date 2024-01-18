# ℹ Action Buttons

<figure><img src="../../.gitbook/assets/Screenshot from 2024-01-18 17-32-20.png" alt=""><figcaption></figcaption></figure>

this component is used to make it easy to add action buttons with some features you can use it like this

```markup
<x-tomato-admin-action-buttons 
    table="users" 
    :item="$item" 
    :view="true" 
    :edit="true" 
    :delete="true"
/>
```

where `table` is the table name of current CRUD
