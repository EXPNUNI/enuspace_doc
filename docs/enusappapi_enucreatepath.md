---
layout: default
title: enuCreatePath
parent: Application API
last_modified_date: now
---
# HNODE enuCreatePath\(HSVG pSvgHandler, wchar\_t\* strID, wchar\_t\* pStrValue, float transx, float transy\)

HNODE enuCreatePath\(HSVG pSvgHandler, wchar\_t\* strID, wchar\_t\* pStrPoints, float transx, float transy\)

#### Parameters

* HSVG pSvgHandler

2d svg 픽쳐 핸들을 입력합니다.

* wchar\_t\* strID

생성객체의 ID를 지정합니다.

* wchar\_t\* pStrPoints

패스정보 포인트를 입력합니다. \(ex : "M69.14,67.28 L0.00,67.28 A69.14,67.28 0 1,0 69.14,-0.00 Z"\)

* float transx

x축의 이동값을 입력합니다.

* float transy

y축의 이동값을 입력합니다.

#### Return Value

Type : HNODE  
생성된 객체의 핸들을 반환합니다.

#### Remarks

동기식 방법으로  동적 패스 객체를 생성합니다. 생성된 객체의 속성을 변경하고자 하는 경우에는 enuSetAttribute\(\) 함수를 이용합니다.

#### Examples

```cpp
HVIEW ViewHandle = NULL; 
void CSampleView::OnInitialUpdate() 
{ 
    CView::OnInitialUpdate(); 

    enuCreateProject(); 

    // Load Project
    enuLoadProjectFile(L"Project\\sample.enup"); 

    // Create View
    ViewHandle = enuCreateView(this->m_hWnd); 

    // New Page Create. 
    CString strPicture = L"picture\\KoreaAIP.svg"; 
    HSVG SvgHandle = enuNewSvgPageFile(strPicture.GetBuffer(0)); 

    // ENU View Attach Set Page 
    enuSetSvgPageView(ViewHandle , strPicture.GetBuffer(0)); 

    // object create
    HNODE hnode = enuCreatePath(SvgHandle, L"MyObject", L"M69.14,67.28 L0.00,67.28 A69.14,67.28 0 1,0 69.14,-0.00 Z", 0, 0);
}
```



