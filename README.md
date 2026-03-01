# Game Boy

A Game Boy and Game Boy Color emulator designed for running in vanilla JavaScript pre-ECMAScript 2015 (no WebAssembly). Simply open the link below, click the red icon, and select a ROM file in `GB` or `GBC` format from your computer; it will be loaded and booted automatically.

## Links:

- [Game Boy emulator](https://lrusso.github.io/GameBoy/GameBoy.htm)
- [Demo booting a sample game](https://lrusso.github.io/GameBoy/GameBoy.htm?demo)

## Screenshots:

![alt screenshot1](https://lrusso.github.io/GameBoy/SCREENSHOT1.jpg)

![alt screenshot2](https://lrusso.github.io/GameBoy/SCREENSHOT2.jpg)

![alt screenshot3](https://lrusso.github.io/GameBoy/SCREENSHOT3.jpg)

## How to use it:

Examples of loading local and online files can be found [here](https://github.com/lrusso/GameBoy/blob/main/GameBoy.htm#L132-L160) and [here](https://github.com/lrusso/GameBoy/blob/main/GameBoy.htm#L188-L211).

```js
embedGameBoy({
  container: "game",
  name: "Mortal Kombat 2",
  rom: romFile,
  player1: {
    up: "ArrowUp",
    down: "ArrowDown",
    left: "ArrowLeft",
    right: "ArrowRight",
    select: "KeyA",
    start: "KeyS",
    a: "KeyX",
    b: "KeyZ",
  },
  cbStarted: function cbStarted() {
    console.log("Emulator started.")
  },
})
```

| Parameter |    Type     | Required | Default value | Description               |
| :-------- | :---------: | :------: | :-----------: | :------------------------ |
| container |   string    |   yes    |       –       | Target element ID.        |
| name      |   string    |   yes    |       –       | Game name.                |
| rom       | ArrayBuffer |   yes    |       –       | ROM file.                 |
| player1   |   object    |    no    |       –       | Player 1 keys.            |
| cbStarted |  function   |    no    |       -       | Called on emulator start. |

## Special keys:

| Action          | macOS Shortcut | Windows Shortcut | Safari Shortcut |
| :-------------- | :------------: | :--------------: | :-------------: |
| Save state      |  Command + 1   |     Ctrl + 1     |    Ctrl + 1     |
| Load state      |  Command + 2   |     Ctrl + 2     |    Ctrl + 2     |
| Toggle sound    |  Command + 3   |     Ctrl + 3     |    Ctrl + 3     |
| Fullscreen mode |  Command + F   |     Ctrl + F     |    Ctrl + F     |
| Reset game      |  Command + R   |     Ctrl + R     |    Ctrl + R     |

## Main differences with the original project:

- Transpiled JS to pre-ES2015 via `node ConverterES5.js gambatte.js`.

## This is a modified version of Gambatte:

https://github.com/lrusso/gambatte-libretro

**NOTE:** Emscripten 4.0.23 was used to build the emulator.
