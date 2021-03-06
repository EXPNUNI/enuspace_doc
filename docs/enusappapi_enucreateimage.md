---
layout: default
title: enuCreateImage
parent: Application API
last_modified_date: now
---
# HNODE enuCreateImage\(HSVG pSvgHandler, wchar\_t\* strID, float x, float y, float width, float height, wchar\_t\* xlink\_href, float transx, float transy\)

HNODE enuCreateImage\(HSVG pSvgHandler, wchar\_t\* strID, float x, float y, float width, float height, wchar\_t\* xlink\_href, float transx, float transy\)

#### Parameters

* HSVG pSvgHandler

2d svg 픽쳐 핸들을 입력합니다.

* wchar\_t\* strID

생성객체의 ID를 지정합니다.

* float x

x축의 좌표를 입력합니다.

* float y

y축의 좌표를 입력합니다.

* float width

폭의 값을 입력합니다.

* float height

높이의 값을 입력합니다.

* wchar\_t\* xlink\_href

이미지 파일의 파일이름을 입력합니다.

* float transx

x축의 이동값을 입력합니다.

* float transy

y축의 이동값을 입력합니다.

#### Return Value

Type : HNODE

생성된 객체의 핸들을 반환합니다.

#### Remarks

스크립트를 이용하여 동적으로 이미지 객체를 생성합니다. 생성된 객체의 속성을 변경하고자 하는 경우에는 enuSetAttribute\(\)함수를 이용합니다.

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
    HNODE hnode = enuCreateImage(SvgHandle, L"MyObject", 0, 0, 300, 500, L"resource\\image.png", 0, 0);
}
```



