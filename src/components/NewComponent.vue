<template>
    <div>
        <Header text="Ini Adalah Header">
            <template #footer>
                <p>Ini Adalah Slot Dari Footer</p>
            </template>
        </Header>

        <MyComponent  nama="Ujang" umur="90"></MyComponent >

        <UmurComponent nama="Mahmud" umur="19"></UmurComponent >

        <LatihanDuaComponent></LatihanDuaComponent>
            
        <h2>WatchersComponent</h2>
        <WatchersComponent nama="Ujang" umur="80"></WatchersComponent>
        <h2>Event Component</h2>
        <LatihanEventComponent :nama="nama" :umur="umur" @greeted="onGreeted">
            <template #footer>
                <div>
                    <p>Ini Adalah Footer Latihan Event</p>
                </div>
            </template>
            <template #header>
                <div>
                    <p>Ini Adalah Header latihan Event</p>
                </div>
            </template>
        </LatihanEventComponent>
    </div>
</template>

<script setup>
import LatihanEventComponent from './LatihanEventComponent.vue';
import UmurComponent from './UmurComponent.vue'
import MyComponent from './MyComponent.vue';
import Header from './Header.vue';
import LatihanDuaComponent from './LatihanDuaComponent.vue';
import WatchersComponent from './WatchersComponent.vue';

// event
import { ref } from 'vue';
const nama = ref('John');
const umur = ref(25);

const onGreeted = () => {
    console.log('Kamu udah disapa, bro!');
};

</script>
