preheat evoker: https://wago.io/7Kdv1YBIZ

m+ healer frame assist: https://wago.io/ZUILNKG16

remove names from raid frames: https://wago.io/x1MSOqXoi

raid ability timeline https://wago.io/RaidAbilityTimeline

/console ffxglow 0

/console floatingCombatTextCombatDamage 1

/console GxAllowCachelessShaderMode 0

/console ShowClassColorInFriendlyNameplate 0 

/console set renderscale 0.999

/console m2Faster 1

/console ffx 0

/console hwPCF 1

/console shadowlod 0

/console timingmethod 1

/console showshadow 0

/console showfootprints 0

/console showfootprintparticles 0

/console spelleffectlevel 2

/console particledensity 1

/console overridefarclip 0

/console farclip 177

/console horizonfarclip 1305

/console detailDoodadAlpha 0

/console groundeffectdensity 16

/console groundeffectdist 1

/console smallcull 1

/console skycloudlod 1

/console characterAmbient 1

/console extshadowquality 0

/console environmentDetail 0.5

spellqueue
Set it to your latency (world) +100 or +150 for optimal global usage. 
/console SpellQueueWindow 135
/dump GetCVar("SpellQueueWindow")

Draw Distance
farclip (-1 - ∞): Sets world draw distance, objects, terrain, horizon, etc. Max is about 10000.
horizonStart (-1 - ∞): Master fog scale, set fog horizon distance also has some control over terrain lod for terrain beyond the horizon. Max is about 10000.

Ground Clutter
groundEffectDist (40 - 500): Controls how far flora is rendered, in 2.x there was no limit.
groundEffectFade (View Range): This value works best if it matches groundEffectDist, if you don't want any fading for Flora just increase it so its groundEffectDist + 10
groundEffectDensity (16 - 256): Controls flora density.

Terrain
terrainLodDist (1 - ∞): Distance at which to render the lowest lod for terrain. Will impact performance!
lodTerrainDiv (256 - 1024): Sets how lod chunks are handled. Smaller chunks are better for more lod levels, larger for less. Must be in a power of 2.

Level of Detail - Objects
lodObjectMinSize (0 - 1000): Min size of an object before its culled
lodObjectCullSize (1 - 100): Objects smaller than the value will be culled, where 1 is all objects visible and 100 is most are not.
lodObjectCullDist (1.0 - 200.0): Distance before objects are culled
lodObjectFadeScale (50 - 300): Controls distance in which objects are faded between lod sets, higher is more detail
doodadLodDist (10 - 1000): Depricated? Not sure if this works anymore.

Models
M2UseLod (0, 1): Toggle LOD usage for all models
M2UseThreads (0 - 3): Sets number of threads for models during rendering
M2UseInstancing (0, 1): Use hardware instancting, aka makes things go faster

Component Textures
componentThread (0 - ∞): Sets number of threads to use when rendering entity textures
componentCompress (0, 1): Use compression, saves video memory.
componentTextureLevel (0, 12): Source texture LOD level to use when rendering entity texture
componentTexLoadLimit (0 - ∞): Number of textures to load simultaneously
componentTexCacheSize (0 - ∞): Texture cache size
componentSpecular (0, 1): Use specular maps
componentEmissive (0, 1): Use emissive maps

Entity
entityLodDist (5 - 1000): Distance before lods are applied
entityLodOffset (5 - 1000): Distance before lod offsets are applied

felrush macro
This WoW macro creates a new frame called "f" and sets an initial delay of 0.5 seconds. It then sets a script to run every update (i.e. every frame) that subtracts the elapsed time "e" from the delay "f.d". If the delay is less than 0, the script removes the onUpdate script and sets "f" to nil (effectively deleting the frame).
If the player's speed is greater than 45 (i.e. moving at a very high speed, possibly on a mount or using a speed boost) then the script waits for 1 second before continuing to update "f". This is because in WoW, the game client does not update the player's position at the same rate as other units when the player is moving quickly.
Overall, this macro seems to be designed to wait for a short period of time before performing some action, while accounting for the player's movement speed.

#showtooltip
/run f=CreateFrame("frame");f.d=0.5;f:SetScript("OnUpdate",function(s,e) f.d=f.d-e if f.d<0 then f:SetScript("OnUpdate",nil) f=nil elseif select(1,GetUnitSpeed("player"))>45 then local d=time()+1 while time()<d do end  end end)
/use Fel Rush

/run C_NamePlate.SetNamePlateFriendlySize(60, 30)

nameplateOccludedAlphaMul

nameplateMinAlpha

/cwm all
/wm 2
Applies a World Marker on the ground, useful to mark stuff like monk ports in arena so you remember where they are.
Press it again to remove the marker.
 
/run MinimapCluster:SetScale(0.7)

WorldFrame:

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

anti afk

/run local f=CreateFrame("Frame")f:RegisterEvent("PLAYER_CAMPING")f:SetScript("OnEvent", function() local p=StaticPopup_Visible("CAMP")_G[p.."Button1"]:Click()end)
