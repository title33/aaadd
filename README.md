local function Y()
    if not game:IsLoaded()then 
        local p=Instance.new("Message",workspace);
        p.Text='XenonV2 is waiting for the game to load';
        game.Loaded:Wait();
        p:Destroy();
        wait(15);
    end;
    local x=game:GetService("Players").LocalPlayer;
    local W=game.ReplicatedStorage.Remotes;pcall(function()
        if x.PlayerGui:FindFirstChild("LoadingScreen")then 
            if not pcall(function()return x.PlayerGui.LoadingScreen.Background.Loading.Skip;end)then 
                game:GetService('TeleportService'):Teleport(game.PlaceId);
            end;
        end;
    end);
    task.spawn(function()
        while true do wait(10);
            pcall(function()
                if x.PlayerGui:FindFirstChild("LoadingScreen")then 
                    if not pcall(function()return x.PlayerGui.LoadingScreen.Background.Loading.Skip;end)then 
                        game:GetService('TeleportService'):Teleport(game.PlaceId);
                    end;
                end;
            end);
        end;
    end);
    pcall(function()
        repeat task.wait(1);
            for p,P in pairs(getconnections(x.PlayerGui.LoadingScreen.Background.Loading.Skip.MouseButton1Click))do 
                P.Function();
            end;
        until not x.PlayerGui:FindFirstChild("LoadingScreen");
    end);
    pcall(function()
    end);
    wait();
    All_Zones2={
    ["Cavern"]=Vector3.new(-2223.955810546875,783.0618286132812,-3904.94482421875),
    ["Sun Mansion"]=Vector3.new(-4819.1220703125,885.63916015625,-4831.20751953125),
    ["Mountain"]=Vector3.new(-2167.412353515625,965.3818969726562,-3992.35009765625),
    ["Cavern Passage"]=Vector3.new(-2183.569091796875,1143.1932373046875,-1903.34765625),
    ["Frosty Forest"]=Vector3.new(929.4169311523438,1093.697265625,-6641.41748046875),
    ["Sakura Passage"]=Vector3.new(-2390.013671875,738.3121337890625,-3229.83984375),
    ["Frosty Cavern"]=Vector3.new(-2271.674560546875,954.1795654296875,-2592.3427734375),
    ["Kamakura Village"]=Vector3.new(-2387.177734375,1151.0936279296875,-1715.179443359375),
    ["Okuyia Plains"]=Vector3.new(-4116.009765625,874.843994140625,292.89849853515625),
    ["The White Peak"]=Vector3.new(1391.6268310546875,1058.7581787109375,-640.4218139648438),
    ["Okuyia Cavern"]=Vector3.new(-4224.09033203125,862.98388671875,952.9228515625),
    ["Crystal Underground"]=Vector3.new(-2606.737060546875,856.9888916015625,1314.547607421875),
    ["Infinity Castle"]=Vector3.new(2042.228515625,1588.5452880859375,-7280.9853515625),
    ["Kurohitsugi"]=Vector3.new(-3323.55029296875,326.0249938964844,-1063.375),
    ["White Underground"]=Vector3.new(1514.102294921875,1180.1484375,-1376.38916015625),
    ["Okuyia Village"]=Vector3.new(-3466.723388671875,769.1138916015625,-1300.3853759765625),
    ["Demon Purgatory"]=Vector3.new(2457.0859375,1171.5732421875,-7421.57177734375),
    ["Waterfall Cavern"]=Vector3.new(-2006.6116943359375,1013.1083984375,-1617.4810791015625),
    ["Hayakawa Village"]=Vector3.new(639.3189697265625,753.4089965820312,-2165.29296875),
    ["White Passage"]=Vector3.new(1192.776123046875,967.9183349609375,-1445.92236328125),
    ["Demon Camp"]=Vector3.new(-748.1751098632812,710.2323608398438,-1526.811279296875),
    ["Demon Hideout"]=Vector3.new(-4314.1484375,862.98388671875,580.3045043945312),
    ["Coast Forest"]=Vector3.new(417.4654541015625,753.408935546875,-148.78143310546875),
    ["Slayer Corps"]=Vector3.new(-1556,872,-6362)
};
    pcall(function()
        getgenv().old_pos=x.Character:FindFirstChild("HumanoidRootPart").Position;
    end);
    pcall(function()
        for G,p in pairs(All_Zones2)do 
            if x:FindFirstChild("SecurityBypass")then 
                x.Character.HumanoidRootPart.CFrame=CFrame.new(p);
            end;
            wait(0.2);
        end;
    end);
    wait(0.2);
    pcall(function()
        x.Character.HumanoidRootPart.CFrame=CFrame.new(getgenv().old_pos);
    end);
    wait(2);
    local e=game.PlaceId;
    local g={};
    local l="";
    local T=os.date("!*t").hour;
    local a=false;
    function TPReturner()
        local I;if l==""then 
            I=game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/'..e..'/servers/Public?sortOrder=Desc&limit=100'));
        else I=game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/'..e..'/servers/Public?sortOrder=Desc&limit=100&cursor='..l));
        end;
        local P="";if I.nextPageCursor and I.nextPageCursor~="null"and I.nextPageCursor~=nil then l=I.nextPageCursor;
        end;
        local p=0;
        for r,G in pairs(I.data)do 
            local E=true;
            P=tostring(G.id);
            if tonumber(G.maxPlayers)>tonumber(G.playing)then 
                for N,Z in pairs(g)do 
                    if p~=0 then 
                    if P==tostring(Z)then 
                        E=false;
                end;
            else if tonumber(T)~=tonumber(Z)then 
                local O0=pcall(function()g={};
                    table.insert(g,T);
                end);
            end;
        end;
        p=p+1;
    end;
    if E==true then 
        table.insert(g,P);
        wait();
        pcall(function()
            wait();
            game:GetService("TeleportService"):TeleportToPlaceInstance(e,P,x);
        end);
        wait(5);
    end;
end;
end;
end;
if getgenv().Teleport==nil then 
    getgenv().Teleport=function()
        while true do task.wait(1);
            pcall(function()
                TPReturner();
                if l~=""then TPReturner();
                end;
            end);
        end;
    end;
end;
local f=game:GetService("HttpService");
local A=game:GetService("RunService");
local F=game:GetService("Players");
local x=F.LocalPlayer;

if not isfolder("Xenon Hub Premium Scripts")then 
    makefolder("Xenon Hub Premium Scripts");
end;
if not isfile("Xenon Hub Premium Scripts/Demonfall_"..x.Name..".cfg")then 
    writefile("Xenon Hub Premium Scripts/Demonfall_"..x.Name..".cfg","[]");
