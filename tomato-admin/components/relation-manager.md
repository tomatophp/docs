# Relation Manager

as we clone FilamentPHP Theme we get some VIP component, here is the relation manager component, this component use to manage the relation between models, for example, if you have a user model and you want to show roles of this user, you can use this component to do that.

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

as you see you can group relations table with `x-tomato-admin-relations-group` component, and you can add many relations table as you want inside this group, and you can use `x-tomato-admin-relations` component to add a relation table.