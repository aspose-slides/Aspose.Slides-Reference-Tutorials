---
date: '2026-08-06'
description: Aspose.Slides for Java를 사용하여 legend font color를 변경하고 chart legend 텍스트를
  수정하는 방법을 배웁니다. 차트 legend를 빠르게 customize하기 위해 step‑by‑step 지침을 따르세요.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Aspose.Slides for Java와 함께 legend font color를 변경하고 chart legend 텍스트를
  수정하는 방법을 배웁니다. 이 가이드는 정확한 단계와 모범 사례를 보여줍니다.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Aspose.Slides for Java에서 legend font color를 변경하는 방법
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Aspose.Slides for Java에서 legend font color를 변경하는 방법
url: /ko/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java에서 범례 글꼴 색상 변경 방법

## 소개
차트에서 **범례 글꼴 색상**을 변경해야 하는 경우, Aspose.Slides for Java는 모든 범례 항목에 대한 완전한 제어를 제공합니다. 이 튜토리얼에서는 범례 텍스트 스타일을 사용자 정의하고, 굵게 또는 기울임꼴 글꼴을 적용하며, 단색을 설정하여 차트를 원하는 대로 보이게 하는 방법을 단계별로 안내합니다. 이 가이드를 마치면 차트 범례 텍스트를 자신 있게 수정하고 기존 프레젠테이션에 변경 사항을 통합할 수 있게 됩니다.

**배우게 될 내용**
- 프로그래밍 방식으로 **범례 글꼴 색상**을 변경하는 방법.
- 굵게, 기울임꼴, 크기 등 **차트 범례 텍스트**를 수정하는 방법.
- 하나의 프레젠테이션에 있는 여러 차트에 변경 사항을 적용하는 팁.
- 이러한 단계를 더 큰 자동화 워크플로에 통합하는 방법.

## 빠른 답변
- **단일 범례 항목의 색상을 변경할 수 있나요?** 예 – 인덱스로 항목에 접근하고 채우기 형식을 단색으로 설정합니다.  
- **이 API를 사용하려면 라이선스가 필요합니까?** 프로덕션에서는 임시 또는 유료 라이선스가 필요하며, 평가용으로는 무료 체험판을 사용할 수 있습니다.  
- **지원되는 Java 버전은 무엇인가요?** Aspose.Slides for Java 25.4+는 JDK 16 및 그 이후 버전과 호환됩니다.  
- **변경 사항이 다른 차트 요소에 영향을 미칩니까?** 아니요, 범례 서식은 데이터 시리즈 스타일링과 분리되어 있습니다.  
- **배치 처리가 가능한가요?** 물론입니다 – 슬라이드와 차트를 순회하면서 전체 프레젠테이션에 동일한 범례 설정을 적용합니다.

## 범례 글꼴 색상 변경이란?
`change legend font color`는 Aspose.Slides API를 사용하여 차트 범례 항목의 텍스트 색상을 설정하는 프로그래밍 작업을 의미합니다. 이 작업은 기본 데이터를 변경하지 않고 범례의 시각적 모습을 업데이트합니다.

## 차트 범례를 사용자 정의하는 이유
Aspose.Slides는 **50개 이상의 입력 및 출력 형식**을 지원하며 **500개 이상의 슬라이드**가 포함된 프레젠테이션도 메모리 사용량을 200 MB 이하로 유지하면서 처리할 수 있습니다. 범례를 사용자 정의하면 가독성이 향상되고 브랜드 색상이 강화되며 주요 데이터 포인트가 돋보이게 됩니다—특히 시각적 명확성이 의사결정을 이끄는 비즈니스 또는 교육용 데크에서 더욱 중요합니다.

## 전제 조건
- **Aspose.Slides for Java** 라이브러리 (버전 25.4 이상).  
- Java Development Kit (JDK) 16 이상.  
- IntelliJ IDEA, Eclipse, NetBeans와 같은 IDE.  
- 의존성 관리를 위한 Maven 또는 Gradle.  
- 기본 Java 프로그래밍 지식.

## Aspose.Slides for Java 설정
차트 범례를 사용자 정의하려면 아래 방법 중 하나를 사용하여 라이브러리를 프로젝트에 추가하십시오.

