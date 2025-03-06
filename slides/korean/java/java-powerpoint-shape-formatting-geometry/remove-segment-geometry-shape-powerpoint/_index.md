---
title: PowerPoint의 기하학 모양에서 세그먼트 제거
linktitle: PowerPoint의 기하학 모양에서 세그먼트 제거
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 자세한 단계별 가이드를 통해 Java용 Aspose.Slides를 사용하여 PowerPoint의 기하학 모양에서 세그먼트를 제거하는 방법을 알아보세요.
weight: 22
url: /ko/java/java-powerpoint-shape-formatting-geometry/remove-segment-geometry-shape-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
Java를 사용하여 PowerPoint 프레젠테이션의 모양을 조작하려고 하시나요? 당신은 올바른 장소에 왔습니다! Aspose.Slides for Java는 프레젠테이션에서 슬라이드를 쉽게 생성, 수정 및 관리할 수 있는 강력한 API입니다. 이 튜토리얼에서는 PowerPoint의 기하학 모양에서 세그먼트를 제거하는 과정을 안내합니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 가이드는 이 작업을 마스터하기 위한 단계별 접근 방식을 제공합니다. 다이빙할 준비가 되셨나요? 시작하자!
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[오라클 웹사이트](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Java용 Aspose.Slides: 다음 위치에서 Java용 Aspose.Slides 라이브러리를 다운로드하세요.[여기](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA 또는 Eclipse와 같은 IDE를 사용하여 Java 코드를 작성하고 실행합니다.
4. Java의 기본 지식: Java 프로그래밍에 대한 기본 지식은 이 튜토리얼을 따라가는 데 도움이 됩니다.
## 패키지 가져오기
시작하려면 Aspose.Slides 라이브러리에서 필요한 패키지를 가져와야 합니다. 방법은 다음과 같습니다.
```java
import com.aspose.slides.*;

```
PowerPoint 슬라이드의 기하학적 모양에서 세그먼트를 제거하는 과정을 여러 단계로 나누어 보겠습니다.
## 1단계: 새 프레젠테이션 만들기
먼저, 새로운 프리젠테이션 객체를 생성해야 합니다. 이 개체는 슬라이드와 모양의 컨테이너 역할을 합니다.
```java
Presentation pres = new Presentation();
```
## 2단계: 슬라이드에 기하학 도형 추가
다음으로 슬라이드에 기하학 모양을 추가합니다. 이 예에서는 하트 모양을 사용하겠습니다.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Heart, 100, 100, 300, 300);
```
## 3단계: 모양의 형상 경로 검색
모양이 추가되면 해당 형상 경로를 검색해야 합니다. 형상 경로에는 모양을 정의하는 세그먼트가 포함되어 있습니다.
```java
IGeometryPath path = shape.getGeometryPaths()[0];
```
## 4단계: 형상 경로에서 세그먼트 제거
이제 형상 경로에서 특정 세그먼트를 제거하겠습니다. 이 예에서는 인덱스 2의 세그먼트를 제거합니다.
```java
path.removeAt(2);
```
## 5단계: 새 형상 경로 설정
세그먼트를 제거한 후 수정된 형상 경로를 다시 모양으로 설정합니다.
```java
shape.setGeometryPath(path);
```
## 6단계: 프레젠테이션 저장
마지막으로 수정된 프레젠테이션을 파일에 저장합니다.
```java
String resultPath = "Your Output Directory" + "GeometryShapeRemoveSegment.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## 7단계: 리소스 정리
메모리 누수를 방지하려면 항상 리소스를 정리하세요.
```java
if (pres != null) pres.dispose();
```
## 결론
그리고 거기에 있습니다! Aspose.Slides for Java를 사용하면 PowerPoint 프레젠테이션의 모양을 간단하고 효율적으로 조작할 수 있습니다. 이 튜토리얼에 설명된 단계를 따르면 기하학 모양에서 세그먼트를 쉽게 제거하여 슬라이드의 디자인과 기능을 보다 효과적으로 제어할 수 있습니다. 즐거운 코딩하세요!
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 생성, 수정 및 관리하기 위한 강력한 API입니다.
### 하트 모양 외에 다른 모양에도 Aspose.Slides for Java를 사용할 수 있나요?
전적으로! Aspose.Slides for Java는 조작할 수 있는 다양한 모양을 지원합니다.
### Aspose.Slides for Java에 대한 무료 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Aspose.Slides for Java를 사용하려면 라이선스가 필요합니까?
 예, 전체 기능을 사용하려면 라이센스가 필요합니다. 하나 구매하시면 됩니다[여기](https://purchase.aspose.com/buy) 아니면 임시면허를 취득하세요.[여기](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java에 대한 추가 문서는 어디서 찾을 수 있나요?
 포괄적인 문서가 제공됩니다.[여기](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
