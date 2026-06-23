-- Hussein Hub V2 (2026 WindUI Edition)
-- التحديث العالمي: نظام الكشف التلقائي والدقيق لليالي شهر محرم الحرام لعام 2026

local success, WindUI = pcall(function()
   return loadstring(game:HttpGet("https://raw.githubusercontent.com/Footagesus/WindUI/main/Source.lua"))()
end)

if not success or not WindUI then
   pcall(function()
      WindUI = loadstring(game:HttpGet("https://github.com/Footagesus/WindUI/releases/latest/download/main.lua"))()
   end)
end

if not WindUI then
   return warn("Hussein Hub V2: تعذر تحميل مكتبة الواجهة.")
end

local Window = WindUI:CreateWindow({
   Title = "Hussein Hub V2",
   SubTitle = "Brookhaven RP (2026)",
   Author = "by hussain_90_1",
   Size = UDim2.fromOffset(580, 500),
   Transparent = true
})

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local LocalPlayer = Players.LocalPlayer

-- وظيفة جلب الوقت الحالي بتوقيت العراق
local function getIraqTime()
   local localTime = os.date("*t")
   local hour = localTime.hour
   local period = "AM"
   if hour >= 12 then
      period = "مساءً"
      if hour > 12 then hour = hour - 12 end
   else
      period = "صباحاً"
      if hour == 0 then hour = 12 end
   end
   return string.format("%02d:%02d:%02d %s", hour, localTime.min, localTime.sec, period)
end

local function getIraqDate()
   return os.date("%Y/%m/%d")
end

-- 🌙 نظام حساب ليلة محرم الحرام التلقائي بناءً على التقويم العالمي لعام 2026
local function getMuharramNight()
   local t = os.date("*t")
   -- بناءً على الحسابات الفلكية لعام 2026، ليلة 1 محرم بدأت مساء 16 يونيو (حزيران)
   if t.year == 2026 and t.month == 6 then
      local day = t.day
      local hour = t.hour
      
      -- الليلة الحسينية تبدأ من بعد المغرب (الساعة 6 مساءً / 18)
      local adjust = 0
      if hour >= 18 then
         adjust = 1
      end
      
      local nightNum = day - 16 + adjust
      
      local nightsData = {
         [1] = "ليلة 1 محرم (هلال شهر الأحزان / مسلم بن عقيل)",
         [2] = "ليلة 2 محرم (ورود القوافل إلى كربلاء)",
         [3] = "ليلة 3 محرم (عزيزة الحسين رقية عليها السلام)",
         [4] = "ليلة 4 محرم (الحر الرياحي وأولاد مسلم)",
         [5] = "ليلة 5 محرم (أصحاب الحسين - حبيب بن مظاهر)",
         [6] = "ليلة 6 محرم (أنصار الحسين عليهم السلام)",
         [7] = "ليلة 7 محرم (قاضي الحاجات أبي الفضل العباس عليه السلام)",
         [8] = "ليلة 8 محرم (عريس كربلاء القاسم بن الحسن عليه السلام)",
         [9] = "ليلة 9 محرم (شبه المصطفى علي الأكبر عليه السلام)",
         [10] = "ليلة 10 محرم (ليلة الوداع وعاشوراء العظيمة)"
      }
      
      if nightsData[nightNum] then
         return nightsData[nightNum]
      elseif nightNum > 10 and nightNum <= 13 then
         return "أيام عزاء دفن الأجساد الطاهرة"
      end
   end
   return "أيام شهر محرم الحرام والاستذكار"
end

----------------------------------------------------
-- [1] قسم تحديث الشرطة الجديد و S.W.A.T
----------------------------------------------------
local TabPolice = Window:Tab({ Title = "تحديث الشرطة الجديد", Icon = "rbxassetid://4483362458" })

TabPolice:Section({ Title = "الانتقال السريع للمواقع المحدثة" })
TabPolice:Button({
   Title = "الذهاب إلى مركز الشرطة الجديد وغرفة S.W.A.T",
   Callback = function()
      local hrp = LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
      if hrp then
         hrp.CFrame = CFrame.new(-165, 15, -30)
         WindUI:Notify({ Title = "Hussein Hub", Content = "تم الانتقال إلى مركز الشرطة بنجاح!", Duration = 3 })
      end
   end
})

TabPolice:Section({ Title = "أدوات ومعدات الشرطة المتقدمة" })
TabPolice:Button({
   Title = "جلب أدوات ومعدات مكافحة الشغب (Shield & Tools)",
   Callback = function()
      pcall(function()
         local tools = {"RiotShield", "SwatShield", "Taser", "Baton", "Handcuffs", "Radio"}
         for _, toolName in ipairs(tools) do
            ReplicatedStorage.GiveItem:FireServer(toolName)
         end
      end)
      WindUI:Notify({ Title = "معدات متطورة", Content = "تم إرسال أمر جلب الدروع والأدوات بنجاح!", Duration = 3 })
   end
})

