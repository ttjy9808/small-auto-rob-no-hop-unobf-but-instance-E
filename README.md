local part = Instance.new("Part")
part.Name = "floorairport"
part.CanCollide = true
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(459.59,120,2148.27)
 localplayer = game.Players.LocalPlayer 
 Char = localplayer.Character or workspace:FindFirstChild(localplayer.Name)
         HRP = Char and Char:FindFirstChild("HumanoidRootPart")
        if not Char or not HRP then
           
        end
         p = HRP.Position
         hrd = game.Players.LocalPlayer.Character.HumanoidRootPart
         x = 459.59
         y = 117
         z = 2148.27
        hrd.CFrame = CFrame.new(p.x, 1000, p.z)
        wait(0.5)
         currentPos = Vector3.new(p.x, 1000, p.z)
         targetPos = Vector3.new(x, 1000, z)

         direction = (targetPos - currentPos).Unit
         distance = (targetPos - currentPos).Magnitude
         steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end

        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(0.1)
         p = hrd.Position
        
         currentPos = Vector3.new(x, 1000, z)
         targetPos = Vector3.new(x, y, z)

         direction = (targetPos - currentPos).Unit
         distance = (targetPos - currentPos).Magnitude
         steps = math.floor(distance / 10) 
        for i = 1, steps do
            currentPos = currentPos + direction * 10 
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end
        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(2)
        for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
        end
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(475.05,116.95,2178.77)
        task.wait(0.8)
        for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
        end
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(499.12,116.8,2224.67)
        task.wait(0.7)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(530.52,116.8,2208.43)
        task.wait(0.5)
        local VirtualInputManager = game:GetService('VirtualInputManager')
        function keyPress(Key, Press)
    	VirtualInputManager:SendKeyEvent(Press, Key, false, game)
		end
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(576.16,121,2216.91)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(581.94,116.8,2181.25)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(642.7,116.8,2150.28)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(695.12,116.8,2124.24)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(728.29,120.13,2137.24)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(752.8,123.39,2121.25)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(788.9,119.5,2123.47)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(839.35,118.74,2136.79)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(889.88,116.8,2131.32)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(839.35,118.74,2136.79)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(831.07,121.63,2188.47)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(831.07,130,2188.47)
        task.wait(0.1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(791.82,123,2186.52)
        task.wait(0.8)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(771.01,116.8,2140.67)
        task.wait(0.8)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(768.3,123.42,2194.2)
        task.wait(0.8)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(711.12,116.8,2171.26)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(715.14,116.8,2220.54)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(702.17,121.84,2239.78)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(702.17,130,2239.78)
        task.wait(0.1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(663.09,121.64,2247.6)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(663.09,130,2247.6)
        task.wait(0.1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(642.55,121.43,2258.89)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(618.94,130,2256.23)
        task.wait(0.1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(557.95,121.08,2248.04)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(530.43,130,2265.46)
        task.wait(0.1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(501.37,116.8,2278.43)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(470.95,116.8,2315.45)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(414.78,116.81,2330.07)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(401.78,117.05,2322.12)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(401.78,117.05,2322.12)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(395.82,117.01,2333.38)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(398.32,117.05,2342.2)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(410.63,119.5,2336.77)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(483.21,116.8,2299.63)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(488.25,116.99,2243.2)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(497.67,117.44,2207.6)
        task.wait(0.8)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(478.1,117.02,2171.61)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(463.66,116.95,2146.68)
        task.wait(1)
        local part = Instance.new("Part")
part.Name = "floorairport"
part.CanCollide = true
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(-1769.01,50,1101.82)
 localplayer = game.Players.LocalPlayer 
 Char = localplayer.Character or workspace:FindFirstChild(localplayer.Name)
         HRP = Char and Char:FindFirstChild("HumanoidRootPart")
        if not Char or not HRP then
           
        end
         p = HRP.Position
         hrd = game.Players.LocalPlayer.Character.HumanoidRootPart
         x = -1769.01
         y = 40
         z = 1101.82
        hrd.CFrame = CFrame.new(p.x, 1000, p.z)
        wait(0.5)
         currentPos = Vector3.new(p.x, 1000, p.z)
         targetPos = Vector3.new(x, 1000, z)

         direction = (targetPos - currentPos).Unit
         distance = (targetPos - currentPos).Magnitude
         steps = math.floor(distance / 5) 
        for i = 1, steps do
            currentPos = currentPos + direction * 5
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end

        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(0.1)
         p = hrd.Position
        
         currentPos = Vector3.new(x, 1000, z)
         targetPos = Vector3.new(x, y, z)

         direction = (targetPos - currentPos).Unit
         distance = (targetPos - currentPos).Magnitude
         steps = math.floor(distance / 5) 
        for i = 1, steps do
            currentPos = currentPos + direction * 5 
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end
        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(1)
        for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1799.96,39.79,1146.57)
		task.wait(0.8)
		for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
        end
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1845.45,39.87,1133.11)
		task.wait(0.5)
		for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
        end
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1845.45,46,1133.11)
        task.wait(0.1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1857.17,45.34,1134.18)
		task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1844.86,45.34,1144.92)
		task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1812.46,41.62,1142.52)
        task.wait(0.8)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1791.73,42.63,1150.34)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1787.37,42.63,1154)
        task.wait(1)
        local part = Instance.new("Part")
