local FOV_Radius = 25

local FOV_Visible = true

local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")
local Camera = game:GetService("Workspace").CurrentCamera


local FOV_CIRCLE = Drawing.new("Circle")
FOV_CIRCLE.Filled = false
FOV_CIRCLE.Color = Color3.fromRGB(0, 0, 0)
FOV_CIRCLE.Radius = FOV_Radius
FOV_CIRCLE.Thickness = 1
FOV_CIRCLE.Visible = FOV_Visible
FOV_CIRCLE.Transparency = .35
FOV_CIRCLE.Position = Vector2.new(Camera.ViewportSize.X / 2, Camera.ViewportSize.Y / 2)


local Move_Circle = nil
Move_Circle = RunService.RenderStepped:Connect(function()
	FOV_CIRCLE.Position = Vector2.new(UserInputService:GetMouseLocation().X, UserInputService:GetMouseLocation().Y)
end)
