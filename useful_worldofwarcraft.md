##

useful items

https://www.wowhead.com/item=152550/sea-mist-potion

https://www.wowhead.com/item=132516/gunshoes

https://www.wowhead.com/item=89682/oddly-shaped-horn

https://www.wowhead.com/item=153123/cracked-radinax-control-gem

https://www.wowhead.com/item=89770/tuft-of-yak-fur

https://www.wowhead.com/item=89697/bag-of-kafa-beans

https://www.wowhead.com/item=182732/the-necronom-i-nom

##
A working 9.1.5 macro to leave an instance if you are alone.

/inv 1

/pr 1

/script C_PartyInfo.LeaveParty()
##

https://wowpedia.fandom.com/wiki/World_of_Warcraft_API

MinimapCluster:Show();

MinimapCluster:Hide();

/console cameraDistanceMaxZoomFactor 4

/run SetConsoleKey("Q")

nameplate numbers:

For enemies with red numbers:
```
/run local U=UnitIsUnit hooksecurefunc("CompactUnitFrame_UpdateName",function(F)if IsActiveBattlefieldArena()and F.unit:find("nameplate")then for i=1,5 do if U(F.unit,"arena"..i)then F.name:SetText(i)F.name:SetTextColor(1,0,0,1)break end end end end)
```

#spellqueue

Set it to your latency (world) +100 or +150 for optimal global usage. 

/console SpellQueueWindow 135

/dump GetCVar("SpellQueueWindow")

# felrush macro

This WoW macro creates a new frame called "f" and sets an initial delay of 0.5 seconds. It then sets a script to run every update (i.e. every frame) that subtracts the elapsed time "e" from the delay "f.d". If the delay is less than 0, the script removes the onUpdate script and sets "f" to nil (effectively deleting the frame).
If the player's speed is greater than 45 (i.e. moving at a very high speed, possibly on a mount or using a speed boost) then the script waits for 1 second before continuing to update "f". This is because in WoW, the game client does not update the player's position at the same rate as other units when the player is moving quickly.
Overall, this macro seems to be designed to wait for a short period of time before performing some action, while accounting for the player's movement speed.

#showtooltip
/run f=CreateFrame("frame");f.d=0.5;f:SetScript("OnUpdate",function(s,e) f.d=f.d-e if f.d<0 then f:SetScript("OnUpdate",nil) f=nil elseif select(1,GetUnitSpeed("player"))>45 then local d=time()+1 while time()<d do end  end end)

/use Fel Rush

---

/cwm all

/wm 2

Applies a World Marker on the ground, useful to mark stuff like monk ports in arena so you remember where they are.
Press it again to remove the marker.
 
/run MinimapCluster:SetScale(0.7)

# WorldFrame

The height of the viewport is fixed, while the width is appropriately sized.

You can manually modify the WorldFrame's (the frame that handles 3D rendering) in-game.

First, run this script once:

Code:

/run WorldFrame:SetUserPlaced(true)

This causes the Client to remember the position of your world frame between sessions.
Afterwards, you can reposition the WorldFrame using this line of code:
Code:

/run WorldFrame:ClearAllPoints() WorldFrame:SetPoint("TOPLEFT", 0, 0) WorldFrame:SetPoint("BOTTOMRIGHT", 0, 0)

What you need to change are the four zeros in this line of code. The first two modify the X and Y offset of the WorldFrame's top left corner.
Positive X values move the corner to the right, negative to the left (off your screen).
Positive Y values move the corner up (off the screen), negative ones move it down.
The same functionality applies to the third and fourth zero and the bottom right corner.

Code:

/run WorldFrame:ClearAllPoints() WorldFrame:SetPoint("TOPLEFT", 0, 0) WorldFrame:SetPoint("BOTTOMRIGHT", 0, 50)

This would put the World Frame's bottom edge 50 pixels above the screen's bottom edge and make your field of view a bit wider. 

/run WorldFrame:ClearAllPoints() WorldFrame:SetPoint("TOPLEFT", 0, -200) WorldFrame:SetPoint("BOTTOMRIGHT", 0, 200)

# antiafk

/run local f=CreateFrame("Frame")f:RegisterEvent("PLAYER_CAMPING")f:SetScript("OnEvent", function() local p=StaticPopup_Visible("CAMP")_G[p.."Button1"]:Click()end)

# keybinds

You can use these functions (and many others) in any addons or macros.

GetBindingKey("command")

SetBinding("KEY", "command")

SetBindingSpell("KEY", "Spell Name")

SetBindingItem("KEY", "itemname")

SetBindingMacro("KEY", "macroname"|macroid)

GetCurrentBindingSet()

Just don't forget to save changes by calling SaveBindings(GetCurrentBindingSet()).

# addon dev

/script print(GetCVar("ShowClassColorInFriendlyNameplate"))

/dump UnitName("player")

-- display the current value

/script print(GetCVar("nameplateHorizontalScale"))

-- change the value to 2

/script SetCVar("nameplateHorizontalScale", 2)

-- display the current value (which should now equal 2)

/script print(GetCVar("nameplateHorizontalScale"))

https://developer.school/tutorials/developing-world-of-warcraft-addons-hello-world-part-one
