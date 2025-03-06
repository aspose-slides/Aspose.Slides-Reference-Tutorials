---
title: Java PowerPoint에서 텍스트를 수직으로 정렬
linktitle: Java PowerPoint에서 텍스트를 수직으로 정렬
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 원활한 슬라이드 서식을 위해 Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션에서 텍스트를 수직으로 정렬하는 방법을 알아보세요.
weight: 10
url: /ko/java/java-powerpoint-text-alignment-formatting/vertically-align-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 표 셀 내에서 텍스트를 수직으로 정렬하는 방법을 배웁니다. 텍스트를 수직으로 정렬하는 것은 슬라이드 디자인의 중요한 측면으로, 콘텐츠가 깔끔하고 전문적으로 표시되도록 보장합니다. Aspose.Slides는 프레젠테이션을 프로그래밍 방식으로 조작하고 형식을 지정하는 강력한 기능을 제공하여 슬라이드의 모든 측면을 완벽하게 제어할 수 있습니다.
## 전제 조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
- 컴퓨터에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
- IntelliJ IDEA 또는 Eclipse와 같은 IDE(통합 개발 환경)가 설치되어 있습니다.

## 패키지 가져오기
튜토리얼을 진행하기 전에 필요한 Aspose.Slides 패키지를 Java 파일로 가져와야 합니다.
```java
import com.aspose.slides.*;
import java.awt.*;
```
## 1단계: Java 프로젝트 설정
선호하는 IDE에서 새 Java 프로젝트를 설정하고 Aspose.Slides 라이브러리를 프로젝트의 빌드 경로에 추가했는지 확인하세요.
## 2단계: 프레젠테이션 개체 초기화
 인스턴스를 생성합니다.`Presentation` 새로운 PowerPoint 프레젠테이션 작업을 시작하는 수업:
```java
Presentation presentation = new Presentation();
```
## 3단계: 첫 번째 슬라이드에 액세스
콘텐츠를 추가하려면 프레젠테이션의 첫 번째 슬라이드를 가져오세요.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## 4단계: 테이블 차원 정의 및 테이블 추가
표의 열 너비와 행 높이를 정의한 다음 슬라이드에 표 모양을 추가합니다.
```java
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};
ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## 5단계: 표 셀에 텍스트 내용 설정
테이블의 특정 행에 대한 텍스트 내용을 설정합니다.
```java
tbl.getRows().get_Item(1).get_Item(0).getTextFrame().setText("10");
tbl.getRows().get_Item(2).get_Item(0).getTextFrame().setText("20");
tbl.getRows().get_Item(3).get_Item(0).getTextFrame().setText("30");
```
## 6단계: 텍스트 프레임에 액세스하고 텍스트 서식 지정
텍스트 프레임에 액세스하고 특정 셀 내의 텍스트 서식을 지정합니다.
```java
ITextFrame txtFrame = tbl.get_Item(0, 0).getTextFrame();
IParagraph paragraph = txtFrame.getParagraphs().get_Item(0);
IPortion portion = paragraph.getPortions().get_Item(0);
portion.setText("Text here");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## 7단계: 텍스트를 세로로 정렬
셀 내 텍스트의 수직 정렬을 설정합니다.
```java
ICell cell = tbl.get_Item(0, 0);
cell.setTextAnchorType(TextAnchorType.Center);
cell.setTextVerticalType(TextVerticalType.Vertical270);
```
## 8단계: 프레젠테이션 저장
수정된 프레젠테이션을 디스크의 지정된 위치에 저장합니다.
```java
String dataDir = "Your Document Directory";
presentation.save(dataDir + "Vertical_Align_Text_out.pptx", SaveFormat.Pptx);
```
## 9단계: 리소스 정리
 처분하다`Presentation` 자원을 해제할 객체:
```java
if (presentation != null) presentation.dispose();
```

## 결론
다음 단계를 수행하면 Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 표 셀 내에서 텍스트를 효과적으로 수직으로 정렬할 수 있습니다. 이 기능은 슬라이드의 시각적 매력과 명확성을 향상시켜 콘텐츠가 전문적으로 표시되도록 합니다.

## FAQ
### 표 외에 다른 도형의 텍스트를 세로로 정렬할 수 있나요?
예, Aspose.Slides는 텍스트 상자 및 자리 표시자를 포함한 다양한 모양의 텍스트를 수직으로 정렬하는 방법을 제공합니다.
### Aspose.Slides는 텍스트 수평 정렬도 지원합니까?
예, Aspose.Slides에서 제공하는 다양한 정렬 옵션을 사용하여 텍스트를 가로로 정렬할 수 있습니다.
### Aspose.Slides는 모든 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 Microsoft PowerPoint의 모든 주요 버전과 호환되는 프레젠테이션 생성을 지원합니다.
### Aspose.Slides에 대한 추가 예제와 문서는 어디서 찾을 수 있나요?
 방문하다[Aspose.Slides 문서](https://reference.aspose.com/slides/java/) 포괄적인 가이드, API 참조 및 코드 샘플을 확인하세요.
### Aspose.Slides에 대한 지원은 어떻게 받을 수 있나요?
 기술 지원 및 커뮤니티 지원을 받으려면 다음을 방문하세요.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
