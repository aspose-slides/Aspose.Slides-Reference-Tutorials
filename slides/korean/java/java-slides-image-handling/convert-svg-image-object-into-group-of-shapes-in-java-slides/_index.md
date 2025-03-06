---
title: Java 슬라이드에서 SVG 이미지 개체를 모양 그룹으로 변환
linktitle: Java 슬라이드에서 SVG 이미지 개체를 모양 그룹으로 변환
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Java용 Aspose.Slides를 사용하여 SVG 이미지를 Java 슬라이드의 모양 그룹으로 변환하는 방법을 알아보세요. 코드 예제가 포함된 단계별 가이드입니다.
weight: 13
url: /ko/java/image-handling/convert-svg-image-object-into-group-of-shapes-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 슬라이드에서 SVG 이미지 객체를 도형 그룹으로 변환하는 방법 소개

이 포괄적인 가이드에서는 Aspose.Slides for Java API를 사용하여 SVG 이미지 개체를 Java 슬라이드의 모양 그룹으로 변환하는 방법을 살펴보겠습니다. 이 강력한 라이브러리를 통해 개발자는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 조작할 수 있으므로 이미지 처리를 포함한 다양한 작업에 유용한 도구가 됩니다.

## 전제 조건

코드 및 단계별 지침을 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

이제 모든 설정이 완료되었으므로 시작해 보겠습니다.

## 1단계: 필요한 라이브러리 가져오기

시작하려면 Java 프로젝트에 필요한 라이브러리를 가져와야 합니다. Java용 Aspose.Slides를 포함해야 합니다.

```java
import com.aspose.slides.*;
```

## 2단계: 프레젠테이션 로드

 다음으로 SVG 이미지 개체가 포함된 PowerPoint 프레젠테이션을 로드해야 합니다. 바꾸다`"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용하십시오.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "image.pptx");
```

## 3단계: SVG 이미지 검색

이제 PowerPoint 프레젠테이션에서 SVG 이미지 개체를 검색해 보겠습니다. SVG 이미지가 첫 번째 슬라이드에 있고 해당 슬라이드의 첫 번째 모양이라고 가정하겠습니다.

```java
try
{
    PictureFrame pFrame = (PictureFrame) pres.getSlides().get_Item(0).getShapes().get_Item(0);
    ISvgImage svgImage = pFrame.getPictureFormat().getPicture().getImage().getSvgImage();
```

## 4단계: SVG 이미지를 도형 그룹으로 변환

SVG 이미지를 사용하면 이제 이를 모양 그룹으로 변환할 수 있습니다. 이는 슬라이드에 새 그룹 모양을 추가하고 소스 SVG 이미지를 제거하여 달성할 수 있습니다.

```java
    if (svgImage != null)
    {
        // SVG 이미지를 모양 그룹으로 변환
        IGroupShape groupShape = pres.getSlides().get_Item(0).getShapes()
                .addGroupShape(svgImage, pFrame.getFrame().getX(), pFrame.getFrame().getY(),
                        pFrame.getFrame().getWidth(), pFrame.getFrame().getHeight());

        // 프레젠테이션에서 소스 SVG 이미지 제거
        pres.getSlides().get_Item(0).getShapes().remove(pFrame);
    }
```

## 5단계: 수정된 프레젠테이션 저장

SVG 이미지를 모양 그룹으로 성공적으로 변환한 후 수정된 프레젠테이션을 새 파일에 저장합니다.

```java
    pres.save(dataDir + "image_group.pptx", SaveFormat.Pptx);
}
finally
{
    pres.dispose();
}
```

축하해요! 이제 Aspose.Slides for Java API를 사용하여 SVG 이미지 개체를 Java 슬라이드의 모양 그룹으로 변환하는 방법을 배웠습니다.

## SVG 이미지 개체를 Java 슬라이드의 모양 그룹으로 변환하기 위한 완전한 소스 코드

```java
        // 문서 디렉터리의 경로입니다.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "image.pptx");
        try
        {
            PictureFrame pFrame = (PictureFrame) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ISvgImage svgImage = pFrame.getPictureFormat().getPicture().getImage().getSvgImage();
            if (svgImage != null)
            {
                // SVG 이미지를 모양 그룹으로 변환
                IGroupShape groupShape = pres.getSlides().get_Item(0).getShapes().
                        addGroupShape(svgImage, pFrame.getFrame().getX(), pFrame.getFrame().getY(),
                                pFrame.getFrame().getWidth(), pFrame.getFrame().getHeight());
                // 프레젠테이션에서 소스 SVG 이미지 제거
                pres.getSlides().get_Item(0).getShapes().remove(pFrame);
            }
            pres.save(dataDir + "image_group.pptx", SaveFormat.Pptx);
        }
        finally
        {
            pres.dispose();
        }
```

## 결론

이 튜토리얼에서는 Java 및 Aspose.Slides for Java 라이브러리를 사용하여 SVG 이미지 개체를 PowerPoint 프레젠테이션 내의 모양 그룹으로 변환하는 프로세스를 탐색했습니다. 이 기능은 동적 콘텐츠로 프레젠테이션을 향상시킬 수 있는 다양한 가능성을 열어줍니다.

## FAQ

### Aspose.Slides를 사용하여 다른 이미지 형식을 도형 그룹으로 변환할 수 있나요?

예, Aspose.Slides는 SVG뿐만 아니라 다양한 이미지 형식을 지원합니다. PNG, JPEG 등과 같은 형식을 PowerPoint 프레젠테이션 내의 도형 그룹으로 변환할 수 있습니다.

### Aspose.Slides는 PowerPoint 프레젠테이션 자동화에 적합합니까?

전적으로! Aspose.Slides는 PowerPoint 프레젠테이션을 자동화하는 강력한 기능을 제공하여 프로그래밍 방식으로 슬라이드 생성, 편집 및 조작과 같은 작업에 유용한 도구입니다.

### Aspose.Slides for Java를 사용하기 위한 라이선스 요구 사항이 있나요?

예, Aspose.Slides를 상업적으로 사용하려면 유효한 라이선스가 필요합니다. Aspose 웹사이트에서 라이선스를 얻을 수 있습니다. 그러나 평가 목적으로 무료 평가판을 제공합니다.

### 변환된 도형의 모양을 사용자 지정할 수 있나요?

틀림없이! 요구 사항에 따라 변환된 도형의 모양, 크기 및 위치를 사용자 정의할 수 있습니다. Aspose.Slides는 모양 조작을 위한 광범위한 API를 제공합니다.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
