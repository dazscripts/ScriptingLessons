# Client And Server
The client and the server have very direct purposes, the Client is to do any visuals or things that the server cant do and the server is to manage replication (sending things to all players) and keep the game secure.

## Scripts

### LocalScript
This is a script that specifically runs on the client. it will not do anything if not placed in `StarterGui`, `StarterCharacterScripts` or `StarterPlayerScripts`

### Script
This is a script designed to run on the server. it can be set to run in different contexts which changes its behavior.

**RunContext**


- Legacy<br>
This is the standard context. it makes the script run on the server in normal places like `workspace` and `ServerScriptService`.

- Client<br>
This will change the script to run in a client context. it will run anywhere the client has access to.

- Server<br>
This will change the script to run anywhere like in `ServerStorage`. i dont see any real usage for this

![image](https://github.com/dazscripts/ScriptingLessons/assets/71845855/c7c35008-e875-4cff-996a-c80a3c40c390)


## Communication
There are two ways the client and server can communicate with each other: `RemoteEvent` and `RemoteFunction`.

### RemoteEvent
This sends a signal to the other platform and can have arguements similar to a function

**Client**
```lua
local Remote = game:GetService("ReplicatedStorage"):WaitForChild("RemoteEvent")

-- Recieve events from the server
Remote.OnServerEvent:Connect(function(Arg1)
  print(Arg1)
end)

-- Fire the remote
Remote:FireServer("This is an arguement")
```

**Server**
> [!NOTE]
> The server recieves events differently than the client. when recieving an event the player who fired the remote will always be the first arguement
```lua
local Remote = Instance.new("RemoteEvent")
Remote.Parent = game:GetService("ReplicatedStorage")

-- Recieve events from clients
Remote.OnClientEvent:Connect(function(PlayerWhoFiredRemote, Arg)
  print(PlayerWhoFiredRemote.Name, Arg)
end)

-- Fire to an individual player
Remote:FireClient(PlayerInstanceGoesHere, "Arguement")

-- Fire to all players
Remote:FireAllClients("Arguement")
```

### RemoteFunction
This lets one platform ask the other for a value. for example the client can ask the server for data. I do not recommend having the server ask the client for values because it is not secure at all.

**Client**
```lua
local Remote = game:GetService("ReplicatedStorage"):WaitForChild("RemoteFunction")

-- Invoke the server
local Value = Remote:InvokeServer("Arguement") -- Will yield until the server returns a value
print(Value)

-- OnServerInvoke
Remote.OnServerInvoke = function(Arguement)
  return "Any value returned gets sent to the server"
end
```

**Server**
```lua
local Remote = Instance.new("RemoteFunction")
Remote.Parent = game:GetService("ReplicatedStorage")

-- OnClientInvoke
Remote.OnClientInvoke = function(PlayerWhoInvoked, Arguement)
  print(PlayerWhoInvoked.Name, Arguement)
  return "This gets sent to the client"
end

-- Invoke the client
Remote:InvokeClient(PlayerInstanceHere, "Arguement")
```

**But now how do we communicate across scripts in the same context??**

### BindableEvent
This lets a script in one context communicate to a script in the same context, for example a local script can talk to another local script.

```lua
local BindableEvent = Instance.new("BindableEvent")

-- Recieve Events
BindableEvent.Event:Connect(function(Arguement)
  print(Arguement)
end)

-- Fire Event
BindableEvent:Fire("Arguement")
```

### BindableFunction
This is the same thing as the `BindableEvent` but serves the same purpose as a `RemoteFunction`

```lua
local BindableFunction = Instance.new("BindableFunction")

-- Recieve Events
BindableFunction.OnInvoke = function(Arguement)
  print(Arguement)
  return "Funny String gets returned"
end

-- Invoke Event
BindableFunction:Invoke("Arguement")
```
