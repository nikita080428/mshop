<script setup>

let route = useRoute();

const id = route.params.id

let iPhones = [
  {
    id: 14,
    price: 450,
    description: "The phone has two cameras located diagonally, flat faces and a fairly large bang with a FaceID face scanner" ,
    imgs: ["https://new-retail.ru/upload/iblock/7c7/w4ikgzeduau3vz1nbbxsqtxpkh123cf8.png", "https://static.cdek.shopping/images/shopping/7c51447b0a8441a1b27c4116f59878b2.jpg",
      "https://content.onliner.by/news/large/e3f09f76c8e3b5420b3d2e045ed1ca33.png", "https://img.championat.com/s/1350x900/news/big/s/k/pervym-smartfonom-apple-s-usb-c-mozhet-stat-iphone-17_16649645111168235955.jpg",
      "https://ir.ozone.ru/s3/multimedia-r/6437162715.jpg"
     ]
  },
  {
    id: 15,
    price: 550,
    description: "By touching Dynamic Island during playback, it is especially dexterous to switch directly to the music app. No unnecessary swipes and body movements." ,
    imgs: ["https://i.ytimg.com/vi/lr0rSqyItHo/maxresdefault.jpg", "https://ir.ozone.ru/s3/multimedia-j/6843111967.jpg",
      "https://www.iphones.ru/wp-content/uploads/2023/09/IMG_8902.jpeg", "https://mactime.pro/images/blog/80/123.jpg",
      "https://media-assets.wired.it/photos/64a6622d0e13ade21c60a717/16:9/w_2512,h_1413,c_limit/nuovi%20colori%20iphone%2015.png"
    ]
  },
  {
    id: 16,
    price: 600,
    description: "The display sizes have not changed either: 6.1 inches for the base model and 6.7 inches for the Plus version. The USB Type-C port is used for charging, as it was last year." ,
    imgs: ["https://blog.eldorado.ru/storage/publication/0/63/viaMdw0NkBpsTIYJnFhM14I4tNSTjeLNmdSZF4el.jpeg", "https://img.gazeta.ru/files3/37/19041037/iPhone-16-Lozenge-2-Isolated-Colors-pic_32ratio_900x600-900x600-14818.jpg",
      "http://img.gazeta.ru/files3/958/16663958/2-819x1456-pic_32ratio_900x600-900x600-15473.jpg", "https://i.ytimg.com/vi/Nd7-9fpspGs/maxresdefault.jpg",
      "https://sun1-89.userapi.com/s/v1/ig2/POf1r0DD1o-H3kW1PmtWS-5mQrxQy5VwDsp6hLxEycbEGom_Jx0ZWoNFY4xpNzI2oXR8tm4PWy0a3kb-GMUDtvPw.jpg?quality=95&as=32x18,48x27,72x40,108x61,160x90,240x135,360x202,480x270,540x303,640x360,720x405,1080x607&from=bu&u=_f6VXTyHnQthzFWHiTGyV6WZ1orXtzwJjMGCHxEfzTk&cs=807x454"
    ] 
  }
];


function iPhone(id) {
  return iPhones.find(element => element.id == id)
}

let nummeral = iPhone(id)

console.log(nummeral)

</script>

<template>

