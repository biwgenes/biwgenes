--_G.Farm = true --Execute with this set to true if you want it enabled, set to _G.Farm = false if you want to disable it
--_G.AutoRebirth = true --Set to false if you dont want it to auto rebirth you, no leaderboard if you do this doe :(
--_G.IJustWannaCashFarm = false --Leave this at false if you want to farm with rebirths and shit, set it to false if you just want it to farm cash and not teleport you for map progress
local prim = 15487337112427
local sec = 13824
local function CheckStage()
    if game:GetService("Workspace").Zones["Parking Lot"]:FindFirstChild("Wall") then
        prim = 15487337112427
        sec = 13824
        return 1
    elseif game:GetService("Workspace").Zones.Garden:FindFirstChild("Wall") then
        prim = 42517256736755
        sec = 24576
        return 2
    elseif game:GetService("Workspace").Zones.Mansion:FindFirstChild("Wall") then
        prim = 69145846366882
        sec = 36864
        return 3
    elseif game:GetService("Workspace").Zones.School:FindFirstChild("Wall") then
        prim = 4657626152038.6
        sec = 12288
        return 4
    elseif game:GetService("Workspace").Zones.Airport:FindFirstChild("Wall") then
        return 5
    elseif game:GetService("Workspace").Zones.Laboratory:FindFirstChild("Wall") then
        prim = 55906653404236
        sec = 33792
        return 6
    elseif game:GetService("Workspace").Zones.Arctic:FindFirstChild("Wall") then
        prim = 62824797630310
        sec = 24576
        return 7
    elseif game:GetService("Workspace").Zones.Castle:FindFirstChild("Wall") then
        prim = 8836483955383.3
        sec = 49152
        return 8
    elseif game:GetService("Workspace").Zones.Mars:FindFirstChild("Wall") then
        prim = 42427039146423
        sec = 73728
        return 9
    elseif game:GetService("Workspace").Zones.Cleandromeda:FindFirstChild("Wall") then
        prim = 41562891006470
        sec = 147456
        return 10
    elseif game:GetService("Workspace").Zones.Bank:FindFirstChild("Wall") then
        prim = 67081284523010
        sec = 27648
        return 11
    elseif game:GetService("Workspace").Zones["Jewelry Store"]:FindFirstChild("Wall") then
        if _G.AutoRebirth then
            game:GetService("ReplicatedStorage").Remotes.RebirthSignal:FireServer()
            wait(3)
        end
        return 12
    end
end

--//TPing
spawn(function()
    if _G.IJustWannaCashFarm == false then
        while wait(5) do
            if _G.Farm then
                if CheckStage() == 1 then
                    game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Vector3.new(16, 35, 159)))
                elseif CheckStage() == 2 then
                    game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Vector3.new(-154, 34, 152)))
                elseif CheckStage() == 3 then
                    game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Vector3.new(-306, 35, 153)))
                elseif CheckStage() == 4 then
                    game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Vector3.new(-471, 34, 156)))
                elseif CheckStage() == 5 then
                    game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Vector3.new(-622, 33, 159)))
                elseif CheckStage() == 6 then
                    game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Vector3.new(-775, 34, 160)))
                elseif CheckStage() == 7 then
                    game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Vector3.new(-933, 37, 157)))
                elseif CheckStage() == 8 then
                    game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Vector3.new(-1107, 36, 168)))
                elseif CheckStage() == 9 then
                    game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Vector3.new(-1294, 33, 157)))
                elseif CheckStage() == 10 then
                    game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Vector3.new(-1468, 34, 151)))
                elseif CheckStage() == 11 then
                    game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Vector3.new(-1696, 34, 171)))
                elseif CheckStage() == 12 then
                    game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(Vector3.new(-1823.22, 35.61, 171.38)))
                end
            end
        end
    end
end)

spawn(function()
    while _G.Farm and wait(1) do
        CheckStage()
    end
end)

spawn(function()
    if _G.Farm then
        game:GetService("StarterGui"):SetCore("SendNotification", {Title = "Starting", Text = "Starting up the farm. Beware that this may get you banned due to you not gaining any 'dirt'."})
    end
end)

spawn(function()
    while _G.Farm and wait() do
        local args = {[1] = prim,[2] = sec}
        game:GetService("ReplicatedStorage").Remotes.SurfaceCompleted:FireServer(unpack(args))
    end
end)

--[[-- Script generated by SimpleSpy - credits to exx#9394

local args = {
    [1] = 67081284523010,
    [2] = 27648
}

game:GetService("ReplicatedStorage").Remotes.SurfaceCompleted:FireServer(unpack(args))
]]
