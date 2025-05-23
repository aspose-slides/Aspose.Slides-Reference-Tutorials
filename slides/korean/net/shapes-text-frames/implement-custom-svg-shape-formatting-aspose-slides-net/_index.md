---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드에서 SVG 도형의 서식을 지정하고 고유하게 식별하는 방법을 알아보세요. 이 가이드에서는 사용자 지정 SVG 도형 서식 컨트롤러의 설정, 구현 및 실제 적용 방법을 다룹니다."
"title": "Aspose.Slides for .NET에서 사용자 지정 SVG 모양 서식을 구현하는 방법"
"url": "/ko/net/shapes-text-frames/implement-custom-svg-shape-formatting-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET에서 사용자 지정 SVG 모양 서식을 구현하는 방법

## 소개

프레젠테이션 슬라이드 내에서 SVG 도형을 관리하고 고유하게 식별하는 것은 어려울 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 사용자 지정 SVG 도형 서식 컨트롤러를 만드는 방법을 안내합니다. 이 기능을 구현하면 각 SVG 도형이 시퀀스의 인덱스를 기반으로 고유 ID를 부여받아 명확한 식별과 구성을 보장합니다.

이 튜토리얼에서는 다음 내용을 다룹니다.
- Aspose.Slides를 사용하여 환경 설정하기
- 구현 `CustomSvgShapeFormattingController` 수업
- 귀하의 프로젝트에 대한 실용적인 응용 프로그램

Aspose.Slides를 사용하여 .NET 애플리케이션을 개선해 보세요. 시작하기 전에 필수 조건을 충족하는지 확인하세요.

## 필수 조건

Aspose.Slides를 사용하여 사용자 정의 SVG 모양 서식을 구현하려면 다음이 필요합니다.
- **필수 라이브러리**: Aspose.Slides for .NET(버전 22.x 이상)이 필요합니다.
- **환경 설정**: .NET Core 또는 .NET Framework(버전 4.6.1 이상)로 설정된 개발 환경입니다.
- **지식 전제 조건**C#에 익숙하고 SVG 파일을 다루는 기본 개념이 필요합니다.

필수 구성 요소를 확인했으므로 이제 .NET용 Aspose.Slides를 설정해 보겠습니다.

## .NET용 Aspose.Slides 설정

Aspose.Slides를 사용하려면 프로젝트에 종속성으로 추가하세요. 설치하는 방법은 다음과 같습니다.

### .NET CLI 사용
```bash
dotnet add package Aspose.Slides
```

### 패키지 관리자 콘솔 사용
```powershell
Install-Package Aspose.Slides
```

### NuGet 패키지 관리자 UI를 통해
IDE 내 NuGet 패키지 관리자에서 "Aspose.Slides"를 검색하여 최신 버전을 설치하세요.

설치 후 라이선스를 취득하세요. 테스트 목적으로는 웹사이트에서 제공되는 무료 체험판을 사용하세요. 모든 기능을 사용하려면 라이선스를 구매하거나 Aspose 구매 포털을 통해 임시 라이선스를 신청하세요.

### 기본 초기화

설치가 완료되면 애플리케이션에서 Aspose.Slides를 초기화합니다.
```csharp
// Presentation 클래스의 인스턴스를 생성합니다.
var presentation = new Presentation();
```

## 구현 가이드

이제 Aspose.Slides를 설정했으므로 사용자 정의 SVG 모양 포맷 컨트롤러를 구현해 보겠습니다.

### 개요 `CustomSvgShapeFormattingController`

그만큼 `CustomSvgShapeFormattingController` 는 다음을 구현하는 클래스입니다. `ISvgShapeFormattingController` 인터페이스입니다. 주요 목적은 인덱스 순서를 기반으로 프레젠테이션의 각 SVG 모양에 고유한 ID를 할당하는 것입니다.

#### 1단계: 모양 인덱스 초기화
```csharp
private int m_shapeIndex;
```
이 개인 정수 변수는 `m_shapeIndex`, 모양에 이름을 지정하기 위한 현재 인덱스를 추적합니다.

### 단계별 구현

구현 과정의 각 부분을 나누어 보겠습니다.

#### 생성자 설정
먼저, 선택적인 시작점으로 모양 인덱스를 초기화합니다.
```csharp
public CustomSvgShapeFormattingController(int shapeStartIndex = 0)
{
    m_shapeIndex = shapeStartIndex;
}
```
**왜**: 이 생성자를 사용하면 필요한 경우 특정 인덱스부터 도형의 이름을 지정할 수 있습니다. 기본값은 0으로 설정되어 시퀀스 관리에 유연성을 제공합니다.

#### SVG 모양 서식 지정
핵심 기능은 다음과 같습니다. `FormatShape` 방법:
```csharp
public void FormatShape(ISvgShape svgShape, IShape shape)
{
    // 인덱스를 기반으로 고유 ID를 할당합니다.
    svgShape.Id = string.Format("shape-{0}\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}