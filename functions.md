# Functions

## `setUnwritable(object, property)`

Marks a property on a given object as **non-writable**, preventing any future modifications to its value.

### Parameters

- `object` **(Object)**: The target object containing the property.
- `property` **(string)**: The name of the property to make non-writable.

### Returns

- `void`: This function does not return a value.

## `createText(ctx, text, x, y, font=22, linewidh=6, fillColor="white", strokeColor="black")`

Draws styled text (both stroke and fill) on the canvas.

### Parameters
- `ctx` **CanvasRenderingContext2D**: The canvas context to draw on.
- `text` **string**: The text content to display.
- `x` **number**: X-coordinate to position the text.
- `y` **number**: Y-coordinate to position the text.
- `font` **number** *(optional)*: Font size in pixels. Default is `22`.
- `linewidh` **number** *(optional)*: Stroke width. Default is `6`.
- `fillColor` **string** *(optional)*: Text fill color. Default is `"white"`.
- `strokeColor` **string** *(optional)*: Text stroke color. Default is `"black"`.

### Returns
- `void`: Draws a text on canvas.

---

## `setGetter(object, property, key)`

Defines a getter for a given property that returns the value of a different key.

### Parameters
- `object` **Object**: The target object.
- `property` **string**: Property name to define a getter on.
- `key` **string**: The actual key whose value will be returned by the getter.

### Returns
- `void`

---

## `canSelect(id)`

Checks whether a given item ID exists in the user's inventory.

### Parameters
- `id` **string | number**: The ID of the item.

### Returns
- `boolean`: `true` if the item exists, `false` otherwise.

---

## `isAlly(id)`

Checks if the given ID is the user or a teammate.

### Parameters
- `id` **string | number**: Player ID to check.

### Returns
- `boolean`: `true` if the ID belongs to the user or a teammate.

---

## `getdist(a, b)`

Calculates the Euclidean distance between two points.

### Parameters
- `a` **{x: number, y: number}**: First point.
- `b` **{x: number, y: number}**: Second point.

### Returns
- `number`: Distance between point `a` and point `b`.

---

## `ctxDrawImage(ctx, img, b, c, d, e, f, g, h, i)`

Draws an image on the canvas using various drawImage overloads.

### Parameters
- `ctx` **CanvasRenderingContext2D**: The canvas context.
- `img` **Image**: Image object (must have `tryLoad()` method).
- `b, c, d, e, f, g, h, i` *(optional)*: Standard drawImage parameters.

### Returns
- `void`: Draws a image on canvas.

---

## `isSpike(PoSTresult)`

Determines if a given item ID is a spike type.

### Parameters
- `PoSTresult` **string | number**: Item ID to check.

### Returns
- `boolean`: `true` if the item is a spike.

---

## `circle(ctx, x, y, r)`

Creates a circular path on the canvas context (does not fill/stroke it).

### Parameters
- `ctx` **CanvasRenderingContext2D**: Canvas context.
- `x` **number**: X-coordinate of the circle center.
- `y` **number**: Y-coordinate of the circle center.
- `r` **number**: Radius of the circle.

### Returns
- `void`: Draws a circle on the canvas.

## `createAlert(title, text, position = "bottomright", alertTimeout = 3000, col = "#2ecc7")`

Displays a visual alert box on the canvas at a specified screen corner.

### Parameters
- `title` **(string)**: The alert's title text.
- `text` **(string)**: The alert's message body.
- `position` **(string, optional)**: One of `'topleft'`, `'topright'`, `'bottomleft'`, `'bottomright'`. Default is `'bottomright'`.
- `alertTimeout` **(number, optional)**: Duration in milliseconds before the alert disappears. Default is `3000`.
- `col` **(string, optional)**: The outer color of the alert box. Default is `"#2ecc7"`.

### Description
Adds a new alert object to the global `alerts` array. To render the alert visually, `drawAlerts(ctx)` must be called.

---

## `drawAlerts(ctx)`

Draws all currently active alerts on the canvas.

