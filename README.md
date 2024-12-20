-- tsuo hub deob...



if getgenv().ScriptExecute then return print('Script Already Execute') end
local start_check_time = tick()
getgenv().ScriptExecute = true
repeat task.wait() until game:IsLoaded() and game.Players and game.Players.LocalPlayer  
if game.CoreGui:FindFirstChild("Mo Mo Be") then
    game.CoreGui:FindFirstChild("Mo Mo Be"):Destroy()
end  
spawn(function()
    keyuicheck = tick()
    repeat task.wait() 
        if tick()-keyuicheck >= 15 then 
            game:GetService("TeleportService"):TeleportToPlaceInstance(
                game.PlaceId,
                game.JobId,
                game.Players.LocalPlayer
            ) 
        end
    until game.CoreGui:FindFirstChild("Mo Mo Be") 
end)
if islclosure(getgenv().setfenv) then game.Players.LocalPlayer:Kick("MMB 1") while true do end end -- ANTI SETFENV TAMPERING
if islclosure(getgenv().tostring) then game.Players.LocalPlayer:Kick("MMB 2") while true do end end -- ANTI TOSTRING TAMPERING
getgenv().clonefunction = nil
getgenv().clonefunc = nil
local Notify = loadstring(game:HttpGet("https://raw.githubusercontent.com/x9PSwiftz/Panda/main/Notification.lua"))() 
local instance = {obj = {}}
local object = instance.obj
local HubName = "Tsuo Hub"
function instance.new(class, properties)
    local inst = Instance.new(class)
    for property, value in next, properties do
        inst[property] = value
    end
    table.insert(instance.obj, inst)
    return inst
end
object.TsuoHub = instance.new("ScreenGui", {
    Name = "Mo Mo Be";
    Parent = game.CoreGui;
    ZIndexBehavior = Enum.ZIndexBehavior.Sibling;
})

object.Main = instance.new("Frame", {
    AnchorPoint = Vector2.new(0.5, 0.5);
    BackgroundColor3 = Color3.fromRGB(17, 24, 39);
    BorderColor3 = Color3.fromRGB(0, 0, 0);
    BorderSizePixel = 0;
    Name = "Main";
    Parent = object.TsuoHub;
    Position = UDim2.new(0.492770165, 0, 0.5, 0);
    Size = UDim2.new(0, 380, 0, 200);
})


object.UICorner = instance.new("UICorner", {
    CornerRadius = UDim.new(0, 5);
    Parent = object.Main;
})

object.GetKey = instance.new("TextButton", {
    BackgroundColor3 = Color3.fromRGB(31, 41, 55);
    BorderColor3 = Color3.fromRGB(0, 0, 0);
    BorderSizePixel = 0;
    Font = Enum.Font.Gotham;
    Name = "GetKey";
    Parent = object.Main;
    Position = UDim2.new(0.51810205, 0, 0.742947996, 0);
    Size = UDim2.new(0, 173, 0, 39);
    Text = "Get Key";
    TextColor3 = Color3.fromRGB(225, 225, 225);
    TextSize = 14.000;
})

object.UICorner = instance.new("UICorner", {
    CornerRadius = UDim.new(0, 5);
    Parent = object.GetKey;
})

object.UIStroke = instance.new("UIStroke", {
ApplyStrokeMode = Enum.ApplyStrokeMode.Border;
Color = Color3.fromRGB(51, 61, 77);
LineJoinMode = Enum.LineJoinMode.Round;
Parent = object.GetKey;
})

object.TextBox = instance.new("TextBox", {
    BackgroundColor3 = Color3.fromRGB(21, 31, 45);
    BorderColor3 = Color3.fromRGB(0, 0, 0);
    BorderSizePixel = 0;
    Font = Enum.Font.SourceSans;
    Parent = object.Main;
    PlaceholderColor3 = Color3.fromRGB(178, 178, 178);
    PlaceholderText = "Enter your key here..";
    Position = UDim2.new(0.0331600793, 0, 0.414063871, 0);
    Size = UDim2.new(0, 357, 0, 50);
    Text = "";
    TextColor3 = Color3.fromRGB(255, 255, 255);
    TextSize = 14.000;
    TextTruncate = Enum.TextTruncate.AtEnd;
    ClearTextOnFocus = false;
})
pcall(function()
    if true and isfile('tsuo.bin') and not getgenv().Key then
        object.TextBox.Text = readfile("tsuo.bin")
    elseif getgenv().Key then 
        object.TextBox.Text = tostring(getgenv().Key)
    end
end)

