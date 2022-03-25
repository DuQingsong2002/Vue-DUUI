<script setup>
import DuIcon from '../components/duui/basic/icon/DuIcon.vue';
import DuButton from '../components/duui/basic/button/DuButton.vue';

</script>

<template>

    <section class="row">
        <span class="title">图标</span>
        <section class="row">
            <span class="title">type</span>
            <DuIcon type="search" />
            <DuIcon type="delete" />
            <DuIcon type="add" />
            <DuIcon type="confirm" />
            <DuIcon type="tel" />
            <DuIcon type="close" />
            <DuIcon type="loading" />
        </section>
        <section class="row">
            <span class="title">size</span>
            <DuIcon type="search" size="2em" />
            <DuIcon type="delete" size="1em"  />
            <DuIcon type="add" size=".5em" />

            <span class="title">color</span>
            <DuIcon type="search" color="blue" />
            <DuIcon type="delete" color="red" />
            <DuIcon type="add" color="gray" />
        </section>
    </section>
    
    <section class="row">
        <span class="title">按钮</span>
        <section class="row">
            <span class="title">type</span>
            <DuButton >default</DuButton>
            <DuButton type="primary" >primary</DuButton>
            <DuButton type="warning" >warning</DuButton>
            <DuButton type="success">success</DuButton>
            <DuButton type="cancle">cancle</DuButton>
            <DuButton type="danger">danger small</DuButton>
        </section>
        <section class="row">
            <span class="title">size</span>
            <DuButton size="large">large</DuButton>
            <DuButton type="default">default</DuButton>
            <DuButton type="default" size="small">small</DuButton>
        </section>
        <section class="row">
            <span class="title">disabled</span>
            <DuButton disabled>default</DuButton>
            <DuButton type="primary" disabled>primary</DuButton>
            <DuButton type="warning" disabled>warning</DuButton>
            <DuButton type="success" disabled>success</DuButton>
            <DuButton type="cancle" disabled>cancle</DuButton>
            <DuButton type="danger" disabled>danger</DuButton>
        </section>
        <section class="row">
            <span class="title">icon</span>
            <DuButton size="large">default<DuIcon type="search" /></DuButton>
            <DuButton type="primary"><DuIcon type="confirm" />primary</DuButton>
            <DuButton size="small" type="warning"><DuIcon type="close" />warning</DuButton>
            <DuButton size="large" type="success"><DuIcon type="tel" /></DuButton>
            <DuButton type="cancle"><DuIcon type="add" /></DuButton>
            <DuButton size="small" type="danger"><DuIcon type="delete" /></DuButton>
        </section>
        <section class="row">
            <span class="title">loading</span>
            <DuButton loading size="large">default</DuButton>
            <DuButton type="primary" loading>primary</DuButton>
            <DuButton type="warning" loading size="small">warning</DuButton>
            <DuButton type="success" loading size="large" disabled>success disabled</DuButton>
            <DuButton type="cancle" loading disabled>cancle disabled</DuButton>
            <DuButton type="danger" loading size="small" disabled>danger disabled</DuButton>
        </section>
        <section class="row">
            <span class="title">color</span>
            <DuButton color="red" size="large">default</DuButton>
            <DuButton color="yellow">default</DuButton>
            <DuButton color="gray" size="small">default</DuButton>
        </section>
        <section class="row">
            <span class="title">round(false)</span>
            <DuButton type="primary" size="large"  :round="false"><DuIcon type="search"/></DuButton>
            <DuButton type="danger" :round="false"><DuIcon type="delete"/></DuButton>
            <DuButton size="small"  :round="false"><DuIcon type="close"/></DuButton>
            <span class="title">circle(true)</span>
            <DuButton circle size="large"  type="primary"><DuIcon type="search"/></DuButton>
            <DuButton circle type="danger"><DuIcon type="delete"/></DuButton>
            <DuButton circle size="small" ><DuIcon type="close"/></DuButton>
        </section>
    </section>

</template>


<style>

.row {
    border: 1px solid #000;
    padding: 20px;
    margin: 20px 0;
}

.row > .du-icon {
    font-size: 28px;
    margin: 0 20px;
}
.row > .title {
    font-size: 30px;
    font-weight: bold;
}
.row > .row .title {
    font-size: 20px;
}
.row > .row .title:not(:first-child) {
    margin-left: 40px;
}
.row > .title::after {
    content: ':';
}
.row > .du-button {
    margin: 0 20px;
}

</style>