### Parameters
- `ctx` **(CanvasRenderingContext2D)**: The canvas context used for drawing.

### Description
Renders alert boxes that are still within their timeout duration. Each alert includes:
- Outer and inner rounded box
- Drop shadow effect
- Title and message text
- A time-based progress bar indicating how long the alert will remain visible

---

## `setCookie(name, value, days)`

Sets a browser cookie with an optional expiration period.

### Parameters
- `name` **(string)**: The name of the cookie.
- `value` **(string)**: The value to store.
- `days` **(number, optional)**: Number of days until the cookie expires.

### Description
If `days` is specified, the cookie will persist until that many days have passed; otherwise, it's a session cookie.

---

## `getCookie(name)`

Retrieves the value of a browser cookie.

### Parameters
- `name` **(string)**: The name of the cookie to retrieve.

### Returns
- **(string | null)**: The value of the cookie if found, otherwise `null`.

---
### `calcDamage(obj)`

Calculates how much damage is dealt to a target based on its type.

#### Parameters

- `obj` *(object)*: Target object containing `.type`

#### Returns

- `number`: Damage amount

#### Damage by Type

| Type                  | Damage |
|-----------------------|--------|
| `ITEMS.PLAYERS`       | null   |
| `ITEMS.WOLF`          | 40     |
| `ITEMS.SPIDER`        | 30     |
| `ITEMS.BOAR`          | 50     |
| `ITEMS.HAWK`          | 40     |
| `ITEMS.FOX`           | 40     |
| `ITEMS.BEAR`          | 60     |
| `ITEMS.BABY_MAMMOTH`  | 50     |
| `ITEMS.MAMMOTH`       | 90     |
| `ITEMS.BABY_DRAGON`   | 30     |
| `ITEMS.DRAGON`        | 85     |
| `ITEMS.CRAB`          | 35     |
| `ITEMS.CRAB_BOSS`     | 80     |
| `ITEMS.PIRANHA`       | 40     |
| `ITEMS.KRAKEN`        | 60     |
| `ITEMS.FLAME`         | 50     |
| `ITEMS.LAVA_DRAGON`   | 90     |
| `ITEMS.BABY_LAVA`     | 70     |
| `ITEMS.VULTURE`       | 45     |
| `ITEMS.SAND_WORM`     | 60     |
| `ITEMS.REIDITE_SPIKE` | 60     |
| `ITEMS.AMETHYST_SPIKE`| 50     |
| `ITEMS.DIAMOND_SPIKE` | 40     |
| `ITEMS.GOLD_SPIKE`    | 30     |
| `ITEMS.STONE_SPIKE`   | 20     |
| `ITEMS.SPIKE`         | 10     |
| Others                | 0      |

---
###  `holdWeapon(id, t)`

Determines weapon type from inventory ID.

#### Parameters

- `id` *(number)*: Inventory item ID
- `t` *(boolean)*: If true, checks for hammer or empty

#### Returns

- `number`: Weapon type code

| Return | Weapon      |
|--------|-------------|
| 0      | Unknown     |
| 1      | Sword       |
| 2      | Spear       |
| 3      | Bow         |
| 4      | Axe         |
| 5      | Hammer      |
| 6      | No Weapon   |

#### Notes

- If `id === -1` and `t === true`, returns `6`
- Matches against constants like `INV.SWORD`, `INV.BOW`, etc.

---
### 🗡️ `weaponRange(player)`

Returns the attack range based on the player's held weapon and flying state.

#### Parameters

- `player` *(object)*: Player object, must include:
  - `right`: weapon ID
  - `fly`: `true` if flying, `false` if not

#### Returns

- `number`: Effective attack range

#### Range Table

| Weapon Type | Flying | Range  |
|-------------|--------|--------|
| Sword       | Yes    | 196.8  |
| Sword       | No     | 157.6  |
| Spear       | Yes    | 291.8  |
| Spear       | No     | 227.6  |
| Bow         | Any    | 0      |
| Axe         | Yes    | 142    |
| Axe         | No     | 131    |
| Hammer      | Any    | 125    |
| No Weapon   | Any    | 97.6   |

