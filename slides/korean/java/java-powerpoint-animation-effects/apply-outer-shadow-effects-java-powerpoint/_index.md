---
"description": "Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션에 바깥쪽 그림자 효과를 쉽게 적용하는 방법을 자세하고 단계별 가이드를 통해 알아보세요."
"linktitle": "Java PowerPoint에서 바깥쪽 그림자 효과 적용"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java PowerPoint에서 바깥쪽 그림자 효과 적용"
"url": "/ko/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint에서 바깥쪽 그림자 효과 적용

## 소개
매력적인 프레젠테이션을 만들려면 슬라이드의 시각적 매력을 높이기 위해 다양한 효과를 추가해야 하는 경우가 많습니다. 이러한 효과 중 하나는 바깥쪽 그림자로, 요소를 돋보이게 하고 콘텐츠에 깊이감을 더할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 도형에 바깥쪽 그림자 효과를 적용하는 과정을 살펴보겠습니다.
## 필수 조건
단계별 가이드를 살펴보기 전에 필요한 모든 것이 있는지 확인해 보겠습니다.
1. Java Development Kit(JDK): 컴퓨터에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [오라클 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Java 라이브러리용 Aspose.Slides: 최신 버전을 다운로드하세요. [Java용 Aspose.Slides](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA나 Eclipse와 같은 IDE를 사용하여 Java 코드를 작성하고 실행합니다.
4. 유효한 Aspose 라이센스: 다음에서 라이센스를 구매할 수 있습니다. [아스포제](https://purchase.aspose.com/buy) 또는 얻을 [임시 면허](https://purchase.aspose.com/temporary-license/) 평가를 위해.
## 패키지 가져오기
먼저 Aspose.Slides에 필요한 패키지를 가져와야 합니다. 이를 통해 라이브러리가 제공하는 강력한 기능을 활용할 수 있는 기반이 마련됩니다.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
바깥쪽 그림자 효과를 적용하는 과정을 관리 가능한 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 디렉토리 설정
코드 작성을 시작하기 전에 PowerPoint 파일을 저장하고 액세스할 프로젝트 디렉터리를 설정해야 합니다.
프로젝트 디렉터리가 있는지 확인하세요. 없으면 다음 코드를 사용하여 디렉터리를 만드세요.
```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉토리가 없으면 새로 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## 2단계: 프레젠테이션 초기화
이제 모양과 효과를 추가할 프레젠테이션을 초기화해야 합니다.

새 인스턴스를 만듭니다. `Presentation` 새로운 PowerPoint 파일로 작업을 시작하는 수업입니다.
```java
// PPTX 클래스 인스턴스화
Presentation pres = new Presentation();
```
## 3단계: 슬라이드 및 도형 추가
다음으로, 프레젠테이션에 슬라이드를 추가한 다음 그림자 효과를 적용할 도형을 추가합니다.
### 슬라이드에 대한 참조 가져오기
프레젠테이션의 첫 번째 슬라이드에 대한 참조를 검색합니다.
```java
// 슬라이드 참조를 얻으세요
ISlide sld = pres.getSlides().get_Item(0);
```
### 자동 모양 추가
슬라이드의 지정된 좌표에 사각형 자동 모양을 추가합니다.
```java
// 사각형 유형의 자동 도형 추가
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## 4단계: 모양 사용자 지정
도형에 텍스트를 추가하고 채우기 설정을 조정하여 그림자 효과가 더 잘 보이게 하세요.
### 모양에 TextFrame 추가
사각형 모양에 텍스트를 삽입합니다.
```java
// 사각형에 TextFrame 추가
aShp.addTextFrame("Aspose TextBox");
```
### 도형 채우기 비활성화
텍스트 그림자를 강조하기 위해 도형 채우기를 비활성화합니다.
```java
// 텍스트의 그림자를 얻고 싶은 경우 도형 채우기를 비활성화합니다.
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## 5단계: 바깥쪽 그림자 효과 적용
이제 모양에 바깥쪽 그림자 효과를 적용할 차례입니다.
### 외부 그림자 효과 활성화
모양에 대해 바깥쪽 그림자 효과를 활성화합니다.
```java
// 외부 그림자를 추가하고 필요한 모든 매개변수를 설정합니다.
aShp.getEffectFormat().enableOuterShadowEffect();
```
### 그림자 매개변수 구성
그림자의 흐림 반경, 방향, 거리, 정렬, 색상 등 다양한 속성을 설정합니다.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## 6단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 디스크에 저장합니다.
```java
//프레젠테이션을 디스크에 기록하세요
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## 7단계: 리소스 폐기
프레젠테이션 객체를 삭제하여 리소스를 해제하세요.
```java
// 자원 정리
if (pres != null) pres.dispose();
```
## 결론
자, 이제 완성했습니다! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 도형에 외부 그림자 효과를 성공적으로 적용했습니다. 이 효과는 슬라이드의 시각적 효과를 크게 향상시켜 콘텐츠를 더욱 돋보이게 만들어 줍니다.
문제가 발생하거나 추가 지원이 필요한 경우 주저하지 말고 다음을 확인하세요. [Aspose.Slides 문서](https://reference.aspose.com/slides/java/) 또는 방문하세요 [지원 포럼](https://forum.aspose.com/c/slides/11)즐거운 코딩 되세요!
## 자주 묻는 질문
### Java용 Aspose.Slides란 무엇인가요?
Java용 Aspose.Slides는 Java 애플리케이션에서 PowerPoint 프레젠테이션을 만들고, 조작하고, 변환할 수 있는 강력한 라이브러리입니다.
### Java용 Aspose.Slides의 무료 평가판을 받으려면 어떻게 해야 하나요?
무료 평가판을 다운로드할 수 있습니다. [Aspose 웹사이트](https://releases.aspose.com/).
### 모든 IDE에서 Aspose.Slides for Java를 사용할 수 있나요?
네, IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 모든 Java IDE에서 Aspose.Slides for Java를 사용할 수 있습니다.
### Aspose.Slides에 대한 임시 라이선스를 받으려면 어떻게 해야 하나요?
임시면허를 받을 수 있습니다. [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides에 대한 더 많은 예제와 문서는 어디에서 찾을 수 있나요?
더 많은 예와 자세한 문서는 다음에서 찾을 수 있습니다. [Aspose.Slides 문서 페이지](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}