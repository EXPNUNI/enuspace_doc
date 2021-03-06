---
layout: default
title: reci
parent: Statistics functions
grand_parent: Math & Statistics
last_modified_date: now
---

# Reci

Ensor.Reci\(Ensor\* pEnsor\)

#### Parameters

* Ensor\* pEnsor

Ensor.new\(\) 함수등에 의해 만들어진 포인터를 입력합니다.

#### Return Value

Ensor\* pRetEnsor : pEnsor의 엘리먼트에 대한 tangent Ensor\*를 반환합니다.

#### Remarks

#### Examples

```lua
function MathEquation()
    local x = ensor.new("[20]","double","1:20")
     local y = ensor.Reci(x)

     ensor.Plot(x, y)
     ensor.Table(y)
end
```

#### Result

![](./MathAPI/ReciResult.png)