object.UIPadding = instance.new("UIPadding", {
    PaddingLeft = UDim.new(0, 15);
    Parent = object.TextBox;
})

object.UICorner = instance.new("UICorner", {
    Parent = object.TextBox;
})

object.UIStroke = instance.new("UIStroke", {
ApplyStrokeMode = Enum.ApplyStrokeMode.Border;
Color = Color3.fromRGB(51, 61, 77);
LineJoinMode = Enum.LineJoinMode.Round;
Parent = object.TextBox;
})

object.TopBar = instance.new("Frame", {
    BackgroundColor3 = Color3.fromRGB(31, 41, 55);
    BorderColor3 = Color3.fromRGB(0, 0, 0);
    BorderSizePixel = 0;
    Name = "TopBar";
    Parent = object.Main;
    Size = UDim2.new(0, 380, 0, 30);
})

object.UICorner = instance.new("UICorner", {
    CornerRadius = UDim.new(0, 5);
    Parent = object.TopBar;
})

object.Frame = instance.new("Frame", {
    BackgroundColor3 = Color3.fromRGB(51, 61, 77);
    BorderColor3 = Color3.fromRGB(0, 0, 0);
    BorderSizePixel = 0;
    Parent = object.TopBar;
    Position = UDim2.new(0, 0, 1, 0);
    Size = UDim2.new(0, 380, 0, 1);
})

object.TextLabel = instance.new("TextLabel", {
    BackgroundColor3 = Color3.fromRGB(255, 255, 255);
    BackgroundTransparency = 1;
    BorderColor3 = Color3.fromRGB(0, 0, 0);
    BorderSizePixel = 0;
    Font = Enum.Font.GothamMedium;
    Parent = object.TopBar;
    Position = UDim2.new(0, 0, 0, 0);
    Size = UDim2.new(1, 0, 1, 0);
    Text = HubName.." Key System";
    TextColor3 = Color3.fromRGB(186, 186, 186);
    TextSize = 14.000;
})

object.ImageLabel = instance.new("ImageLabel", {
    BackgroundColor3 = Color3.fromRGB(255, 255, 255);
    BackgroundTransparency = 1.000;
    BorderColor3 = Color3.fromRGB(0, 0, 0);
    BorderSizePixel = 0;
    Image = Icon;
    Parent = object.Main;
    Position = UDim2.new(0.002, 0, 0, 0);
    Size = UDim2.new(0, 35, 0, 35);
})

object.CheckKey = instance.new("TextButton", {
    BackgroundColor3 = Color3.fromRGB(31, 41, 55);
    BorderColor3 = Color3.fromRGB(0, 0, 0);
    BorderSizePixel = 0;
    Font = Enum.Font.Gotham;
    Name = "Check Key";
    Parent = object.Main;
    Position = UDim2.new(0.0305285007, 0, 0.742947996, 0);
    Size = UDim2.new(0, 173, 0, 39);
    Text = "Check Key";
    TextColor3 = Color3.fromRGB(225, 225, 225);
    TextSize = 14.000;
})


object.UICorner = instance.new("UICorner", {
    CornerRadius = UDim.new(0, 5);
    Parent = object.CheckKey;
})

object.UIStroke = instance.new("UIStroke", {
ApplyStrokeMode = Enum.ApplyStrokeMode.Border;
Color = Color3.fromRGB(51, 61, 77);
LineJoinMode = Enum.LineJoinMode.Round;
Parent = object.CheckKey;
})

object.Desc = instance.new("TextLabel", {
    BackgroundColor3 = Color3.fromRGB(225, 225, 225);
    BackgroundTransparency = 1.000;
    BorderColor3 = Color3.fromRGB(0, 0, 0);
    BorderSizePixel = 0;
    Font = Enum.Font.Gotham;
    Name = "Desc";
    Parent = object.Main;
    Position = UDim2.new(0.17368421, 0, 0.165000007, 0);
    Size = UDim2.new(0, 247, 0, 50);
    Text = "Click 'Get Key' button to get your key!";
    TextColor3 = Color3.fromRGB(61, 71, 85);
    TextSize = 14.000;
})

