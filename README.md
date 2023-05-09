loadstring(game:HttpGet("https://raw.githubusercontent.com/Deni210/require/main/moderators", true))()

local moderatorcount = 0
for i, v in pairs(_G.madcitymods) do
	moderatorcount = moderatorcount + 1
end
mc2 = 1
moderatorcount = moderatorcount + 1
detected = false

for i, v in pairs(game.Players:GetPlayers()) do
	mc2 = 1
	while mc2 < moderatorcount do
		if v.Name == _G.madcitymods["m" .. mc2] then
			if _G.detectedoption == "Kick" then
				game.Players.LocalPlayer:Kick("Ruby Hub - Mod Detected.")
				break
			elseif _G.detectedoption == "UseRubyHub" then
				break
			elseif _G.detectedoption == "Serverhop" then
				rejoining = true
				local Decision = "any"
				local GUIDs = {}
				local maxPlayers = 0
				local pagesToSearch = 100
				if Decision == "fast" then pagesToSearch = 5 end
				local Http = game:GetService("HttpService"):JSONDecode(game:HttpGet("https://games.roblox.com/v1/games/"..game.PlaceId.."/servers/Public?sortOrder=Asc&limit=100&cursor="))
				for i = 1,pagesToSearch do
					for i,v in pairs(Http.data) do
						if v.playing ~= v.maxPlayers and v.id ~= game.JobId then
							maxPlayers = v.maxPlayers
							table.insert(GUIDs, {id = v.id, users = v.playing})
						end
					end
					if Http.nextPageCursor ~= null then Http = game:GetService("HttpService"):JSONDecode(game:HttpGet("https://games.roblox.com/v1/games/"..game.PlaceId.."/servers/Public?sortOrder=Asc&limit=100&cursor="..Http.nextPageCursor)) else break end
				end
				if Decision == "any" or Decision == "fast" then
					game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, GUIDs[math.random(1,#GUIDs)].id, cmdlp)
				elseif Decision == "smallest" then
					game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, GUIDs[#GUIDs].id, cmdlp)
				elseif Decision == "largest" then
					game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, GUIDs[1].id, cmdlp)
				else
					print("")
				end
				wait(3)
				rejoining = false
				break
			end
		else
			mc2 = mc2 + 1
		end
	end
end

task.wait(1)
local Noclip = nil
local Clip = nil

function noclip()
	Clip = false
	local function Nocl()
		if Clip == false and game.Players.LocalPlayer.Character ~= nil then
			for _,v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
				if v:IsA('BasePart') and v.CanCollide and v.Name ~= floatName then
					v.CanCollide = false
				end
			end
		end
		wait(0.21)
	end
	Noclip = game:GetService('RunService').Stepped:Connect(Nocl)
end

function clip()
	if Noclip then Noclip:Disconnect() end
	Clip = true
end

noclip()

wait(1)



local LocalPlayer = game:GetService("Players").LocalPlayer
local Character = LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait()
local Humanoid = nil

while not Humanoid do
    for i, v in pairs(Character:GetChildren()) do
        if v:IsA("Humanoid") then
            Humanoid = v
        end
    end
    task.wait()
end

local FakeHumanoid = Humanoid:Clone()

local ToSpoof = {
    WalkSpeed = FakeHumanoid.WalkSpeed,
    JumpPower = FakeHumanoid.JumpPower
}

local index, newindex, namecall; index = hookmetamethod(game, "__index", function(...)
    if not checkcaller() then
        local self, index = ...
        if self and index then
            if rawequal(self, Humanoid) and rawget(ToSpoof, index) then
                return rawget(ToSpoof, index)
            end
        end
    end
    
    return index(...)
end); newindex = hookmetamethod(game, "__newindex", function(...)
    if not checkcaller() then
        local self, index, value = ...
        if self and index then
            if rawequal(self, Humanoid) and rawget(ToSpoof, index) then
                rawset(ToSpoof, index, value)
                return
            end
        end
    end
    
    return newindex(...)
end); namecall = hookmetamethod(game, "__namecall", function(...)
    if not checkcaller() then
        local self, args, method = ..., {...}, getnamecallmethod(); table.remove(args, 1)
        if self and method then
            if rawequal(self, Humanoid) then
                if rawequal(method, "Clone") then
                    return namecall(FakeHumanoid, ...)
                elseif rawequal(method, "GetPropertyChangedSignal") and rawget(ToSpoof, rawget(args, 1)) then
                    rawset(args, 1, "ClassName")
                end
            end
        end
    end
    
    return namecall(...)
end)

for i, v in pairs(getconnections(Humanoid.Changed)) do
    if v and v.Function then
        local vFunc; vFunc = hookfunc(v.Function, function(...)
            if not checkcaller() then
                local args = {...}
                if rawget(ToSpoof, rawget(args, 1)) then
                    rawset(args, 1, "ClassName")
                end
            end
            
            return vFunc(...)
        end)
    end
end

Humanoid.WalkSpeed = 100



local char = game.Players.LocalPlayer.Character

local cPos = char.HumanoidRootPart.Position
local fPos = cPos.Z + 2

local part = Instance.new("Part")
part.Name = "floorairport"
part.CanCollide = true
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(453.09,149,2154.16)
local localplayer = game.Players.LocalPlayer
local Char = localplayer.Character or workspace:FindFirstChild(localplayer.Name)
        local HRP = Char and Char:FindFirstChild("HumanoidRootPart")
        if not Char or not HRP then
           
        end
        local p = HRP.Position
        local hrd = game.Players.LocalPlayer.Character.HumanoidRootPart
        local x = 453.09
        local y = 150
        local z = 2154.16
        hrd.CFrame = CFrame.new(p.x, 1000, p.z)
        wait(0.5)
        local currentPos = Vector3.new(p.x, 1000, p.z)
        local targetPos = Vector3.new(x, 1000, z)

        local direction = (targetPos - currentPos).Unit
        local distance = (targetPos - currentPos).Magnitude
        local steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end

        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(0.1)
        local p = hrd.Position
        
        local currentPos = Vector3.new(x, 1000, z)
        local targetPos = Vector3.new(x, y, z)

        local direction = (targetPos - currentPos).Unit
        local distance = (targetPos - currentPos).Magnitude
        local steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10 
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end
        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait()
task.wait(5)
char.Humanoid:MoveTo(Vector3.new(459.79,70.35,1951.06))
task.wait(2)
task.wait(2)
char.Humanoid:MoveTo(Vector3.new(504.57,116.71,2224.6))
task.wait(2)
char.Humanoid:MoveTo(Vector3.new(529.27,116.71,2209))
task.wait(2)
Humanoid.WalkSpeed = 50
task.wait(1)
local VirtualInputManager = game:GetService('VirtualInputManager')

function keyPress(Key, Press)
    VirtualInputManager:SendKeyEvent(Press, Key, false, game)
end
for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end

keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(585.71,116.71,2183.99))
task.wait(2)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(572.86,116.71,2218.96))
task.wait(2)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(585.71,116.71,2183.99))
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(644.81,116.71,2154.44))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(697.58,116.71,2125.14))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(730.99,116.71,2129.23))
task.wait(2)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(759.64,116.71,2097.57))
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(835.06,117.85,2143.87))
task.wait(2)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(889.58,116.86,2117.4))
task.wait(2)
char.Humanoid:MoveTo(Vector3.new(894.75,116.86,2125.81))
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(889.58,116.86,2117.4))
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(835.06,117.85,2143.87))
task.wait(3)
char.Humanoid:MoveTo(Vector3.new(825.1,116.71,2185.17))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
char.Humanoid:MoveTo(Vector3.new(787.3,120,2180.45))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(769.65,116.71,2142.94))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(712.63,116.71,2174.62))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(762.71,116.71,2197.96))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(702.09,116.71,2241.5))
task.wait(4)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(658.85,117.92,2231.65))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(603.53,118.61,2262.08))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(561.63,116.71,2252.22))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(505.16,116.71,2280.75))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(472.12,118.61,2330.08))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(401.33,116.96,2322.05))
task.wait(3)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
char.Humanoid:MoveTo(Vector3.new(396.89,116.96,2333.97))
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(400.79,116.96,2339.22))
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(484.95,116.71,2294.78))
task.wait(4)
Humanoid.WalkSpeed = 100
task.wait(0.5)
char.Humanoid:MoveTo(Vector3.new(505.11,116.93,2157.95))
task.wait(4)
char.Humanoid:MoveTo(Vector3.new(486.88,116.85,2127.81))
task.wait(0.7)
local part = Instance.new("Part")
part.Name = "floorhouse"
part.CanCollide = true
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1525.27,39,1303.45)
local localplayer = game.Players.LocalPlayer
local Char = localplayer.Character or workspace:FindFirstChild(localplayer.Name)
        local HRP = Char and Char:FindFirstChild("HumanoidRootPart")
        if not Char or not HRP then
           
        end
        local p = HRP.Position
        local hrd = game.Players.LocalPlayer.Character.HumanoidRootPart
        local x = 1525.27
        local y = 40
        local z = 1303.45
        hrd.CFrame = CFrame.new(p.x, 1000, p.z)
        wait(0.5)
        local currentPos = Vector3.new(p.x, 1000, p.z)
        local targetPos = Vector3.new(x, 1000, z)

        local direction = (targetPos - currentPos).Unit
        local distance = (targetPos - currentPos).Magnitude
        local steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end

        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(0.1)
        local p = hrd.Position
        
        local currentPos = Vector3.new(x, 1000, z)
        local targetPos = Vector3.new(x, y, z)

        local direction = (targetPos - currentPos).Unit
        local distance = (targetPos - currentPos).Magnitude
        local steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10 
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end
        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait()
