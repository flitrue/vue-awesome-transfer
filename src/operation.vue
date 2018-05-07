<template>
    <div :class="prefixCls + '-operation'">
        <i-button type="primary" size="small" :disabled="!rightActive" @click.native="moveToLeft">
            <i class="fa fa-angle-left" aria-hidden="true"></i> {{ operations[0] }}
        </i-button>
        <i-button type="primary" size="small" :disabled="!leftActive" @click.native="moveToRight">
            {{ operations[1] }} <i class="fa fa-angle-right" aria-hidden="true"></i>
        </i-button>
    </div>
</template>
<script>

    export default {
        name: 'Operation',
        props: {
            prefixCls: String,
            operations: Array,
            leftActive: Boolean,
            rightActive: Boolean
        },
        methods: {
            moveToLeft () {
                this.$parent.moveTo('left');
            },
            moveToRight () {
                this.$parent.moveTo('right');
            }
        }
    };
</script>
