---
"date": "2025-04-16"
"description": "Aspose.Slides for .NET을 사용하여 PowerPoint 슬라이드에 콘텐츠, 세로 텍스트, 차트 및 표 자리 표시자를 효율적으로 추가하는 방법을 알아보세요."
"title": "Aspose.Slides를 사용하여 .NET 슬라이드에 자리 표시자를 추가하는 방법"
"url": "/ko/net/shapes-text-frames/add-placeholders-in-dotnet-slides-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides를 사용하여 .NET 슬라이드에 자리 표시자를 추가하는 방법

## 소개

프레젠테이션에 콘텐츠, 세로 텍스트, 차트, 표 등의 자리 표시자를 자동으로 추가하는 효율적인 방법을 찾고 계신가요? Aspose.Slides for .NET을 사용하면 이 과정이 훨씬 수월해집니다. 이 튜토리얼에서는 Aspose.Slides를 사용하여 .NET 환경에서 PowerPoint 슬라이드에 자리 표시자를 간편하게 추가하는 방법을 안내합니다.

이 포괄적인 가이드에서는 다음 내용을 살펴보겠습니다.
- .NET용 Aspose.Slides 설정
- 다양한 플레이스홀더를 추가하기 위한 단계별 지침
- 이러한 기능의 실제 적용
- 최적의 사용을 위한 성능 고려 사항

## 필수 조건

### 필수 라이브러리 및 버전
이 튜토리얼을 따르려면 다음 사항이 필요합니다.
- .NET 라이브러리 버전 22.x 이상용 Aspose.Slides.
- 호환되는 .NET 환경(예: .NET Core 3.1 이상).

### 환경 설정 요구 사항
개발 환경이 Visual Studio나 .NET 프로젝트를 지원하는 다른 IDE로 설정되어 있는지 확인하세요.

### 지식 전제 조건
C#에 대한 기본 지식과 .NET 프로그래밍 개념에 대한 친숙함은 유익하지만 필수는 아닙니다. 과정을 따라가면서 기본 사항을 모두 다루기 때문입니다.

## .NET용 Aspose.Slides 설정
프로젝트에서 Aspose.Slides를 사용하려면 먼저 설치해야 합니다. 설치 방법은 다음과 같습니다.

**.NET CLI 사용:**
```bash
dotnet add package Aspose.Slides
```

**패키지 관리자 콘솔 사용:**
```powershell
Install-Package Aspose.Slides
```

**NuGet 패키지 관리자 UI:**
"Aspose.Slides"를 검색하여 최신 버전을 설치하세요.

### 라이센스 취득
Aspose.Slides를 사용해 보려면 무료 체험판을 이용하거나 임시 라이선스를 구매하세요. 프로덕션 환경에서 사용하려면 정식 라이선스 구매를 고려해 보세요. [Aspose 구매 페이지](https://purchase.aspose.com/buy) 라이선싱 옵션에 대해 자세히 알아보세요.

#### 기본 초기화
인스턴스를 생성하여 프로젝트를 초기화하세요. `Presentation` 수업:
```csharp
using Aspose.Slides;
// ...
var presentation = new Presentation();
```

## 구현 가이드

### 콘텐츠 자리 표시자 추가
콘텐츠 자리 표시자를 추가하면 슬라이드에 텍스트, 이미지 및 기타 미디어를 삽입할 수 있습니다. Aspose.Slides for .NET을 사용하여 삽입하는 방법은 다음과 같습니다.

#### 개요
이 섹션에서는 Aspose.Slides for .NET을 사용하여 빈 슬라이드 레이아웃에 콘텐츠 자리 표시자를 추가하는 과정을 안내합니다.

#### 구현 단계
**1. 프로젝트 설정**
앞서 언급한 대로 새로운 C# 프로젝트를 만들고 Aspose.Slides 라이브러리를 설치하는 것으로 시작합니다.

**2. 프레젠테이션 초기화**
인스턴스를 생성합니다 `Presentation` 슬라이드 작업:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "content_placeholder.pptx");

using (var pres = new Presentation())
{
    // 여기에 코드가 추가됩니다.
}
```
**3. 레이아웃 슬라이드 접근**
자리 표시자를 추가할 빈 레이아웃 슬라이드를 검색합니다.
```csharp
// 빈 레이아웃 슬라이드를 가져옵니다.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
이 단계에서는 사용자 정의 디자인에 적합한 미리 정의된 빈 레이아웃에 액세스합니다.

**4. 콘텐츠 자리 표시자 추가**
사용하세요 `PlaceholderManager` 지정된 좌표와 크기에 콘텐츠 자리 표시자를 삽입하려면:
```csharp
// 레이아웃 슬라이드의 플레이스홀더 관리자를 가져옵니다.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// 위치(10, 10)에 크기(300x200)의 콘텐츠 자리 표시자를 추가합니다.
placeholderManager.AddContentPlaceholder(10, 10, 300, 200);
```
매개변수는 위치를 정의합니다. `(x, y)` 및 치수 `(width x height)` 플레이스홀더의.

