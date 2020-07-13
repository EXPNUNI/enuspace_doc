---
layout: default
title: SendBackwardObject
parent: Script API
---
# SendBackwardObject\(objects\)

SendBackwardObject\(\)

#### Parameters

objects

수행하고자 하는 객체의 ID를 입력합니다. 여러개의 객체를 입력하고자 하는경우에는 ","을 이용합니다.

#### Return Value

none

#### Remarks

lua 스크립트에서 제공합니다.

#### Examples



```lua
-- lua
function _onmousedown()
    SendBackwardObject("ID_OBJ1, ID_OBJ2")
end
```






