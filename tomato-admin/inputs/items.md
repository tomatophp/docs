# 🧾 Items



<figure><img src="../../.gitbook/assets/Screenshot from 2024-01-18 17-03-50.png" alt=""><figcaption></figcaption></figure>

items component can be used on your invoice like a [inputs-repeater.md](inputs-repeater.md "mention") but it's support calculation operations for qty and price and total and vat.

you can use it like this&#x20;

```html
<x-tomato-items :options="['item'=>'', 'price'=>0, 'discount'=>0, 'tax'=>0, 'qty'=>1,'total'=>0, 'options' =>(object)[]]" name="items">
    <div class="grid-cols-12 gap-4 border-b py-4 my-4 hidden lg:grid">
        <div class="col-span-4">
            {{__('Item')}}
        </div>
        <div>
            {{__('Price')}}
        </div>
        <div>
            {{__('Discount')}}
        </div>
        <div>
            {{__('Tax')}}
        </div>
        <div>
            {{__('QTY')}}
        </div>
        <div class="col-span-2">
            {{__('Total')}}
        </div>
    </div>
    <div class="block border-b py-4 mb-4 lg:hidden">
        {{__('Items')}}
    </div>
    <div class="flex flex-col gap-4">
        <div class="grid grid-cols-12 gap-4" v-for="(item, key) in items.main">
            <div class="col-span-12 lg:col-span-4 flex justify-between gap-4">
                <x-tomato-search
                    @change="
                                items.main[key].price = items.main[key].item?.price;
                                items.main[key].discount = items.main[key].item?.discount;
                                items.main[key].tax = items.main[key].item?.vat;
                                items.updateTotal(key)
                            "
                    :remote-url="route('admin.orders.product')"
                    option-label="name?.{{app()->getLocale()}}"
                    remote-root="data"
                    v-model="items.main[key].item"
                    placeholder="{{__('Select Item')}}"
                    label="{{__('Product')}}"
                />
            </div>
            <x-splade-input
                class="col-span-12 lg:col-span-1"
                type="number"
                placeholder="Price"
                v-model="items.main[key].price"
                @input="items.updateTotal(key)"
            />
            <x-splade-input
                class="col-span-12 lg:col-span-1"
                type="number"
                placeholder="Item Name"
                v-model="items.main[key].discount"
                @input="items.updateTotal(key)"
            />
            <x-splade-input
                disabled
                class="col-span-12 lg:col-span-1"
                type="number"
                placeholder="Tax"
                v-model="items.main[key].tax"
                @input="items.updateTotal(key, data.discount_type)"
            />
            <x-splade-input
                class="col-span-12 lg:col-span-1"
                type="number"
                placeholder="QTY"
                v-model="items.main[key].qty"
                @input="items.updateTotal(key)"
            />
            <x-splade-input
                disabled
                class="col-span-12 lg:col-span-2"
                type="text"
                placeholder="Item Name"
                v-model="items.main[key].total"
                @input="items.updateTotal(key)"
            />
            <button @click.prevent="items.addItem" class="col-span-12 lg:col-span-1 filament-button inline-flex items-center justify-center py-1 gap-1 font-medium rounded-lg border transition-colors focus:outline-none focus:ring-offset-2 focus:ring-2 focus:ring-inset dark:focus:ring-offset-0 min-h-[2.25rem] px-4 text-sm shadow-sm focus:ring-white filament-page-button-action bg-primary-600 hover:bg-primary-500 focus:bg-primary-700 focus:ring-offset-primary-700 text-white border-transparent">
                <i class="bx bx-plus"></i>
            </button>
            <button @click.prevent="items.removeItem(item)" class="col-span-12 lg:col-span-1 filament-button inline-flex items-center justify-center py-1 gap-1 font-medium rounded-lg border transition-colors focus:outline-none focus:ring-offset-2 focus:ring-2 focus:ring-inset dark:focus:ring-offset-0 min-h-[2.25rem] px-4 text-sm shadow-sm focus:ring-white filament-page-button-action bg-danger-600 hover:bg-danger-500 focus:bg-danger-700 focus:ring-offset-danger-700 text-white border-transparent">
                <i class="bx bx-trash"></i>
            </button>
            <div class="col-span-12 lg:col-span-4" v-if="items.main[key].item.has_options" v-for="(option, optionIndex) in items.main[key].item.product_metas[0].value">
                <div>
                    <label for="">
                        @{{ optionIndex.charAt(0).toUpperCase() + optionIndex.slice(1) }}
                    </label>
                    <x-splade-select class="w-full" v-model="items.main[key].options[optionIndex]">
                        <option v-for="(value, valueIndex) in option" :value="value">
                            @{{ value.charAt(0).toUpperCase() + value.slice(1) }}
                        </option>
                    </x-splade-select>
                </div>
            </div>
        </div>
        <div v-if="form.errors.inventory"
             class="text-danger-500 mt-2 text-xs font-chakra flex gap-2 mb-[6px]">
            <p v-text="form.errors.inventory"> </p>
        </div>
    </div>
    <div class="flex flex-col gap-4 mt-4">
        <div class="flex justify-between gap-4 py-4 border-b">
            <div>
                {{__('Tax')}}
            </div>
            <div>
                @{{ items.tax }}
            </div>
        </div>
        <div class="flex justify-between gap-4 py-4 border-b">
            <div>
                {{__('Sub Total')}}
            </div>
            <div>
                @{{ items.price }}
            </div>
        </div>
        <div class="flex justify-between gap-4 py-4 border-b">
            <div>
                {{__('Discount')}}
            </div>
            <div>
                @{{ items.discount }}
            </div>
        </div>
        <div class="flex justify-between gap-4 py-4 border-b">
            <div>
                {{__('Total')}}
            </div>
            <div>
                @{{ items.total }}
            </div>
        </div>
    </div>
</x-tomato-items>
```
