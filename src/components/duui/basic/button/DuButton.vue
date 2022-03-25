<script setup>
import DuIcon from '../icon/DuIcon.vue';

/**
 * button
 */

defineProps({
    type: String,   // { type: String, default: '' || 'primary' || 'warning' || 'success' || 'cancle' || 'danger' }
    size: { type: String, deafult: 'default' || 'large' || 'small' },
    disabled: { type: Boolean, default: false },
    loading: { type: Boolean, default: false },
    round: { type: Boolean, default: true },
    circle: { type: Boolean, default: false },
    color: { type: String },
})

</script>


<template>

    <button class="du-button" 
            :class="`--${$props.type}
                    --${$props.size} 
                    ${$props.disabled ? '--disabled' : ''}  
                    ${$props.loading ? '--loading' : ''}  
                    ${$props.color ? '--color' : ''}  
                    ${$props.circle ? '--circle' : ''}  
                    ${$props.round ? '--round' : ''} `">
        <DuIcon type="loading" v-if="$props.loading"/> <slot />
    </button>

</template>


<style>

.du-button {

    --du-button-bg-color: var(--du-color-white);
    --du-button-text-color: var(--du-color-white);
    --du-button-radius: .2em;
    --du-button-padding-x: .5em;
    --du-button-padding-y: 1em;
    --du-button-radius: .2em;
    background-color: var(--du-button-bg-color);
    font-size: var(--du-font-size-base);
    color: var(--du-color-regular);
    padding: var(--du-button-padding-x) var(--du-button-padding-y);
    
    
    border: var(--du-border);

    cursor: pointer;
    outline: none;
}

/* 交互 */
/* 暂时不处理移动端兼容 */
.du-button:not(.--disabled):not(.--loading):hover {
    filter: brightness(1.1);
}
.du-button:not(.--disabled):not(.--loading):active {
    filter: brightness(.9);
}

/* type */
.du-button.--primary {
    --du-color-regular: #fff;
    border: none;
    --du-button-bg-color: var(--du-color-primary);
}
.du-button.--warning {
    --du-color-regular: #fff;
    border: none;
    --du-button-bg-color: var(--du-color-warning);
}
.du-button.--success {
    --du-color-regular: #fff;
    border: none;
    --du-button-bg-color: var(--du-color-success);
}
.du-button.--cancle {
    --du-color-regular: #fff;
    border: none;
    --du-button-bg-color: var(--du-color-cancle);
}
.du-button.--danger {
    --du-color-regular: #fff;
    border: none;
    --du-button-bg-color: var(--du-color-danger);
}

/* color */
.du-button.--color {
    border: none;
    --du-button-bg-color: v-bind($props.color);
}

/* radius */
.du-button.--round {
    border-radius: var(--du-button-radius);
}
.du-button.--circle {
    line-height: 0;
    --du-button-radius: 50%;
    --du-button-padding-y: var(--du-button-padding-x);
}

/* size */
.du-button.--large {
    --du-font-size-base: var(--du-font-size-large);
}
.du-button.--small {
    --du-font-size-base: var(--du-font-size-small);
}
/* loading */
.du-button.--loading {
    cursor: default;
    filter: brightness(.95);
}

/* disabled */
.du-button.--disabled {
    cursor: not-allowed;
    filter: brightness(.9);
}

/* icon */
.du-button > .du-icon:first-child {
    /* margin-right: 4px; */
}
.du-button > .du-icon:last-of-type {
    /* margin-left: 4px; */
}

</style>