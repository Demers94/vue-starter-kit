<script setup>
    import { cn } from '@/lib/utils';
    import { reactiveOmit } from '@vueuse/core';
    import { DialogDescription, useForwardProps } from 'reka-ui';

    const props = defineProps({
        asChild: { type: Boolean, required: false },
        as: { type: null, required: false },
        class: { type: null, required: false },
    });

    const delegatedProps = reactiveOmit(props, 'class');

    const forwardedProps = useForwardProps(delegatedProps);
</script>

<template>
    <DialogDescription data-slot="dialog-description" v-bind="forwardedProps" :class="cn('text-muted-foreground text-sm', props.class)">
        <slot />
    </DialogDescription>
</template>
