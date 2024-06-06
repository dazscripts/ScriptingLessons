> [!CAUTION]
> not finished

# Organization

# Services
Roblox has different `Services`. Each can be accessed by using ```game:GetService(ServiceNameHere)```. Here is a few important services with explanations on what they can do.

## ReplicatedStorage
This is meant to store any module scripts that the client or server will access. Both the client and server can see anything inside of here.

## ReplicatedFirst
Anything inside of here will be loaded before anything else in the game gets loaded. ive only ever seen it used for custom loading screens but idk

## ServerScriptService
This is for scripts that will run on the server.

## ServerStorage
This is for any assets like maps that the client doesnt need unregulated access to.

## Players
This has all of the player instances inside of it.
<details>
  <summary>Methods & Events</summary>
  
### Methods
**:GetPlayers()**<br>
Returns a table of all players that are currently in the game

**GetPlayerFromCharacter(Character: model)**<br>
Returns the player instance associated with the character provided

**GetPlayerByUserId(UserId: number)**<br>
Returns a player instance for the UserId provided.

### Events

**PlayerAdded**
Fired whenever a player joins

**PlayerRemoving**
Fired whenever a player leaves

</details>

## UserInputService
