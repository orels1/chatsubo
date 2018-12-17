<template lang="pug">
  .header
    .spacer
      .left
      .center
      .right
    .nameplate
      .name Chatsubo
      .version Ver {{version}}
</template>

<script>
import { Vue, Component } from 'vue-property-decorator';
import { State } from 'vuex-class';

@Component
class Header extends Vue {
  @State version
}
export default Header;
</script>

<style scoped>
.header {
  grid-area: header;
  height: 100%;
  width: 100%;
  background-color: var(--base-green);
  display: flex;
  flex-direction: column;
}

.spacer {
  -webkit-app-region: drag;
  display: flex;
  width: 100%;
  height: 23px;
  border-bottom: 1px solid var(--shadow);
  border-right: 1px solid var(--shadow);
  background-image: linear-gradient(
    #66786b,
    #8cbf95 1px,
    #719983 2px,
    #526865 3px,
    #49605d 21px,
    #203739 22px
  );
}

.left {
  width: 12px;
  border-right: 1px solid #1d3937;
  border-left: 1px solid var(--shadow);
}

.center {
  width: 100%;
}

.right {
  width: 12px;
  border-right: 1px solid #678c77;
  border-left: 1px solid #678c77;
}

.left,
.center,
.right {
  height: 100%;
  -webkit-app-region: drag;
}

.nameplate {
  height: 100%;
  width: 100%;
  background-color: var(--base-yellow);
  box-shadow: inset 1px -1px 2px rgba(0, 0, 0, 0.3), inset 0 1px #e7d7b0;
  border: 1px solid var(--shadow);
  border-bottom-color: #2c4744;
  display: flex;
  text-transform: uppercase;
  justify-content: space-between;
  align-items: center;
  padding: 0 30px;
}

.name,
.version {
  font-family: "Six Caps", sans-serif;
  font-size: 35px;
  background-color: #c8bb9c;
  color: transparent;
  text-shadow: 1px -1px 0 #826e55;
  background-clip: text;
  -webkit-background-clip: text;
  letter-spacing: 7px;
}
</style>
