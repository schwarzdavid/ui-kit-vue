<template>
    <h1>Hi</h1>
</template>

<script lang="ts" setup>
    import type {
        FormDialogComponentEmits,
        FormDialogComponentExposed,
        FormDialogComponentProps,
    } from '@/composables/dialog/presets/FormDialogProps'

    defineProps<FormDialogComponentProps>()

    defineEmits<FormDialogComponentEmits>()

    defineExpose<FormDialogComponentExposed<string>>({
        finish(): Promise<string> {
            console.log('hi')
            return Promise.resolve('Hi')
        },
    })

    const model = defineModel('loading')

    function log() {
        console.log(model.value)
    }
</script>
