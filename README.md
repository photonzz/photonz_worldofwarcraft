# photonz_worldofwarcraft

## TBC 29.01.26

### Clear all buttons 

```
/run for i = 1,120 do PickupAction(i) PutItemInBackpack() ClearCursor() end;
```


### Clear all bindings

```
/run for bar=1,8 do for btn=1,12 do local n=bar==1 and "ACTIONBUTTON"..btn or "MULTIACTIONBAR"..(bar-1).."BUTTON"..btn local k=GetBindingKey(n) if k then SetBinding(k) end end end

/run SaveBindings(2)
```
