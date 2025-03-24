local player = game.Players.LocalPlayer

local function setSpeed()
    local character = player.Character or player.CharacterAdded:Wait()
    local humanoid = character:FindFirstChildOfClass("Humanoid")

    if humanoid then
        humanoid.WalkSpeed = 100
    end
end

-- 캐릭터가 로드될 때 실행
player.CharacterAdded:Connect(setSpeed)

-- 이미 캐릭터가 존재하면 즉시 적용
if player.Character then
    setSpeed()
end
