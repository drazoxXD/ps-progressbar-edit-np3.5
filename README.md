# Dillinger
## PS-progressbar with Nopixel3.5 look

Original script https://github.com/Project-Sloth/progressbar
Original CSS https://github.com/xViperAG/ps-css-edits/tree/main/progressbar

- Type some Markdown on the left
- Special thanks to Project Sloth boys and to the guy how made this css!

## Features

- As i know you just need to drag & drop 

## Orginial setup
-Drag&Drop
-Go to qb-core and found clint/function.lua
-Find progressbar function and replace it with this down here!
```lua
function QBCore.Functions.Progressbar(name, label, duration, useWhileDead, canCancel, disableControls, animation, prop, propTwo, onFinish, onCancel, icon)
    if GetResourceState('progressbar') ~= 'started' then error('progressbar needs to be started in order for QBCore.Functions.Progressbar to work') end
    exports['progressbar']:Progress({
        name = name:lower(),
        duration = duration,
        label = label,
        icon = icon,
        useWhileDead = useWhileDead,
        canCancel = canCancel,
        controlDisables = disableControls,
        animation = animation,
        prop = prop,
        propTwo = propTwo,
    }, function(cancelled)
        if not cancelled then
            if onFinish then
                onFinish()
            end
        else
            if onCancel then
                onCancel()
            end
        end
    end)
end
```
