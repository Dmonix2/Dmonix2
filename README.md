------------- Configs here -------------
GG=getgenv and getgenv()or _G or shared;
GG.LoopLoading = false; -- Toggle loop loading until no error


------------- Script -------------
srcName="https://raw.githubusercontent.com/Yumiara/CPP/refs/heads/main/Main.cpp";

------------- Don't  Change-------------
repeat ONERUN1, ONERUN2 = pcall(function() Iden=nil;pcall(function()Iden=identifyexecutor()end)GG=getgenv and getgenv()or _G or shared;GG.HttpsSer=game.GetService(game,'HttpService')function EnCodeJ(a)return GG.HttpsSer:JSONEncode(a)end;function DeCodeJ(a)return GG.HttpsSer:JSONDecode(a)end;if not isfolder("NeuronXS")then makefolder("NeuronXS")end;repeat task.wait(0.7)until isfolder("NeuronXS")GG.ALLVersion=readfile and isfile and(isfile("NeuronXSVersion.json")and readfile("NeuronXSVersion.json"))and DeCodeJ(readfile("NeuronXSVersion.json"))or{["MagicCity"]=true}APISource=isfile("NeuronXS/Main.lua")and readfile("NeuronXS/Main.lua")or nil;if GG.ALLVersion["Main"]==nil or tick()-tonumber(GG.ALLVersion["Main"])>=600 or GG.ALLVersion["Main"]==nil or not APISource or not isfile("NeuronXSVersion.json")then SourceXS=game.HttpGet(game,srcName)writefile("NeuronXS/Main.lua",SourceXS)GG.ALLVersion["Main"]=tostring(tick())ContentsXSV=EnCodeJ(GG.ALLVersion)writefile("NeuronXSVersion.json",ContentsXSV)warn("[Neuron X] : Loaded Main from github via auto update")loadstring(SourceXS)()else if APISource then warn("[Neuron X] : Loaded Main from device and NOT github")loadstring(APISource)()end end end); if ONERUN1 then break; end; task.wait(5); until not GG.LoopLoading;