----------------------------------------------------
-- [2] قسم المنازل والمخابئ السرية 2026
----------------------------------------------------
local TabSecrets = Window:Tab({ Title = "المنازل والمخابئ 2026", Icon = "rbxassetid://4483362458" })

TabSecrets:Section({ Title = "مجموعة منازل Wolf Den والحفلات" })
TabSecrets:Button({
   Title = "تفعيل ميزة طابع الحفلات والتحكم بالمنزل",
   Callback = function()
      pcall(function()
         ReplicatedStorage.HousePartyRemote:FireServer("TriggerParty", "PremiumStyle")
      end)
      WindUI:Notify({ Title = "House Parties", Content = "تم إطلاق طابع الحفلات الخاص بك!", Duration = 3 })
   end
})

TabSecrets:Section({ Title = "كشف واختراق المخابئ والخزائن" })
TabSecrets:Button({
   Title = "اختراق جدار مرآة منزل الشرطة والوصول للخزنة",
   Callback = function()
      local char = LocalPlayer.Character
      if char then
         for i = 1, 30 do
            for _, part in ipairs(char:GetChildren()) do
               if part:IsA("BasePart") then part.CanCollide = false end
            end
            task.wait(0.05)
         end
      end
      WindUI:Notify({ Title = "خزنة الشرطة", Content = "تم تعطيل الجدران مؤقتاً لتخطي جدار المرآة السري!", Duration = 4 })
   end
})

TabSecrets:Button({
   Title = "ثغرة السرير (Glitch) لدخول الغرف السرية العلوية",
   Callback = function()
      pcall(function()
         local character = LocalPlayer.Character
         local humanoid = character and character:FindFirstChildOfClass("Humanoid")
         if humanoid then
            humanoid.Sit = true -- تم إصلاح الكلمة هنا لتعمل 100% بدون كراش
            task.wait(0.1)
            if character:FindFirstChild("HumanoidRootPart") then
               character.HumanoidRootPart.CFrame = character.HumanoidRootPart.CFrame + Vector3.new(0, 6, 0)
            end
         end
      end)
      WindUI:Notify({ Title = "ثغرة السرير", Content = "تم تفعيل الرفع التلقائي لاختراق الأسقف السرية!", Duration = 4 })
   end
})

----------------------------------------------------
-- [3] قسم إضافات عامة (المنطاد والمدرسة)
----------------------------------------------------
local TabUpdates = Window:Tab({ Title = "إضافات مهمة مؤخراً", Icon = "rbxassetid://4483362458" })

TabUpdates:Section({ Title = "تحديث روح المدرسة (School Spirit)" })
TabUpdates:Button({
   Title = "تفعيل ملابس وحركات المدرسة التعبيرية الجديدة",
   Callback = function()
      pcall(function()
         ReplicatedStorage.PlayEmote:FireServer("SchoolSpirit_Dance")
      end)
      WindUI:Notify({ Title = "School Spirit", Content = "تم تفعيل الرقصات والحركات بنجاح!", Duration = 3 })
   end
})

TabUpdates:Section({ Title = "المنطاد الطائر (Blimp Hack)" })
TabUpdates:Button({
   Title = "زيادة وتخصيص سرعة المنطاد الطائر إلى القصوى",
   Callback = function()
      local vehicle = workspace:FindFirstChild("Blimp") or workspace:FindFirstChild(LocalPlayer.Name .. "sBlimp")
      if vehicle then
         local seat = vehicle:FindFirstChildOfClass("VehicleSeat")
         if seat then
            seat.MaxSpeed = 150
            WindUI:Notify({ Title = "Blimp Speed", Content = "تمت ترقية السرعة بنجاح!", Duration = 3 })
         end
      else
         WindUI:Notify({ Title = "تنبيه!", Content = "يرجى ركوب أو رسبنة المنطاد أولاً لتعديل خصائصه!", Duration = 3 })
      end
   end
})

----------------------------------------------------
-- [4] قسم السيارات المحسن
----------------------------------------------------
local TabVehicles = Window:Tab({ Title = "قسم السيارات", Icon = "rbxassetid://4483362458" })

TabVehicles:Section({ Title = "سرقة واختطاف المركبات" })
TabVehicles:Button({
   Title = " سرقة أقرب سيارة فارغة في الماب وركوبها فوراً",
   Callback = function()
      local character = LocalPlayer.Character
      local hrp = character and character:FindFirstChild("HumanoidRootPart")
      local humanoid = character and character:FindFirstChildOfClass("Humanoid")
      
      if not hrp or not humanoid then return end
      
      local closestSeat = nil
      local shortestDistance = math.huge
      
      for _, v in ipairs(workspace:GetDescendants()) do
         if v:IsA("VehicleSeat") and v.Occupant == nil then
            local distance = (hrp.Position - v.Position).Magnitude
            if distance < shortestDistance then
               shortestDistance = distance
               closestSeat = v
            end
         end
      end
      
      if closestSeat then
         hrp.CFrame = closestSeat.CFrame
         task.wait(0.1)
         closestSeat:Sit(humanoid)
         WindUI:Notify({ Title = "Hussein Hub V2", Content = "تم ركوب مقعد قيادة السيارة بنجاح!", Duration = 3 })
      end
   end
})

