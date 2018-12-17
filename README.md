# Chatsubo (exapunks)

## What's this? `(OwO)`

This is a clone of an "in-game chat" from the game [Exapunks](https://gog.com/game/exapunks). I was so inspired by the game that I wanted to make a discord client theme first, but then I realised that making a separate chat client would be faster :)

So in the end, here we are. It's not complete, and it's just the frontend part. I tried connecting it to discord with `discord.js` and it worked ok if you're not in a ton of servers, so take that as you will.

Current setup includes

- Vuex store with decorators from `vuex-class`
- Message sending to a local state
- Users list connected to the vuex-state

You can probably wire it up to some websocket-based backend in a couple hours and have a pretty neat chat client for throwaway discussion rooms. That was the intention anyways: to have a random room generated, and to use the room hash to join it.

Have fun!

## Project setup

```bash
yarn install
```

### Compiles and hot-reloads for development

```bash
yarn run serve
```

### Compiles and minifies for production

```bash
yarn run build
```

### Run your tests

```bash
yarn run test
```

### Lints and fixes files

```bash
yarn run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