end;
GetSubPrefix=function(G)
    local G=tostring(G):gsub(" ","");
    local E="";
    if#G==2 then 
        local Z=string.sub(G,#G,#G+1);
        E=Z=="1"and"st"or Z=="2"and"nd"or Z=="3"and"rd"or"th";
    end;
    return E;
end;

local O,J=loadstring(game:HttpGet("https://raw.githubusercontent.com/ErenYeaker/SaveScript/main/LibXe.lua"))();

local q="%A, %B";
local m=os.date(" %d",os.time());
local s=", %Y.";
q=os.date(q,os.time())..m..GetSubPrefix(m)..os.date(s,os.time());

local o=O:CreateWindow(("Xenon Hub Premium Scripts - "..tostring(q)));

O:Notify("Loading User Interface.");

local u={Load={AutoLoad={Enabled=true,RageSettings=false,SilentLoad=false,AutoLoadType="Last Config",LastUsedConfig="",LastConfig={},CustomConfig=""},Configs={},Ignored={"SettingsConfigName","SettingsConfigData","SettingsConfigConfigs","SettingsAutoLoadData","SettingsAutoLoadEnabled","SettingsAutoLoadRage","SettingsAutoLoadSilent","SettingsAutoLoadType","SettingsAutoLoadConfig"}},Tick=tick()};

function UpdateTheme()
    O.BackgroundColor=J.SettingsMenuBackgroundColor.Value;
    O.MainColor=J.SettingsMenuMainColor.Value;
    O.AccentColor=J.SettingsMenuAccentColor.Value;
    O.AccentColorDark=O:GetDarkerColor(O.AccentColor);
    O.InlineColor=J.SettingsMenuInlineColor.Value;O.OutlineColor=J.SettingsMenuOutlineColor.Value;
    O.FontColor=J.SettingsMenuFontColor.Value;
    O:UpdateColorsUsingRegistry();
end;

function SetDefault()
    J.SettingsMenuFontColor:SetValueRGB(Color3.fromRGB(175,175,175));
    J.SettingsMenuMainColor:SetValueRGB(Color3.fromRGB(30,30,30));
    J.SettingsMenuBackgroundColor:SetValueRGB(Color3.fromRGB(20,20,20));
    J.SettingsMenuAccentColor:SetValueRGB(Color3.fromRGB(0,219,225));
    J.SettingsMenuInlineColor:SetValueRGB(Color3.fromRGB(75,75,75));
    J.SettingsMenuOutlineColor:SetValueRGB(Color3.fromRGB(75,75,75));
    UpdateTheme();
end;
function ResetSettings()
    for E,I in pairs(J)do 
        if typeof(I.Original)~="nil"then 
            I:SetValue(I.Original);
        end;
    end;
end;
function GetConfigNames()
    local E={};
    for N,Z in pairs(u.Load.Configs)do 
        E[#E+1]=Z[1];
    end;
    return E;
end;

function GetConfigByName(P)
    for E,Z in pairs(u.Load.Configs)do 
        if Z[1]==P then 
            return Z[2];
        end;
    end;
end;

function CreateConfig(Z)
    if typeof(Z)=="string"then 
        if(#Z>3 and#Z<=25)then 
            if(not GetConfigByName(Z))then 
                u.Load.Configs[#u.Load.Configs+1]={Z,(O:GetConfig(u.Load.Ignored))};
                J.SettingsConfigConfigs.Values=GetConfigNames();
                J.SettingsConfigConfigs:SetValues();
                J.SettingsAutoLoadConfig.Values=GetConfigNames();
                J.SettingsAutoLoadConfig:SetValues();
                return O:Notify(("Config \"%s\" Has Been Created."):format(Z));
            end;
            return O:Notify(("Config \"%s\" Already Exists."):format(Z));
        end;
        return O:Notify("Config Name Is Too Long / Short.");
    end;
    return O:Notify("Config Name Is Not A String.");
end;

function GetConfig()
    return(f:JSONEncode(O:GetConfig(u.Load.Ignored)));
end;

function LoadConfig(r)if typeof(r)=="table"then 
    O:SetConfig(r,u.Load.Ignored);
elseif typeof(r)=="string"then 
    local p,I=pcall(function()r=f:JSONDecode(r);
    end);
    if p then 
        O:SetConfig(r,u.Load.Ignored);
        return O:Notify("Config Data Has Been Imported.");
    end;
    return O:Notify(("Error When Loading Config Data Statement : %s."):format(I));
end;
end;

function DeleteConfig(E)
    for P,r in pairs(u.Load.Configs)do 
        if r[1]==E then 
            table.remove(u.Load.Configs,P);
            J.SettingsConfigConfigs.Values=GetConfigNames();
            J.SettingsConfigConfigs:SetValue(J.SettingsConfigConfigs.Value);
            J.SettingsAutoLoadConfig.Values=GetConfigNames();
            J.SettingsAutoLoadConfig:SetValues();
            return O:Notify(("Config \"%s\" Has Been Removed."):format(E));
        end;
    end;
end;

function SaveConfig(G)
    for E,Z in pairs(u.Load.Configs)do 
        if Z[1]==G then u.Load.Configs[E]={G,(O:GetConfig(u.Load.Ignored))};
            return O:Notify(("Config \"%s\" Has Been Saved."):format(G));
        end;
    end;
end;

function ExportData()
    setclipboard(GetConfig());
    O:Notify("Config Data Has Been Exported.");
end;

function ImportData()
    LoadConfig(J.SettingsConfigData.Value);
end;
do O.SaveManager={};
    function O.SaveManager:Save()
        u.Load.AutoLoad.LastConfig=O:GetConfig(u.Load.Ignored);
    end;
    
    function O.SaveManager:Load()
        local p=f:JSONDecode(readfile("Xenon Hub Premium Scripts/Demonfall_"..x.Name..".cfg"));
        u.Load.AutoLoad=(p.AutoLoad or u.Load.AutoLoad);
        u.Load.Configs=(p.Configs or u.Load.Configs);
        do J.SettingsConfigConfigs.Values=GetConfigNames();
            J.SettingsConfigConfigs:SetValues();
            J.SettingsAutoLoadConfig.Values=GetConfigNames();
            J.SettingsAutoLoadConfig:SetValues();
        end;
        local P;
        if u.Load.AutoLoad.AutoLoadType=="Last Used Config"then 
            if GetConfigByName(u.Load.AutoLoad.LastUsedConfig)then 
                P=GetConfigByName(u.Load.AutoLoad.LastUsedConfig);
            end;
        elseif u.Load.AutoLoad.AutoLoadType=="Last Config"then 
            if u.Load.AutoLoad.LastConfig then P=u.Load.AutoLoad.LastConfig;
            end;
        elseif u.Load.AutoLoad.AutoLoadType=="Custom Config"then 
            if GetConfigByName(u.Load.AutoLoad.CustomConfig)then 
                P=GetConfigByName(u.Load.AutoLoad.CustomConfig);
            end;
        end;
        if P then 
            if(not u.Load.RageSettings)then 
                for E,I in pairs(J)do 
                    if(I.Type=="Toggle"and E:sub(1,4)=="Rage")then 
                        if P[E]then warn(("Set %s to false."):format(E));
                            P[E]=false;
                        end;
                    end;
                end;
            end;
            if u.Load.AutoLoad.SilentLoad then 
                P["SettingsMenuKeybinds"]=false;
                P["SettingsMenuWatermark"]=false;
                P["SettingsMiscNotifications"]=false;
                O:SetWatermarkVisibility(false);
                o.Holder.Visible=false;
            end;
            LoadConfig(P);
        end;
    end;
    function O.SaveManager:SaveFile()
        local I=f:JSONEncode({AutoLoad=u.Load.AutoLoad,Configs=u.Load.Configs});
        writefile("Xenon Hub Premium Scripts/Demonfall_"..x.Name..".cfg",I);
    end;
end;
    
    local k=o:AddTab("General");

    local H=k:AddLeftGroupbox("General");

    H:AddLabel("Level - Farm",true);

    local X={"GenericSlayer","GenericOni","FrostyOni","Green Demon","Blue Demon","Lower Moon 3","Zenitsu","Kaigaku"};
    local y={};
    pcall(function()
        for I in pairs(y)do
            y[I]=nil;
        end;
        for r,P in pairs(game.Players:GetPlayers())do 
            if not table.find(y,P.Name)then 
                table.insert(y,P.Name);
            end;
        end;
        for p,P in pairs(workspace:GetChildren())do 
            if not table.find(y,P.Name)and not table.find(X,P.Name)and P:FindFirstChild("Humanoid")then 
                table.insert(X,P.Name);
            end;
        end;
    end);
    task.spawn(function()
        game:GetService("RunService").RenderStepped:Connect(function()
            pcall(function()
            sethiddenproperty(x,"SimulationRadius",math.huge);
            sethiddenproperty(x,"MaxSimulationRadius",math.huge);
        end);
    end);
end);

H:AddDropdown("Selected_Mobs",{Text="Select Monster / Bosses",Multi=true,Default=1,Values=X});
H:AddToggle("Auto_Farm_Level",{Text="Auto Farm Level",Default=false});
H:AddToggle("Auto_Farm_Level_Hop",{Text="Auto Farm Level Hop",Default=false});
task.spawn(function()
    while true do wait(5);
        for I in pairs(y)do 
            y[I]=nil;
        end;
        for E,P in pairs(game.Players:GetPlayers())do 
            if not table.find(y,P.Name)then 
                table.insert(y,P.Name);
            end;
        end;
        for I,P in pairs(game.Workspace:GetChildren())do 
            if not table.find(y,P.Name)and not table.find(X,P.Name)and P:FindFirstChild("Humanoid")then 
                table.insert(X,P.Name);
            end;
        end;
        J.Selected_Mobs.Values=X;
        J.Selected_Mobs:SetValues();
    end;
end);

local B=k:AddLeftGroupbox("Auto Farm Status");
local M=B:AddLabel("Status : N/A");
local i=B:AddLabel("CV : 69.0245 (15%CV)");
local L={};
for I,p in pairs(game:GetService("Players"):GetChildren())do 
    if p.Name~=x.Name then 
        table.insert(L,p.Name);
    end;
end;
local w=k:AddLeftGroupbox("Players - Farm");
w:AddDropdown("Selected_Players",{Text="Select Players",Values=L});
game:GetService("Players").PlayerAdded:Connect(function(E)table.insert(L,tostring(E.Name));
    J.Selected_Players.Values=L;
    J.Selected_Players:SetValues();
end);
game:GetService("Players").PlayerRemoving:Connect(function(Z)
    local N=table.find(L,tostring(Z.Name));
    if N then 
        table.remove(L,N);
    end;
    J.Selected_Players.Values=L;
    J.Selected_Players:SetValues();
end);

w:AddToggle("Spectate",{Text="Spectate",Default=false}):OnChanged(function(p)
    if not p then 
        workspace.Camera.CameraSubject=x.Character;
    end;
end);

task.spawn(function()
    repeat wait();
    until J.Spectate.Value;print("Toggled : Spectate");
    while true do wait();
        pcall(function()
            if J.Spectate.Value then 
                workspace.Camera.CameraSubject=game:GetService("Players")[tostring(J.Selected_Players.Value)].Character;
            end;
        end);
    end;
end);
pcall(function()
    getgenv().ESP=loadstring(game:HttpGet("https://androssy.net/TrashXenon/ESP.lua"))();
end);
w:AddToggle("ESP Players",{Text="ESP Players",Default=false}):OnChanged(function(N)
    getgenv().ESP:Toggle(N);
end);

w:AddToggle("Auto_Farm_Players",{Text="Auto Farm Players",Default=false});
w:AddToggle("FE_Kick",{Text="FE Kick",Default=false});
w:AddToggle("Teleport",{Text="Teleport",Default=false});
w:AddButton("Servers Hop",function()
    getgenv().Teleport();
end);
task.spawn(function()
    while true do wait();
    if J.Teleport.Value then 
        if x:FindFirstChild("SecurityBypass")then 
            pcall(function()
                if game.Players[tostring(J.Selected_Players.Value)].Character:FindFirstChild("HumanoidRootPart")then 
                    x.Character.HumanoidRootPart.CFrame=game.Players[tostring(J.Selected_Players.Value)].Character:FindFirstChild("HumanoidRootPart").CFrame*CFrame.new(0,0,3);else x.Character.HumanoidRootPart.CFrame=CFrame.new(game.Players[tostring(J.Selected_Players.Value)].LastPosition.Value);
                    end;
                end);
            end;
        end;
    end;
end);
task.spawn(function()
    while true do wait();
        if J.Auto_Farm_Players.Value then 
            if x:FindFirstChild("SecurityBypass")then 
                pcall(function()
                    if game.Players[tostring(J.Selected_Players.Value)]then 
                        local G=game.Players[tostring(J.Selected_Players.Value)];
                        if game.Players[tostring(J.Selected_Players.Value)].Character:FindFirstChild("HumanoidRootPart")then 
                            if not G.Character:FindFirstChild("Down")then 
                                if not G.Character:FindFirstChild("Block")then 
                                    task.spawn(function()x.Character.HumanoidRootPart.CFrame=G.Character.HumanoidRootPart.CFrame*CFrame.new(0,0,-3);
                                        x.Character.HumanoidRootPart.CFrame=x.Character.HumanoidRootPart.CFrame*CFrame.Angles(0,math.rad(180),0);
                                        getgenv().Skill();
                                        pcall(function()
                                            W.Async:FireServer("Katana","Server");
                                        end);
                                        pcall(function()
                                            W.Async:FireServer("Combat","Server");
                                        end);
                                    end);
                                else if x:FindFirstChild("SecurityBypass")then 
                                    x.Character.HumanoidRootPart.CFrame=G.Character.PrimaryPart.CFrame*CFrame.new(0,0,-5);
                                    x.Character.HumanoidRootPart.CFrame=x.Character.HumanoidRootPart.CFrame*CFrame.Angles(0,math.rad(180),0);
                                end;
                                if not G:FindFirstChild("Stun")then 
                                    W.Async:FireServer("Katana","Heavy");
                                    W.Async:FireServer("Combat","Heavy");
                                end;
                            end;
                        else if not G.Character:FindFirstChild("Carryed")then 
                            x.Character.HumanoidRootPart.CFrame=G.Character.HumanoidRootPart.CFrame;
                            wait();
                            game:GetService("VirtualInputManager"):SendKeyEvent(true,"V",false,x.Character.HumanoidRootPart);
                        end;
                    end;
                else x.Character.HumanoidRootPart.CFrame=CFrame.new(game.Players[tostring(J.Selected_Players.Value)].LastPosition.Value);
                end;
            end;
        end);
    end;
end;
end;
end);
task.spawn(function()
    while true do wait();
        if J.FE_Kick.Value then 
            if x:FindFirstChild("SecurityBypass")then 
                pcall(function()
                    workspace.CurrentCamera.CameraType=Enum.CameraType.Custom;
                    if game.Players[tostring(J.Selected_Players.Value)]then 
                        local r=game.Players[tostring(J.Selected_Players.Value)];
                        if game.Players[tostring(J.Selected_Players.Value)].Character:FindFirstChild("HumanoidRootPart")then 
                            if not r.Character:FindFirstChild("Down")then 
                                workspace.CurrentCamera.CameraType=Enum.CameraType.Custom;
                                if not r.Character:FindFirstChild("Block")then 
                                    task.spawn(function()
                                        x.Character.HumanoidRootPart.CFrame=r.Character.HumanoidRootPart.CFrame*CFrame.new(0,0,-3);
                                        x.Character.HumanoidRootPart.CFrame=x.Character.HumanoidRootPart.CFrame*CFrame.Angles(0,math.rad(180),0);
                                        getgenv().Skill();
                                        pcall(function()
                                            W.Async:FireServer("Katana","Server");
                                        end);
                                        pcall(function()
                                            W.Async:FireServer("Combat","Server");
                                        end);
                                    end);
                                else if x:FindFirstChild("SecurityBypass")then 
                                    x.Character.HumanoidRootPart.CFrame=r.Character.PrimaryPart.CFrame*CFrame.new(0,0,-5);
                                    x.Character.HumanoidRootPart.CFrame=x.Character.HumanoidRootPart.CFrame*CFrame.Angles(0,math.rad(180),0);
                                end;
                                if not r:FindFirstChild("Stun")then 
                                    W.Async:FireServer("Katana","Heavy");
                                    W.Async:FireServer("Combat","Heavy");
                                end;
                            end;
                        else if not r.Character:FindFirstChild("Carryed")then 
                            x.Character.HumanoidRootPart.CFrame=r.Character.HumanoidRootPart.CFrame;
                            wait(0.3);
                            game:GetService("VirtualInputManager"):SendKeyEvent(true,"V",false,x.Character.HumanoidRootPart);
                            wait(1);
                        else for E,Z in pairs(All_Zones2)do if x:FindFirstChild("SecurityBypass")then 
                            if J.FE_Kick.Value then 
                                workspace.CurrentCamera.CameraType=Enum.CameraType.Fixed;
                                x.Character.HumanoidRootPart.CFrame=CFrame.new(Z);
                            end;
                        end;
                        wait(0.1);
                    end;
                end;
            end;
        else x.Character.HumanoidRootPart.CFrame=CFrame.new(game.Players[tostring(J.Selected_Players.Value)].LastPosition.Value);
        end;
    end;
end);
end;
end;
end;
end);

local C=k:AddLeftGroupbox("Trinket Farm");
C:AddToggle("Auto_Trinkets",{Text="Auto Trinkets",Default=false});
C:AddToggle("Auto_Sell_Trinkets",{Text="Auto Sell Trinkets",Default=false});
local b=k:AddRightGroupbox("Settings");local R={"One","Two","Three","Four","Five","Six","Seven"};
b:AddDropdown("Selected_Skill",{Text="Select Skill & Numbers",Multi=true,Values=R});
b:AddToggle("Auto_Perfect_Block",{Text="Auto Perfect Block",Default=false});
task.spawn(function()
    while true do task.wait(0.1);
    if J.Auto_Perfect_Block.Value and not J.Auto_Farm_Level.Value then 
        game:GetService("ReplicatedStorage").Remotes.Async:FireServer("Combat","Block",true);
        game:GetService("ReplicatedStorage").Remotes.Async:FireServer("Combat","Block",false);
    end;
end;
end);

b:AddToggle("Breathing",{Text="Breathing",Default=false});
task.spawn(function()
    while true do wait(1);
        pcall(function()
            if J.Breathing.Value then 
                if not x.Character:FindFirstChild("Breath")then
                     game.ReplicatedStorage.Remotes.Async:FireServer("Character","Breath",true);
                    else if x.Character:FindFirstChild("Slow")then x.Character:FindFirstChild("Slow"):Remove();
                    end;
                    if x.Character:FindFirstChild("Busy")then 
                        x.Character:FindFirstChild("Busy"):Remove();
                    end;
                end;
            end;
        end);
    end;
end);

b:AddToggle("Collect_Drops",{Text="Collect Drops",Default=false});
b:AddToggle("Collect_Ores",{Text="Collect Ores",Default=false});

local d={
    ["Rock15"]=Vector3.new(1480.390380859375,1148.2445068359375,-1193.4259033203125),
    ["Rock16"]=Vector3.new(-3759.53857421875,764.1908569335938,1008.9010620117188),
    ["Rock20"]=Vector3.new(1757.8377685546875,1102.6883544921875,-1426.4979248046875),
    ["Rock11"]=Vector3.new(-2089.637939453125,776.140869140625,-3942.89697265625),
    ["Rock13"]=Vector3.new(1242.654541015625,962.811279296875,-445.3817138671875),
    ["Rock7"]=Vector3.new(-1961.4710693359375,809.5393676757812,-2688.359619140625),
    ["Rock6"]=Vector3.new(-2406.611083984375,1000.9754638671875,-2354.830322265625),
    ["Rock5"]=Vector3.new(-1667.5611572265625,991.7250366210938,-2104.93017578125),
    ["Rock8"]=Vector3.new(-1676.3616943359375,871.1751708984375,-3183.630126953125),
    ["Rock4"]=Vector3.new(-2066.761474609375,775.3751220703125,-2114.23046875),
    ["Rock18"]=Vector3.new(-3500.30810546875,767.2711791992188,983.8624877929688),
    ["Rock14"]=Vector3.new(-4269.99072265625,735.1410522460938,1064.7510986328125),
    ["Rock12"]=Vector3.new(1202.9892578125,941.4750366210938,-1442.23095703125),
    ["Rock17"]=Vector3.new(-3493.602294921875,772.50048828125,958.18017578125),
    ["Rock19"]=Vector3.new(1657.4833984375,1207.7100830078125,-968.6232299804688),
    ["Rock10"]=Vector3.new(-2166.738037109375,804.990966796875,-4043.6474609375),
    ["Rock3"]=Vector3.new(-2047.890380859375,1031.353515625,-1589.87109375),
    ["Rock9"]=Vector3.new(-2275.089111328125,804.990966796875,-3862.3974609375),
    ["Rock2"]=Vector3.new(-1734.08544921875,991.498291015625,-1695.965087890625)
};

getgenv().getOres=function()
    for P,N in pairs(workspace.Map.Minerals:GetChildren())do 
        if N:IsA("MeshPart")and N:FindFirstChild("Mineral")then 
            if N:FindFirstChild("Mineral"):FindFirstChild("Spawn")then 
                return N:FindFirstChild("Mineral");
            end;
        end;
    end;
    return nil;
end;
task.spawn(function()
    while true do wait();
        if J.Collect_Ores.Value then 
            local P=getOres();
            if P~=nil then 
                pcall(function()
                    if x:FindFirstChild("SecurityBypass")then 
                        x.Character.HumanoidRootPart.CFrame=P.CFrame;
                    end;
                    game:GetService("ReplicatedStorage").Remotes.Sync:InvokeServer("Pickaxe","Server");
                end);
            else for G,N in pairs(d)do 
                if getOres()==nil then 
                x.Character.HumanoidRootPart.CFrame=CFrame.new(N);
            end;
            wait(0.3);
        end;
    end;
end;
end;
end);

b:AddToggle("Unlock_Mouse",{Text="Unlock Mouse",Default=true}):OnChanged(function(r)
    game:GetService("UserInputService").MouseIconEnabled=r;
    game:GetService("UserInputService").MouseBehavior=Enum.MouseBehavior.Default;
end);
pcall(function()
    game:GetService("UserInputService").MouseIconEnabled=J.Unlock_Mouse.Value;
    game:GetService("UserInputService").MouseBehavior=Enum.MouseBehavior.Default;
end);
b:AddToggle("Unlock_ChatLogs",{Text="Unlock ChatLogs",Default=false}):OnChanged(function(r)
    game:GetService("Players").LocalPlayer.PlayerGui.Chat.Frame.Visible=r;
    game:GetService("Players").LocalPlayer.PlayerGui.Chat.Frame.ChatChannelParentFrame.Visible=r;
end);
pcall(function()
    game:GetService("Players").LocalPlayer.PlayerGui.Chat.Frame.Visible=J.Unlock_ChatLogs.Value;
    game:GetService("Players").LocalPlayer.PlayerGui.Chat.Frame.ChatChannelParentFrame.Visible=J.Unlock_ChatLogs.Value;
end);
b:AddToggle("WalkSpeed",{Text="WalkSpeed",Default=false});
task.spawn(function()
    while true do wait();
        pcall(function()
            if not game.Players.LocalPlayer.Character:FindFirstChild("W")then 
                game.Players.LocalPlayer.Character.Humanoid.Changed:connect(function()
                    if J.WalkSpeed.Value then 
                        pcall(function()
                            game.Players.LocalPlayer.Character.Humanoid.WalkSpeed=100;
                        end);
                    end;
                end);
                local r=Instance.new("Part",game.Players.LocalPlayer.Character);
                r.Name="W";
                wait(0.1);
            end;
        end);
    end;
end);

b:AddToggle("No_Cooldown_God_Modes",{Text="No Cooldown & God Modes",Default=false});
function test()
    for Z,N in pairs(x.Character:GetChildren())do 
        if N.Name=="Combat"then 
            N:Remove();
        end;
        if N.Name=="Executing"then 
            N:Remove();
        end;
        if N.Name=="Slow"then 
            N:Remove();
        end;
        if N.Name=="Stun"then 
            N:Remove();
        end;
        if N.Name=="Damaged"then 
            N:Remove();
        end;
        if N.Name:find("cd")then 
            N:Remove();
        end;
        if N.Name:find("DashCooldown")then 
            N:Remove();
        end;
        if N.Name:find("Cooldown")then 
            N:Remove();
        end;
        if N.Name=="Attacking"then 
            N:Remove();
        end;
        if N.Name=="Busy"then 
            N:Remove();
        end;
        if N.Name=="TryTo"then 
            N:Remove();
        end;
        if N.Name=="BuringTimer"then 
            N:Remove();
        end;
        if N.Name=="AttackAnnounce"then 
            N:Remove();
        end;
        if N.Name=="HeavyAnnounce"then 
            N:Remove();
        end;
        if N.Name=="DoubleJumpCooldown"then 
            N:Remove();
        end;
        if N.Name=="Executing"then 
            N:Remove();
        end;
        if N.Name=="Down"then 
            N:Remove();
        end;
        if N.Name=="Ragdoll"then 
            N:Remove();
        end;
        if N.Name=="SequenceFactor"then 
            N:Remove();
        end;
        if N.Name=="Sequence"then 
            N:Remove();
        end;
        if N.Name=="CanDie"then 
            N:Remove();
        end;
        if N.Name=="PerfectBlock"then 
            N:Remove();
        end;
        if N.Name=="RecentBlock"then 
            N:Remove();
        end;
    end;
end;
spawn(function()
    while true do task.wait();
        pcall(function()
            if J.No_Cooldown_God_Modes.Value then 
                test();
            end;
        end);
    end;
end);

local S=k:AddRightTabbox();
local z=S:AddTab("NPCs");
All_NPCs={};
for p,Z in pairs(workspace.Npcs:GetChildren())do 
    if Z:IsA("Model")and Z:FindFirstChild("NPC")and Z:FindFirstChild("HumanoidRootPart")and not table.find(All_NPCs,Z.Name)then
        table.insert(All_NPCs,Z.Name);
    end;
end;

z:AddDropdown("Selected_NPCs",{Text="Select NPCs",Default=1,Values=All_NPCs});
z:AddToggle("Teleport_NPCs",{Text="Teleport",Default=false});
task.spawn(function()
    while true do wait(5);
        for I in pairs(All_NPCs)do 
            All_NPCs[I]=nil;
        end;
        for I,N in pairs(workspace.Npcs:GetChildren())do 
            if N:IsA("Model")and N:FindFirstChild("NPC")and N:FindFirstChild("HumanoidRootPart")and not table.find(All_NPCs,N.Name)then 
                table.insert(All_NPCs,N.Name);
            end;
        end;
        J.Selected_NPCs.Values=All_NPCs;
        J.Selected_NPCs:SetValues();
    end;
end);
task.spawn(function()
    while true do wait();
        if J.Teleport_NPCs.Value then 
            pcall(function()
                if x:FindFirstChild("SecurityBypass")then 
                    x.Character:FindFirstChild("HumanoidRootPart").CFrame=workspace.Npcs:FindFirstChild(J.Selected_NPCs.Value).PrimaryPart.CFrame*CFrame.new(0,0,-4);
                end;
            end);
        end;
    end;
end);
All_Zones={
["Cavern"]=Vector3.new(-2223.955810546875,783.0618286132812,-3904.94482421875),
["Slayer Corps"]=Vector3.new(-1556,872,-6362),
["Sun Mansion"]=Vector3.new(-4819.1220703125,885.63916015625,-4831.20751953125),
["Mountain"]=Vector3.new(-2167.412353515625,965.3818969726562,-3992.35009765625),
["Cavern Passage"]=Vector3.new(-2183.569091796875,1143.1932373046875,-1903.34765625),
["Frosty Forest"]=Vector3.new(929.4169311523438,1093.697265625,-6641.41748046875),
["Sakura Passage"]=Vector3.new(-2390.013671875,738.3121337890625,-3229.83984375),
["Frosty Cavern"]=Vector3.new(-2271.674560546875,954.1795654296875,-2592.3427734375),
["Home"]=Vector3.new(3097.290771484375,844.10888671875,-964.8120727539062),
["Kamakura Village"]=Vector3.new(-2387.177734375,1151.0936279296875,-1715.179443359375),
["Corps Grove"]=Vector3.new(-4976.29638671875,775.848876953125,-6562.04248046875),
["Okuyia Plains"]=Vector3.new(-4116.009765625,874.843994140625,292.89849853515625),
["The White Peak"]=Vector3.new(1391.6268310546875,1058.7581787109375,-640.4218139648438),
["Fall's Bridge"]=Vector3.new(-1816.0404052734375,803.2840576171875,-387.60101318359375),
["Okuyia Cavern"]=Vector3.new(-4224.09033203125,862.98388671875,952.9228515625),
["Crystal Underground"]=Vector3.new(-2606.737060546875,856.9888916015625,1314.547607421875),
["Infinity Castle"]=Vector3.new(2042.228515625,1588.5452880859375,-7280.9853515625),
["Kurohitsugi"]=Vector3.new(-3323.55029296875,326.0249938964844,-1063.375),
["White Underground"]=Vector3.new(1514.102294921875,1180.1484375,-1376.38916015625),
["Okuyia Village"]=Vector3.new(-3466.723388671875,769.1138916015625,-1300.3853759765625),
["Demon Purgatory"]=Vector3.new(2457.0859375,1171.5732421875,-7421.57177734375),
["Waterfall Cavern"]=Vector3.new(-2006.6116943359375,1013.1083984375,-1617.4810791015625),
["Hayakawa Village"]=Vector3.new(639.3189697265625,753.4089965820312,-2165.29296875),
["Selection Exam"]=Vector3.new(-5523.87548828125,764.043701171875,-3438.81494140625),
["White Passage"]=Vector3.new(1192.776123046875,967.9183349609375,-1445.92236328125),
["Demon Camp"]=Vector3.new(-748.1751098632812,710.2323608398438,-1526.811279296875),
["Arena"]=Vector3.new(-14760.529296875,2234.05712890625,-9712.017578125),
["Demon Hideout"]=Vector3.new(-4314.1484375,862.98388671875,580.3045043945312),
["Coast Forest"]=Vector3.new(417.4654541015625,753.408935546875,-148.78143310546875)
};

All_Zone_Name={};
for p,r in pairs(All_Zones)do 
    table.insert(All_Zone_Name,p);
end;
local z=S:AddTab("Zone");
z:AddDropdown("Selected_Zone",{Text="Select Zone",Values=All_Zone_Name,Default=1});
z:AddToggle("Teleport_Zone",{Text="Teleport",Default=false});
task.spawn(function()
    while true do wait();
        if J.Teleport_Zone.Value then 
            pcall(function()
                if x:FindFirstChild("SecurityBypass")then 
                    x.Character:FindFirstChild("HumanoidRootPart").CFrame=CFrame.new(All_Zones[tostring(J.Selected_Zone.Value)])*CFrame.new(0,50,0);
                end;
            end);
        end;
    end;
end);

All_Village={
    ["Hayakawa Village"]=Vector3.new(498,755,-1961),
    ["Okuyia Village"]=Vector3.new(-3200,704,-1161),
    ["Slayers Corps"]=Vector3.new(-1556,872,-6362),
    ["Kamakura Village"]=Vector3.new(-2146,1162,-1687)
};
All_Village_Name={};
for N,I in pairs(All_Village)do 
    table.insert(All_Village_Name,N);
end;
local z=S:AddTab("Village");
z:AddDropdown("Select_Village",{Text="Select Village",Values=All_Village_Name,Default=1});
z:AddToggle("Teleport_Village",{Text="Teleport",Default=false});
task.spawn(function()
    while true do wait();
        if J.Teleport_Village.Value then 
            pcall(function()
                if x:FindFirstChild("SecurityBypass")then 
                    x.Character:FindFirstChild("HumanoidRootPart").CFrame=CFrame.new(All_Village[tostring(J.Select_Village.Value)]);
                end;
            end);
        end;
    end;
end);

local h=k:AddRightGroupbox("Character");

h:AddToggle("No_Sun_Damage",{Text="No Sun Damage",Default=true});

h:AddToggle("No_Fall_Damage",{Text="No Fall Damage",Default=true});

task.spawn(function()
    LPH_JIT_ULTRA(function()
        local I;
        I=hookmetamethod(game,"__namecall",function(...)
            local p,E=(...),({select(2,...)});
            if J.No_Sun_Damage.Value or J.No_Fall_Damage.Value then 
                if tostring(p)=="Async"and tostring(E[1])=="Character"then 
                    if tostring(E[2])=="DemonWeakness"and J.No_Sun_Damage.Value then 
                        return wait(9.0E9);
                    end;
                    if tostring(E[2])=="FallDamageServer"and J.No_Fall_Damage.Value then 
                            return wait(9.0E9);
                        end;
                    end;
                end;
                return I(...);
            end);
        end)();
    end);
    
    local V=o:AddTab("Settings");
    local t=V:AddLeftGroupbox("Menu");
    local c=V:AddRightGroupbox("Config");
    local j=V:AddLeftGroupbox("Auto-Load");
    local K=V:AddRightGroupbox("Misc");
    t:AddLabel("Background Color"):AddColorPicker("SettingsMenuBackgroundColor",{Default=O.BackgroundColor});
    t:AddLabel("Main Color"):AddColorPicker("SettingsMenuMainColor",{Default=O.MainColor});
    t:AddLabel("Accent Color"):AddColorPicker("SettingsMenuAccentColor",{Default=O.AccentColor});
    t:AddLabel("Inline Color"):AddColorPicker("SettingsMenuInlineColor",{Default=O.InlineColor});
    t:AddLabel("Outline Color"):AddColorPicker("SettingsMenuOutlineColor",{Default=O.OutlineColor});
    t:AddLabel("Font Color"):AddColorPicker("SettingsMenuFontColor",{Default=O.FontColor});
    t:AddButton("Default Theme",SetDefault);t:AddToggle("SettingsMenuKeybinds",{Text="Show Keybinds Menu"}):OnChanged(function(G)
        O.KeybindFrame.Visible=G;
    end);
    t:AddToggle("SettingsMenuWatermark",{Text="Show Watermark",Default=true}):OnChanged(function(N)
        O:SetWatermarkVisibility(N);
    end);
    t:AddButton("Unload",function()
        O:Unload();
    end);
    c:AddInput("SettingsConfigName",{Text="Config Name",Default="",Placeholder="Name"});
    c:AddButton("Create Config",function()
        CreateConfig(J.SettingsConfigName.Value);
    end);
    c:AddDropdown("SettingsConfigConfigs",{Text="Configs",Default=1,Values=GetConfigNames()});
    c:AddButton("Load Config",function()u.Load.AutoLoad.LastUsedConfig=J.SettingsConfigConfigs.Value;
        LoadConfig(GetConfigByName(J.SettingsConfigConfigs.Value));
        O:Notify(("Config \"%s\" Has Been Loaded."):format(J.SettingsConfigConfigs.Value));
    end);
    c:AddButton("Save Config",function()
        SaveConfig(J.SettingsConfigConfigs.Value);
    end);
    c:AddButton("Delete Config",function()
        DeleteConfig(J.SettingsConfigConfigs.Value,true);
    end);
    c:AddInput("SettingsConfigData",{Text="Config Data",Default="",Placeholder="Data"});
    c:AddButton("Export Data",ExportData);
    c:AddButton("Import Data",ImportData);
    j:AddToggle("SettingsAutoLoadEnabled",{Text="Enabled",Default=true}):OnChanged(function(E)
        u.Load.AutoLoad.Enabled=E;
    end);
    j:AddToggle("SettingsAutoLoadRage",{Text="Rage Settings"}):OnChanged(function(G)
        u.Load.AutoLoad.RageSettings=G;
    end);
    j:AddToggle("SettingsAutoLoadSilent",{Text="Silent Load"}):OnChanged(function(p)
        u.Load.AutoLoad.SilentLoad=p;
    end);
    j:AddDropdown("SettingsAutoLoadType",{Text="Type",Default=2,Values={"Last Used Config","Last Config","Custom Config"}}):OnChanged(function(r)
        u.Load.AutoLoad.AutoLoadType=r;
    end);
    j:AddDropdown("SettingsAutoLoadConfig",{Text="Custom Config",Default=1,Values=GetConfigNames()}):OnChanged(function(E)
        u.Load.AutoLoad.CustomConfig=E;
    end);
    K:AddToggle("SettingsMiscNotifications",{Text="Show Notifications",Default=true}):OnChanged(function(Z)
        O.NotificationArea.Visible=Z;
    end);
    K:AddButton("Reset All Settings",ResetSettings);
    SetDefault();
    J.SettingsMenuBackgroundColor:OnChanged(UpdateTheme);
    J.SettingsMenuMainColor:OnChanged(UpdateTheme);
    J.SettingsMenuAccentColor:OnChanged(UpdateTheme);
    J.SettingsMenuInlineColor:OnChanged(UpdateTheme);
    J.SettingsMenuOutlineColor:OnChanged(UpdateTheme);
    J.SettingsMenuFontColor:OnChanged(UpdateTheme);
    k:ShowTab();
    O.SaveManager:Load();
    task.spawn(function()
        while(task.wait(1)and O and O.SaveManager)do 
            O.SaveManager:SaveFile();
        end;
    end);
    _G.Current_Time="N/A";O:SetWatermark(("Xenon Hub Premium Scripts | %s"):format(_G.Current_Time));
    task.spawn(function()
        while true do wait();
            pcall(function()
                local P=math.floor(workspace.DistributedGameTime);
                local N=math.floor(workspace.DistributedGameTime/60);
                local Z=math.floor(workspace.DistributedGameTime/60/60);
                local P=P-(N*60);
                local N=N-(Z*60);
                if Z<1 then 
                    if N<1 then 
                        _G.Current_Time=P.." Second(s)";
                    else _G.Current_Time=N.." Minute(s), "..P.." Second(s)";
                    end;
                else _G.Current_Time=Z.." Hour(s), "..N.." Minute(s), "..P.." Second(s)";
                end;
                O:SetWatermark(("Xenon Hub Premium Scripts | %s"):format(_G.Current_Time));
            end);
        end;
    end);
    
    O:Notify("User Interface Finished Loading.");
    local D=math.floor(((tick()-u.Tick)*1000)*10)/10;
    O:Notify(("Loading Time : %sms."):format(D));
    task.spawn(function()
        while true do 
            if J.Auto_Farm_Level.Value or J.Auto_Trinkets.Value or J.Collect_Ores.Value or J.Teleport_Zone.Value or J.Teleport_Village.Value or J.Teleport_NPCs.Value or J.Auto_Farm_Players.Value or J.FE_Kick.Value or J.Auto_Sell_Trinkets.Value or J.Teleport.Value then 
                if not x:FindFirstChild("SecurityBypass")then 
                    pcall(function()
                        if x.Character~=nil and not x:FindFirstChild("SpawnCooldown")and x.Character.Humanoid~=nil and tonumber(x.Character.Humanoid.Health)~=0 and not x:FindFirstChild("Executed")and not x.PlayerGui:FindFirstChild("LoadingScreen")then 
                            if not x:FindFirstChild("SecurityBypass")then 
                                getrenv()._G.Player.new().SpawnCharacter();
                            end;
                            wait(1);
                        end;
                    end);
                end;
            end;
            wait(1);
        end;
    end);
    getgenv().Skill=function()
        task.spawn(function()
            pcall(function()
                if x.Character:FindFirstChild("Breath")then 
                    if J.Selected_Skill.Value["One"]then 
                        game:GetService("VirtualInputManager"):SendKeyEvent(true,"One",false,x.Character.HumanoidRootPart);
                    end;
                    if J.Selected_Skill.Value["Two"]then 
                        game:GetService("VirtualInputManager"):SendKeyEvent(true,"Two",false,x.Character.HumanoidRootPart);
                    end;
                    if J.Selected_Skill.Value["Three"]then 
                        game:GetService("VirtualInputManager"):SendKeyEvent(true,"Three",false,x.Character.HumanoidRootPart);
                    end;
                    if J.Selected_Skill.Value["Four"]then 
                        game:GetService("VirtualInputManager"):SendKeyEvent(true,"Four",false,x.Character.HumanoidRootPart);
                    end;
                    if J.Selected_Skill.Value["Five"]then 
                        game:GetService("VirtualInputManager"):SendKeyEvent(true,"Five",false,x.Character.HumanoidRootPart);
                    end;
                    if J.Selected_Skill.Value["Six"]then 
                        game:GetService("VirtualInputManager"):SendKeyEvent(true,"Six",false,x.Character.HumanoidRootPart);
                    end;
                    if J.Selected_Skill.Value["Seven"]then 
                        game:GetService("VirtualInputManager"):SendKeyEvent(true,"Seven",false,x.Character.HumanoidRootPart);
                    end;
                end;
            end);
        end);
    end;
    
    getgenv().getMobs=function()
        local p=nil;
        local r=math.huge;
        if x.Character and x.Character:FindFirstChild("HumanoidRootPart")then 
            if workspace:FindFirstChildOfClass("Model")and workspace:FindFirstChildOfClass("Model"):FindFirstChild("Down")then 
                local P=workspace:FindFirstChildOfClass("Model"):FindFirstChild("Down").Parent;
                if not P:FindFirstChild("Executed")then 
                    return P;
                end;
            end;
            for G,E in pairs(workspace:GetChildren())do 
                if J.Selected_Mobs.Value[tostring(E.Name)]and E:FindFirstChild("Humanoid")and E:FindFirstChild("HumanoidRootPart")and E:FindFirstChild("Down")and E:FindFirstChild("Health")then 
                    local N=x:DistanceFromCharacter(E:FindFirstChild("HumanoidRootPart").Position);
                    if tonumber(N)<r then 
                        p=E;
                        r=N;
                    end;
                end;
                if J.Selected_Mobs.Value[tostring(E.Name)]and E:FindFirstChild("Humanoid")and E:FindFirstChild("HumanoidRootPart")and E:FindFirstChild("Health")then 
                    local I=x:DistanceFromCharacter(E:FindFirstChild("HumanoidRootPart").Position);
                    if tonumber(I)<r then 
                        p=E;
                        r=I;
                    end;
                end;
            end;
        end;
        return p;
    end;
    getgenv().closestT=function()
        local G=nil;
        local P=math.huge;
        for p,r in pairs(workspace:GetChildren())do 
            if r:IsA("Model")and r.PrimaryPart~=nil and r:FindFirstChild("PickableItem")then 
                local E=x:DistanceFromCharacter(r.PrimaryPart.Position);
                if tonumber(E)<P then 
                    G=r;
                    P=E;
                end;
            end;
        end;
    return G;
end;
getgenv().closestTT=function()
    local N=nil;
    local Z=math.huge;
    for I,P in pairs(workspace.Trinkets:GetChildren())do 
        if P:FindFirstChild("Spawned")then 
            local G=x:DistanceFromCharacter(P.Position);
            if tonumber(G)<Z then 
                N=P;
                Z=G;
            end;
        end;
    end;
    return N;
end;
getgenv().closestDrop=function()
    local I=nil;
    local N=math.huge;
    for Z,E in pairs(workspace:GetChildren())do 
        if E.Name=="DropItem"then 
            local G=x:DistanceFromCharacter(E.Position);
            if tonumber(G)<N then 
                I=E;
                N=G;
            end;
        end;
    end;
    return I;
end;
task.spawn(function()
    while true do wait(1);
        pcall(function()
            if J.Auto_Trinkets.Value then 
                if x:FindFirstChild("SecurityBypass")then 
                    local r=closestTT();
                    if x:FindFirstChild("SecurityBypass")then 
                        x.Character.HumanoidRootPart.CFrame=r.CFrame;
                    end;
                    wait(1.5);
                    local G=closestT();
                    if x:DistanceFromCharacter(G.PrimaryPart.Position)<10 then 
                        game:GetService("VirtualInputManager"):SendKeyEvent(true,"E",false,x.Character.HumanoidRootPart);
                        W.Async:FireServer("Character","Interaction",G.PrimaryPart);
                    end;
                end;
            end;
        end);
    end;
end);
task.spawn(function()
    while true do wait(1);
        if J.Auto_Sell_Trinkets.Value then 
            pcall(function()
                if x:FindFirstChild("SecurityBypass")then 
                    x.Character.HumanoidRootPart.CFrame=CFrame.new(826,750,-2249);
                end;
                if x:FindFirstChild("SecurityBypass")then 
                    task.wait(1);
                    W.Sync:InvokeServer("Dialogue","Talk");
                    W.Sync:InvokeServer("Dialogue","Prompt",workspace.Npcs.Merchant);
                    Sell=nil;
                    for p,Z in pairs(x.Character.Answers:GetChildren())do 
                        if Z.Value=="I want to sell all my trinkets"then 
                            Sell=Z;
                        end;
                    end;
                    W.Sync:InvokeServer("Dialogue","Answer",Sell,"Merchant");
                    W.Sync:InvokeServer('Dialogue','Untalk');
                    for r,P in pairs(x.Character:GetChildren())do 
                        if P.Name=="Prompt"and P.Value==nil then 
                            P:Destroy();
                        end;
                    end;
                end;
            end);
        end;
    end;
end);
task.spawn(function()
    while true do wait();
        if J.Auto_Farm_Level.Value then 
            pcall(function()
                n=true;
                for E,r in pairs(workspace:GetChildren())do 
                    if J.Selected_Mobs.Value[tostring(r.Name)]and r:FindFirstChild("Humanoid")and r:FindFirstChild("HumanoidRootPart")and r:FindFirstChild("Health")then 
                        n=false;
                    end;
                end;
                if n==true then 
                    if J.Auto_Farm_Level_Hop.Value then 
                        getgenv().Teleport();
                    end;
                end;
                Drops=getgenv().closestDrop();
                if Drops~=nil and J.Collect_Drops.Value then 
                    if x:FindFirstChild("SecurityBypass")then 
                        x.Character.HumanoidRootPart.CFrame=Drops.CFrame;
                        wait(1);
                        if x:DistanceFromCharacter(Drops.Position)<10 then 
                            W.Async:FireServer("Character","Interaction",Drops);
                        end;
                    end;
                else v=getgenv().getMobs();
                    if v~=nil then 
                        if v:FindFirstChild("HumanoidRootPart")then 
                        if x:DistanceFromCharacter(v:FindFirstChild("HumanoidRootPart").Position)<=150 then 
                            v:WaitForChild("Humanoid").PlatformStand=true;if not v:FindFirstChild("Down")then 
                                if not v:FindFirstChild("Block")then 
                                    task.spawn(function()
                                        x.Character.HumanoidRootPart.CFrame=v.HumanoidRootPart.CFrame*CFrame.new(0,0,3);
                                        getgenv().Skill();
                                        pcall(function()
                                            W.Async:FireServer("Katana","EquippedEvents",true,true);
                                        end);
                                        pcall(function()
                                            W.Async:FireServer("Katana","Server");
                                        end);
                                        pcall(function()
                                            W.Async:FireServer("Combat","Server");
                                        end);
                                    end);
                                else if x:FindFirstChild("SecurityBypass")then 
                                    x.Character.HumanoidRootPart.CFrame=v.PrimaryPart.CFrame*CFrame.new(0,0,5);
                                end;
                                if not v:FindFirstChild("Stun")then 
                                    W.Async:FireServer("Katana","Heavy");
                                    W.Async:FireServer("Combat","Heavy");
                                end;
                            end;
                        else if not v:FindFirstChild("Executed")then 
                            if x:FindFirstChild("SecurityBypass")then 
                                if x.Character:FindFirstChild("OnExecute")then 
                                    x.Character.HumanoidRootPart.CFrame=v.PrimaryPart.CFrame*CFrame.new(0,30,0);
                                else x.Character.HumanoidRootPart.CFrame=v.PrimaryPart.CFrame;
                                    wait();
                                    W.Sync:InvokeServer("Character","Execute");
                                end;
                            end;
                        end;
                    end;
                else x.Character.HumanoidRootPart.CFrame=v.HumanoidRootPart.CFrame*CFrame.new(20,30,20);
                    wait(1);
                end;
            end;
        else for G,I in pairs(All_Zones2)do 
            if x:FindFirstChild("SecurityBypass")then 
                if getgenv().getMobs()==nil then 
                    if J.Auto_Farm_Level.Value then 
                        x.Character.HumanoidRootPart.CFrame=CFrame.new(I);
                    end;
                end;
                wait(1);
            end;
        end;
    end;
end;
end);
end;
end;
end);
setfflag("HumanoidParallelRemoveNoPhysics","False");
setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2","False");
task.spawn(function()
    while true do wait();
        pcall(function()
            local Z=x.Character or x.CharacterAdded:Wait();
            if J.Auto_Farm_Level.Value or J.Auto_Trinkets.Value or J.FE_Kick.Value or J.Auto_Sell_Trinkets.Value or J.Teleport_Zone.Value or J.Teleport_NPCs.Value or J.Teleport_Village.Value or J.Auto_Farm_Players.Value or J.Teleport.Value or J.Collect_Ores.Value then 
                pcall(function()
                    x.Character.Humanoid.Sit=false;
                end);
                pcall(function()
                    if not x.Character.HumanoidRootPart:FindFirstChild("BV")then 
                        local G=Instance.new("BodyVelocity");
                        G.Parent=x.Character.HumanoidRootPart;
                        G.Name="BV";
                        G.MaxForce=Vector3.new(100000,100000,100000);
                        G.Velocity=Vector3.new(0,0,0);
                    end;
                end);
            else pcall(function()
                if x.Character.HumanoidRootPart:FindFirstChild("BV")then 
                    x.Character.HumanoidRootPart:FindFirstChild("BV"):Remove();
                end;
            end);
        end;
    end);
end;
end);
task.spawn(function()
    while true do wait();
        pcall(function()
            if J.Auto_Farm_Level.Value then 
                v=getgenv().getMobs();
                if v~=nil then 
                    if v:FindFirstChild("Down")then 
                        M:ChangeText("Finishing "..tostring(v.Name));
                    else M:ChangeText("Killing "..tostring(v.Name).." | "..v:FindFirstChild("Health").Value.."/"..v:FindFirstChild("MaxHealth").Value);
                    end;
                else M:ChangeText("Looking For Mobs");
                end;
            else M:ChangeText("Status : N/A");
            end;
        end);
    end;
end);
task.spawn(function()
    while true do 
        pcall(function()
            i:ChangeText("CV : "..game:GetService("Stats").Network.ServerStatsItem["Data Ping"]:GetValueString());
        end);
        wait(10);
    end;
end);
task.spawn(function()
    wait(2);
    pcall(function()
        num=0;
        for I,p in pairs(x.PlayerGui.Interface.HUD.Hotbar.List:GetChildren())do 
            if p:IsA("ImageButton")and p.Visible and p:FindFirstChild("Icon")and tostring(p:FindFirstChild("Icon").Image)=="rbxassetid://6258362633"then 
                num=num+1;
            end;
        end;
        if num==9 then 
            getgenv().Teleport();
        end;
    end);
end);
end;
Y();
