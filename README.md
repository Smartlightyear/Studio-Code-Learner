# Studio-Code-Learner
by Smartlightyear

# Touched Events
```lua
local block = script.Parent
local cooldownTime = 5 -- seconds
local lastTouched = {} -- stores player touch timestamps

block.Touched:Connect(function(hit)
	local character = hit.Parent
	local humanoid = character:FindFirstChild("Humanoid")

	if humanoid then
		local player = game.Players:GetPlayerFromCharacter(character)
		if not player then return end

		local lastTime = lastTouched[player.UserId] or 0
		if tick() - lastTime < cooldownTime then
			return
		end
```

# No Cooldown
```lua
block = script.Parent

block.Touched:Connect(function(hit)
	local character = hit.Parent
	local humanoid = character:FindFirstChild("Humanoid")

	if humanoid then
		print(character.Name .. " touched the block!")
		-- Add your custom logic here
	end
end)
```

# Badge giver on touch
```
script.Parent.Touched:Connect(function(part)
	if part.Parent:FindFirstChild("Humanoid") then
		local player = game.Players:GetPlayerFromCharacter(part.Parent)
		game:GetService("BadgeService"):AwardBadge(player.UserId, 3858858562832058) -- Put your badge id
	end
end)
```


		lastTouched[player.UserId] = tick()
		print(character.Name .. " touched the block!")

		-- Add your custom logic here
	end
end)```
