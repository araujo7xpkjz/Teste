repeat
    wait()
until game.IsLoaded and (game.Players.LocalPlayer or game.Players.PlayerAdded:Wait()) and
    (game.Players.LocalPlayer.Character or game.Players.LocalPlayer.CharacterAdded:Wait())

-- Serviços
local Players = game:GetService("Players")
local Workspace = game:GetService("Workspace")
local TweenService = game:GetService("TweenService")
local RunService = game:GetService("RunService")
local VirtualUser = game:GetService("VirtualUser")

local l = true
game.Players.LocalPlayer.Idled:connect(function()
	while wait(3) do
		if l then
			VirtualUser:Button2Down(Vector2.new(0,0), workspace.CurrentCamera.CFrame)
			wait(1)
			VirtualUser:Button2Up(Vector2.new(0,0), workspace.CurrentCamera.CFrame)
		end
	end
end)

-- Interface Principal
local a = Instance.new("ScreenGui")
local b = Instance.new("Frame")
local c = Instance.new("UICorner")
local d = Instance.new("Frame")
local e = Instance.new("ImageButton")
local f = Instance.new("ImageLabel")
local g = Instance.new("ImageLabel")
local h = Instance.new("TextButton")
local i = Instance.new("TextButton")
local j = Instance.new("TextLabel")
local k = Instance.new("TextLabel")
local fruitStatus = Instance.new("TextLabel") -- Novo: Exibir nome da fruta
local l = Instance.new("ScreenGui")
local m = Instance.new("ImageButton")

l.Parent = game.CoreGui
l.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
_G.Primary = Color3.fromRGB(43, 43, 43)
m.Parent = l
m.Position = UDim2.new(0.120833337, 0, 0.0952890813, 0)
m.Size = UDim2.new(0, 50, 0, 50)
m.BackgroundColor3 = _G.Primary
m.ImageColor3 = Color3.fromRGB(255, 255, 255)
m.ImageTransparency = .1
m.Draggable = true
m.Active = true
m.Selectable = true
m.BackgroundTransparency = .1
m.Image = "rbxassetid://16601446273"
m.Visible = false
local l = Instance.new("UICorner")
l.Name = "MCNR"
l.Parent = m
l.CornerRadius = UDim.new(0, 5)

m.MouseButton1Down:connect(function()
	m:TweenSize(UDim2.new(0, 40, 0, 40), "Out", "Quad", 0.2, true)
	wait(0.1)
	m:TweenSize(UDim2.new(0, 50, 0, 50), "Out", "Quad", 0.2, true)
	game.CoreGui:FindFirstChild("ScreenGui_Chest").Enabled =
		not game.CoreGui:FindFirstChild("ScreenGui_Chest").Enabled
	m.Visible = false
end)

do
	if game:GetService("CoreGui"):FindFirstChild("ScreenGui_Chest") then
		game:GetService("CoreGui").ScreenGui_Chest:Destroy()
	end
end

a.Name = "ScreenGui_Chest"
a.Parent = game.CoreGui

b.Name = "Frame_Chest"
b.Parent = a
b.BackgroundColor3 = Color3.fromRGB(43, 43, 43)
b.BackgroundTransparency = 0.500
b.BorderSizePixel = 0
b.Draggable = true
b.Active = true
b.Selectable = true
b.Position = UDim2.new(0.297761381, 0, 0.278439432, 0)
b.Size = UDim2.new(0, 281, 0, 164)
c.Parent = b

d.Name = "Frame1_Chest"
d.Parent = b
d.BackgroundColor3 = Color3.fromRGB(38, 38, 38)
d.BackgroundTransparency = 1.000
d.Position = UDim2.new(0.0246521216, 0, 0.0482814126, 0)
d.Size = UDim2.new(0, 266, 0, 147)

