```
/console cameraDistanceMaxZoomFactor 4

/console maxfps 999

/run MainMenuBarLeftEndCap:Hide(); MainMenuBarRightEndCap:Hide()

/run MinimapCluster:Hide();

/dump GetCVar("SpellQueueWindow")

/console SpellQueueWindow 135


--- MACROS -----
#showtooltip Auto Shot
/cast !Auto Shot
 
#showtooltip Kill Command
/petattack
 
- Aspect of the Cheetah
/cancelaura Aspect of the Cheetah
/cast Aspect of the Cheetah
 
#showtooltip Eagle Eye
/cast !Eagle Eye
 
#showtooltip Raptor Strike
/cleartarget
/targetlasttarget
/stopcasting
/cast Raptor Strike
/startattack
 
#showtooltip Feign Death
/stopattack
/petpassive
/use [mod:ctrl] Renataki's Charm of Beasts
/cast [combat] Feign Death
 
HIDE GRYPHONS (STANDARD BARS)
/run MainMenuBarLeftEndCap:Hide(); MainMenuBarRightEndCap:Hide()
 
#showtooltip Viper Sting
/targetexact Cho'Rush The Observer
/cast Viper Sting(Rank 3)
/targetlasttarget
 
#showtooltip Distracting Shot
/targetexact Cho'Rush The Observer
/cast Distracting Shot
/targetlasttarget
 
#showtooltip
/stopattack
/cleartarget
/targetlasttarget
/targetenemy [noharm]
/tar [@mouseover,harm]
/use Raptor Strike
/startattack
/stopmacro [@mouseover,noharm]
/targetlasttarget
/use !Auto Shot
/targetlasttarget [noharm][dead]
 
 
 #showtooltip Immolation Trap
/cast Immolation Trap
/petpassive [@pettarget, harm]
/cast [combat] Feign Death
 
#showtooltip Frost Trap
/cast Frost Trap
/petpassive [@pettarget, harm]
/cast [combat] Feign Death
 
#showtooltip Explosive Trap
/cast Explosive Trap
/petpassive [@pettarget, harm]
/cast [combat] Feign Death
 
#showtooltip Freezing Trap
/cast Freezing Trap
/petpassive [@pettarget, harm]
/cast [combat] Feign Death
 
/use [@pettarget,exists][]Claw
 
instance group to enter/solo ghetto hearth
/run InviteUnit("a");C_Timer.After(.25,function() ConvertToRaid() end)
 
 
----- Weakauaras -----
 
 Castbar+Range bar
https://wago.io/QvUhjzL8H
 
Pet Happiness
https://wago.io/xkzc0BxaD/
 
Target Movement Speed
https://wago.io/2X5frQaU_/
 
Next Mana Tick
https://wago.io/NextManaTick/
 
Debuffs on Nameplate
https://wago.io/s8EGafICm/
 
Uldaman NPC Casts
https://wago.io/UdfHigEU9
 
EOTB Combat Pulse
https://wago.io/f_y-jlrhK
 
Trap Timers
https://wago.io/qZnF-qcKl

Waylaid Supply Tooltip
https://wago.io/7qw41eQ1D

Focus Fire
https://wago.io/_2CEyFZGR

Sniper Training 
https://wago.io/7THab2Wfc/4

Total Aoe Tracker
https://wago.io/JFDpzVq-7

XP Gain from Dungeon kills + Party exp tracking (they need the WA)
https://wago.io/L9Az0ln0E/3
```
