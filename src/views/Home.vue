<template lang="pug">
  .window
    .left-side
    chat-header
    .right-side
    chat
    chat-footer
</template>

<script>
import Header from '@/components/Header.vue';
import Footer from '@/components/Footer.vue';
import Chat from '@/components/Chat.vue';
import { Vue, Component } from 'vue-property-decorator';

@Component({
  components: {
    'chat-header': Header,
    'chat-footer': Footer,
    chat: Chat,
  },
})
class Home extends Vue {
}
export default Home;
</script>

<style scoped>
.window {
  height: 100%;
  width: 100%;
  display: grid;
  grid-template-columns: 10px 1fr 10px;
  grid-template-rows: 80px 1fr 20px;
  grid-template-areas:
    "left header right"
    "left content right"
    "left footer right";
}

.left-side {
  grid-area: left;
}

.right-side {
  grid-area: right;
}

.left-side,
.right-side {
  background-color: var(--base-yellow);
  width: 10px;
  height: 100%;
  box-shadow: inset -1px 1px 1px rgba(255, 255, 255, 0.3),
    inset 1px -1px 1px rgba(0, 0, 0, 0.3);
  position: relative;
  z-index: 3;
}
</style>
