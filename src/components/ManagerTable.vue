<template>
    <div class=" hidden lg:flex lg:flex-col fixed z-40 bg-slate-800 dark:bg-slate-900  min-h-screen w-[300px] drop-shadow-md shrink-0">
        <div class="flex px-4 py-4 border-b-[2px] border-slate-900 justify-between w-full ">
            <router-link to="/" class="flex flex-col items-center justify-center w-full" v-on:click="counter.Show_Search=1;">
                <img src="@/assets/logo.png" class="text-[30px] text-cyan-600 w-[150px]"/>
                <h1 class="font-bold text-yellow-500 text-[35px]">Food King</h1>
                <p class="font-bold text-blue-600">Manager</p>
            </router-link>
        </div>
        <div class="flex flex-col px-4 py-4  justify-between w-full font-bold border-b-[1px] border-slate-900">
            <h1 class="text-[25px] text-lime-500">Quản lý bàn ăn </h1>
            <div class="flex flex-col text-slate-100  mt-2 gap-2 text-[19px] ">
                <div :class="{'bg-slate-700 ':counter.Tab_Manager==1,'bg-transparent':counter.Tab_Manager!=1}" class="cursor-pointer px-2 py-1 rounded hover:text-yellow-400" v-on:click="counter.Tab_Manager=1">Bàn số 1</div>
                <div :class="{'bg-slate-700 ':counter.Tab_Manager==2,'bg-transparent':counter.Tab_Manager!=2}" class="cursor-pointer px-2 py-1 rounded hover:text-yellow-400" v-on:click="counter.Tab_Manager=2">Bàn số 2</div>
                <div :class="{'bg-slate-700 ':counter.Tab_Manager==3,'bg-transparent':counter.Tab_Manager!=3}" class="cursor-pointer px-2 py-1 rounded hover:text-yellow-400" v-on:click="counter.Tab_Manager=3">Bàn số 3</div>
                <div :class="{'bg-slate-700 ':counter.Tab_Manager==4,'bg-transparent':counter.Tab_Manager!=4}" class="cursor-pointer px-2 py-1 rounded hover:text-yellow-400" v-on:click="counter.Tab_Manager=4">Bàn số 4</div>
                <div :class="{'bg-slate-700 ':counter.Tab_Manager==5,'bg-transparent':counter.Tab_Manager!=5}" class="cursor-pointer px-2 py-1 rounded hover:text-yellow-400" v-on:click="counter.Tab_Manager=5">Bàn số 5</div>
            </div>
        </div>
        <!-- <div  class="flex flex-col px-4 py-2 cursor-pointer  justify-between w-full font-bold border-b-[1px] border-slate-900">
            <button class="bg-blue-600 rounded-full px-5 py-3 text-gray-200 text-[15px] hover:bg-blue-500">Tạo Hóa Đơn Mới cho bàn ăn</button>
        </div> -->
        <div v-on:click="counter.Show_Table_Hoa_don = false;" class="flex flex-col px-4 py-2 cursor-pointer  justify-between w-full font-bold border-b-[1px] border-slate-900">
            <button v-on:click="counter.Log_out_NVQL();" class="bg-blue-600 rounded-full px-5 py-3 text-gray-200 hover:bg-blue-500">Đăng xuất</button>
        </div>
    </div>

    <!-- manhinh < lg -->
    <!-- <div class=" flex flex-col lg:hidden fixed z-20 bg-slate-800 dark:bg-slate-900  min-h-screen w-[300px] drop-shadow-md shrink-0" v-show="counter.Menu==true">
        <div class="flex px-4 py-4 border-b-[2px] border-slate-900 justify-between w-full ">
            <router-link to="/" class="flex flex-col items-center justify-center gap-2 w-full" v-on:click="counter.Show_Search=1;">
                <img src="@/assets/logo.png" class="text-[30px] text-cyan-600 w-[150px]"/>
                <h1 class="font-bold text-yellow-500 text-[35px]">Food Kingggg</h1>
            </router-link>
        </div>
        <div class="flex flex-col px-4 py-4  justify-between w-full font-bold border-b-[1px] border-slate-900">
            <h1 class="text-[26px] text-slate-300">Danh mục thực phẩm</h1>
            <div class="flex flex-col text-slate-100 px-3 mt-2 gap-2 text-[19px]">
                <router-link to="/SeaFood" class="flex items-center gap-2 hover:ml-2 hover:text-yellow-500 cursor-pointer duration-100 " v-bind:class="{'text-yellow-500 border-l-4 border-yellow-500':counter. Path_Route.path=='/SeaFood'}"><font-awesome-icon icon="fa-solid fa-shrimp" /><h1>Hải sản</h1></router-link>
                <router-link to="/WaterFood" class="flex items-center gap-2 hover:ml-2 hover:text-yellow-500 cursor-pointer duration-100" v-bind:class="{'text-yellow-500':counter. Path_Route.path=='/WaterFood'}"><font-awesome-icon icon="fa-solid fa-fish-fins" /><h1>Thủy sản</h1></router-link>
                <router-link to="/Cachloroathite" class="flex items-center gap-2 hover:ml-2 hover:text-yellow-500 cursor-pointer duration-100" v-bind:class="{'text-yellow-500':counter. Path_Route.path=='/Cachloroathite'}"><font-awesome-icon icon="fa-solid fa-stroopwafel" /><h1>Các loại thịt</h1></router-link>
                <router-link to="/Other" class="flex items-center gap-2 hover:ml-2 hover:text-yellow-500 cursor-pointer duration-100" v-bind:class="{'text-yellow-500':counter. Path_Route.path=='/Other'}"><font-awesome-icon icon="fa-solid fa-network-wired" /><h1>Khác</h1></router-link>
                <router-link to="/Drinks" class="flex items-center gap-2 hover:ml-2 hover:text-yellow-500 cursor-pointer duration-100" v-bind:class="{'text-yellow-500':counter. Path_Route.path=='/Drinks'}"><font-awesome-icon icon="fa-solid fa-wine-glass" /><h1>Đồ uống</h1></router-link>
                <router-link to="/Dessert" class="flex items-center gap-2 hover:ml-2 hover:text-yellow-500 cursor-pointer duration-100" v-bind:class="{'text-yellow-500':counter. Path_Route.path=='/Dessert'}"><font-awesome-icon icon="fa-solid fa-cookie" /><h1>Tráng miệng</h1></router-link>
            </div>
        </div>
        <div class="flex flex-col px-4 py-4  justify-between w-full font-bold border-b-[1px] border-slate-900">
            {{ counter.Table_Code_Oder }}
        </div>
    </div> -->

</template>

<script>
    import { useCounterStore } from '@/stores/counter';
    import axios from 'axios';
    import VueCookies from 'vue-cookies'
    

    export default {

    setup() {
        const counter = useCounterStore();
        return {counter}
    },
    // destroyed () {
    // document.body.classList.remove('overflow-hidden')
    // },
    methods:{
        add() {document.body.classList.add('overflow-hidden')},
        remove() {document.body.classList.remove('overflow-hidden')},
        scrollBehavior(){window.scrollTo(0,0);},
    }
    }
</script>

<!-- <style v-if="counter.Open_Scroll==2">
  body {
   overflow: default;
  }
</style> -->

<!-- <style v-if="true">
  body {
   overflow: hidden;
  }
</style> -->