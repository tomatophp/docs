# 🔗 Relation Manager

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

as we clone FilamentPHP Theme we get some VIP components, here is the relation manager component, The component is used to manage the relation between models, for example, if you have a user model and you want to show the roles of this user, you can use this component to do that.

### Use

you can use it like this

```html
<x-tomato-admin-relations-group :relations="['groups', 'locations']">
    <x-tomato-admin-relations
        :model="$model"
        name="groups"
        :table="\TomatoPHP\TomatoCrm\Tables\GroupTable::class"
    />
    <x-tomato-admin-relations
            :model="$model"
            name="locations"
            :table="\TomatoPHP\TomatoCrm\Tables\LocationTable::class"
            :show="true"
            :edit="true"
            :delete="true"
            :path="/admin/locations"
            :view="tomato-admin::components.relations"
    />
</x-tomato-admin-relations-group>
```

as you see you can group the relations table with `x-tomato-admin-relations-group` component and you can add as many relations tables as you want inside this group, and you can use `x-tomato-admin-relations` component to add a relation table.
