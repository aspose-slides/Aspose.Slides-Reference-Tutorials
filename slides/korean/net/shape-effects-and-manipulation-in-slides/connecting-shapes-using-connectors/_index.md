---
title: Aspose.Slides - .NET에서 모양을 원활하게 연결
linktitle: 프레젠테이션에서 커넥터를 사용하여 도형 연결
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: 프레젠테이션에서 모양을 쉽게 연결하는 Aspose.Slides for .NET의 강력한 기능을 살펴보세요. 동적 커넥터로 슬라이드를 향상시키세요.
weight: 29
url: /ko/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
역동적인 프레젠테이션 세계에서 연결선을 사용하여 셰이프를 연결하는 기능은 슬라이드에 정교함을 더해줍니다. .NET용 Aspose.Slides는 개발자가 이를 원활하게 달성할 수 있도록 지원합니다. 이 튜토리얼에서는 프로세스를 안내하고 각 단계를 세분화하여 명확한 이해를 보장합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.
- C# 및 .NET 프레임워크에 대한 기본 지식
-  .NET용 Aspose.Slides가 설치되었습니다. 그렇지 않은 경우 다운로드하십시오.[여기](https://releases.aspose.com/slides/net/).
- 개발 환경이 설정되었습니다.
## 네임스페이스 가져오기
C# 코드에서 필요한 네임스페이스를 가져오는 것부터 시작하세요.
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. 문서 디렉토리 설정
문서의 디렉터리를 정의하는 것부터 시작하세요.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. 프레젠테이션 클래스 인스턴스화
PPTX 파일을 나타내는 Presentation 클래스의 인스턴스를 만듭니다.
```csharp
using (Presentation input = new Presentation())
{
    // 선택한 슬라이드의 도형 컬렉션에 액세스 중
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. 슬라이드에 도형 추가
타원, 직사각형 등 필요한 모양을 슬라이드에 추가합니다.
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. 커넥터 모양 추가
슬라이드의 모양 컬렉션에 연결선 모양을 포함합니다.
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. 커넥터를 사용하여 셰이프 연결
커넥터로 연결할 셰이프를 지정합니다.
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. 커넥터 경로 재지정
도형 사이의 자동 최단 경로를 설정하려면 reroute 메서드를 호출하세요.
```csharp
connector.Reroute();
```
## 7. 프레젠테이션 저장
연결된 셰이프를 보려면 프레젠테이션을 저장하세요.
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 결론
축하해요! Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드의 커넥터를 사용하여 모양을 성공적으로 연결했습니다. 이 고급 기능으로 프레젠테이션을 향상하고 청중을 사로잡으세요.
## 자주 묻는 질문
### Aspose.Slides for .NET은 최신 .NET 프레임워크와 호환됩니까?
예, .NET용 Aspose.Slides는 최신 .NET 프레임워크 버전과의 호환성을 보장하기 위해 정기적으로 업데이트됩니다.
### 단일 연결선을 사용하여 두 개 이상의 셰이프를 연결할 수 있나요?
물론, 코드에서 연결선 논리를 확장하여 여러 셰이프를 연결할 수 있습니다.
### 연결할 수 있는 셰이프에 제한이 있나요?
Aspose.Slides for .NET은 기본 도형, 스마트 아트, 사용자 정의 도형을 포함한 다양한 도형 연결을 지원합니다.
### 커넥터의 모양을 어떻게 사용자 정의할 수 있나요?
선 스타일 및 색상과 같은 커넥터 모양을 사용자 정의하는 방법에 대해서는 Aspose.Slides 설명서를 살펴보세요.
### Aspose.Slides 지원을 위한 커뮤니티 포럼이 있습니까?
 예, 다음에서 도움을 받고 경험을 공유할 수 있습니다.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
