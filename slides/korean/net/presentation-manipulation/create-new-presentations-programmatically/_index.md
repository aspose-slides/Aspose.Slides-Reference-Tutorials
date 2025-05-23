---
"description": "Aspose.Slides for .NET을 사용하여 프로그래밍 방식으로 프레젠테이션을 만드는 방법을 알아보세요. 효율적인 자동화를 위한 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "프로그래밍 방식으로 새 프레젠테이션 만들기"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "프로그래밍 방식으로 새 프레젠테이션 만들기"
"url": "/ko/net/presentation-manipulation/create-new-presentations-programmatically/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 프로그래밍 방식으로 새 프레젠테이션 만들기


.NET에서 프로그래밍 방식으로 프레젠테이션을 만들고 싶다면 Aspose.Slides for .NET이 이 작업을 효율적으로 수행하는 데 도움이 되는 강력한 도구입니다. 이 단계별 튜토리얼은 제공된 소스 코드를 사용하여 새 프레젠테이션을 만드는 과정을 안내합니다.

## .NET용 Aspose.Slides 소개

Aspose.Slides for .NET은 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업할 수 있도록 지원하는 강력한 라이브러리입니다. 보고서 생성, 프레젠테이션 자동화, 슬라이드 조작 등 어떤 작업이든 Aspose.Slides는 작업을 더욱 간편하게 만들어 주는 다양한 기능을 제공합니다.

## 1단계: 환경 설정

코드를 살펴보기 전에 개발 환경을 설정해야 합니다. 다음 필수 조건을 충족하는지 확인하세요.

- Visual Studio 또는 .NET 개발 환경.
- .NET 라이브러리용 Aspose.Slides(다운로드 가능) [여기](https://releases.aspose.com/slides/net/)).

## 2단계: 프레젠테이션 만들기

다음 코드를 사용하여 새로운 프레젠테이션을 만들어 보겠습니다.

```csharp
// 프레젠테이션 만들기
Presentation pres = new Presentation();
```

이 코드는 PowerPoint 파일의 기반이 되는 새로운 프레젠테이션 객체를 초기화합니다.

## 3단계: 제목 슬라이드 추가

대부분의 프레젠테이션에서 첫 번째 슬라이드는 제목 슬라이드입니다. 제목 슬라이드를 추가하는 방법은 다음과 같습니다.

```csharp
// 제목 슬라이드 추가
Slide slide = pres.AddTitleSlide();
```

이 코드는 프레젠테이션에 제목 슬라이드를 추가합니다.

## 4단계: 제목 및 부제 설정

이제 제목 슬라이드의 제목과 부제를 설정해 보겠습니다.

```csharp
// 제목 텍스트를 설정하세요
((TextHolder)slide.Placeholders[0]).Text = "Slide Title Heading";

// 자막 텍스트 설정
((TextHolder)slide.Placeholders[1]).Text = "Slide Title Sub-Heading";
```

"슬라이드 제목 제목"과 "슬라이드 제목 하위 제목"을 원하는 제목으로 바꾸세요.

## 5단계: 프레젠테이션 저장

마지막으로 프레젠테이션을 파일로 저장해 보겠습니다.

```csharp
// 디스크에 출력 쓰기
pres.Write("outAsposeSlides.ppt");
```

이 코드는 프레젠테이션을 프로젝트 디렉토리에 "outAsposeSlides.ppt"라는 이름으로 저장합니다.

## 결론

축하합니다! Aspose.Slides for .NET을 사용하여 프로그래밍 방식으로 PowerPoint 프레젠테이션을 만들었습니다. 이 강력한 라이브러리를 사용하면 프레젠테이션을 손쉽게 자동화하고 사용자 지정할 수 있는 유연성을 제공합니다.

이제 이 코드를 .NET 프로젝트에 통합하여 특정 요구 사항에 맞는 동적 프레젠테이션을 생성할 수 있습니다.

## 자주 묻는 질문

1. ### Aspose.Slides for .NET은 무료로 사용할 수 있나요?
   아니요, Aspose.Slides for .NET은 상용 라이브러리입니다. 가격 및 라이선스 정보는 여기에서 확인하실 수 있습니다. [여기](https://purchase.aspose.com/buy).

2. ### 내 프로젝트에서 Aspose.Slides for .NET을 사용하려면 특별한 권한이 필요합니까?
   Aspose.Slides for .NET을 사용하려면 유효한 라이선스가 필요합니다. 임시 라이선스를 받을 수 있습니다. [여기](https://purchase.aspose.com/temporary-license/) 평가를 위해.

3. ### .NET용 Aspose.Slides에 대한 지원은 어디에서 찾을 수 있나요?
   기술 지원 및 토론을 위해 Aspose.Slides 포럼을 방문하세요. [여기](https://forum.aspose.com/).

4. ### 구매하기 전에 Aspose.Slides for .NET을 사용해 볼 수 있나요?
   네, Aspose.Slides for .NET의 무료 평가판을 다운로드할 수 있습니다. [여기](https://releases.aspose.com/)체험판에는 제약이 있으니, 귀하의 요구 사항을 충족하는지 꼭 확인해 주시기 바랍니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}