**5. 프레젠테이션 저장**
마지막으로 프레젠테이션 파일을 저장합니다.
```csharp
// 추가된 콘텐츠 자리 표시자와 함께 프레젠테이션을 저장합니다.
pres.Save(outFilePath, SaveFormat.Pptx);
```
이렇게 하면 수정된 레이아웃이 지정된 디렉토리에 저장됩니다.

### 세로 텍스트 자리 표시자 추가
세로 텍스트 자리 표시자는 텍스트 방향을 변경해야 하는 사이드바나 고유한 디자인 요소에 적합합니다.

#### 개요
이 섹션에서는 슬라이드의 미적 감각을 향상시키기 위해 세로 텍스트 자리 표시자를 추가하는 방법을 알아봅니다.

#### 구현 단계
**1. 프레젠테이션 초기화**
새 인스턴스를 만듭니다. `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "vertical_text_placeholder.pptx");

using (var pres = new Presentation())
{
    // 여기에 코드가 추가됩니다.
}
```
**2. 레이아웃 슬라이드 접근**
빈 레이아웃 슬라이드를 검색합니다.
```csharp
// 빈 레이아웃 슬라이드를 가져옵니다.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. 세로 텍스트 자리 표시자 추가**
다음을 사용하여 세로 텍스트 자리 표시자를 추가합니다. `PlaceholderManager`:
```csharp
// 레이아웃 슬라이드의 플레이스홀더 관리자를 가져옵니다.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// 위치(350, 10)에 크기(200x300)의 세로 텍스트 자리 표시자를 추가합니다.
placeholderManager.AddVerticalTextPlaceholder(350, 10, 200, 300);
```
**4. 프레젠테이션 저장**
프레젠테이션을 저장하세요:
```csharp
// 세로 텍스트 자리 표시자를 추가하여 프레젠테이션을 저장합니다.
pres.Save(outFilePath, SaveFormat.Pptx);
```

### 차트 자리 표시자 추가
차트는 프레젠테이션에서 데이터를 표현하는 데 매우 중요합니다. Aspose.Slides를 사용하여 차트 자리 표시자를 추가하는 방법은 다음과 같습니다.

#### 개요
이 섹션에서는 Aspose.Slides를 사용하여 PowerPoint 슬라이드에 차트 자리 표시자를 통합하는 방법을 설명합니다.

#### 구현 단계
**1. 프레젠테이션 초기화**
인스턴스를 생성합니다 `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "chart_placeholder.pptx");

using (var pres = new Presentation())
{
    // 여기에 코드가 추가됩니다.
}
```
**2. 레이아웃 슬라이드 접근**
빈 레이아웃 슬라이드를 검색합니다.
```csharp
// 빈 레이아웃 슬라이드를 가져옵니다.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. 차트 자리 표시자 추가**
사용 `PlaceholderManager` 차트 자리 표시자를 추가하려면:
```csharp
// 레이아웃 슬라이드의 플레이스홀더 관리자를 가져옵니다.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// 위치(10, 350)에 크기(300x300)의 차트 자리 표시자를 추가합니다.
placeholderManager.AddChartPlaceholder(10, 350, 300, 300);
```
**4. 프레젠테이션 저장**
프레젠테이션을 저장하세요:
```csharp
// 차트 자리 표시자를 추가하여 프레젠테이션을 저장합니다.
pres.Save(outFilePath, SaveFormat.Pptx);
```

### 테이블 자리 표시자 추가
표는 데이터를 효과적으로 구성하며, 명확성을 위해 프레젠테이션에 자주 사용됩니다.

#### 개요
Aspose.Slides를 사용하여 슬라이드에 정보를 깔끔하게 구성하기 위한 테이블 자리 표시자를 추가하는 방법을 알아보세요.

#### 구현 단계
**1. 프레젠테이션 초기화**
인스턴스를 생성합니다 `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "table_placeholder.pptx");

using (var pres = new Presentation())
{
    // 여기에 코드가 추가됩니다.
}
```
**2. 레이아웃 슬라이드 접근**
빈 레이아웃 슬라이드를 검색합니다.
```csharp
// 빈 레이아웃 슬라이드를 가져옵니다.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. 테이블 자리 표시자 추가**
사용 `PlaceholderManager` 테이블 자리 표시자를 추가하려면:
```csharp
// 레이아웃 슬라이드의 플레이스홀더 관리자를 가져옵니다.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// 위치(350, 350)에 크기(300x200)의 테이블 자리 표시자를 추가합니다.
placeholderManager.AddTablePlaceholder(350, 350, 300, 200);
```
**4. 프레젠테이션 저장**
프레젠테이션을 저장하세요:
```csharp
// 테이블 자리 표시자를 추가하여 프레젠테이션을 저장합니다.
pres.Save(outFilePath, SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}