<script setup>
import ModalExample from './modal/examples/ModalExample.vue';
import ModalSizeExample from './modal/examples/ModalSizeExample.vue';
import ModalEscapableExample from './modal/examples/ModalEscapableExample.vue';
</script>
# Vue Modal - Flowbite

## Demo

<ModalExample />

```vue
<script setup>
import { Modal } from 'flowbite-vue'
import { ref } from 'vue'

const isShowModal = ref(false)
function closeModal() {
  isShowModal.value = false
}
function showModal() {
  isShowModal.value = true
}
</script>
<template>
    <button @click="showModal" type="button" class="mt-5 text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
        Show modal
    </button>
    <Modal :size="size" v-if="isShowModal" @close="closeModal">
      <template #header>
        <div class="flex items-center text-lg">
          Terms of Service
        </div>
      </template>
      <template #body>
        <p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
          With less than a month to go before the European Union enacts new consumer privacy laws for its citizens, companies around the world are updating their terms of service agreements to comply.
        </p>
        <p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
          The European Union’s General Data Protection Regulation (G.D.P.R.) goes into effect on May 25 and is meant to ensure a common set of data rights in the European Union. It requires organizations to notify users as soon as possible of high-risk data breaches that could personally affect them.
        </p>
      </template>
      <template #footer>
        <div class="flex justify-between">
          <button @click="closeModal" type="button" class="text-gray-500 bg-white hover:bg-gray-100 focus:ring-4 focus:outline-none focus:ring-blue-300 rounded-lg border border-gray-200 text-sm font-medium px-5 py-2.5 hover:text-gray-900 focus:z-10 dark:bg-gray-700 dark:text-gray-300 dark:border-gray-500 dark:hover:text-white dark:hover:bg-gray-600 dark:focus:ring-gray-600">
            Decline
          </button>
          <button @click="closeModal" type="button" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
            I accept
          </button>
        </div>
      </template>
    </Modal>
</template>
```

## Size

You can use four different modal sizing options starting from small to extra large, but keep in mind that the width of these modals will remain the same when browsing on smaller devices.

`xs`, `sm`, `md`, `lg`, `xl`, `2xl`, `3xl`, `4xl`, `5xl`, `6xl`, `7xl`

The default value is: `2xl`

Demo:
<ModalSizeExample/>

```vue
<script setup>
import { Modal } from 'flowbite-vue'
</script>
<template>
    <Modal size="xs" />
    <Modal size="md" />
    <Modal size="xl" />
    <Modal size="5xl" />
</template>
```

## Escapable

The escapable property is true by default to improve user experience and accessibility.

This means that you may close the modal by

 - Using the close button on the modal
 - Clicking outside of the modal
 - Pressing the escape key

In some situations, your user may be required to interact with the modal content. If this is the case, you can set the `escapable` property to false. The developer can then choose when they want to close the modal.

Demo:
<ModalEscapableExample/>

```vue
<script setup>
import { Modal } from 'flowbite-vue'
</script>
<template>
    <Modal />
    <Modal :escapable="false" />
</template>
```
