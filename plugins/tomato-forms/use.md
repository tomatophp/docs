# 📐 Use

if you have something like services and every service has a custom form, you can use this plugin to attach a form to this service.

or if you need a Contact Us form to view on your frontend website, you can use this plugin to create a form and attach it to a page.

## Tomato Form Component

you can use this component to view your form anywhere in your app like this

```html
 <x-tomato-form :form="$model" :default="['form_id'=>$model->id]" :action="route('admin.form-requests.store')"></x-tomato-form>
```

