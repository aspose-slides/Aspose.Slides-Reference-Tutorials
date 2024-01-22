---
title: Java 슬라이드에서 차트 이미지 가져오기
linktitle: Java 슬라이드에서 차트 이미지 가져오기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드에서 차트 이미지를 얻는 방법을 알아보세요. 이 단계별 가이드에서는 원활한 통합을 위한 소스 코드와 팁을 제공합니다.
type: docs
weight: 19
url: /ko/java/data-manipulation/get-chart-image-java-slides/
---

## Java 슬라이드에서 차트 이미지 가져오기 소개

Aspose.Slides for Java는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업할 수 있는 강력한 라이브러리입니다. 이 라이브러리를 사용하면 차트를 포함한 프레젠테이션의 다양한 요소를 생성, 조작 및 추출할 수 있습니다. 일반적인 요구 사항 중 하나는 슬라이드에서 차트 이미지를 얻는 것입니다. 이 가이드에서는 이를 수행하는 방법을 보여 드리겠습니다.

## 전제조건

코드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  프로젝트에 다운로드 및 구성된 Java 라이브러리용 Aspose.Slides. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 1단계: 프로젝트 설정

선호하는 통합 개발 환경(IDE)에서 Java 프로젝트를 생성하는 것부터 시작하세요. 프로젝트의 종속성에 Aspose.Slides for Java 라이브러리를 추가했는지 확인하세요.

## 2단계: 프레젠테이션 초기화

시작하려면 PowerPoint 프레젠테이션을 초기화해야 합니다. 이 예에서는 문서 디렉터리에 "test.pptx"라는 PowerPoint 파일이 있다고 가정합니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 3단계: 차트 추가 및 이미지 가져오기

다음으로 슬라이드에 차트를 추가하고 해당 이미지를 얻을 수 있습니다. 이 예에서는 묶은 세로 막대형 차트를 추가하겠습니다.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

이 코드 조각에서는 프레젠테이션의 첫 번째 슬라이드에 클러스터형 세로 막대형 차트를 만든 다음 축소판 이미지를 가져옵니다. 이미지는 지정된 디렉토리에 "image.png"로 저장됩니다.

## Java 슬라이드에서 차트 이미지 가져오기를 위한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

Aspose.Slides for Java를 사용하여 Java 슬라이드에서 차트 이미지를 얻는 것은 간단한 프로세스입니다. 제공된 코드를 사용하면 이 기능을 Java 애플리케이션에 쉽게 통합하여 PowerPoint 프레젠테이션을 효과적으로 작업할 수 있습니다.

## FAQ

### Java용 Aspose.Slides를 어떻게 설치하나요?

 Java용 Aspose.Slides 설치는 간단합니다. 다음에서 라이브러리를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/)설명서에 제공된 설치 지침을 따르세요.

### 이미지를 얻기 전에 차트를 사용자 정의할 수 있나요?

예, 이미지를 얻기 전에 차트의 모양, 데이터 및 기타 속성을 사용자 정의할 수 있습니다. Aspose.Slides for Java는 차트 사용자 정의를 위한 광범위한 옵션을 제공합니다.

### Aspose.Slides for Java는 어떤 다른 기능을 제공합니까?

Aspose.Slides for Java는 슬라이드 생성, 텍스트 조작, 모양 편집 등을 포함하여 PowerPoint 프레젠테이션 작업을 위한 광범위한 기능을 제공합니다. 자세한 내용은 설명서를 살펴보세요.

### Aspose.Slides for Java는 상업용으로 적합합니까?

예, Aspose.Slides for Java는 상업적 목적으로 사용할 수 있습니다. 개인 개발자와 기업 모두에게 적합한 라이선스 옵션을 제공합니다.

### 차트 이미지를 다른 형식으로 저장할 수 있나요?

틀림없이! 에서 적절한 파일 확장자를 지정하여 차트 이미지를 JPEG, GIF 등 다양한 형식으로 저장할 수 있습니다.`ImageIO.write` 방법.