---
## `joinTotem(pid, id)`
Joins the player to a totem.

### Parameters
- `pid` **(number)**: The player's ID.
- `id` **(number)**: The totem's ID.

### Returns
- `void`

---

## `equipItem(id)`
Equips an item to the player.

### Parameters
- `id` **(number)**: The item ID to equip.

### Returns
- `void`

---

## `takeExtractor(pid, id, extid)`
Takes resources from an extractor.

### Parameters
- `pid` **(number)**: Player ID.
- `id` **(number)**: Extractor object ID.
- `extid` **(number)**: Extractor inv ID.

### Returns
- `void`

---

## `putExtractor(pid, id, extid)`
Puts resources into an extractor.

### Parameters
- `pid` **(number)**: Player ID.
- `id` **(number)**: Extractor object ID.
- `extid` **(number)**: Extractor inv ID.

### Returns
- `void`

---

## `putOven(pid, id)`
Puts flour and wood into an oven.

### Parameters
- `pid` **(number)**: Player ID.
- `id` **(number)**: Oven object ID.

### Returns
- `void`

---

## `takeOven(pid, id)`
Takes bread from the oven.

### Parameters
- `pid` **(number)**: Player ID.
- `id` **(number)**: Oven object ID.

### Returns
- `void`

---

## `putWindmill(pid, id)`
Puts resources into a windmill.

### Parameters
- `pid` **(number)**: Player ID.
- `id` **(number)**: Windmill object ID.

### Returns
- `void`

---

## `takeWindmill(pid, id)`
Takes resources from a windmill.

### Parameters
- `pid` **(number)**: Player ID.
- `id` **(number)**: Windmill object ID.

### Returns
- `void`

---

## `DropItem(id)`
Drops an item from the inventory.

### Parameters
- `id` **(number)**: The ID of the item to drop.

### Returns
- `void`

---

## `sendMove(movement)`
Sends a movement signal to the server.

### Parameters
- `movement` **(number)**: Movement direction or state.

### Returns
- `void`

---

## `ReBorn(pid, id)`
Reborns the player.

### Parameters
- `pid` **(number)**: Player ID.
- `id` **(number)**: Resurrection ID.

### Returns
- `void`

---

## `putBuild(id)`
Places a building at the current angle.

### Parameters
- `id` **(number)**: Building ID.

### Returns
- `void`

---

## `takeChest(pid, id)`
Takes contents from a chest.

### Parameters
- `pid` **(number)**: Player ID.
- `id` **(number)**: Chest object ID.

### Returns
- `void`

---

## `sendAngle(angl)`
Sends player rotation angle to the server.

### Parameters
- `angl` **(number)**: Rotation angle in radians.

### Returns
- `void`

---

## `sendAttack(angl)`
Sends an attack command at a specific angle.

### Parameters
- `angl` **(number)**: Attack angle in radians.

### Returns
- `void`

---

## `stopAttack()`
Stops the current attack action.

### Parameters
- _None_

### Returns
- `void`

---
## `getFood()`
Returns the first available food item in the inventory that can be selected.

### Parameters
- _None_

### Returns
- `number|null`: The inventory ID of the available food item, or `null` if none are available.

---

## `calcMeandEnemy(myPlayer, enemy, isTrue)`
Calculates the angle between the player and an enemy, using either relative or absolute coordinates.

### Parameters
- `myPlayer` **(Object)**: The current player's data.
- `enemy` **(Object)**: The enemy's data.
- `isTrue` **(boolean)**: Whether to use `.r.x` and `.r.y` (true) or `.x` and `.y` (false) properties.

### Returns
- `number|null`: The angle in radians between the player and the enemy, or `null` if any object is missing.

---

## `send(data)`
Sends a raw data packet to the server through the socket.

### Parameters
- `data` **(Array|Object)**: The data to send, which will be serialized using `JSON.stringify`.

### Returns
- `void`

