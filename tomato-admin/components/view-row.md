# 👁 View Row

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

we all need to get a ready-to-use view item for our model, so we built this component to make it easy to use and customize.

### Use

you can use it like this

```html
<x-tomato-admin-row 
    :label="__('Name')" 
    :value="$model->name" 
    type="text" 
/>
```

or you can use it as a link like

```html
<x-tomato-admin-row 
    :label="__('Name')" 
    :value="$model->name" 
    :href="route('admin.users.index')" 
    icon="bx bx-user" 
    color="#fff" 
    type="badge" 
/>
```

and it's accepted on value just string value and you can use this types:

* text
* string
* rich
* number
* email
* tel
* badge `this type accept icon and color and href`
* date
* datetime
* time
* image
* images
* icon
* color
* bool
* copy
* password
