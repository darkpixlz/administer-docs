# Plugins: Building and more

Now that you have a functioning plugin which can be inserted into a game, you should make it interface with Administer.



To start, you can require the API one of two ways.



```lua
-- Way 1
local API = require(script.Parent.Parent.Parent.PluginsAPI)
-- Way 2 (more reliable)
local API = require(game.ServerScriptService:WaitForChild("Administer").PluginsAPI)
```

Congrats! You now have access to the full API library. However, when you join the game, it won't work. To get it to work, you have to call `Build`. Here's an example:



<pre class="language-lua"><code class="lang-lua">API.BuildPlugin(
    {
    -- Button config
    	"rbxassetid://10065089093", --Image
	"Computer", -- Name
	script.Computer, --Frame
	"G", -- Position in the menu
	"This is an example plugin." -- Short description
    },
    require(script.Config)
<strong>    function()
</strong>        print("The plugin is now running!")
<strong>    end
</strong><strong>)
</strong></code></pre>
