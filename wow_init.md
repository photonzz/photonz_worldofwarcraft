Hi, I've been compiling a list of [console variables](https://warcraft.wiki.gg/wiki/Console_variables) which I like to adjust on a fresh install.

full screen glow effect
```
/console ffxglow 0
```

Increase maximum zoom distance, max 2.6 in retail
```
/console cameraDistanceMaxZoomFactor 4
```

Adjusts when the horizon start, will increase fps by lowering value
```
/run SetCVar("horizonStart", 400)
```

View distance of the environment
```
/run SetCVar("farclip", 400)
```

Enable sharpening 
```
/console set ResampleAlwaysSharpen 1
```

Blueish friendly nameplate colors
```
/console ShowClassColorInFriendlyNameplate 0
```

Nameplate horizontal size
```
/run SetCVar("nameplateHorizontalScale", 0.7)
```

Disable the advanced flying velocity VFX
```
/run SetCVar("DisableAdvancedFlyingVelocityVFX", 1)
```

Disable the advanced flying full screen effects
```
/run SetCVar("DisableAdvancedFlyingFullScreenEffects", 1)
```

Alpha multiplier of nameplates for occluded targets
```
/run SetCVar("nameplateOccludedAlphaMult", 1)
```

The minimum alpha of nameplates
```
/run SetCVar("nameplateMinAlpha", 1)
```

The minimum scale of nameplates
```
/run SetCVar("nameplateMinScale", 1)
```

Colors raid frames with the class color
```
/run SetCVar("raidFramesDisplayClassColor", 1)
```

WorldTextScale
```
/run SetCVar("WorldTextScale", 2.5)
```


