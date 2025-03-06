---
title: Java를 사용하여 PowerPoint에서 단락 글머리 기호 추가
linktitle: Java를 사용하여 PowerPoint에서 단락 글머리 기호 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드에 단락 글머리 기호를 추가하는 방법을 알아보세요. 이 튜토리얼에서는 코드 예제를 통해 단계별로 안내합니다.
weight: 15
url: /ko/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 PowerPoint에서 단락 글머리 기호 추가

## 소개
단락 글머리 기호를 추가하면 PowerPoint 프레젠테이션의 가독성과 구조가 향상됩니다. Aspose.Slides for Java는 다양한 글머리 기호 스타일로 텍스트 서식을 지정하는 기능을 포함하여 프로그래밍 방식으로 프레젠테이션을 조작할 수 있는 강력한 도구를 제공합니다. 이 튜토리얼에서는 Aspose.Slides를 활용하여 Java 코드를 사용하여 PowerPoint 슬라이드에 글머리 기호를 통합하는 방법을 배웁니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
시작하려면 필요한 Aspose.Slides 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## 1단계: 프로젝트 설정
먼저 새 Java 프로젝트를 생성하고 Aspose.Slides for Java 라이브러리를 프로젝트 빌드 경로에 추가합니다.
## 2단계: 프레젠테이션 초기화
프리젠테이션 객체 초기화(`Presentation`) 슬라이드 작업을 시작합니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 인스턴스 만들기
Presentation pres = new Presentation();
```
## 3단계: 슬라이드 및 텍스트 프레임에 액세스
슬라이드에 액세스합니다(`ISlide`및 해당 텍스트 프레임(`ITextFrame`) 글머리 기호를 추가하려는 위치입니다.
```java
// 첫 번째 슬라이드에 액세스하기
ISlide slide = pres.getSlides().get_Item(0);
// Autoshape 추가 및 액세스
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// 생성된 자동 모양의 텍스트 프레임에 액세스
ITextFrame txtFrm = aShp.getTextFrame();
```
## 4단계: 글머리 기호를 사용하여 단락 만들기 및 서식 지정
단락 만들기(`Paragraph`) 글머리 기호 스타일, 들여쓰기 및 텍스트를 설정합니다.
```java
// 단락 만들기
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// 다른 단락 만들기
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## 5단계: 프레젠테이션 저장
수정된 프리젠테이션을 PowerPoint 파일(`PPTX`).
```java
// 프레젠테이션을 PPTX 파일로 작성
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## 6단계: 리소스 정리
리소스를 해제하려면 프레젠테이션 개체를 삭제하세요.
```java
// 프레젠테이션 개체 삭제
if (pres != null) {
    pres.dispose();
}
```

## 결론
제공된 코드 예제를 사용하면 Java용 Aspose.Slides를 사용하여 PowerPoint에 단락 글머리 기호를 추가하는 것이 간단합니다. 프레젠테이션 요구 사항에 맞게 글머리 기호 스타일과 서식을 원활하게 사용자 정의하세요.

## 자주 묻는 질문
### 글머리 기호 색상을 맞춤설정할 수 있나요?
예, Aspose.Slides API를 사용하여 글머리 기호에 대한 사용자 정의 색상을 설정할 수 있습니다.
### 중첩된 글머리 기호를 어떻게 추가하나요?
글머리 기호 중첩에는 단락 내에 단락을 추가하고 이에 따라 들여쓰기를 조정하는 작업이 포함됩니다.
### 슬라이드별로 글머리 기호 스타일을 다르게 만들 수 있나요?
예, 프로그래밍 방식으로 다양한 슬라이드에 고유한 글머리 기호 스타일을 적용할 수 있습니다.
### Aspose.Slides는 Java 11과 호환됩니까?
예, Aspose.Slides는 Java 11 이상 버전을 지원합니다.
### 더 많은 예제와 문서는 어디에서 찾을 수 있나요?
 방문하다[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/) 포괄적인 가이드와 예시를 보려면
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
