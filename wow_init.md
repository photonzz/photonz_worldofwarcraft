Hi, I've been compiling a list of console variables which I like to adjust on a fresh install.

These are mostly my personal preferences, but I would like to know if anyone of you have any useful stuff to add to the list. I'm especially interested in commands / variables that increase performance.

Most of these can also be adjusted with the addon AdvancedInterfaceOptions

Edit: Added tips from comments

Reseting values to default

/run SetCVar("autoSelfCast", GetCVarDefault("autoSelfCast"))
/console cvar_default autoSelfCast
u/Balticataz: Bring up vault rewards so it is easy to check your progress anywhere

/run C_AddOns.LoadAddOn("Blizzard_WeeklyRewards"); WeeklyRewardsFrame:Show()
u/ChalkLitMilk: Spell Que Window.

/console SpellQueueWindow 400
u/dadof2brats: Disable the default behavior of adding new spells/abilities automatically to your action bars:

/console AutoPushSpellToActionBar 0
u/carniel: This may not be for everyone, but personally I love it (as a caster) and as a melee I'm used to it.

/script SetCVar( "nameplateOtherAtBase", 2 )
u/BudoBoy07: Disables the looping sound when someone signs up to your group:

/script QueueStatusMinimapButton.EyeHighlightAnim:SetScript('OnLoop', nil)
u/BudoBoy07: For addon debugging

/etrace
/fstack
u/BudoBoy07: Freeze your game for 7 seconds (can be useful in certain quests)

/run local t = time() + 7 while time() < t do end
full screen glow effect

/console ffxglow 0
Increase maximum zoom distance, max 2.6 in retail

/console cameraDistanceMaxZoomFactor 4
Adjusts when the horizon start, will increase fps by lowering value

/run SetCVar("horizonStart", 400)
View distance of the environment

/run SetCVar("farclip", 185)
Enable sharpening

/console set ResampleAlwaysSharpen 1
Blueish friendly nameplate colors

/console ShowClassColorInFriendlyNameplate 0
Nameplate horizontal size

/run SetCVar("nameplateHorizontalScale", 0.7)
Disable the advanced flying velocity VFX

/run SetCVar("DisableAdvancedFlyingVelocityVFX", 1)
Disable the advanced flying full screen effects

/run SetCVar("DisableAdvancedFlyingFullScreenEffects", 1)
Alpha multiplier of nameplates for occluded targets

/run SetCVar("nameplateOccludedAlphaMult", 1)
The minimum alpha of nameplates

/run SetCVar("nameplateMinAlpha", 1)
The minimum scale of nameplates

/run SetCVar("nameplateMinScale", 1)
Colors raid frames with the class color

/run SetCVar("raidFramesDisplayClassColor", 1)
WorldTextScale

/run SetCVar("WorldTextScale", 2.5)


/console ShowClassColorInFriendlyNameplate 1