### Maven
다음 의존성을 `pom.xml` 파일에 추가합니다:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` 파일에 다음 줄을 포함합니다:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
최신 JAR 파일은 [Aspose.Slides for Java 릴리스](https://releases.aspose.com/slides/java/)에서 다운로드할 수 있습니다.

#### 라이선스 획득 단계
- **무료 체험:** Aspose.Slides 기능을 탐색하기 위해 무료 체험으로 시작합니다.  
- **임시 라이선스:** 장기 평가를 위해 임시 라이선스를 신청합니다.  
- **구매:** 전체 기능을 사용하려면 [Aspose 구매](https://purchase.aspose.com/buy)에서 라이선스를 구매하는 것을 고려하십시오.

#### 기본 초기화 및 설정
라이브러리를 프로젝트에 추가한 후:
1. Java 애플리케이션에서 Aspose.Slides를 초기화합니다.  
2. 기존 프레젠테이션을 로드하거나 새 프레젠테이션을 생성합니다.

## 범례 글꼴 색상을 변경하는 방법
범례 글꼴 색상을 변경하려면 프레젠테이션을 로드하고 차트 객체를 가져온 다음 범례를 얻고, 각 범례 항목의 텍스트 형식을 채우기 유형을 단색으로 설정하고 원하는 색상을 지정하여 수정합니다. 이 단일 작업으로 전체 슬라이드를 다시 그릴 필요 없이 즉시 범례 텍스트 색상이 업데이트됩니다. 예시: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` 이 방법은 모든 차트 유형에 적용 가능하며 전체 슬라이드를 다시 렌더링할 필요가 없습니다.

### 범례 텍스트 속성 접근 및 수정

#### 정의 앵커
`IChart` 인터페이스는 슬라이드의 차트 객체를 나타내며, `getLegend()` 메서드는 `ILegendEntry` 항목 컬렉션을 포함하는 `ILegend` 객체를 반환합니다.

#### 프레젠테이션에 차트 추가
1. **프레젠테이션 로드:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **클러스터형 컬럼 차트 추가:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### 글꼴 속성 사용자 정의
3. **범례 항목 텍스트 형식에 접근:**  
   여기서 `legendEntry`는 차트 범례의 단일 항목을 나타내는 `ILegendEntry` 객체입니다.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **특정 높이와 함께 굵게 및 기울임꼴 스타일 설정:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **가시성을 높이기 위해 채우기 유형을 단색으로 변경:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### 프레젠테이션 저장
6. **변경 사항 저장:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### 일반적인 함정 및 문제 해결
- 범례 항목 인덱스가 차트의 시리즈 순서와 일치하는지 확인하십시오.  
- `setSolidFillColor`를 지원하는 라이브러리 버전을 사용하고 있는지 확인하십시오(버전 20.9부터 사용 가능).

## 실용적인 적용 사례
범례 텍스트를 사용자 정의하는 것은 다양한 실제 시나리오에서 유용합니다:

1. **비즈니스 프레젠테이션:** 범례 색상을 기업 브랜드와 맞추어 세련된 모습을 제공합니다.  
2. **교육 자료:** 대비되는 범례 색상을 사용하여 주요 데이터 시리즈를 강조합니다.  
3. **마케팅 데크:** 굵고 색상이 있는 범례로 성과 지표를 강조하여 이해관계자의 관심을 끕니다.

또한 데이터베이스나 구성 파일에서 색상 값을 가져와 범례 업데이트를 자동화할 수 있습니다.

## 성능 고려 사항
대규모 데크를 처리할 때는 다음 팁을 기억하십시오:

- **효율적인 메모리 관리:** 저장 후 `presentation.dispose()`를 호출하여 네이티브 리소스를 해제합니다.  
- **필요한 슬라이드만 로드:** 부분 슬라이드만 필요할 경우 `Presentation.load(String path, LoadOptions options)`와 `LoadOptions.setLoadOnlySlideIds()`를 사용합니다.  
- **배치 처리:** 슬라이드당 범례 업데이트를 그룹화하여 API 호출 수를 줄이고 처리량을 향상시킵니다.

