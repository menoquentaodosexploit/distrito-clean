local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local camera = workspace.CurrentCamera
local maxFOV = 120
local function lockFOV()
    if camera then
        camera.FieldOfView = maxFOV
    end
end
RunService.RenderStepped:Connect(function()
    lockFOV()
end)
workspace:GetPropertyChangedSignal("CurrentCamera"):Connect(function()
    camera = workspace.CurrentCamera
end)