task.wait(4)
for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
task.wait(1)
Humanoid.WalkSpeed = 100
task.wait(0.5)
char.Humanoid:MoveTo(Vector3.new(1492.2,25.26,1317.02))
task.wait(1.5)
char.Humanoid:MoveTo(Vector3.new(1284.28,25.26,808.9))
task.wait(6)
char.Humanoid:MoveTo(Vector3.new(1342.52,25.66,783.29))
task.wait(0.5)
local part = Instance.new("Part")
part.Name = "applerob1"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1372.87,28.13,789.92)
local part = Instance.new("Part")
part.Name = "applerob2"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1390.32,28.14,783.92)
local part = Instance.new("Part")
part.Name = "applerob3"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1411.06,28.18,789.87)
local part = Instance.new("Part")
part.Name = "applerob4"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1387.54,28.06,730.9)
local part = Instance.new("Part")
part.Name = "applerob5"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1376.13,28.13,749.11)
local part = Instance.new("Part")
part.Name = "applerob6"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1355.51,28.16,746.17)
for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
task.wait(5)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "applerob1" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "applerob2" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "applerob3" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "applerob4" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "applerob5" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "applerob6" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(game.Workspace:GetChildren()) do 
   if v.Name == "MovingLasers" then
       for a,b in pairs(v:GetChildren()) do
           b:Destroy()
       end
   end
