---
title: Java PowerPoint에서 단락 그림 글머리 기호 관리
linktitle: Java PowerPoint에서 단락 그림 글머리 기호 관리
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드에 사용자 정의 그림 글머리 기호를 추가하는 방법을 알아보세요. 원활한 통합을 위해 자세한 단계별 가이드를 따르세요.
type: docs
weight: 11
url: /ko/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---
## 소개
매력적이고 시각적으로 매력적인 프레젠테이션을 만드는 것은 현대 비즈니스 세계에서 중요한 기술입니다. Java 개발자는 Aspose.Slides를 활용하여 PowerPoint 슬라이드의 사용자 정의된 그림 글머리 기호로 프레젠테이션을 향상할 수 있습니다. 이 튜토리얼에서는 프레젠테이션에 그림 글머리 기호를 자신있게 추가할 수 있도록 프로세스를 단계별로 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- JDK(Java 개발 키트)가 설치되었습니다.
- Eclipse 또는 IntelliJ IDEA와 같은 통합 개발 환경(IDE)
- Aspose.Slides for Java 라이브러리
- Java 프로그래밍에 대한 기본 지식
- 총알 사진의 이미지 파일
 Java 라이브러리용 Aspose.Slides를 다운로드하려면 다음을 방문하세요.[다운로드 페이지](https://releases.aspose.com/slides/java/) . 문서를 확인하려면 다음을 확인하세요.[선적 서류 비치](https://reference.aspose.com/slides/java/).
## 패키지 가져오기
먼저 프로젝트에 필요한 패키지를 가져왔는지 확인하세요. Java 파일 시작 부분에 다음 가져오기를 추가합니다.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
프로세스를 관리 가능한 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 디렉터리 설정
프로젝트에 대한 새 디렉터리를 만듭니다. 이 디렉토리에는 Java 파일, Aspose.Slides 라이브러리 및 글머리 기호의 이미지 파일이 포함됩니다.
```java
String dataDir = "Your Document Directory";
```
## 2단계: 프레젠테이션 초기화
 새 인스턴스를 초기화합니다.`Presentation` 수업. 이 개체는 PowerPoint 프레젠테이션을 나타냅니다.
```java
Presentation presentation = new Presentation();
```
## 3단계: 첫 번째 슬라이드에 액세스
프레젠테이션의 첫 번째 슬라이드에 액세스합니다. 슬라이드의 색인은 0이므로 첫 번째 슬라이드의 색인은 0입니다.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## 4단계: 글머리 기호 이미지 로드
글머리 기호에 사용할 이미지를 로드합니다. 이 이미지는 프로젝트 디렉터리에 배치되어야 합니다.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## 5단계: 슬라이드에 도형 추가
슬라이드에 도형을 추가합니다. 모양에는 사용자 정의 글머리 기호가 있는 텍스트가 포함됩니다.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## 6단계: 텍스트 프레임에 액세스
단락을 조작하려면 도형의 텍스트 프레임에 액세스하세요.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## 7단계: 기본 단락 제거
텍스트 프레임에 자동으로 추가된 기본 단락을 제거합니다.
```java
textFrame.getParagraphs().removeAt(0);
```
## 8단계: 새 단락 만들기
새 단락을 만들고 텍스트를 설정합니다. 이 단락에는 사용자 정의 그림 글머리 기호가 포함됩니다.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## 9단계: 글머리 기호 스타일 및 이미지 설정
이전에 로드한 사용자 정의 이미지를 사용하도록 글머리 기호 스타일을 설정합니다.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## 10단계: 총알 높이 조정
프레젠테이션에서 보기 좋게 보이도록 글머리 기호의 높이를 설정합니다.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## 11단계: 텍스트 프레임에 단락 추가
도형의 텍스트 프레임에 새로 생성된 단락을 추가합니다.
```java
textFrame.getParagraphs().add(paragraph);
```
## 12단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 PPTX와 PPT 파일로 저장합니다.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## 결론
 그리고 거기에 있습니다! 다음 단계를 따르면 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 사용자 정의 그림 글머리 기호를 쉽게 추가할 수 있습니다. 이 강력한 라이브러리는 전문적이고 시각적으로 매력적인 프레젠테이션을 만드는 데 도움이 되는 다양한 기능을 제공합니다. 탐험하는 것을 잊지 마세요.[선적 서류 비치](https://reference.aspose.com/slides/java/)고급 기능과 사용자 정의 옵션을 확인하세요.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 Java 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 수정 및 조작할 수 있는 강력한 라이브러리입니다.
### 그림 글머리 기호에 어떤 이미지든 사용할 수 있나요?
예, 프로젝트 디렉터리에서 액세스할 수 있는 이미지라면 어떤 이미지든 그림 글머리 기호로 사용할 수 있습니다.
### Aspose.Slides for Java를 사용하려면 라이선스가 필요합니까?
 Aspose.Slides for Java는 전체 기능을 이용하려면 라이선스가 필요합니다. 임시면허를 취득하실 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/) 또는 정식 라이센스를 구매하세요[여기](https://purchase.aspose.com/buy).
### 하나의 도형에 글머리 기호 스타일이 다른 여러 단락을 추가할 수 있나요?
예, 각 단락을 개별적으로 만들고 구성하여 단일 도형에 다양한 글머리 기호 스타일을 가진 여러 단락을 추가할 수 있습니다.
### 더 많은 예제와 지원은 어디서 찾을 수 있나요?
 다음에서 더 많은 예를 찾을 수 있습니다.[선적 서류 비치](https://reference.aspose.com/slides/java/) Aspose 커뮤니티로부터 지원을 받으세요.[포럼](https://forum.aspose.com/c/slides/11).