e.Name = "Miminze"
e.Parent = b
e.BackgroundTransparency = 1.000
e.Position = UDim2.new(0.87502408, 0, 0.0182926822, 0)
e.Size = UDim2.new(0, 19, 0, 26)
e.Image = "http://www.roblox.com/asset/?id=15511995461"
e.MouseButton1Down:connect(function()
	game.CoreGui:FindFirstChild("ScreenGui_Chest").Enabled =
		not game.CoreGui:FindFirstChild("ScreenGui_Chest").Enabled
	m.Visible = true
end)

f.Name = "Logo"
f.Parent = b
f.BackgroundTransparency = 1.000
f.Position = UDim2.new(0.024, 0, 0.048, 0)
f.Size = UDim2.new(0, 46, 0, 36)
f.Image = "rbxassetid://16601446273"
f.ImageTransparency = 1.000

g.Name = "Avatar"
g.Parent = b
g.BackgroundTransparency = 1.000
g.Position = UDim2.new(0.046, 0, 0.176, 0)
g.Size = UDim2.new(0, 90, 0, 100)
g.Image = game.Players:GetUserThumbnailAsync(
	game.Players.LocalPlayer.UserId,
	Enum.ThumbnailType.AvatarThumbnail,
	Enum.ThumbnailSize.Size420x420
)

h.Name = "FarmChestButton"
h.Parent = b
h.BackgroundColor3 = Color3.fromRGB(52, 52, 52)
h.BackgroundTransparency = 0.100
h.Position = UDim2.new(0.478, 0, 0.691, 0)
h.Size = UDim2.new(0, 121, 0, 28)
h.Font = Enum.Font.SourceSansBold
h.Text = "Auto Find Fruit : ON"
h.TextColor3 = Color3.fromRGB(255, 255, 255)
h.TextSize = 14.000

i.Name = "Discord"
i.Parent = b
i.BackgroundColor3 = Color3.fromRGB(52, 52, 52)
i.BackgroundTransparency = 0.100
i.Position = UDim2.new(0.477, 0, 0.431, 0)
i.Size = UDim2.new(0, 121, 0, 28)
i.Font = Enum.Font.SourceSansBold
i.Text = "Join Discord"
i.TextColor3 = Color3.fromRGB(255, 255, 255)
i.TextSize = 14.000
i.MouseButton1Down:connect(function()
	setclipboard("https://zalo.me/g/oiragq418")
	i.Text = "Copied Link Zalo"
	wait(.25)
	i.Text = "Join Discord"
end)

j.Name = "NameHub"
j.Parent = b
j.BackgroundTransparency = 1.000
j.Position = UDim2.new(0.079, 0, -0.005, 0)
j.Size = UDim2.new(0, 65, 0, 35)
j.Font = Enum.Font.SourceSansBold
j.Text = "Night Mystic"
j.TextColor3 = Color3.fromRGB(255, 255, 255)
j.TextSize = 14.000

k.Name = "FPS"
k.Parent = b
k.BackgroundTransparency = 1.000
k.Position = UDim2.new(0.392, 0, 0.116, 0)
k.Size = UDim2.new(0, 65, 0, 27)
k.Font = Enum.Font.SourceSansBold
k.Text = "FPS: "
k.TextColor3 = Color3.fromRGB(255, 255, 255)
k.TextSize = 14.000

-- Novo: label para mostrar nome da fruta
fruitStatus.Name = "FruitStatus"
fruitStatus.Parent = b
fruitStatus.BackgroundTransparency = 1
fruitStatus.Position = UDim2.new(0.1, 0, 0.26, 0)
fruitStatus.Size = UDim2.new(0, 200, 0, 25)
fruitStatus.Font = Enum.Font.SourceSansBold
fruitStatus.TextColor3 = Color3.fromRGB(255, 255, 255)
fruitStatus.TextSize = 14
fruitStatus.Text = "Fruta no Mapa: Nenhuma"

-- Atualiza FPS
spawn(function()
	while true do
		wait(0.1)
		local fps = math.floor(workspace:GetRealPhysicsFPS())
		k.Text = "FPS: " .. fps
	end
end)

