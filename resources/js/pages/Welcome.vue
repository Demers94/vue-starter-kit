<template>
    <div class="max-w-xl mx-auto py-8 flex flex-col items-center gap-8">
        <h1 class="text-4xl font-semibold">{{ $t('Hello world!') }}</h1>

        <Button @click="showModal = true">Open the modal!</Button>
    </div>

    <Modal v-model="showModal" title="Testing modal">
        <div>
            <div>
                <Label>Your Name</Label>
                <Input placeholder="John Doe" />
            </div>
        </div>
    </Modal>
</template>

<script setup>
    import Modal from '@/components/Modal.vue';
    import Button from '@/components/ui/button/Button.vue';
    import Input from '@/components/ui/input/Input.vue';
    import Label from '@/components/ui/label/Label.vue';
    import { ref } from 'vue';

    const showModal = ref(false);
</script>
