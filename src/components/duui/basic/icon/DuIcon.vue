<script setup>

/**
 * icon
 */
import './../../font/iconfont'

defineProps({
    // iconfont-type
    type: { type: String, required: true },
    color: { type: String, default: 'inherit' },   // css color
    size: { type: String, default: '1em' }, // css width x height
    
})

</script>


<template>

    <svg class="du-icon" aria-hidden="true" :class="{'--loading': type === 'loading'}">
        <use v-bind:xlink:href="`#icon-${$props.type}`"></use>
    </svg>

</template>


<style>

.du-icon {

    width: v-bind($props.size);
    height: v-bind($props.size);
    vertical-align: -0.15em;
    fill: currentColor;
    overflow: hidden;
    color: v-bind($props.color);
}
.du-icon.--loading {
    animation-name: loading;
    animation-duration: 1.25s;
    animation-iteration-count: infinite;
    animation-timing-function: linear;
}
@keyframes loading {
    from {
        transform: rotate(0);
    }
    to {
        transform: rotate(360deg);
    }
}


</style>