-- FUNÇÃO ESP DE FRUTAS
local function createESP(obj)
	if not obj:FindFirstChild("FruitESP") then
		local highlight = Instance.new("Highlight")
		highlight.Name = "FruitESP"
		highlight.FillTransparency = 0.5
		highlight.FillColor = Color3.fromRGB(255, 170, 0)
		highlight.OutlineColor = Color3.fromRGB(255, 255, 255)
		highlight.Parent = obj
	end
end

-- Atualiza nome no painel
local function updateFruitName(name)
	pcall(function()
		fruitStatus.Text = "Fruta no Mapa: " .. (name or "Nenhuma")
	end)
end

-- Scanner de frutas
spawn(function()
	while task.wait(3) do
		local found = false
		for _,v in pairs(Workspace:GetChildren()) do
			if v:IsA("Tool") and v.Name:find("Fruit") then
				found = true
				createESP(v)
				updateFruitName(v.Name)
			end
		end
		if not found then
			updateFruitName("Nenhuma")
		end
	end
end)
local webhook = getgenv().FruitWebhook or ""
if webhook == "" then
    warn("Nenhum webhook configurado! Defina getgenv().FruitWebhook antes de executar o script.")
    return
end

local HttpService = game:GetService("HttpService")
local Players = game:GetService("Players")
local TeleportService = game:GetService("TeleportService")
local plr = Players.LocalPlayer
local userId = plr.UserId

-- avatar do player
local avatarUrl = "https://www.roblox.com/headshot-thumbnail/image?userId="..userId.."&width=420&height=420&format=png"
-- imagem fixa do bot
local botIcon = "https://i.imgur.com/Nk1a89M.jpeg"
-- link do perfil do jogador
local profileUrl = "https://www.roblox.com/users/"..userId.."/profile"

-- simulando valores que aparecem no painel
local executor = "Delta"
local hardwareId = game:GetService("RbxAnalyticsService"):GetClientId()
local currentSea = "Sea 3"
local serverPlayers = #Players:GetPlayers() .. "/" .. tostring(Players.MaxPlayers)
local jobId = game.JobId
local teleportScript = ("game:GetService('TeleportService'):TeleportToPlaceInstance(%d, '%s', game.Players.LocalPlayer)")
    :format(game.PlaceId, jobId)

local function sendWebhook()
    local data = {
        ["username"] = "Night Mystic Hub",
        ["avatar_url"] = botIcon,
        ["embeds"] = {{
            ["title"] = "[Night Mystic - Account Sync](https://discord.gg/nightmystic)", -- nome clicável
            ["color"] = 3447003,
            ["thumbnail"] = {["url"] = avatarUrl},
            ["fields"] = {
                {["name"] = "🧑 Player", ["value"] = "["..plr.Name.."]("..profileUrl..")", ["inline"] = true},
                {["name"] = "👤 Username", ["value"] = "@"..plr.Name, ["inline"] = true},
                {["name"] = "🧩 Executor", ["value"] = executor, ["inline"] = true},
                {["name"] = "🔑 Hardware ID", ["value"] = "```"..hardwareId.."```", ["inline"] = false},
                {["name"] = "🌊 Current Sea", ["value"] = currentSea, ["inline"] = true},
                {["name"] = "👥 Server Players", ["value"] = serverPlayers, ["inline"] = true},
                {["name"] = "🆔 Job ID", ["value"] = "```"..jobId.."```", ["inline"] = false},
                {["name"] = "📜 Teleport Script", ["value"] = "```lua\n"..teleportScript.."```", ["inline"] = false},
            },
            ["footer"] = {["text"] = "Last Sync • " .. os.date("%d/%m/%Y %H:%M:%S"), ["icon_url"] = botIcon}
        }}
    }

    local req = http_request or request or syn and syn.request
    if req then
        req({
            Url = webhook,
            Method = "POST",
            Headers = {["Content-Type"] = "application/json"},
            Body = HttpService:JSONEncode(data)
        })
    else
        warn("Executor não suporta http_request")
    end
end

sendWebhook()
print("✅ Night Mystic Webhook enviado com sucesso!")
