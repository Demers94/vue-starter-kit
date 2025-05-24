<template>
    <Dialog :open="open" @update:open="open = $event">
        <DialogContent>
            <DialogHeader>
                <DialogTitle>{{ title }}</DialogTitle>
                <DialogDescription>{{ description }}</DialogDescription>
            </DialogHeader>

            <slot></slot>

            <DialogFooter>
                <slot name="footer"></slot>
            </DialogFooter>
        </DialogContent>
    </Dialog>
</template>

<script setup>
    import {
        Dialog,
        DialogContent,
        DialogDescription,
        DialogFooter,
        DialogHeader,
        DialogTitle,
        DialogTrigger,
    } from '@/components/ui/dialog';

    const props = defineProps({
        title: String,
        description: String,
    });

    const open = defineModel();
</script>
