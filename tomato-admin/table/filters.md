# 🗄 Filters

<figure><img src="../../.gitbook/assets/Screenshot from 2024-01-18 17-58-10.png" alt=""><figcaption></figcaption></figure>

there is a limitation on a filtering table inside [Splade table](https://splade.dev/docs/table-query-builder) so we added more features to the filters inside Splade Table

## Boolean Filter

I think we all need a filter with a boolean inside our tables to get active users or any boolean value filter, so we added a new filter method to Splade Table&#x20;

you can use it like this

```php
->boolFilter(
    key: 'is_active',
    label: __('Activated')
);
```

## Date Filter

as we go we need to filter a table by date range from to, so we add auto data filter to filter your records by created\_at filed form, to. just in one line

```php
->dataFilter();
```

you can custom it by using another like updated\_at

```php
->dateFilter(
    key: 'updated_at', 
    label: __('Updated At')
);
```

## Select Filter With Remote Data

is the feature we all need to get data from the remote URL inside the table filter, we make this happen we adding a new method to the table with more features.

you can use this selected like this

```php
->selectFilter(
    key: 'account_id',
    label: __('Account'),
    remote_root: 'data',
    remote_url: route('admin.accounts.index'),
    option_label: 'name',
    option_value: 'id',
);
```

## Override Filter Auto Query

as we know when we change the table filter it does the magic of filtering without any logic for this filter, but sometimes we need to do some extra custom query when the filter changes, so we add a new attribute inside all types of filters to do this.

you can use it like this.

```php
->selectFilter(
    key: 'account_id',
    label: __('Account'),
    remote_root: 'data',
    remote_url: route('admin.accounts.index'),
    option_label: 'name',
    option_value: 'id',
    applyQuery: false
);

```

