# Constants and Variables

## alerts

Array to store alert messages or notifications.

```js
const alerts = [];
```
# Languages

This section lists the supported languages along with their language codes used throughout the project.

## Contents

- English (`en`)
- Turkce (`tr`)
- Vietnamese (`vi`)
- Chinese (Simplified) (`zh-CN`)
- Chinese (Traditional) (`zh-TW`)
- Japanese (`ja`)
- Korean (`ko`)
- French (`fr`)
- German (`de`)
- Spanish (`es`)
- Russian (`ru`)
- Italian (`it`)
- Portuguese (`pt`)
- Thai (`th`)
- Arabic (`ar`)
- Hindi (`hi`)
- Indonesian (`id`)

---

## Language Codes

| Language             | Code  |
|----------------------|-------|
| English              | en    |
| Turkce               | tr    |
| Vietnamese           | vi    |
| Chinese (Simplified) | zh-CN |
| Chinese (Traditional)| zh-TW |
| Japanese             | ja    |
| Korean               | ko    |
| French               | fr    |
| German               | de    |
| Spanish              | es    |
| Russian              | ru    |
| Italian              | it    |
| Portuguese           | pt    |
| Thai                 | th    |
| Arabic               | ar    |
| Hindi                | hi    |
| Indonesian           | id    |

---
# states

The `STATE` object defines various status flags used in the game logic. Each state is represented by a unique power of two, allowing them to be combined using bitwise operations.

| State       | Value | Description                      |
|-------------|-------|---------------------------------|
| DELETE      | 1     | Entity marked for deletion       |
| HURT        | 2     | Entity is hurt                   |
| COLD        | 4     | Entity is affected by cold       |
| HUNGER      | 8     | Entity is hungry                 |
| ATTACK      | 16    | Entity is attacking              |
| WALK        | 32    | Entity is walking                |
| IDLE        | 64    | Entity is idle                   |
| HEAL        | 128   | Entity is healing                |
| WEB         | 256   | Entity is caught in a web effect |

---

# packets

The `packets` object lists the packet types used for network communication, each mapped to a specific numeric code. These are used to identify different types of actions or commands sent between client and server.

| Packet Name      | Code | Description                   |
|------------------|------|-------------------------------|
| angle            | 10   | Send angle/direction update   |
| attack           | 19   | Initiate attack action        |
| stopAttack       | 38   | Stop attack action            |
| selectInv        | 33   | Select inventory item         |
| craft            | 13   | Start crafting                |
| chat             | 5    | Send chat message             |
| build            | 17   | Build structure               |
| update_cam       | 0    | Update camera position        |
| equip            | 33   | Equip an item                 |
| drop_one         | 35   | Drop one item                 |
| drop_all         | 27   | Drop all items                |
| resurrection     | 30   | Resurrection action           |
| extractorput     | 11   | Put item into extractor       |
| extractortake    | 21   | Take item from extractor      |
| chestTake        | 9    | Take item from chest          |
| put_windmill     | 37   | Place a windmill              |
| take_windmill    | 20   | Remove a windmill             |
| put_wood_oven    | 36   | Place a wood oven             |
| put_flour_oven   | 1    | Place a flour oven            |
| take_bread       | 25   | Take bread from oven          |
| put_chest        | 24   | Place a chest                 |
| join_totem       | 12   | Join a totem                  |
| cancel_crafting  | 32   | Cancel crafting process       |
| recycle          | 31   | Recycle item                  |

---
# sprite

`sprite` is an array that holds image data for sprites used in the game.

---
## `world`

