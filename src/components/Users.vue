<template lang="pug">
  .users
    .room(:style="iconBg('roomIcon')") 64efc4 ({{online.length}})
    .user(v-for="user in online" :key="user" :style="iconBg('sectionMark')")
      .name(:style="iconBg('userIcon')") {{user}}
</template>

<script>
import roomIcon from '@/assets/room.svg';
import userIcon from '@/assets/user.svg';
import sectionMark from '@/assets/sectionMark.svg';
import { Vue, Component } from 'vue-property-decorator';
import { State } from 'vuex-class';

@Component
class Users extends Vue {
  @State online

  userIcon = userIcon;

  sectionMark = sectionMark;

  roomIcon = roomIcon;

  iconBg(icon) {
    return ({
      backgroundImage: `url(${this[icon]})`,
    });
  }
}
export default Users;
</script>

<style scoped>
.users {
  width: 200px;
  flex-shrink: 0;
  background-color: var(--dark);
  border-radius: 4px;
  display: flex;
  flex-direction: column;
  overflow-y: scroll;
  align-items: center;
  padding: 25px;
  justify-content: flex-start;
  margin-right: 8px;
  box-shadow: inset 1px 0 0 rgba(255, 255, 255, 0.3),
    inset 0 -1px 0 rgba(255, 255, 255, 0.3),
    inset -1px 1px 2px rgba(0, 0, 0, 0.3);
}

.user {
  text-align: left;
  width: 100%;
  padding: 16px 0 0 27px;
  background-size: 19px 23px;
  background-position: left top;
  background-repeat: no-repeat;
  margin-bottom: 2px;
  margin-left: 12px;
}

.name {
  color: var(--text);
  font-size: 14px;
  font-family: "Inconsolata", monospace;
  font-weight: 600;
  background-size: 14px;
  background-position: left center;
  background-repeat: no-repeat;
  padding-left: 23px;
}

.room {
  text-align: left;
  width: 100%;
  color: var(--text);
  font-size: 12px;
  font-family: "Inconsolata", monospace;
  font-weight: 600;
  text-transform: uppercase;
  background-size: contain;
  background-position: left center;
  background-repeat: no-repeat;
  padding-left: 30px;
  margin-bottom: 5px;
}
</style>