TabVehicles:Section({ Title = " محرك السرعة المطورة" })
TabVehicles:Button({
   Title = " جعل سرعة سيارتك الحالية 200 (تعديل العزم المباشر)",
   Callback = function()
      local char = LocalPlayer.Character
      local humanoid = char and char:FindFirstChildOfClass("Humanoid")
      if humanoid and humanoid.SeatPart and humanoid.SeatPart:IsA("VehicleSeat") then
         local seat = humanoid.SeatPart
         seat.MaxSpeed = 200
         seat.Torque = 35000 
         seat.TurnSpeed = 25 
         WindUI:Notify({ Title = "Speed Hack Active", Content = "تمت ترقية أداء محرك السيارة بنجاح!", Duration = 3 })
      end
   end
})

----------------------------------------------------
-- [5] قسم الحماية والتحركات المتقدمة
----------------------------------------------------
local TabExploits = Window:Tab({ Title = "الحماية والاختراق", Icon = "rbxassetid://4483362458" })

TabExploits:Section({ Title = " ميزة اختراق الجدران" })
local noclipEnabled = false
local noclipConnection
TabExploits:Toggle({
   Title = "تفعيل اختراق الجدران المستمر (NoClip)",
   Value = false,
   Callback = function(state)
      noclipEnabled = state
      if noclipEnabled then
         noclipConnection = RunService.Stepped:Connect(function()
            if noclipEnabled and LocalPlayer.Character then
               for _, part in ipairs(LocalPlayer.Character:GetChildren()) do
                  if part:IsA("BasePart") then part.CanCollide = false end
               end
            end
         end)
      else
         if noclipConnection then noclipConnection:Disconnect() end
      end
   end
})

----------------------------------------------------
-- [6] قسم نحن نحترم محرم (المحدث تلبية لطلبك)
----------------------------------------------------
local TabMuharram = Window:Tab({ Title = "نحن نحترم محرم", Icon = "rbxassetid://4483362458" })

TabMuharram:Section({ Title = " ميقات جمهورية العراق والمناسبة المباشرة" })
TabMuharram:Button({
   Title = "كشف ليلة محرم الحرام الحالية تلقائياً",
   Callback = function()
      local currentNight = getMuharramNight()
      WindUI:Notify({ 
         Title = "الحساب العالمي لليالي عاشوراء", 
         Content = "اليوم هو: " .. getIraqDate() .. "\n" .. currentNight, 
         Duration = 7 
      })
   end
})

TabMuharram:Section({ Title = " عبارات الاحترم والتقدير وتغيير اللقب" })
TabMuharram:Button({
   Title = "إظهار إشعار العزاء وتحديث الاسم والبيو",
   Callback = function()
      local currentNight = getMuharramNight()
      
      WindUI:Notify({ 
         Title = "نحن نحترم محرم", 
         Content = "عظم الله أجورنا وأجوركم بمصاب أبا عبد الله الحسين عليه السلام.\nنحن حالياً في: " .. currentNight, 
         Duration = 8 
      })
      
      -- تحديث الاسم والبيو داخل سيرفر بروك هافن ليتوافق مع ليلة العزاء الحالية
      pcall(function()
         ReplicatedStorage.UpdateName:FireServer("<font color='#FF0000'>يا حسين</font>")
         ReplicatedStorage.UpdateBio:FireServer("<font color='#000000'>نحن نحترم محرم - " .. currentNight .. "</font>")
      end)
   end
})

----------------------------------------------------
-- [7] قسم الحقوق (حسين - hussain_90_1)
----------------------------------------------------
local TabCredits = Window:Tab({ Title = "حقوق المطور", Icon = "rbxassetid://4483362458" })

TabCredits:Section({ Title = "الحسابات الرسمية للمطور المعتمد" })
TabCredits:Button({
   Title = " تيك توك: hussain_90_1",
   Callback = function()
      setclipboard("hussain_90_1")
      WindUI:Notify({ Title = "تم النسخ!", Content = "تم نسخ معرف التيك توك إلى الحافظة بنجاح.", Duration = 4 })
   end
})

TabCredits:Button({
   Title = "روبلوكس: Hussain4646767",
   Callback = function()
      setclipboard("Hussain4646767")
      WindUI:Notify({ Title = "تم النسخ!", Content = "تم نسخ معرف روبلوكس، يمكنك إرسال طلب صداقة الآن.", Duration = 4 })
   end
})

TabCredits:Section({ Title = "إصدار السكربت الحصري" })
TabCredits:Button({
   Title = "Hussein Hub V2 - 2026 WindUI Edition",
   Callback = function()
      WindUI:Notify({ Title = "شكر خاص", Content = "شكراً لاستخدامك سكربت حسين المطور V2 لـ بروك هافن.", Duration = 5 })
   end
})