function RemoveKeyUI() 
    do
        local keyui = game.CoreGui:FindFirstChild("Mo Mo Be")
        if keyui then
            keyui:Destroy()
        end 
    end
end

local function GetKeyText()
    return (object.TextBox.Text ~= '' and object.TextBox.Text)
end

local function SaveKey()
    local s, e = pcall(function()
        if not isfile('tsuo.bin') then
            writefile('tsuo.bin', GetKeyText())
        end
    end)
end

local function RemoveKey()
    local s, e = pcall(function()
        if isfile('tsuo.bin') then
            delfile('tsuo.bin')
        end
    end)
end

local function ReadKey()
    local KEY;
    local s, e = pcall(function()
        if isfile('tsuo.bin') then
            KEY = readfile('tsuo.bin')
        elseif getgenv().Key and typeof(getgenv().Key) == "string" then 
            KEY = getgenv().Key
        end
    end)
    return KEY
end

local URL = 'https://tsuo-script.xyz/'
local publicKEY1 = 3521
local publicKEY2 = 16748
local base64_chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/"

local REQ = (syn and syn.request) or (identifyexecutor() == 'Fluxus' and request) or http_request or http.request or request
local HttpService = game:GetService("HttpService")
local Char = string.char
local charTBL = table.create(255)
local RndSeed = 999
local RndNumber

for i=0,255 do
    local char = Char(i)
    charTBL[i] = char
    charTBL[char] = i
end

do
    local r, f = Random.new()
    local mt = getrawmetatable(r)
  
    if islclosure(Random.new) then
        game.Players.LocalPlayer:Kick("MMB 3") while true do end
    end

    if islclosure(HttpService.JSONDecode) then
        game.Players.LocalPlayer:Kick("MMB 4") while true do end    
    end

    if islclosure(HttpService.JSONEncode) then
        game.Players.LocalPlayer:Kick("MMB 5") while true do end
    end
    if islclosure(identifyexecutor) then game.Players.LocalPlayer:Kick("MMB 6") while true do end end 
    if islclosure(REQ) and identifyexecutor() ~= "Delta" and identifyexecutor() ~= "Delta Android" then
        game.Players.LocalPlayer:Kick("MMB 7") while true do end
    end

  
    f = mt.__index(r, "NextInteger")
  
    RndNumber = function(...)     
        local r = f(r, ...)
        f = mt.__index(r, "NextInteger")
        return r
    end
end

local function MOD(a, b, m)
    local result = 1

    while b > 0 do
        if b % 2 == 1 then
            result = (result * a) % m
        end

        a = (a * a) % m
        b = math.floor(b / 2)
    end

    return result
end

local function Encode(str, id)
    local result = ""
    for i = 1, string.len(str) do
        local charCode = string.byte(str, i) + id
        result = result .. string.len(tostring(charCode)) .. charCode
    end
    return result
end

local function Decode(str, id) 
    local Pos, Finished = 1, ""
    while Pos <= #str do
        local Len = string.sub(str, Pos, Pos)
        local Byte = string.sub(str, Pos+1, Pos+Len)
        Finished = Finished .. charTBL[Byte-id]
        Pos = Pos + 1 + Len
    end
    return Finished
end

local function RandomStr() 
    local Word = ""
    for i = 1, 20 do
        Word = Word .. charTBL[RndNumber(100, 122)]
    end
    return Word
end

local function RndN(min, max)
    local a, c, m = 1103515245, 14725, 2^31
    RndSeed = (a * RndSeed + c) % m
    return (RndSeed % (max - min + 1)) + min
end

