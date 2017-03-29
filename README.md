# What is hammerspoon
http://www.hammerspoon.org/


# Simple Configuration
just remapping control+hjkl to arrow keys.

```
control + h => left
control + j => down
control + k => up
control + l => right
```
# update ~/.hammerspoon/init.lua

```
local function pressFn(mods, key)
	if key == nil then
		key = mods
		mods = {}
	end

	return function() hs.eventtap.keyStroke(mods, key, 1000) end
end

local function remap(mods, key, pressFn)
	hs.hotkey.bind(mods, key, pressFn, nil, pressFn)	
end


remap({'ctrl'}, 'h', pressFn('left'))
remap({'ctrl'}, 'j', pressFn('down'))
remap({'ctrl'}, 'k', pressFn('up'))
remap({'ctrl'}, 'l', pressFn('right'))

```