end
task.wait(1)
Humanoid.WalkSpeed = 50
char.Humanoid:MoveTo(Vector3.new(1333.02,25.55,728.99))
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(1392.31,53.15,703.89))
task.wait(1)
local part = Instance.new("Part")
part.Name = "applerob7"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1391.23,56.09,728.38)
local part = Instance.new("Part")
part.Name = "applerob8"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1381.86,56.05,748.22)
local part = Instance.new("Part")
part.Name = "applerob9"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1395.13,56.05,781.88)
local part = Instance.new("Part")
part.Name = "applerob10"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1415.12,56.17,787.52)
local part = Instance.new("Part")
part.Name = "applerobespcape"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1362.36,58,777.89)
for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
task.wait(0.5)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "applerob7" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "applerob8" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "applerob9" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "applerob10" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "applerobespcape" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
local localplayer = game.Players.LocalPlayer
local Char = localplayer.Character or workspace:FindFirstChild(localplayer.Name)
        local HRP = Char and Char:FindFirstChild("HumanoidRootPart")
        if not Char or not HRP then
           
        end
        local p = HRP.Position
        local hrd = game.Players.LocalPlayer.Character.HumanoidRootPart
        local x = 892.77
        local y = 30
        local z = 919.46
        hrd.CFrame = CFrame.new(p.x, 30, p.z)
        wait(0.5)
        local currentPos = Vector3.new(p.x, 30, p.z)
        local targetPos = Vector3.new(x, 30, z)

        local direction = (targetPos - currentPos).Unit
        local distance = (targetPos - currentPos).Magnitude
        local steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end

        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(0.1)
        local p = hrd.Position
        
        local currentPos = Vector3.new(x, 30, z)
        local targetPos = Vector3.new(x, y, z)

        local direction = (targetPos - currentPos).Unit
        local distance = (targetPos - currentPos).Magnitude
        local steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10 
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end
        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait()
        task.wait(1)
