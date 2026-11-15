local Players = game:GetService("Players")
local UIS = game:GetService("UserInputService")

local gui = Instance.new("ScreenGui", Players.LocalPlayer.PlayerGui)
gui.Name = "Trade Scam"

local frame = Instance.new("Frame",gui)
frame.Size = UDim2.fromOffset(220,180)
frame.Position = UDim2.new(.5,-110,.5,-90)
frame.BackgroundColor3 = Color3.fromRGB(25,25,35)
frame.Active = true
Instance.new("UICorner",frame).CornerRadius = UDim.new(0,12)

local title = Instance.new("TextLabel",frame)
title.Size = UDim2.new(1,0,0,40)
title.Text = "Trade Scam"
title.TextColor3 = Color3.new(1,1,1)
title.BackgroundTransparency = 1
title.TextSize = 17

local dragging,start,pos = false,nil,nil

title.InputBegan:Connect(function(i)
    if i.UserInputType == Enum.UserInputType.MouseButton1 or i.UserInputType == Enum.UserInputType.Touch then
        dragging,start,pos = true,i.Position,frame.Position
    end
end)

UIS.InputChanged:Connect(function(i)
    if dragging and (i.UserInputType == Enum.UserInputType.MouseMovement or i.UserInputType == Enum.UserInputType.Touch) then
        local d = i.Position-start
        frame.Position = UDim2.new(pos.X.Scale,pos.X.Offset+d.X,pos.Y.Scale,pos.Y.Offset+d.Y)
    end
end)

UIS.InputEnded:Connect(function(i)
    if i.UserInputType == Enum.UserInputType.MouseButton1 or i.UserInputType == Enum.UserInputType.Touch then
        dragging = false
    end
end)

local function button(name,y,callback)
    local b = Instance.new("TextButton",frame)
    b.Size = UDim2.new(.8,0,0,32)
    b.Position = UDim2.new(.1,0,0,y)
    b.Text = name
    b.TextSize = 13
    b.BackgroundColor3 = Color3.fromRGB(90,65,180)
    b.TextColor3 = Color3.new(1,1,1)
    Instance.new("UICorner",b).CornerRadius = UDim.new(0,8)
    b.MouseButton1Click:Connect(callback)
end

button("Trade Freeze",48,function() print("Simulator ON") end)
button("Auto Add Item",88,function() print("Item added!") end)
button("Auto Accept",128,function() print("Trade accepted!") end)
