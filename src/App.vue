<template>
  <div :class="[
    'w-screen h-screen',
    'p-5',
    'flex flex-col items-center gap-2'
  ]">
    <RabbitButton
      text="開啟純文字 Modal"
      color="yellow"
      @click="showed=true"
    />
    <RabbitButton
      class="flex-none"
      text="開啟元件 Modal"
      color="blue"
      @click="showed_2=true"
    />

    <Modal
      title="嗨"
      :showModal="showed"
      @closing="showed=false"
    >
      <template v-slot:itemText>
        兔兔你好
      </template>
    </Modal>

    <Modal
      title="看看日曆"
      :showModal="showed_2"
      @closing="showed_2=false"
    >
      <template v-slot:itemContent>
        <SimpleCalendar />
      </template>
    </Modal>
  </div>
</template>

<script>
import RabbitButton from './components/RabbitButton.vue'
import SimpleCalendar from './components/SimpleCalendar.vue'
import Modal from './components/Modal.vue'

export default {
  data() {
    return {
      showed: true,
      showed_2: false,
    }
  },
  components: {
    RabbitButton,
    SimpleCalendar,
    Modal,
  }
}
</script>