# ✅ Bulk Actions

<figure><img src="../../.gitbook/assets/Screenshot from 2024-01-18 17-57-36.png" alt=""><figcaption></figcaption></figure>

as we know [Splade](https://splade.dev/docs/table-bulk-actions) has its Bulk action function we added more features to this action.

## Modal Bulk Action

you can use bulk action to open the modal and we send selected IDs on the requests with, sprit so you can extract it and use it inside your modal or form to confirm an action.

you can use it like this

```php
$table->bulkAction(
    label: __('Attach to group'),
    type: 'modal',
    href: route('admin.accounts.groups'),
    style: "primary"
);
```

you can see there are 3 new attributes on the `bulkAction()` method, type it can be modal or bulk, and href to the route of modal, and style of the bulk action button
