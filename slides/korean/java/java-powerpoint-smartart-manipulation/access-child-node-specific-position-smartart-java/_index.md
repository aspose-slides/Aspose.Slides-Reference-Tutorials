---
title: SmartArt의 특정 위치에서 하위 노드에 액세스
linktitle: SmartArt의 특정 위치에서 하위 노드에 액세스
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 이 자세한 가이드를 통해 Java용 Aspose.Slides에서 SmartArt를 조작하는 방법을 알아보세요. 단계별 지침, 예시, 모범 사례가 포함되어 있습니다.
weight: 11
url: /ko/java/java-powerpoint-smartart-manipulation/access-child-node-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
정교한 SmartArt 그래픽을 사용하여 프레젠테이션을 한 단계 더 발전시키고 싶으십니까? 더 이상 보지 마세요! Aspose.Slides for Java는 SmartArt 개체 작업 기능을 포함하여 프레젠테이션 슬라이드를 생성, 조작 및 관리하기 위한 강력한 제품군을 제공합니다. 이 포괄적인 튜토리얼에서는 Aspose.Slides for Java 라이브러리를 사용하여 SmartArt 그래픽 내의 특정 위치에 있는 하위 노드에 액세스하고 조작하는 과정을 안내합니다.

## 전제 조건
시작하기 전에 준비해야 할 몇 가지 전제 조건이 있습니다.
1.  JDK(Java Development Kit): 컴퓨터에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[오라클 JDK 페이지](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java 라이브러리: 다음에서 Aspose.Slides for Java 라이브러리를 다운로드하세요.[다운로드 페이지](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): 원하는 Java IDE를 사용하세요. IntelliJ IDEA, Eclipse 또는 NetBeans는 널리 사용되는 옵션입니다.
4.  Aspose 라이선스: 무료 평가판으로 시작할 수 있지만 전체 기능을 사용하려면[임시면허](https://purchase.aspose.com/temporary-license/) 또는 다음에서 정식 라이센스를 구매하세요.[여기](https://purchase.aspose.com/buy).
## 패키지 가져오기
먼저 Java 프로젝트에 필요한 패키지를 가져옵니다. 이는 Aspose.Slides 기능을 사용하는 데 중요합니다.
```java
import com.aspose.slides.*;
import java.io.File;
```
이제 예제를 세부 단계로 나누어 보겠습니다.
## 1단계: 디렉터리 생성
첫 번째 단계는 프레젠테이션 파일을 저장할 디렉터리를 설정하는 것입니다. 이렇게 하면 애플리케이션에 파일 관리를 위한 지정된 공간이 있습니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉터리가 아직 없으면 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
여기서는 디렉터리가 존재하는지 확인하고, 없으면 생성합니다. 이는 파일 처리 오류를 방지하기 위한 일반적인 모범 사례입니다.
## 2단계: 프레젠테이션 인스턴스화

다음으로 새 프레젠테이션 인스턴스를 만듭니다. 이것은 모든 슬라이드와 모양이 추가될 프로젝트의 백본입니다.
```java
//프레젠테이션 인스턴스화
Presentation pres = new Presentation();
```
이 코드 줄은 Aspose.Slides를 사용하여 새 프레젠테이션 개체를 초기화합니다.
## 3단계: 첫 번째 슬라이드에 액세스

이제 프레젠테이션의 첫 번째 슬라이드에 액세스해야 합니다. 슬라이드는 프레젠테이션의 모든 내용이 배치되는 곳입니다.
```java
// 첫 번째 슬라이드에 액세스하기
ISlide slide = pres.getSlides().get_Item(0);
```
그러면 프레젠테이션의 첫 번째 슬라이드에 액세스하여 콘텐츠를 추가할 수 있습니다.
## 4단계: SmartArt 모양 추가
### SmartArt 도형 추가
다음으로 슬라이드에 SmartArt 도형을 추가하겠습니다. SmartArt는 정보를 시각적으로 표현하는 훌륭한 방법입니다.
```java
// 첫 번째 슬라이드에 SmartArt 도형 추가
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
 여기서는 SmartArt 도형의 위치와 크기를 지정하고 레이아웃 유형을 선택합니다. 이 경우에는`StackedList`.
## 5단계: SmartArt 노드에 액세스

이제 SmartArt 그래픽 내의 특정 노드에 액세스합니다. 노드는 SmartArt 도형 내의 개별 요소입니다.
```java
// 인덱스 0에서 SmartArt 노드에 액세스
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
그러면 SmartArt 그래픽의 첫 번째 노드가 검색되며, 이를 추가로 조작하게 됩니다.
## 6단계: 하위 노드에 액세스

이 단계에서는 상위 노드 내의 특정 위치에 있는 하위 노드에 액세스합니다.
```java
// 상위 노드의 위치 1에 있는 하위 노드에 액세스
int position = 1;
SmartArtNode chNode = (SmartArtNode) node.getChildNodes().get_Item(position);
```
그러면 지정된 위치에서 하위 노드가 검색되어 해당 속성을 조작할 수 있습니다.
## 7단계: 하위 노드 매개변수 인쇄

마지막으로 조작을 검증하기 위해 하위 노드의 매개변수를 인쇄해 보겠습니다.
```java
// SmartArt 하위 노드 매개변수 인쇄
String outString = String.format("j = {0},.Text{1},  Level = {2}, Position = {3}", position, chNode.getTextFrame().getText(), chNode.getLevel(), chNode.getPosition());
System.out.println(outString);
```
이 코드 줄은 텍스트, 수준, 위치 등 하위 노드의 세부 정보를 형식화하고 인쇄합니다.
## 결론
축하해요! Aspose.Slides for Java를 사용하여 SmartArt 그래픽 내의 하위 노드에 성공적으로 액세스하고 조작했습니다. 이 가이드에서는 프로젝트 설정, SmartArt 추가 및 해당 노드 조작을 단계별로 안내했습니다. 이러한 지식을 바탕으로 이제 더욱 역동적이고 시각적으로 매력적인 프레젠테이션을 만들 수 있습니다.
 더 많은 고급 기능을 읽고 살펴보려면 다음을 확인하세요.[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/) 질문이 있거나 지원이 필요한 경우,[Aspose 커뮤니티 포럼](https://forum.aspose.com/c/slides/11) 도움을 구하기에 좋은 곳입니다.
## FAQ
### Java용 Aspose.Slides를 어떻게 설치하나요?
 다음에서 다운로드할 수 있습니다.[다운로드 페이지](https://releases.aspose.com/slides/java/) 제공된 설치 지침을 따르십시오.
### 구매하기 전에 Java용 Aspose.Slides를 사용해 볼 수 있나요?
 예, 다음을 얻을 수 있습니다.[무료 시험판](https://releases.aspose.com/) 또는[임시면허](https://purchase.aspose.com/temporary-license/) 기능을 테스트합니다.
### Aspose.Slides에서는 어떤 유형의 SmartArt 레이아웃을 사용할 수 있나요?
 Aspose.Slides는 List, Process, Cycle, Hierarchy 등과 같은 다양한 SmartArt 레이아웃을 지원합니다. 자세한 정보는 에서 확인하실 수 있습니다.[선적 서류 비치](https://reference.aspose.com/slides/java/).
### Java용 Aspose.Slides에 대한 지원을 받으려면 어떻게 해야 하나요?
 에서 지원을 받으실 수 있습니다.[Aspose 커뮤니티 포럼](https://forum.aspose.com/c/slides/11) 또는 광범위한 내용을 참조하십시오.[선적 서류 비치](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java의 정식 라이선스를 구입할 수 있나요?
 예, 다음에서 정식 라이센스를 구입할 수 있습니다.[구매 페이지](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
