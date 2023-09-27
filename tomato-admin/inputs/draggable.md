# 💧 Draggable

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

everyone needs a draggable input on a project, but it's very hard to handle, for this, we created a very easy component to make it easy to handle draggable objects and make it very easy to store and sort them on the database.

you can start using this like this

```markup
<x-tomato-admin-draggable  
    :levels="3" 
    :options="$menusItems->toArray()" 
    url="{{route('admin.menus.item.all', $menu->id)}}" 
    order-by="order"
>
     <div>@{{ drag.item.name }}</div>
</x-tomato-admin-draggable>
```

our component works with multi-levels which means you can create a tree of objects just by using this component you can change `:levels` as you like to be the count of levels

and to make this component work you must pass options to it where `:options` is an array of objects you need to sort

and at the end of this, you need to add `:url` and we will hit this your everytime you make a change on sorting inside the dragging area

the last attribute is `:order-by` and we use it to order the objects by it

to store this object and make the ordering successful you can just use this code on your store method

```php
public function itemAll(Request $request, Menu $menu){
    $request->validate([
        "all" => "required|array",
        "orderBy" => "required|string",
    ]);

    $counter = 0;
    foreach($request->get('all') as $key=>$item){
        $menuItem = MenusItem::where('id', $item['id'])->first();
        $menuItem->{$request->get('orderBy')} = $counter;
        $menuItem->save();

        if(isset($item['children']) && count($item['children'])){
            $countChild = 0;
            foreach($item['children'] as $key=>$child){
                $childItem = MenusItem::where('id', $child['id'])->first();
                $childItem->parent_id = $menuItem->id;
                $childItem->{$request->get('orderBy')} = $countChild;
                $childItem->save();

                $countChild++;

                if(isset($child['children']) && count($child['children'])){
                    $this->setChildren($child, $childItem);
                }
            }
        }
        else {
            $menuItem->parent_id = null;
            $menuItem->save();
        }
        $counter++;
    }

    return back();
}
```

this method takes all objects on the draggable and sorting it

this component used [vue-draggable-next](https://github.com/SortableJS/vue.draggable.next)
