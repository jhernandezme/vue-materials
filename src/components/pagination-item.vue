<template>
    <li :class="classes"
        @click.prevent="click"
    >
        <a href="#!">
            <slot></slot>
        </a>
    </li>
</template>

<script type="text/babel">
    export default {
        props: {
            active: {
                type: Boolean,
                default: false
            },

            color: {
                type: String,
                default: ''
            },

            disabled: {
                type: Boolean,
                default: false
            },

            waves: {
                type: Boolean,
                default: false
            }
        },

        computed: {
            classes () {
                return {
                    'active': this.active,
                    [this.color]: this.active,
                    'disabled': this.disabled,
                    'waves-effect': this.waves
                }
            }
        },

        methods: {
            click () {
                if (!this.disabled) {
                    this.$emit('click')
                }
            }
        }
    }
</script>