part.Name = "floorairport"
part.CanCollide = true
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(-1590.6,46,1186.84)
 localplayer = game.Players.LocalPlayer 
 Char = localplayer.Character or workspace:FindFirstChild(localplayer.Name)
         HRP = Char and Char:FindFirstChild("HumanoidRootPart")
        if not Char or not HRP then
           
        end
         p = HRP.Position
         hrd = game.Players.LocalPlayer.Character.HumanoidRootPart
         x = -1590.6
         y = 33
         z = 1186.84
        hrd.CFrame = CFrame.new(p.x, 1000, p.z)
        wait(0.5)
         currentPos = Vector3.new(p.x, 1000, p.z)
         targetPos = Vector3.new(x, 1000, z)

         direction = (targetPos - currentPos).Unit
         distance = (targetPos - currentPos).Magnitude
         steps = math.floor(distance / 5) 
        for i = 1, steps do
            currentPos = currentPos + direction * 5
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end

        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(0.1)
         p = hrd.Position
        
         currentPos = Vector3.new(x, 1000, z)
         targetPos = Vector3.new(x, y, z)

         direction = (targetPos - currentPos).Unit
         distance = (targetPos - currentPos).Magnitude
         steps = math.floor(distance / 5) 
        for i = 1, steps do
            currentPos = currentPos + direction * 5 
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end
        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(1)
        for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1546.69,32.65,1187.53)
        task.wait(0.8)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1544.1,33.45,1200.57)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1522.57,39.88,1194.56)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1520.35,39.88,1207.52)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1517.31,39.88,1221.07)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1549.33,34,1185.28)
        task.wait(0.8)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1597.24,32.65,1190.3)
        task.wait(1)
        local part = Instance.new("Part")
part.Name = "floorairport"
part.CanCollide = true
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(897.41,35,901.93)
 localplayer = game.Players.LocalPlayer 
 Char = localplayer.Character or workspace:FindFirstChild(localplayer.Name)
         HRP = Char and Char:FindFirstChild("HumanoidRootPart")
        if not Char or not HRP then
           
        end
         p = HRP.Position
         hrd = game.Players.LocalPlayer.Character.HumanoidRootPart
         x = 897.41
         y = 25.34
         z = 901.93
        hrd.CFrame = CFrame.new(p.x, 1000, p.z)
        wait(0.5)
         currentPos = Vector3.new(p.x, 1000, p.z)
         targetPos = Vector3.new(x, 1000, z)

         direction = (targetPos - currentPos).Unit
         distance = (targetPos - currentPos).Magnitude
         steps = math.floor(distance / 5) 
        for i = 1, steps do
            currentPos = currentPos + direction * 5
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end

        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(0.1)
         p = hrd.Position
        
         currentPos = Vector3.new(x, 1000, z)
         targetPos = Vector3.new(x, y, z)

         direction = (targetPos - currentPos).Unit
         distance = (targetPos - currentPos).Magnitude
         steps = math.floor(distance / 5) 
        for i = 1, steps do
            currentPos = currentPos + direction * 5 
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end
        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(1)
        for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(878.68,25.84,939.8)
        for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
        task.wait(0.8)
        for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(893.21,30.27,982.31)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(899.6,31.62,979.28)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(911.15,31.62,973.74)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(874.88,28.94,989.07)
        task.wait(0.8)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(891,25.84,1029.43)
        task.wait(0.8)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(916.3,25.84,1012.72)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(891,25.84,1029.43)
        task.wait(0.8)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(874.88,28.94,989.07)
        task.wait(0.8)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(879.56,28.94,967.52)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(883.01,25.84,935.42)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(896.67,25.84,908.69)
        task.wait(1)
        local part = Instance.new("Part")