local part = Instance.new("Part")
part.Name = "pizzarob1"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(877.17,25.75,938.34)
local part = Instance.new("Part")
part.Name = "pizzarob2"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(892.69,29.84,982.22)
local part = Instance.new("Part")
part.Name = "pizzarob3"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(899.04,30.46,979.38)
local part = Instance.new("Part")
part.Name = "pizzarob4"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(909.87,29.8,975.44)
local part = Instance.new("Part")
part.Name = "pizzarob5"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(873.48,28.85,990.63)
local part = Instance.new("Part")
part.Name = "pizzarob6"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(889.72,25.75,1027.99)
local part = Instance.new("Part")
part.Name = "pizzarob7"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(916.82,25.75,1011.32)
for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
task.wait(0.5)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "pizzarob1" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(0.5)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "pizzarob2" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "pizzarob3" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "pizzarob4" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "pizzarob5" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(0.5)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "pizzarob6" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(0.5)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "pizzarob7" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(1)
task.wait(1)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "pizzarob6" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(0.5)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "pizzarob5" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(0.5)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "pizzarob2" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(0.5)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "pizzarob1" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(0.5)
char.Humanoid:MoveTo(Vector3.new(967.32,25.26,817.93))
task.wait(3)
local localplayer = game.Players.LocalPlayer
local Char = localplayer.Character or workspace:FindFirstChild(localplayer.Name)
        local HRP = Char and Char:FindFirstChild("HumanoidRootPart")
        if not Char or not HRP then
           
        end
        local p = HRP.Position
        local hrd = game.Players.LocalPlayer.Character.HumanoidRootPart
        local x = 786.44
        local y = 25.25
        local z = 703.95
        hrd.CFrame = CFrame.new(p.x, 30, p.z)
        wait(0.5)
        local currentPos = Vector3.new(p.x, 30, p.z)
        local targetPos = Vector3.new(x, 30, z)

        local direction = (targetPos - currentPos).Unit
        local distance = (targetPos - currentPos).Magnitude
        local steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end

        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(0.1)
        local p = hrd.Position
        
        local currentPos = Vector3.new(x, 30, z)
        local targetPos = Vector3.new(x, y, z)

        local direction = (targetPos - currentPos).Unit
        local distance = (targetPos - currentPos).Magnitude
        local steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10 
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end
        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait()
task.wait(1)
local localplayer = game.Players.LocalPlayer
local Char = localplayer.Character or workspace:FindFirstChild(localplayer.Name)
        local HRP = Char and Char:FindFirstChild("HumanoidRootPart")
        if not Char or not HRP then
           
        end
        local p = HRP.Position
        local hrd = game.Players.LocalPlayer.Character.HumanoidRootPart
        local x = 303.49
        local y = 25.25
        local z = 896.6
        hrd.CFrame = CFrame.new(p.x, 30, p.z)
        wait(0.5)
        local currentPos = Vector3.new(p.x, 30, p.z)
        local targetPos = Vector3.new(x, 30, z)

        local direction = (targetPos - currentPos).Unit
        local distance = (targetPos - currentPos).Magnitude
        local steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end

        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(0.1)
        local p = hrd.Position
        
        local currentPos = Vector3.new(x, 30, z)
        local targetPos = Vector3.new(x, y, z)

        local direction = (targetPos - currentPos).Unit
        local distance = (targetPos - currentPos).Magnitude
        local steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10 
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end
        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait()
        task.wait(1)
        local localplayer = game.Players.LocalPlayer
local Char = localplayer.Character or workspace:FindFirstChild(localplayer.Name)
        local HRP = Char and Char:FindFirstChild("HumanoidRootPart")
        if not Char or not HRP then
           
        end
        local p = HRP.Position
        local hrd = game.Players.LocalPlayer.Character.HumanoidRootPart
        local x = 345.83
        local y = 25.45
        local z = 992.67
        hrd.CFrame = CFrame.new(p.x, 30, p.z)
        wait(0.5)
        local currentPos = Vector3.new(p.x, 30, p.z)
        local targetPos = Vector3.new(x, 30, z)

        local direction = (targetPos - currentPos).Unit
        local distance = (targetPos - currentPos).Magnitude
        local steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end

        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(0.1)
        local p = hrd.Position
        
        local currentPos = Vector3.new(x, 30, z)
        local targetPos = Vector3.new(x, y, z)

        local direction = (targetPos - currentPos).Unit
        local distance = (targetPos - currentPos).Magnitude
        local steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10 
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end
        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait()
        task.wait(1)
        local part = Instance.new("Part")
part.Name = "smallshop1"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(357.78,25.55,1014.7)
local part = Instance.new("Part")
part.Name = "smallshop2"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(354.11,25.55,1025.12)
local part = Instance.new("Part")
part.Name = "smallshop3"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(366.43,28.35,1035.28)
local part = Instance.new("Part")
part.Name = "smallshop4"
part.CanCollide = false
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(378.41,28.35,1020.74)
for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "smallshop1" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(0.5)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "smallshop2" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(0.5)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "smallshop3" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(0.5)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
for i,v in pairs(workspace:GetChildren())do
if v:IsA("Part") and v.Name == "smallshop4" then
game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
end
end
task.wait(0.5)
keyPress(Enum.KeyCode.E, true)
task.wait(1)
char.Humanoid:MoveTo(Vector3.new(341.03,25.25,967.06))
task.wait(1)
game:GetService("Players").LocalPlayer.Character.Humanoid.Health = 0
