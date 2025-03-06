---
title: Java PowerPoint에서 표 셀 내부에 이미지 추가
linktitle: Java PowerPoint에서 표 셀 내부에 이미지 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 상세한 단계별 가이드를 통해 Java PowerPoint 프레젠테이션의 표 셀 내부에 이미지를 추가하는 방법을 알아보세요.
weight: 10
url: /ko/java/java-powerpoint-table-manipulation/add-image-inside-table-cells-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
표 셀 내에 이미지를 삽입하여 Java PowerPoint 프레젠테이션을 향상시키려는 경우 올바른 위치에 오셨습니다! 오늘은 Aspose.Slides for Java를 사용하여 자세한 단계별 가이드를 살펴보겠습니다. 이 튜토리얼에서는 전체 프로세스를 안내하므로 초보자도 따라하고 놀라운 결과를 얻을 수 있습니다.
## 전제 조건
시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.
1.  JDK(Java Development Kit): 컴퓨터에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[오라클 사이트](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Java용 Aspose.Slides: 다음에서 Aspose.Slides 라이브러리를 다운로드하세요.[웹사이트](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): Java 개발에는 IntelliJ IDEA 또는 Eclipse를 사용하는 것이 좋습니다.
4. 이미지 파일: PowerPoint 표 셀에 포함할 이미지 파일을 준비하세요.
이제 모든 필수 구성 요소가 준비되었으므로 필요한 패키지를 가져오고 코드를 작성해 보겠습니다.
## 패키지 가져오기
먼저 필요한 패키지를 Java 프로젝트로 가져옵니다. 이 패키지를 사용하면 Aspose.Slides 및 Java의 이미지 처리에서 제공하는 기능을 활용할 수 있습니다.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
더 쉽게 따라할 수 있도록 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프레젠테이션 설정
프리젠테이션 개체를 설정하고 첫 번째 슬라이드에 액세스하는 것으로 시작하세요.
```java
// 문서 디렉터리의 경로를 정의하세요.
String dataDir = "Your Document Directory";
// Presentation 클래스 객체를 인스턴스화합니다.
Presentation presentation = new Presentation();
```
이 코드 조각은 새 PowerPoint 프레젠테이션을 초기화하고 추가 수정을 위해 준비합니다.
## 2단계: 첫 번째 슬라이드에 액세스
다음으로 프레젠테이션의 첫 번째 슬라이드에 액세스합니다. 이 슬라이드는 테이블을 추가할 캔버스가 됩니다.
```java
try {
    // 첫 번째 슬라이드에 액세스
    ISlide slide = presentation.getSlides().get_Item(0);
```
## 3단계: 테이블 차원 정의
테이블의 열 너비와 행 높이를 정의합니다. 이 단계는 표 셀의 크기가 올바른지 확인하는 데 중요합니다.
```java
    // 너비가 있는 열과 높이가 있는 행 정의
    double[] columns = {150, 150, 150, 150};
    double[] rows = {100, 100, 100, 100, 90};
```
## 4단계: 슬라이드에 표 추가
지정된 치수를 사용하여 슬라이드에 테이블 모양을 추가합니다.
```java
    // 슬라이드에 표 모양 추가
    ITable table = slide.getShapes().addTable(50, 50, columns, rows);
```
## 5단계: 이미지 로드
테이블 셀에 포함하려는 이미지를 로드합니다. 지정된 디렉터리에서 이미지 파일을 사용할 수 있는지 확인하세요.
```java
    // 이미지 파일을 보관할 BufferedImage 객체를 만듭니다.
    BufferedImage image = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    // 비트맵 객체를 사용하여 IPPImage 객체 생성
    IPPImage imgx = presentation.getImages().addImage(image);
```
## 6단계: 표 셀에 이미지 추가
이제 테이블의 첫 번째 셀에 이미지를 추가할 차례입니다. 채우기 형식을 구성하고 그림 속성을 설정합니다.
```java
    // 첫 번째 테이블 셀에 이미지 추가
    table.get_Item(0, 0).getCellFormat().getFillFormat().setFillType(FillType.Picture);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
## 7단계: 이미지 자르기 조정
필요한 경우 이미지 자르기를 조정하여 셀 내에 완벽하게 맞도록 합니다. 이 단계를 통해 이미지가 제대로 보이는지 확인할 수 있습니다.
```java
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropRight(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropLeft(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropTop(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropBottom(20);
```
## 8단계: 프레젠테이션 저장
마지막으로 수정된 프레젠테이션을 원하는 디렉터리에 저장합니다.
```java
    // PPTX를 디스크에 저장
    presentation.save(dataDir + "Image_In_TableCell_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## 결론
거기 있어요! 다음 단계를 수행하면 Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 표 셀 내부에 이미지를 성공적으로 추가할 수 있습니다. 이 가이드에서는 환경 설정부터 최종 프레젠테이션 저장까지 모든 내용을 다루었습니다. 이 튜토리얼이 시각적으로 더욱 매력적인 프레젠테이션을 만드는 데 도움이 되기를 바랍니다.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 Java 애플리케이션에서 PowerPoint 프레젠테이션을 생성, 수정 및 관리할 수 있는 강력한 API입니다.
### Aspose.Slides에 대한 무료 평가판이 있습니까?
 예, 다음을 얻을 수 있습니다.[무료 시험판](https://releases.aspose.com/) 구매하기 전에 Aspose.Slides를 사용해 보세요.
### Aspose.Slides에 어떤 이미지 형식이라도 사용할 수 있나요?
Aspose.Slides는 JPEG, PNG, BMP 등을 포함한 다양한 이미지 형식을 지원합니다.
### 더 자세한 문서는 어디서 찾을 수 있나요?
 당신은[선적 서류 비치](https://reference.aspose.com/slides/java/) 더 자세한 정보와 예시를 보려면
### Java용 Aspose.Slides를 어떻게 구매할 수 있나요?
 에서 구매하실 수 있습니다.[Aspose 웹사이트](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
