---
title: Aspose.Slides를 사용하여 PowerPoint에서 커넥터 선 각도 조정
linktitle: Aspose.Slides를 사용하여 프레젠테이션 슬라이드의 커넥터 선 각도 조정
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: Aspose.Slides for .NET을 사용하여 PowerPoint 슬라이드에서 연결선 각도를 조정하는 방법을 알아보세요. 정확하고 쉽게 프레젠테이션을 향상시켜 보세요.
weight: 28
url: /ko/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides를 사용하여 PowerPoint에서 커넥터 선 각도 조정

## 소개
시각적으로 매력적인 프레젠테이션 슬라이드를 만들려면 연결선을 정밀하게 조정해야 하는 경우가 많습니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드에서 연결선 각도를 조정하는 방법을 살펴보겠습니다. Aspose.Slides는 개발자가 프로그래밍 방식으로 PowerPoint 파일을 작업할 수 있도록 하는 강력한 라이브러리로, 프레젠테이션 생성, 수정 및 조작을 위한 광범위한 기능을 제공합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
- C# 프로그래밍 언어에 대한 기본 지식.
- Visual Studio 또는 기타 C# 개발 환경이 설치되어 있습니다.
-  .NET 라이브러리용 Aspose.Slides. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/slides/net/).
- 조정하려는 연결선이 포함된 PowerPoint 프레젠테이션 파일.
## 네임스페이스 가져오기
시작하려면 C# 코드에 필요한 네임스페이스를 포함해야 합니다.
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## 1단계: 프로젝트 설정
Visual Studio에서 새 C# 프로젝트를 만들고 Aspose.Slides NuGet 패키지를 설치합니다. Aspose.Slides 라이브러리를 참조하여 프로젝트 구조를 설정합니다.
## 2단계: 프레젠테이션 로드
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
 PowerPoint 프리젠테이션 파일을`Presentation`물체. "문서 디렉토리"를 파일의 실제 경로로 바꾸십시오.
## 3단계: 슬라이드 및 셰이프에 액세스
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
프레젠테이션의 첫 번째 슬라이드에 액세스하고 슬라이드의 모양을 나타내는 변수를 초기화합니다.
## 4단계: 모양 반복
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // 연결선 처리 코드
}
```
슬라이드의 각 모양을 반복하여 연결선을 식별하고 처리합니다.
## 5단계: 커넥터 선 각도 조정
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // AutoShapes 처리를 위한 코드
}
else if (shape is Connector)
{
    // 커넥터 처리 코드
}
Console.WriteLine(dir);
```
 모양이 AutoShape인지 연결선인지 확인하고 제공된 도구를 사용하여 연결선 각도를 조정합니다.`getDirection` 방법.
##  6단계: 정의`getDirection` Method
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // 방향 계산 코드
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
 구현`getDirection` 치수와 방향을 기준으로 연결선의 각도를 계산하는 방법입니다.
## 결론
이 단계를 통해 Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션의 연결선 각도를 프로그래밍 방식으로 조정할 수 있습니다. 이 튜토리얼은 슬라이드의 시각적 매력을 향상시키기 위한 기초를 제공합니다.
## 자주 묻는 질문
### Aspose.Slides는 Windows와 웹 애플리케이션 모두에 적합합니까?
예, Aspose.Slides는 Windows와 웹 애플리케이션 모두에서 사용할 수 있습니다.
### 구매하기 전에 Aspose.Slides 무료 평가판을 다운로드할 수 있나요?
 예, 무료 평가판을 다운로드할 수 있습니다[여기](https://releases.aspose.com/).
### .NET용 Aspose.Slides에 대한 포괄적인 문서는 어디서 찾을 수 있나요?
 문서를 사용할 수 있습니다[여기](https://reference.aspose.com/slides/net/).
### Aspose.Slides의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides에 대한 지원 포럼이 있습니까?
 예, 지원 포럼을 방문하실 수 있습니다[여기](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
