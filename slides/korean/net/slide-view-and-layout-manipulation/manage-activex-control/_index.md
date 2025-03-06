---
title: PowerPoint에서 ActiveX 컨트롤 관리
linktitle: PowerPoint에서 ActiveX 컨트롤 관리
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 ActiveX 컨트롤로 PowerPoint 프레젠테이션을 향상시키는 방법을 알아보세요. 단계별 가이드에서는 삽입, 조작, 사용자 정의, 이벤트 처리 등을 다룹니다.
weight: 13
url: /ko/net/slide-view-and-layout-manipulation/manage-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 ActiveX 컨트롤 관리

ActiveX 컨트롤은 PowerPoint 프레젠테이션의 기능과 상호 작용성을 향상시킬 수 있는 강력한 요소입니다. 이러한 컨트롤을 사용하면 멀티미디어 플레이어, 데이터 입력 양식 등과 같은 개체를 슬라이드에 직접 포함하고 조작할 수 있습니다. 이 기사에서는 .NET 애플리케이션에서 PowerPoint 파일을 원활하게 통합하고 조작할 수 있는 다목적 라이브러리인 Aspose.Slides for .NET을 사용하여 PowerPoint에서 ActiveX 컨트롤을 관리하는 방법을 살펴보겠습니다.

## PowerPoint 슬라이드에 ActiveX 컨트롤 추가

PowerPoint 프레젠테이션에 ActiveX 컨트롤을 통합하려면 다음 단계를 따르세요.

