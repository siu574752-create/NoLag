-- Auto join + auto gift pet (mẫu)
local TeleportService = game:GetService("TeleportService")
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

-- ID place chính của Grow a Garden (bạn cần thay đúng ID)
local placeId = 126884695634066  

-- Nếu bạn muốn auto join VIP server, thay link VIP vào đây
local vipCode = "https://www.roblox.com/share?code=1852bfd0bbba64448ebaf2c8e3e9a08c&type=Server" 

-- Tên người cố định sẽ nhận pet
local targetPlayerName = "haihonhonko"

-- RemoteEvent bạn tìm được bằng RemoteSpy
local giftEvent = ReplicatedStorage:WaitForChild("Gift") 

-- PetId bạn tìm được bằng RemoteSpy
local petId = dragon fly  

-- Hàm auto gift
local function autoGift()
    local targetPlayer = Players:FindFirstChild(haihonhonko)
    if targetPlayer then
        giftEvent:FireServer(dragon fly, haihonhonko)
        warn("✅ Đã auto gift pet cho: "..haihonhonko)
    else
        warn("❌ Không tìm thấy người nhận trong server")
    end
end

-- Tự join VIP server
TeleportService:TeleportToPrivateServer(126884695634066, https://www.roblox.com/share?code=1852bfd0bbba64448ebaf2c8e3e9a08c&type=Server, {Players.LocalPlayer})

-- Khi load game xong thì auto gift
Players.LocalPlayer.CharacterAdded:Connect(function()
    autoGift()
end)