part.Name = "floorairport"
part.CanCollide = true
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(1330.33,35,788.48)
 localplayer = game.Players.LocalPlayer 
 Char = localplayer.Character or workspace:FindFirstChild(localplayer.Name)
         HRP = Char and Char:FindFirstChild("HumanoidRootPart")
        if not Char or not HRP then
           
        end
         p = HRP.Position
         hrd = game.Players.LocalPlayer.Character.HumanoidRootPart
         x = 1330.33
         y = 25.75
         z = 788.48
        hrd.CFrame = CFrame.new(p.x, 1000, p.z)
        wait(0.5)
         currentPos = Vector3.new(p.x, 1000, p.z)
         targetPos = Vector3.new(x, 1000, z)

         direction = (targetPos - currentPos).Unit
         distance = (targetPos - currentPos).Magnitude
         steps = math.floor(distance / 5) 
        for i = 1, steps do
            currentPos = currentPos + direction * 5
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end

        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(0.1)
         p = hrd.Position
        
         currentPos = Vector3.new(x, 1000, z)
         targetPos = Vector3.new(x, y, z)

         direction = (targetPos - currentPos).Unit
         distance = (targetPos - currentPos).Magnitude
         steps = math.floor(distance / 5) 
        for i = 1, steps do
            currentPos = currentPos + direction * 5 
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end
        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(1)
        for i,v in next, getgc(true) do
                if type(v) == "table" and rawget(v, "ID") and rawget(v, "Seconds") then
                    if typeof(v.Seconds) == "number" then
                        rawset(v, "Seconds", 0.001) -- setting it to 0 will not work because the game checks that.
                    end
                end
            end
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1373.64,28.21,790.43)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1390.54,28.26,783.48)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1410.95,28.25,789.09)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1400.37,30,760.46)
        task.wait(0.1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1387.96,28.15,730.32)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1376.56,28.21,748.88)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1354.65,28.26,745.59)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1354.65,70,745.59)
        task.wait(0.1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1380.13,56.24,746.82)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1391.76,56.24,727.66)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1404.81,56,758.9)
        task.wait(0.1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1415.84,56.24,787.82)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1357.99,60,778.1)
        task.wait(1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1319.61,25.35,793.29)
        task.wait(1)
        local part = Instance.new("Part")
part.Name = "floorairport"
part.CanCollide = true
part.Anchored = true
part.Color = Color3.new(1, 1, 1)
part.Parent = workspace 
part.Position = Vector3.new(335.66,35,966.4)
 localplayer = game.Players.LocalPlayer 
 Char = localplayer.Character or workspace:FindFirstChild(localplayer.Name)
         HRP = Char and Char:FindFirstChild("HumanoidRootPart")
        if not Char or not HRP then
           
        end
         p = HRP.Position
         hrd = game.Players.LocalPlayer.Character.HumanoidRootPart
         x = 335.66
         y = 25.34
         z = 966.4
        hrd.CFrame = CFrame.new(p.x, 1000, p.z)
        wait(0.5)
         currentPos = Vector3.new(p.x, 1000, p.z)
         targetPos = Vector3.new(x, 1000, z)

         direction = (targetPos - currentPos).Unit
         distance = (targetPos - currentPos).Magnitude
         steps = math.floor(distance / 5) 
        for i = 1, steps do
            currentPos = currentPos + direction * 5
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end

        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(0.1)
         p = hrd.Position
        
         currentPos = Vector3.new(x, 1000, z)
         targetPos = Vector3.new(x, y, z)

         direction = (targetPos - currentPos).Unit
         distance = (targetPos - currentPos).Magnitude
         steps = math.floor(distance / 5) 
        for i = 1, steps do
            currentPos = currentPos + direction * 5 
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
            task.wait()
        end
        
        currentPos = targetPos
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(currentPos)
        task.wait(1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(350,25.65,1002.53)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(361.47,30.61,1012.02)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(355.06,30.18,1026.67)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(371.28,30.61,1033.4)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(377.12,30.61,1017.49)
        task.wait(0.5)
        keyPress(Enum.KeyCode.E, true)
        task.wait(0.5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(346.83,27,976.68)
        task.wait(0.1)
local player = game.Players.LocalPlayer

-- Create a ScreenGui
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "ExampleScreenGui"
screenGui.Parent = player.PlayerGui

-- Create a Frame
local frame = Instance.new("Frame")
frame.Name = "ExampleFrame"
frame.Size = UDim2.new(0.5, 0, 0.5, 0) -- Adjust the size as needed
frame.Position = UDim2.new(0.25, 0, 0.25, 0) -- Adjust the position as needed
frame.BackgroundColor3 = Color3.new(0.5, 0.5, 0.5) -- Adjust the color as needed
frame.BackgroundTransparency = 1 -- Adjust the transparency as needed
frame.Parent = screenGui

-- Create a TextLabel
local textLabel = Instance.new("TextLabel")
textLabel.Name = "ExampleTextLabel"
textLabel.Size = UDim2.new(1, 0, 1, 0)
textLabel.BackgroundTransparency = 1
textLabel.Text = "FINISH! RUN FROM THE POLICEEE"
textLabel.TextSize = 50
textLabel.TextColor3 = Color3.new(0, 1, 0) -- Set text color to green
textLabel.Parent = frame

-- Destroy the TextLabel after 5 seconds
wait(5)
textLabel:Destroy()
frame:Destroy()
screenGui:Destroy()


        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
