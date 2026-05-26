## How to create a chat tag

### Step 1: Define who to give it to

```js
const Target = "John" ; // use ; -- its important
```

### Step 2: Define what call back we wanna use
```js
onPlayerChat = (playerId, message) => {
    // the heart of stuff will go here.
} 
```

### Step 3: Get the players name
```js
let plr = api.getEntityName(playerId) // plr = player
```

### Step 4: Check if the player is listed in target.
```js
if (Target.includes(plr)) {
    // heart of stuff goes here
}
```

### Step 5: Make it broadcast to the chat with the tag.
```js
api.broadcastMessage([
            { str: "[", style: { color: "lime", fontWeight: "bold" } },
            { icon: "star", style: { color: "red" } },
            { str: " Owner", style: { color: "yellow", fontWeight: "bold" } },
            { str: "] ", style: { color: "lime", fontWeight: "bold" } },
            { str: plr, style: { color: "cyan" } },
            { str: ": " + message, style: { color: "white" } }
        ])
```

### Your end result should look like
```js
const Target = "John"

onPlayerChat = (playerId, message) => {
    let plr = api.getEntityName(playerId)

    if (Target.includes(plr)) {
        api.broadcastMessage([
            { str: "[", style: { color: "lime", fontWeight: "bold" } },
            { icon: "star", style: { color: "red" } },
            { str: " Owner", style: { color: "yellow", fontWeight: "bold" } },
            { str: "] ", style: { color: "lime", fontWeight: "bold" } },
            { str: plr, style: { color: "cyan" } },
            { str: ": " + message, style: { color: "white" } }
        ])
        
    }
}
```