| Property       | Type                | Description                                      |
|----------------|---------------------|------------------------------------------------|
| `units`        | `Array<Object>`     | All units in the game (mobs, players).|
| `fast_units`        | `Array<Object>`     | All fast_units in the game (mobs, players).|
| `dist_winter`  | `number`            | Distance between the player and winter. If true 1 else 0    |
| `dist_water`  | `number`            | Distance between the player and water. If true 1 else 0    |
| `dist_lava`  | `number`            | Distance between the player and lava. If true 1 else 0    |
| `dist_desert`  | `number`            | Distance between the player and desert. If true 1 else 0    |
| `dist_forest`  | `number`            | Distance between the player and forest. If true 1 else 0    |
| `dist_dragon`  | `number`            | Distance between the player and dragon. If true 1 else 0    |
| `pid`       | `property`            | Player's unique id.                     |
| `vehicle`       | `property`            | Player vehicle status.                     |
| `fly`       | `property`            | Player vehicle status.                     |
| `clothe`       | `property`            | Player vehicle status.                     |
| `speed`       | `property`            | Player vehicle status.                     |
| `ghost`       | `property`            | Player vehicle status.                     |
| `drawcrate`     | `Function`          | The function used for in-game drawing.           |
| `drawplayer`     | `Function`          | The function used for in-game drawing.           |
| `players`     | `Array` | Returns the serverlist|



## `user`

| Property       | Type                | Description                                      |
|----------------|---------------------|------------------------------------------------|
| `team`         | `string` or `number`| Player's team information.                        |
| `cam`       | `Object`            | Information related to the player's camera.      |
| `craft`        | `Object`            | Data related to the crafting.              |
| `chat`         | `Object`            | Chat interface and data.                           |
| `inv`    | `Array<Object>`     | Items in the player's inventory.                   |
| `craft.preview`| `number`            | Preview the build |
| `terminal`     | `Object` | Terminal interface and data. |
| `uid` | `number` | Unit ID |
| `inv.n` | `Array`| User's inventory data |
| `all_inv`| `Array`| User's inventory data |


## `client`

| Property       | Type                | Description                                      |
|----------------|---------------------|------------------------------------------------|
| `socket`           | `WebSocket`         | The game's WebSocket connection.                  |
| `chat`         | `Function`          | The function responsible for get chatting.|
| `send_chat` | `Function` | The function hooks sending chat |
| `send_attack` | `Function` | The function for attacking |
| `send_move` | `Function` | The function for moving |
| `send_angle` | `Function` | The function for angle |
| `select_inv` | `Function` | The function for select item in inv |
| `send_build` | `Function` | The function build item |
| `recycle_inv` | `Function` | The function for recycle item |
| `select_craft` | `Function` | The function for craft item |
| `give_item` | `Function` | The function for put item to chest |

## `ui`
| Property       | Type                | Description                                      |
|----------------|---------------------|------------------------------------------------|
| `chest_buttons` | `object` | Chest buttons in the game for making chest info |
| `minimap` | `object` | Controls the minimap |

## `mouse`
| Property       | Type                | Description                                      |
|----------------|---------------------|------------------------------------------------|
| `pos` | `object` | Returns mouse pos {x: 0, y: 0} |

## workertimers

`workertimers` provides **Web Worker-based timers** for browsers, offering more accurate and reliable timing than native `setTimeout` and `setInterval`.

---

## `setTimeout(callback, delay)`

Executes the given function once after the specified delay. Uses Web Worker for better timing accuracy.

### Parameters

- `callback` **(Function)**: The function to execute.
- `delay` **(number)**: Delay time in milliseconds.

### Returns

- `number`: Timeout ID that can be canceled with `clearTimeout`.

```js
const id = workertimers.setTimeout(() => {
  console.log('Executed after 1 second');
}, 1000);
```

---

## `clearTimeout(id)`

Cancels a timeout created by `setTimeout`.

### Parameters

- `id` **(number)**: The ID of the timeout to cancel.

### Returns

- `void`

```js
workertimers.clearTimeout(id);
```

---

## `setInterval(callback, interval)`

Runs the given function repeatedly at specified intervals. Uses Web Worker for improved precision.

### Parameters

- `callback` **(Function)**: The function to run repeatedly.
- `interval` **(number)**: Interval time in milliseconds.

### Returns

- `number`: Interval ID that can be canceled with `clearInterval`.

```js
const intervalId = workertimers.setInterval(() => {
  console.log('Runs every 2 seconds');
}, 2000);
```

---

## `clearInterval(id)`

Stops a repeating timer created by `setInterval`.

### Parameters

- `id` **(number)**: The ID of the interval to cancel.

### Returns

- `void`

```js
workertimers.clearInterval(intervalId);
```

