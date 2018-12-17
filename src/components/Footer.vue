<template lang="pug">
  .footer
    .panel
    .panel
</template>

<script>
import { Vue, Component } from 'vue-property-decorator';

@Component
class Footer extends Vue {
}
export default Footer;
</script>

<style scoped>
.footer {
  position: relative;
  z-index: 1;
  background-color: var(--dark-green);
  grid-area: footer;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  border-right: 1px solid var(--shadow);
  border-left: 1px solid var(--shadow);
}

.panel {
  background-color: var(--dark-green);
  box-shadow: inset 0 1px 1px rgba(255, 255, 255, 0.2),
    inset 0 -1px 1px rgba(0, 0, 0, 0.3);
  height: 10px;
  border-bottom: 1px solid var(--shadow);
}
</style>
