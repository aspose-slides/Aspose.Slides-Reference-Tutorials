---
"date": "2025-04-16"
"description": "Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션에서 동적 표와 도형을 만드는 방법을 알아보세요. 시각적 효과를 높이는 단계별 가이드를 따라해 보세요."
"title": "Aspose.Slides for .NET을 사용하여 PowerPoint에서 표와 도형 만들기 - 단계별 가이드"
"url": "/ko/net/shapes-text-frames/aspose-slides-dotnet-table-shape-creation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET을 사용하여 PowerPoint에서 표와 도형 만들기: 단계별 가이드

## 소개

C#과 Aspose.Slides for .NET을 사용하여 동적 표를 만들거나 텍스트 주위에 도형을 그려 PowerPoint 프레젠테이션을 더욱 풍성하게 만들어 보세요. 이 가이드에서는 표 생성 및 도형 그리기 기능을 구현하는 과정을 안내하여 슬라이드를 더욱 유익하고 시각적으로 매력적으로 만들어 드립니다.

이 튜토리얼에서는 다음 내용을 다룹니다.
- PowerPoint 프레젠테이션에서 표 만들기
- 텍스트 부분이 있는 단락을 표 셀에 추가
- 모양 내에 텍스트 프레임 포함
- 특정 텍스트 요소 주위에 사각형 그리기

이 가이드를 마치면 Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드를 더욱 멋지게 만들 수 있을 것입니다. 먼저 필수 구성 요소를 살펴보겠습니다.

### 필수 조건

이 튜토리얼을 따라하려면 다음 사항이 있는지 확인하세요.
- **개발 환경**: Visual Studio가 컴퓨터에 설치되어 있어야 합니다.
- **.NET용 Aspose.Slides 라이브러리**: 22.x 버전 이상을 사용하겠습니다.
- **기본 C# 지식**: C# 구문과 개념에 대한 익숙함이 필요합니다.

## .NET용 Aspose.Slides 설정

코딩을 시작하기 전에 프로젝트에 Aspose.Slides 라이브러리를 설정해 보겠습니다. 설치하는 방법은 여러 가지가 있습니다.

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**패키지 관리자 콘솔**
```powershell
Install-Package Aspose.Slides
```

**NuGet 패키지 관리자 UI**: "Aspose.Slides"를 검색하고 설치 버튼을 클릭합니다.

### 라이센스 취득

무료 체험판 라이선스로 모든 기능을 체험해 보세요. 장기 사용을 원하시면 임시 라이선스 또는 구매 라이선스를 구매하실 수 있습니다. [Aspose 웹사이트](https://purchase.aspose.com/buy).

설치가 완료되면 다음을 추가하여 프로젝트에서 Aspose.Slides를 초기화합니다.

```csharp
using Aspose.Slides;
```

## 구현 가이드

### 슬라이드에 표 만들기

**개요:**
데이터를 명확하게 표현해야 할 때 표를 만드는 것은 필수적입니다. Aspose.Slides를 사용하면 표의 크기와 위치를 쉽게 정의할 수 있습니다.

#### 1단계: 프레젠테이션 초기화
인스턴스를 생성하여 시작하세요. `Presentation` 수업:

```csharp
Presentation pres = new Presentation();
```

#### 2단계: 테이블 추가
사용하세요 `AddTable` 슬라이드에 표를 추가하는 방법입니다. 행과 열의 위치와 크기를 지정하세요.

```csharp
ITable tbl = pres.Slides[0].Shapes.AddTable(50, 50, new double[] { 50, 70 }, new double[] { 50, 50, 50 });
```

**매개변수 설명:**
- `50, 50`: 좌측 상단 모서리의 X 및 Y 좌표입니다.
- 배열은 열 너비와 행 높이를 지정합니다.

#### 3단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 저장합니다.

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY/CreateTable_Out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}