<div class="gap-1 px-6 flex flex-1 justify-center py-5">
    <div class="layout-content-container flex flex-col max-w-[920px] flex-1">
      <div class="flex flex-wrap gap-2 p-4">
        <NuxtLink to="/" class="text-[#636f88] text-base font-medium leading-normal" >Home</NuxtLink>
        <span class="text-[#636f88] text-base font-medium leading-normal">/</span>
        <a class="text-[#636f88] text-base font-medium leading-normal" href="#">iPhone</a>
        <span class="text-[#636f88] text-base font-medium leading-normal">/</span>
        <span class="text-[#111318] text-base font-medium leading-normal">iPhone {{ nummeral.id }} Pro Max</span>
      </div>
      <div class="flex flex-wrap justify-between gap-3 p-4">
        <div class="flex min-w-72 flex-col gap-3">
          <p class="text-[#111318] tracking-light text-[32px] font-bold leading-tight">iPhone {{ nummeral.id }} Pro</p>
          <p class="text-[#636f88] text-sm font-normal leading-normal">${{ nummeral.price }}</p>
        </div>
      </div>
      <div class="pb-3">
        <div class="flex border-b border-[#dcdfe5] px-4 gap-8">
          <a class="flex flex-col items-center justify-center border-b-[3px] border-b-[#111318] text-[#111318] pb-[13px] pt-4" href="#">
            <p class="text-[#111318] text-sm font-bold leading-normal tracking-[0.015em]">Overview</p>
          </a>
          <a class="flex flex-col items-center justify-center border-b-[3px] border-b-transparent text-[#636f88] pb-[13px] pt-4" href="#">
            <p class="text-[#636f88] text-sm font-bold leading-normal tracking-[0.015em]">Tech Specs</p>
          </a>
          <a class="flex flex-col items-center justify-center border-b-[3px] border-b-transparent text-[#636f88] pb-[13px] pt-4" href="#">
            <p class="text-[#636f88] text-sm font-bold leading-normal tracking-[0.015em]">Pricing</p>
          </a>
          <a class="flex flex-col items-center justify-center border-b-[3px] border-b-transparent text-[#636f88] pb-[13px] pt-4" href="#">
            <p class="text-[#636f88] text-sm font-bold leading-normal tracking-[0.015em]">Software</p>
          </a>
        </div>
      </div>
      <div class="grid grid-cols-[repeat(auto-fit,minmax(158px,1fr))] gap-3 p-4">
        <div class="flex flex-col gap-3" v-for="img in nummeral.imgs">
          <div
            class="w-full bg-center bg-no-repeat aspect-square bg-cover rounded-xl"
            :style=" `background-image: url(${img})` "
          ></div>
        </div>
        
      </div>
      <h3 class="text-[#111318] text-lg font-bold leading-tight tracking-[-0.015em] px-4 pb-2 pt-4">iPhone {{nummeral.id}} Pro</h3>
      <p class="text-[#111318] text-base font-normal leading-normal pb-3 pt-1 px-4">
        {{nummeral.description}}
      </p>
      <h3 class="text-[#111318] text-lg font-bold leading-tight tracking-[-0.015em] px-4 pb-2 pt-4">Tech Specs</h3>
      <div class="p-4 grid grid-cols-2">
        <div class="flex flex-col gap-1 border-t border-solid border-t-[#dcdfe5] py-4 pr-2">
          <p class="text-[#636f88] text-sm font-normal leading-normal">Super Retina XDR display</p>
          <p class="text-[#111318] text-sm font-normal leading-normal">6.1-inch (diagonal) all-screen OLED display</p>
        </div>
        <div class="flex flex-col gap-1 border-t border-solid border-t-[#dcdfe5] py-4 pl-2">
          <p class="text-[#636f88] text-sm font-normal leading-normal">Ceramic Shield</p>
          <p class="text-[#111318] text-sm font-normal leading-normal">4x better drop performance</p>
        </div>
        <div class="flex flex-col gap-1 border-t border-solid border-t-[#dcdfe5] py-4 pr-2">
          <p class="text-[#636f88] text-sm font-normal leading-normal">5G capable</p>
          <p class="text-[#111318] text-sm font-normal leading-normal">Superfast downloads and high-quality streaming</p>
        </div>
        <div class="flex flex-col gap-1 border-t border-solid border-t-[#dcdfe5] py-4 pl-2">
          <p class="text-[#636f88] text-sm font-normal leading-normal">A15 Bionic chip</p>
          <p class="text-[#111318] text-sm font-normal leading-normal">50% faster CPU and GPU than any other smartphone chip</p>
        </div>
        <div class="flex flex-col gap-1 border-t border-solid border-t-[#dcdfe5] py-4 pr-2">
          <p class="text-[#636f88] text-sm font-normal leading-normal">Pro camera system</p>
          <p class="text-[#111318] text-sm font-normal leading-normal">12MP camera system</p>
        </div>
        <div class="flex flex-col gap-1 border-t border-solid border-t-[#dcdfe5] py-4 pl-2">
          <p class="text-[#636f88] text-sm font-normal leading-normal">LiDAR Scanner</p>
          <p class="text-[#111318] text-sm font-normal leading-normal">Cinematic mode</p>
        </div>
        <div class="flex flex-col gap-1 border-t border-solid border-t-[#dcdfe5] py-4 pr-2 col-span-2 pr-[50%]">
          <p class="text-[#636f88] text-sm font-normal leading-normal">Dolby Vision recording</p>
          <p class="text-[#111318] text-sm font-normal leading-normal">ProRAW and ProRes video</p>
        </div>
      </div>
      <div class="flex px-4 py-3 justify-start">
        <button
          class="flex min-w-[84px] max-w-[480px] cursor-pointer items-center justify-center overflow-hidden rounded-xl h-10 px-4 bg-[#3571e9] text-white text-sm font-bold leading-normal tracking-[0.015em]"
        >
          <span class="truncate">Add to Bag</span>
        </button>
      </div>
    </div>
    <div class="layout-content-container flex flex-col w-[360px]">
      <h3 class="text-[#111318] text-lg font-bold leading-tight tracking-[-0.015em] px-4 pb-2 pt-4">Select your iPhone {{ nummeral.id }} Pro</h3>
      <div class="flex flex-wrap gap-5 p-4">
        <label
          class="size-10 rounded-full border border-[#dcdfe5] ring-[color-mix(in_srgb,#111318_50%,_transparent)] has-[:checked]:border-[3px] has-[:checked]:border-white has-[:checked]:ring"
          style="background-color: rgb(0, 0, 0);"
        >
          <input type="radio" class="invisible" name="7c4caaa2-55e9-419f-a4a3-f9b0087fef62" checked = "false" />
        </label>
        <label
          class="size-10 rounded-full border border-[#dcdfe5] ring-[color-mix(in_srgb,#111318_50%,_transparent)] has-[:checked]:border-[3px] has-[:checked]:border-white has-[:checked]:ring"
          style="background-color: rgb(255, 255, 255);"
        >
          <input type="radio" class="invisible" name="7c4caaa2-55e9-419f-a4a3-f9b0087fef62" />
        </label>
      </div>
      <div class="flex flex-wrap gap-3 p-4">
        <label
          class="text-sm font-medium leading-normal flex items-center justify-center rounded-xl border border-[#dcdfe5] px-4 h-11 text-[#111318] has-[:checked]:border-[3px] has-[:checked]:px-3.5 has-[:checked]:border-[#3571e9] relative cursor-pointer"
        >
          128GB
          <input type="radio" class="invisible absolute" name="9aab891a-7a29-414a-8f17-07fe579482ca" />
        </label>
        <label
          class="text-sm font-medium leading-normal flex items-center justify-center rounded-xl border border-[#dcdfe5] px-4 h-11 text-[#111318] has-[:checked]:border-[3px] has-[:checked]:px-3.5 has-[:checked]:border-[#3571e9] relative cursor-pointer"
        >
          256GB
          <input type="radio" class="invisible absolute" name="9aab891a-7a29-414a-8f17-07fe579482ca" />
        </label>
        <label
          class="text-sm font-medium leading-normal flex items-center justify-center rounded-xl border border-[#dcdfe5] px-4 h-11 text-[#111318] has-[:checked]:border-[3px] has-[:checked]:px-3.5 has-[:checked]:border-[#3571e9] relative cursor-pointer"
        >
          512GB
          <input type="radio" class="invisible absolute" name="9aab891a-7a29-414a-8f17-07fe579482ca" />
        </label>
        <label
          class="text-sm font-medium leading-normal flex items-center justify-center rounded-xl border border-[#dcdfe5] px-4 h-11 text-[#111318] has-[:checked]:border-[3px] has-[:checked]:px-3.5 has-[:checked]:border-[#3571e9] relative cursor-pointer"
        >
          1TB
          <input type="radio" class="invisible absolute" name="9aab891a-7a29-414a-8f17-07fe579482ca" />
        </label>
      </div>
      <div class="flex items-center gap-4 bg-white px-4 min-h-[72px] py-2">
        <div
          class="bg-center bg-no-repeat aspect-square bg-cover rounded-lg size-14"
          style='background-image: url("https://cdn.usegalileo.ai/sdxl10/8ff92ef5-7990-4ad5-927c-413a653862c4.png");'
        ></div>
        <div class="flex flex-col justify-center">
          <p class="text-[#111318] text-base font-medium leading-normal line-clamp-1">Pay over time with Apple Card Monthly Installments</p>
          <p class="text-[#636f88] text-sm font-normal leading-normal line-clamp-2">From $25/mo or $599 with trade-in</p>
        </div>
      </div>
      <p class="text-[#636f88] text-sm font-normal leading-normal pb-3 pt-1 px-4">Or pay $999 upfront</p>
      <p class="text-[#636f88] text-sm font-normal leading-normal pb-3 pt-1 px-4 underline">Buy directly from Apple</p>
      <p class="text-[#636f88] text-sm font-normal leading-normal pb-3 pt-1 px-4 underline">Learn more about financing</p>
    </div>
  </div>

</template>