# 🎁 Use Coupon Service

you can use coupon service to check if a coupon is valid or not

you can use this method to check for selected Order

```php
use \TomatoPHP\FilamentEcommerce\Facades\FilamentEcommerce;

FilamentEcommerce::coupon()->check('coupon_code', \TomatoPHP\FilamentEcommerce\Models\Order::find(1));
```

or you can check the code for selected products

```php
use \TomatoPHP\FilamentEcommerce\Facades\FilamentEcommerce;

FilamentEcommerce::coupon()->products([1,2,4])->check('coupon_code');
```

or you can get the direct discount amount of the code

```php
use \TomatoPHP\FilamentEcommerce\Facades\FilamentEcommerce;

FilamentEcommerce::coupon()->products([1,2,4])->discount('coupon_code');
```

and it's the same as a check you can apply to selected orders or selected products.
