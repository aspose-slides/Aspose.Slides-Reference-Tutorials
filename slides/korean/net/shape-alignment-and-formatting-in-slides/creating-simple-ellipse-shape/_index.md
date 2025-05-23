---
"description": "Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드에 멋진 타원 모양을 만드는 방법을 알아보세요. 역동적인 디자인을 위한 간단한 단계입니다!"
"linktitle": "Aspose.Slides를 사용하여 프레젠테이션 슬라이드에 간단한 타원 모양 만들기"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "Aspose.Slides .NET을 사용하여 타원 모양을 쉽게 만드세요"
"url": "/ko/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides .NET을 사용하여 타원 모양을 쉽게 만드세요

## 소개
역동적인 프레젠테이션 디자인 세계에서 타원과 같은 도형을 사용하면 창의성과 전문성을 더할 수 있습니다. Aspose.Slides for .NET은 프레젠테이션 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드에 간단한 타원 도형을 만드는 과정을 안내합니다.
## 필수 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- .NET용 Aspose.Slides: .NET용 Aspose.Slides 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [릴리스 페이지](https://releases.aspose.com/slides/net/).
- 개발 환경: 컴퓨터에 .NET 개발 환경을 설정합니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 먼저 필요한 네임스페이스를 가져옵니다.
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
이러한 네임스페이스는 프레젠테이션 슬라이드와 도형 작업에 필요한 필수 클래스와 메서드를 제공합니다.
## 1단계: 프레젠테이션 설정
새 프레젠테이션을 만들고 첫 번째 슬라이드에 접근합니다. 다음 코드를 추가하여 이를 구현합니다.
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "Your Document Directory";
// 디렉토리가 없으면 새로 만듭니다.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// 프레젠테이션 클래스 인스턴스화
using (Presentation pres = new Presentation())
{
    // 첫 번째 슬라이드를 받으세요
    ISlide sld = pres.Slides[0];
```
이 코드는 새로운 프레젠테이션을 초기화하고 추가 조작을 위해 첫 번째 슬라이드를 선택합니다.
## 2단계: 타원 모양 추가
이제 다음을 사용하여 슬라이드에 타원 모양을 추가해 보겠습니다. `AddAutoShape` 방법:
```csharp
// 타원 유형의 자동 모양 추가
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
이 코드 줄은 좌표 (50, 150)에 너비가 150단위, 높이가 50단위인 타원 모양을 만듭니다.
## 3단계: 프레젠테이션 저장
마지막으로, 다음 코드를 사용하여 수정된 프레젠테이션을 지정된 파일 이름으로 디스크에 저장합니다.
```csharp
// PPTX 파일을 디스크에 쓰기
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
이 단계를 거치면 변경 사항이 유지되고 새로 추가된 타원 모양으로 결과 프레젠테이션을 볼 수 있습니다.
## 결론
축하합니다! Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드에 간단한 타원 도형을 성공적으로 만들었습니다. 이 튜토리얼에서는 도형 작업, 프레젠테이션 설정, 수정된 파일 저장에 대한 기본적인 내용을 제공합니다.
---
## 자주 묻는 질문
### 타원 모양을 더욱 구체적으로 사용자 지정할 수 있나요?
네, 타원 모양의 다양한 속성(색상, 크기, 위치 등)을 수정하여 특정 디자인 요구 사항을 충족할 수 있습니다.
### Aspose.Slides는 최신 .NET 프레임워크와 호환됩니까?
네, Aspose.Slides는 최신 .NET 프레임워크와의 호환성을 보장하기 위해 정기적으로 업데이트됩니다.
### Aspose.Slides에 대한 더 많은 튜토리얼과 예제는 어디에서 찾을 수 있나요?
방문하세요 [선적 서류 비치](https://reference.aspose.com/slides/net/) 포괄적인 가이드와 예시를 확인하세요.
### Aspose.Slides에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
를 따르세요 [임시 라이센스 링크](https://purchase.aspose.com/temporary-license/) 테스트 목적으로 임시 면허를 요청합니다.
### 도움이 필요하거나 구체적인 질문이 있으신가요?
방문하세요 [Aspose.Slides 지원 포럼](https://forum.aspose.com/c/slides/11) 지역 사회와 전문가로부터 도움을 받으세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}