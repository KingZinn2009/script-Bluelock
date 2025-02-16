local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

local ball = game.Workspace:FindFirstChild("Ball")

local function autoBlock()
    if ball then
        local direction = (ball.Position - humanoidRootPart.Position).unit
        humanoidRootPart.Velocity = direction * 75
    end
end

game:GetService("RunService").Heartbeat:Connect(autoBlock)
