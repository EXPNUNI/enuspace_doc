---
layout: default
title: enuGetLogicSymbolList
parent: Application API
last_modified_date: now
---
# void\* enuGetLogicSymbolList\(wchar\_t\* pStrFilename\)

void\* enuGetLogicSymbolList\(wchar\_t\* pStrFilename\)

#### Parameters

* wchar\_t\* pStrFilename

HMI영역의 SVG 파일이름을 입력합니다.

#### Return Value

Type : void\*

CPtrList의 포인터를 반환합니다. CPtrList의 포인터를 통하여 심볼노드의 리스트를 취득합니다.

```cpp
struct DataItemStruct
{
    CString name;
    CString value;
    void* pnode;

    public: DataItemStruct()
    {
        pnode = NULL;
    }
};
```

#### Remarks

HMI 영역의 SVG 심볼리스트를 취득시 사용합니다.

```xml
<?xml version="1.0" encoding="UTF-16"?>
<svg
    id="ID_1encCj"
    stroke="rgb(0,119,189)"
    stroke-opacity="1.00"
    stroke-width="1.00"
    transform="translate(0.00,0.00) rotate(0.00) scale(1.0000, 1.0000)"
    pg-xcenter="0.00"
    pg-ycenter="0.00"
    style="stroke:rgb(127,127,127);stroke-opacity:1.00;stroke-width:2.00;stroke-dasharray:1,1,1;"
    enuspace-version="3.0.2.0"
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
    pg-create-time="2018-2-19 3:33:25.1"
    width="1920"
    height="1080"
>
    <defs
        id="ID_1encCj1"
    >
        <symbol
            id="NODE"
            type="node"
            stroke="rgb(0,119,189)"
            stroke-opacity="1.00"
            stroke-width="1.00"
            transform="translate(0.00,0.00) rotate(0.00) scale(1.0000, 1.0000)"
            pg-xcenter="0.00"
            pg-ycenter="0.00"
        >
            <script
                id="ID_1encDi"
                type="text/lua"
            >
                    <![CDATA[function _ontask()
    output = input
end]]>
            </script>
            <pg-pin
                id="ID_1encD2"
                name="input"
                desc=""
                pin-type="input"
                color="rgb(255,255,255)"
                var-type="int"
                unit=""
                default-value="0"
            >
                <circle
                    id="ID_1encD21"
                    stroke="rgb(200,0,0)"
                    stroke-opacity="1.00"
                    stroke-width="1.00"
                    transform="translate(9.00,11.00) rotate(0.00) scale(1.0000, 1.0000)"
                    pg-xcenter="0.00"
                    pg-ycenter="0.00"
                    stroke-dasharray="1,1,1"
                     cx="0.00"
                    cy="0.00"
                    rx="0.00"
                    ry="0.00"
                    r="5.00"
                    fill="rgb(0,176,80)"
                    fill-opacity="1.00"
                >
                </circle>
            </pg-pin>
            <pg-pin
                id="ID_1encDG"
                name="output"
                desc=""
                pin-type="input"
                color="rgb(255,255,255)"
                var-type="int"
                unit=""
                default-value="0"
            >
                <circle
                    id="ID_1encDG1"
                    stroke="rgb(200,0,0)"
                    stroke-opacity="1.00"
                    stroke-width="1.00"
                    transform="translate(47.18,12.21) rotate(0.00) scale(1.0000, 1.0000)"
                    pg-xcenter="0.00"
                    pg-ycenter="0.00"
                    stroke-dasharray="1,1,1"
                     cx="0.00"
                    cy="0.00"
                    rx="0.00"
                    ry="0.00"
                    r="5.00"
                    fill="rgb(0,176,80)"
                    fill-opacity="1.00"
                >
                </circle>
            </pg-pin>
        </symbol>
    </defs>
</svg>
```

#### Examples

```cpp
CPtrList* pSymList = (CPtrList*)enuGetLogicSymbolList(L"library\\logic\\logic_symbol.svg");

POSITION posSymbol = pSymList->GetHeadPosition();
DataItemStruct* pSymData = NULL;
while (posSymbol)
{
    pSymData = (DataItemStruct*) pSymList->GetAt(posSymbol);

    // TO DO JOB
    // m_wndFileView.InsertItem(pSymData->value, 9, 9, hSymItem);

    (DataItemStruct *)pSymList->GetNext(posSymbol);    
}
```