1.  새 PowerPoint 프레젠테이션 만들기: 먼저 Aspose.Slides for .NET을 사용하여 새 PowerPoint 프레젠테이션을 만듭니다. 당신은[.NET API 참조용 Aspose.Slides](https://reference.aspose.com/slides/net/) 프레젠테이션 작업 방법에 대한 지침을 확인하세요.

2. 슬라이드 추가: 라이브러리를 사용하여 프레젠테이션에 새 슬라이드를 추가합니다. 이는 ActiveX 컨트롤을 삽입할 슬라이드입니다.

3. ActiveX 컨트롤 삽입: 이제 슬라이드에 ActiveX 컨트롤을 삽입할 차례입니다. 아래 샘플 코드를 따르면 이를 달성할 수 있습니다.

```csharp
// 프레젠테이션 로드
Presentation presentation = new Presentation("path_to_your_presentation.pptx");

// ActiveX 컨트롤을 삽입하려는 슬라이드를 가져옵니다.
ISlide slide = presentation.Slides[0];

// ActiveX 컨트롤의 속성 정의
int left = 100; // 왼쪽 위치 지정
int top = 100; // 상단 위치 지정
int width = 200; // 너비 지정
int height = 100; // 높이 지정
string progId = "YourActiveXControl.ProgID"; // ActiveX 컨트롤의 ProgID 지정

// 슬라이드에 ActiveX 컨트롤 추가
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(left, top, width, height, progId);
```

 꼭 교체하세요`"YourActiveXControl.ProgID"` 삽입하려는 ActiveX 컨트롤의 실제 ProgID를 사용합니다.

4. 프레젠테이션 저장: ActiveX 컨트롤을 삽입한 후 다음 코드를 사용하여 프레젠테이션을 저장합니다.

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## 프로그래밍 방식으로 ActiveX 컨트롤 조작

슬라이드에 ActiveX 컨트롤을 추가한 후에는 이를 프로그래밍 방식으로 조작할 수 있습니다. 방법은 다음과 같습니다.

1. ActiveX 컨트롤에 액세스: ActiveX 컨트롤의 속성과 메서드에 액세스하려면 이에 대한 참조를 얻어야 합니다. 슬라이드에서 제어권을 얻으려면 다음 코드를 사용하십시오.

```csharp
IOleObjectFrame oleObjectFrame = slide.Shapes[0] as IOleObjectFrame;
```

2. 메서드 호출: 얻은 참조를 사용하여 ActiveX 컨트롤의 메서드를 호출할 수 있습니다. 예를 들어 ActiveX 컨트롤에 "Play"라는 메서드가 있는 경우 다음과 같이 호출할 수 있습니다.

```csharp
oleObjectFrame.InvokeMethod("Play");
```

3. 속성 설정: ActiveX 컨트롤의 속성을 프로그래밍 방식으로 설정할 수도 있습니다. 예를 들어 컨트롤에 "볼륨"이라는 속성이 있는 경우 다음과 같이 설정할 수 있습니다.

```csharp
oleObjectFrame.SetProperty("Volume", 50);
```

## ActiveX 컨트롤 속성 사용자 정의

ActiveX 컨트롤의 속성을 사용자 지정하면 프레젠테이션의 사용자 경험이 크게 향상될 수 있습니다. 이러한 속성을 맞춤설정하는 방법은 다음과 같습니다.

1.  속성 액세스: 앞에서 언급한 것처럼 다음을 사용하여 ActiveX 컨트롤의 속성에 액세스할 수 있습니다.`IOleObjectFrame` 참조.

2.  속성 설정:`SetProperty`ActiveX 컨트롤의 다양한 속성을 설정하는 방법입니다. 예를 들어 다음과 같이 배경색을 변경할 수 있습니다.

```csharp
oleObjectFrame.SetProperty("BackColor", Color.Red);
```

## ActiveX 컨트롤과 관련된 이벤트 처리

ActiveX 컨트롤에는 사용자 상호 작용을 기반으로 작업을 트리거할 수 있는 관련 이벤트가 있는 경우가 많습니다. 이러한 이벤트를 처리하는 방법은 다음과 같습니다.

1. 이벤트 구독: 먼저 ActiveX 컨트롤의 원하는 이벤트를 구독합니다. 예를 들어 컨트롤에 "Clicked" 이벤트가 있는 경우 다음과 같이 구독할 수 있습니다.

```csharp
oleObjectFrame.EventClick += (sender, args) =>
{
    // 이벤트 처리 코드는 여기에 있습니다.
};
```

## 슬라이드에서 ActiveX 컨트롤 삭제

슬라이드에서 ActiveX 컨트롤을 제거하려면 다음 단계를 따르세요.

1.  컨트롤에 액세스: 다음을 사용하여 ActiveX 컨트롤에 대한 참조를 얻습니다.`IOleObjectFrame` 이전에 표시된 대로 참조하세요.

2. 컨트롤 제거: 다음 코드를 사용하여 슬라이드에서 컨트롤을 제거합니다.

```csharp
slide.Shapes.Remove(oleObjectFrame);
```

## 수정된 프리젠테이션 저장 및 내보내기

프레젠테이션에 필요한 사항을 모두 변경한 후 다음 코드를 사용하여 프레젠테이션을 저장하고 내보낼 수 있습니다.

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## .NET용 Aspose.Slides 사용의 이점

.NET용 Aspose.Slides는 이러한 컨트롤을 원활하게 통합하고 조작할 수 있는 사용자 친화적인 API를 제공하여 PowerPoint 프레젠테이션에서 ActiveX 컨트롤 작업 프로세스를 단순화합니다. .NET용 Aspose.Slides를 사용하면 다음과 같은 이점이 있습니다.

- 슬라이드에 ActiveX 컨트롤을 쉽게 삽입할 수 있습니다.
- 프로그래밍 방식으로 컨트롤과 상호 작용하기 위한 포괄적인 방법입니다.
- 컨트롤 속성의 사용자 정의가 단순화되었습니다.
- 대화형 프레젠테이션을 위한 효율적인 이벤트 처리.
- 슬라이드에서 컨트롤을 간편하게 제거합니다.

## 결론

ActiveX 컨트롤을 PowerPoint 프레젠테이션에 통합하면 청중의 상호 작용 및 참여 수준을 높일 수 있습니다. .NET용 Aspose.Slides를 사용하면 ActiveX 컨트롤을 원활하게 관리할 수 있는 강력한 도구를 갖게 되어 지속적인 인상을 남기는 역동적이고 매력적인 프레젠테이션을 만들 수 있습니다.

## 자주 묻는 질문

### 특정 슬라이드에 ActiveX 컨트롤을 추가하려면 어떻게 해야 합니까?

 특정 슬라이드에 ActiveX 컨트롤을 추가하려면`AddOleObjectFrame` .NET용 Aspose.Slides에서 제공하는 메서드입니다. 이 방법을 사용하면 삽입하려는 ActiveX 컨트롤의 위치, 크기 및 ProgID를 지정할 수 있습니다.

### 프로그래밍 방식으로 ActiveX 컨트롤을 조작할 수 있습니까?

 예, Aspose.Slides for .NET을 사용하여 프로그래밍 방식으로 ActiveX 컨트롤을 조작할 수 있습니다. 에 대한 참조를 얻음으로써`IOleObjectFrame` 컨트롤을 나타내면 메서드를 호출하고 속성을 설정하여 컨트롤과 동적으로 상호 작용할 수 있습니다.

### 이벤트를 어떻게 처리하나요?

 ActiveX 컨트롤에 의해 트리거됩니까?

다음을 사용하여 해당 이벤트를 구독함으로써 ActiveX 컨트롤에 의해 트리거된 이벤트를 처리할 수 있습니다.`EventClick` (또는 유사한) 이벤트 핸들러. 이를 통해 사용자와 컨트롤의 상호 작용에 응답하여 특정 작업을 실행할 수 있습니다.

### ActiveX 컨트롤의 모양을 사용자 정의할 수 있습니까?

 물론, 다음을 사용하여 ActiveX 컨트롤의 모양을 사용자 정의할 수 있습니다.`SetProperty` .NET용 Aspose.Slides에서 제공하는 메서드입니다. 이 방법을 사용하면 배경색, 글꼴 스타일 등과 같은 다양한 속성을 수정할 수 있습니다.

### 슬라이드에서 ActiveX 컨트롤을 제거할 수 있나요?

 예, 다음을 사용하여 슬라이드에서 ActiveX 컨트롤을 제거할 수 있습니다.`Remove` 의 방법`Shapes` 수집. 참조를 다음 항목에 전달합니다.`IOleObjectFrame` 컨트롤을 인수로 표현`Remove` 방법을 사용하면 컨트롤이 슬라이드에서 제거됩니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