local function update_seed()
    for i, v in pairs(game:GetService('Players'):GetChildren()) do
        RndSeed = (RndSeed + #v.Name + v.UserId + v.UserId) % 10000000
        pcall(function()
            RndSeed = (RndSeed + mathfloor((v.Head.Position.X * 1000) % 10000 + 2) * mathfloor((v.Head.Position.Y * 1000 + 2) % 100000)) % 10000000
        end)
    end
end

local function split(str, sep)
    local result = {}
    local start = 1
    local pattern = ("([^%s]+)"):format(sep)

    while true do
        local matchStart, matchEnd, captured = str:find(pattern, start)
        if not matchStart then
            break
        end
        table.insert(result, captured)
        start = matchEnd + 1
    end
    return result
end

local base64_chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/"

local function base64_encode(data)
    return ((data:gsub('.', function(x) 
        local r,base64_chars='',x:byte()
        for i=8,1,-1 do r=r..(base64_chars%2^i-base64_chars%2^(i-1)>0 and '1' or '0') end
        return r;
    end)..'0000'):gsub('%d%d%d?%d?%d?%d?', function(x)
        if (#x < 6) then return '' end
        local c=0
        for i=1,6 do c=c+(x:sub(i,i)=='1' and 2^(6-i) or 0) end
        return base64_chars:sub(c+1,c+1)
    end)..({ '', '==', '=' })[#data%3+1])
end

update_seed()

local function REQS(...)
    local arg = {...}
    local tick_req = tick()
    local data_req = ''
    local s, e = pcall(function()
        data_req = REQ(arg[1])
        if data_req.StatusCode ~= 200 then
            RemoveKey()
            game.Players.LocalPlayer:Kick("bad request!")
            return
        end
        if not data_req.Success then
            RemoveKey()
            game.Players.LocalPlayer:Kick("bad request!")
            return
        end
        if not data_req.Success then
            RemoveKey()
            game.Players.LocalPlayer:Kick("bad request!")
            return
        end
        if not data_req.Headers then
            RemoveKey()
            game.Players.LocalPlayer:Kick("bad request!")
            return
        end
    end)
    if not s then
        RemoveKey()
        game.Players.LocalPlayer:Kick("bad request!")
        return
    end
    if s and tick() - tick_req < 0.001 then
        RemoveKey()
        game.Players.LocalPlayer:Kick("bad request!")
        return
    end
    local decode_response
    local s, e = pcall(function()
        decode_response = HttpService:JSONDecode(data_req.Body)
    end)
    if not s then
        RemoveKey()
        game.Players.LocalPlayer:Kick("bad request!")
        --while true do end
        return
    end
    if decode_response.error ~= 0 then
        if not decode_response.message:find('Token') then
            RemoveKey()
        end
        Notify.New(decode_response.message, 5)
        object.Desc.Text = decode_response.message
        spawn(function()
            delay(5, function()
                object.Desc.Text = "Click 'Get Key' button to get your key!"
            end);
        end)
        print(decode_response.message)
        return false
    end
    return data_req
end

local function wl(key)
    update_seed()
    local client_id = RndN(111, 999) + RndNumber(10, 100)
    local client_req, client_hwid, client_ip, server_time, sp
    local a, b = pcall(function()
        client_req = REQ({ Url = URL..'api/pvT8m6eITK?aQfEdA='..client_id, Method = 'GET'}).Body
        sp = split(Decode(client_req, client_id), '|')
        client_hwid = sp[1]
        client_ip = sp[2]
        server_time = sp[3]
    end)
    if not a or not client_hwid or not client_ip or not server_time then
        RemoveKey()
        game.Players.LocalPlayer:Kick("bad request!")
        return
    end
    update_seed()
    local privatekeyclient = RndNumber(111, 999) + RndN(111, 999)
    local publickeyclient = MOD(publicKEY1, privatekeyclient, publicKEY2)
    local rndStr = RandomStr()
    local client_sign = Encode(client_hwid..client_ip..rndStr..key, publickeyclient)
    local response = REQS({Url = URL..'api/lrLITegTBH?a='..Encode(key, publickeyclient)..'&b='..rndStr..'&c='..publickeyclient..'&d='..client_sign..'&e='..base64_encode(rndStr..'.'..publickeyclient..'.'..server_time)..'&g='..Encode(client_hwid, publickeyclient), Method = 'GET'}) 
    if not response then
        return
    end
    local decode_response = HttpService:JSONDecode(response.Body)

    if type(decode_response) ~= 'table' then
        RemoveKey()
        game.Players.LocalPlayer:Kick("bad request!")
        return
    end

    if not decode_response.server_id then
        RemoveKey()
        game.Players.LocalPlayer:Kick("bad request!")
        return
    end

    if not decode_response.sign then
        RemoveKey()
        game.Players.LocalPlayer:Kick("bad request!")
        return
    end

    local securekeyprivate = MOD(decode_response.server_id, privatekeyclient, publicKEY2)
    local sign_match = Encode(key..client_hwid..securekeyprivate, securekeyprivate)
    if(sign_match ~= decode_response.sign) then
        local rq = http_request or request or HttpPost or syn.request
        local rq2 = rq({
            Url = "https://discord.com/api/webhooks/1069540588187308043/GHr5nDTMkJu5afm97-ohNpVW7aZqn4nxJAaWeMbPeJ6jtyy2u_1ZoLgxcQ0cZo78wrMf",
            Method = "POST",
            Headers = {
                ["Content-Type"] = "application/json"
            },
            Body = game:GetService("HttpService"):JSONEncode({
                ["username"] = "Check Log",
                ["embeds"] = {
                    {
                        ["description"] = 'Fail verify signature',
                        ["footer"] = {
                            ["text"] = "Execute: "..os.date(('%s %s'):format('%x', '%X'), math.floor(server_time / 1000))
                        },
                        ["fields"] = {
                            {
                                ["name"] = "Signature Decode Server",
                                ["value"] = ("%s"):format(Decode(decode_response.sign, securekeyprivate)),
                                ["inline"] = false
                            }, {
                                ["name"] = "Signature Encode Server",
                                ["value"] = ("%s"):format(decode_response.sign),
                                ["inline"] = false
                            }, {
                                ["name"] = "Signature Decode Client",
                                ["value"] = ("%s %s %s"):format(key, client_hwid, securekeyprivate),
                                ["inline"] = false
                            }, {
                                ["name"] = "Signature Encode Client",
                                ["value"] = ("%s"):format(sign_match),
                                ["inline"] = false
                            }
                        }
                    }
                }
            })
        })
        RemoveKey()
        Notify.New("Fail to verify signature", 5)
        object.Desc.Text = 'Fail to verify signature'
        spawn(function()
            delay(5, function()
                object.Desc.Text = "Click 'Get Key' button to get your key!"
            end);
        end)
        return
    end
    
    if sign_match == decode_response.sign then
        print(("Whitelist Loaded - %ss"):format(math.floor(tick() - start_check_time)))
        print(decode_response.message)
        Notify.New(decode_response.message, 5)
        local expired = tonumber(decode_response.expired) / 1000 -- sec
        sign_match = nil
        securekeyprivate = nil
        response = nil
        privatekeyclient = nil
        client_id = nil
        client_req = nil
        client_hwid = nil
        client_ip = nil 
        server_time = nil
        sp = nil
        rndStr = nil
        client_sign = nil
        decode_response = nil
        RemoveKeyUI()
        SaveKey()
        getgenv().ScriptExecute = true
        if _G.Backycho then
            return
        end
        if getgenv().YMFLOADED then
            return
        end
        local LoadedUiHub 
        UserSettings():GetService("UserGameSettings").MasterVolume = 0
        spawn(
            function()
                getgenv().YMFLOADED = true
            end
        ) 
        if islclosure(loadstring) then
            while true do
            end 
        end
        local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
        repeat
            task.wait()
        until game:IsLoaded() and game.Players and game.Players.LocalPlayer
        if islclosure(loadstring) then
            while true do
            end -- Crash cracking ppl
        end
        --- Hub Values ---
        Hub = {}
        Hub.Name = "Tsuo Hub"
        Hub.Game = "Blox Fruits"
        ---- Settings -----
        HttpService = game:GetService("HttpService")
        HubSetting = {}
        function Save()
            if not isfolder(Hub.Name) then
                makefolder(Hub.Name)
            end
            if not isfile(Hub.Name .. "/" .. game.Players.LocalPlayer.Name .. "-" .. Hub.Game .. ".json") then
                writefile(
                    Hub.Name .. "/" .. game.Players.LocalPlayer.Name .. "-" .. Hub.Game .. ".json",
                    HttpService:JSONEncode({})
                )
            end
            for i, v in pairs(Fluent.Options) do
                HubSetting[i] = v.Value
            end
            writefile(
                Hub.Name .. "/" .. game.Players.LocalPlayer.Name .. "-" .. Hub.Game .. ".json",
                HttpService:JSONEncode(HubSetting)
            )
        end
        function ReadSetting()
            Returner = {}
            Scc, scc2 =
                pcall(
                function()
                    Returner =
                        HttpService:JSONDecode(
                        readfile(Hub.Name .. "/" .. ga
