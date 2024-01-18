# 🛣 Slider

<figure><img src="../../.gitbook/assets/Screenshot from 2024-01-18 17-26-13.png" alt=""><figcaption></figcaption></figure>

we are using Swiper to build this slider so all Swiper functions can be applied to the slider using native js buy use `<x-splade-script>` tag and you can use the slider like this&#x20;

```markup
<x-tomato-admin-slider
    class="w-full h-80"
    :images="$imagesTM ?? []"
    :horizontal="false"
    :items="1"
    :navigation="false"
>
    @foreach($images as $image)
        <x-tomato-admin-slider-item zoom>
            <div class="flex justify-center">
                <div class=" w-80 h-80">
                    <img src="{{$image}}"  class="object-contain" />
                </div>
            </div>
        </x-tomato-admin-slider-item>
    @endforeach
</x-tomato-admin-slider>
```

this component uses [Swiper](https://swiperjs.com/vue)
