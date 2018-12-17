<template lang="pug">
  .chat
    .wrapper
      users
      .messages-wrapper
        transition-group.messages(
          ref="scroller"
          tag="div"
          name="messages"
        )
          .message(v-for="(message, index) in messages" :key="'message-' + index")
            .author orels1
            .text {{message}}
        .bottom
          //- .typing(v-show="typing") orels1 is typing...
          input(
            type="text"
            placeholder="type to chat"
            @input="showTyping"
            v-model="message"
            @keydown.enter="sendMessage"
          ).inputField
</template>

<script>
import Users from '@/components/Users.vue';
import { Vue, Component } from 'vue-property-decorator';

@Component({
  components: {
    users: Users,
  },
})
class Chat extends Vue {
  messages = [];

  message = null;

  typingTimeout = null;

  typing = false;

  sendMessage() {
    if (!this.message) {
      return;
    }
    this.messages.push(this.message);
    this.message = null;
  }

  updated() {
    this.$refs.scroller.$el.scrollTo(0, this.$refs.scroller.$el.scrollHeight);
  }

  showTyping() {
    if (this.typingTimeout) {
      clearTimeout(this.typingTimeout);
    }
    this.typing = true;
    this.typingTimeout = setTimeout(() => {
      this.typing = false;
    }, 1000);
  }
}
export default Chat;
</script>

<style scoped>
.chat {
  grid-area: content;
  width: 100%;
  display: flex;
  background-color: var(--base-green);
  min-height: 200px;
  position: relative;
  z-index: 2;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.6);
  border-left: 1px solid var(--shadow);
  border-right: 1px solid var(--shadow);
  padding: 15px;
}

.wrapper {
  background-color: var(--dark-green);
  width: 100%;
  display: flex;
  padding: 6px 6px;
  border-radius: 6px;
  box-shadow: inset 1px 0 0 rgba(255, 255, 255, 0.3),
    inset 0 -1px 0 rgba(255, 255, 255, 0.4),
    inset -1px 1px 2px rgba(0, 0, 0, 0.3);
}

.messages-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 100%;
  background-color: var(--dark);
  border-radius: 4px;
  padding: 5px 0;
  box-shadow: inset 1px 0 0 rgba(255, 255, 255, 0.3),
    inset 0 -1px 0 rgba(255, 255, 255, 0.3),
    inset -1px 1px 2px rgba(0, 0, 0, 0.3);
}

.messages {
  display: flex;
  flex-direction: column;
  overflow-y: scroll;
  align-items: stretch;
  scroll-behavior: smooth;
  height: 100%;
  font-family: "Inconsolata", monospace;
}

.message {
  margin: 5px;
  display: flex;
  justify-content: stretch;
  flex-shrink: 0;
  color: var(--text);
  align-items: flex-start;
}

.message-enter-active,
.message-leave-active {
  transition: all 300ms;
}
.message-enter,
.message-leave-to {
  opacity: 0;
  transform: translateY(30px);
}

.author {
  width: 100px;
  margin-right: 10px;
  margin-left: 10px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
  border: 2px solid var(--dark-text);
  border-radius: 4px;
  flex-shrink: 0;
  padding: 2px 0;
}

.text {
  padding: 5px 10px;
  background-color: var(--red);
  flex-grow: 1;
  text-align: left;
  border-radius: 4px;
  line-height: 16px;
}

.bottom {
  width: 100%;
  flex-direction: column;
  display: flex;
  position: relative;
  margin-bottom: 5px;
}

.typing {
  text-align: left;
  top: -7px;
  margin-left: 6px;
  color: var(--dark-text);
  font-size: 12px;
  font-style: italic;
  position: absolute;
}

.inputField {
  margin: 10px 5px 0 5px;
  height: 50px;
  background-color: var(--red);
  border: none;
  line-height: 50px;
  font-size: 14px;
  padding: 0 10px;
  color: var(--text);
  border-radius: 4px;
}

.inputField:focus {
  outline-style: solid;
  outline-width: 1px;
  outline-color: var(--dark-text);
}

.inputField::placeholder {
  color: var(--dark-text);
}
</style>