## 결론
이제 Aspose.Slides for Java를 사용하여 **범례 글꼴 색상**을 **변경하고 차트 범례 텍스트**를 **수정**하는 방법을 알게 되었습니다. 이러한 사용자 정의는 시각적 명확성을 높이고 데이터를 보다 효과적으로 전달하는 데 도움이 됩니다. 다양한 글꼴, 크기 및 색상을 실험하여 프레젠테이션 스타일 가이드에 맞추고, 다른 차트 스타일링 기능을 탐색하여 진정한 전문가 수준의 데크를 만들어 보세요.

**다음 단계**
- 파이 차트와 라인 차트에도 동일한 범례 스타일을 적용해 보세요.  
- 범례 사용자 정의를 데이터 레이블 서식과 결합하여 완전한 브랜드 차트를 만들세요.

프레젠테이션을 한 단계 끌어올릴 준비가 되셨나요? 위 단계들을 구현하고 즉시 차이를 확인하세요!

## FAQ 섹션
1. **범례 항목 텍스트 색상을 어떻게 변경하나요?**  
   범례 항목의 텍스트 형식에 `getFillFormat().setFillType(FillType.Solid)`를 사용한 다음 `setSolidFillColor(Color.YOUR_COLOR)`를 호출합니다.

2. **프레젠테이션의 모든 범례에 이러한 변경을 적용할 수 있나요?**  
   예 – 각 슬라이드를 순회하고 각 차트를 찾아 루프 내에서 범례 항목을 업데이트합니다.

3. **텍스트 길이에 따라 글꼴 크기를 동적으로 조정할 수 있나요?**  
   `TextFrame.getTextFrameFormat().getFontHeight()`를 사용해 필요한 크기를 계산하고 `setFontHeight(double)`로 설정할 수 있습니다.

4. **범례 항목 인덱싱에 문제가 발생하면 어떻게 해야 하나요?**  
   사용 중인 인덱스가 시리즈 순서와 일치하는지 다시 확인하십시오; 인덱스는 0부터 시작한다는 점을 기억하세요.

5. **더 많은 Aspose.Slides 예제를 어디서 찾을 수 있나요?**  
   포괄적인 가이드와 API 레퍼런스를 위해 [Aspose 문서](https://reference.aspose.com/slides/java/)를 살펴보세요.

**추가 Q&A**

**Q: 범례 글꼴 색상 변경이 내보낸 PDF 파일에 영향을 줍니까?**  
A: 아니요, 색상 변경은 PDF 및 PPTX를 포함한 Aspose.Slides가 지원하는 모든 내보내기 형식에 그대로 유지됩니다.

**Q: 단색 대신 그라디언트를 사용할 수 있나요?**  
A: 예 – `FillType.Gradient`를 설정하고 `getGradientStyle()`을 통해 그라디언트 스톱을 구성합니다.

**Q: 차트에 몇 개의 범례 항목을 가질 수 있나요?**  
A: 차트는 최대 256개의 범례 항목을 가질 수 있으며, 이는 추가하는 데이터 시리즈 수에만 제한됩니다.

## 리소스
- **Documentation:** Aspose.Slides 기능 사용에 대한 포괄적인 가이드 ([링크](https://reference.aspose.com/slides/java/)).  
- **Download:** 최신 Aspose.Slides for Java 버전을 다운로드 ([링크](https://releases.aspose.com/slides/java/)).  
- **Purchase:** 전체 기능을 이용하려면 라이선스를 구매하십시오 ([링크](https://purchase.aspose.com/buy)).  
- **Free trial & temporary license:** 무료 체험으로 시작하고 임시 라이선스를 신청하십시오 ([무료 체험 링크](https://releases.aspose.com/slides/java/), [임시 라이선스 링크](https://purchase.aspose.com/temporary-license/)).  
- **Support:** Aspose 지원 포럼에서 커뮤니티의 도움을 받으세요 ([링크](https://forum.aspose.com/c/slides/11)).

**마지막 업데이트:** 2026-08-06  
**테스트 환경:** Aspose.Slides for Java 25.4  
**작성자:** Aspose

## 관련 튜토리얼
- [Aspose.Slides for Java를 사용한 PowerPoint 차트 향상: 글꼴 및 축 사용자 정의](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides for Java: 동적 텍스트 프레임 및 글꼴 사용자 정의 가이드](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Aspose.Slides for Java로 PowerPoint 차트 애니메이션 – 단계별 가이드](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}