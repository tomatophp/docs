# ⏩ Tomato Froms

as we go to integrate our tomato plugins inside the Flutter app we build a module to make it easy to integrate the package into our Flutter app without any code.

to make this happen you need to install [tomato-forms](../tomato-forms/ "mention") and create a new form with fields from the dashboard and then use the form ID to access the form on Flutter.

to use a create form you can use it like this

```dart
storage.remove('form-values');
Get.toNamed('/forms/1');
```

where `1` is the id of form, to use it as an edit form you can use it like this&#x20;

```dart
storage.write('form-values', controller.data?.toJson());
Get.toNamed('/forms/1');
```

where `1` is the id of the form and `controller.data?.toJson()` is the data you when to fill it on the form, make sure to make the keys matched&#x20;
