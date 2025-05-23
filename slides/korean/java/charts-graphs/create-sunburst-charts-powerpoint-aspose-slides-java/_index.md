---
"date": "2025-04-17"
"description": "Aspose.Slides for Java를 사용하여 PowerPoint에서 선버스트 차트를 만들고 사용자 지정하는 방법을 알아보세요. 이 단계별 가이드에서는 설정, 사용자 지정 및 실제 적용 방법을 다룹니다."
"title": "Java용 Aspose.Slides를 사용하여 PowerPoint에서 Sunburst 차트 만들기 및 사용자 지정"
"url": "/ko/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java용 Aspose.Slides를 사용하여 PowerPoint에서 Sunburst 차트 만들기 및 사용자 지정

## 소개

매력적인 프레젠테이션을 만들려면 데이터를 효과적으로 전달하는 시각적으로 뛰어난 차트를 활용하는 것이 중요합니다. 이러한 차트 중 하나는 방사형 레이아웃을 통해 계층적 데이터를 표현하는 독특한 방법을 제공하는 선버스트 차트입니다. 하지만 적절한 도구 없이 이러한 차트를 추가하고 사용자 지정하는 것은 어려울 수 있습니다. 이 가이드에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 선버스트 차트를 만들고 수정하는 방법을 안내합니다.

**배울 내용:**
- Aspose.Slides 환경 설정
- 선버스트 차트로 새로운 프레젠테이션 만들기
- 차트 내 데이터 포인트 사용자 지정
- 이러한 기술의 실제 적용

Java용 Aspose.Slides를 사용하여 이 프로세스를 단순화하는 방법을 알아보겠습니다.

## 필수 조건

시작하기 전에 개발 환경이 준비되었는지 확인하세요. 필요한 사항은 다음과 같습니다.
- **자바 개발 키트(JDK)** 버전 16 이상
- 안 **통합 개발 환경(IDE)** IntelliJ IDEA나 Eclipse와 같은
- 기본 지식 **자바** 및 PowerPoint 프레젠테이션

## Java용 Aspose.Slides 설정

### Maven 종속성

프로젝트에 Aspose.Slides를 포함하려면 다음 종속성을 추가하세요. `pom.xml` 파일:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 종속성

Gradle을 사용하는 경우 다음을 포함하세요. `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드

또는 다음에서 최신 JAR을 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

### 라이센스 취득

평가 제한 없이 Aspose.Slides를 사용하려면:
- **무료 체험:** 모든 기능을 탐색하려면 임시 라이선스로 시작하세요.
- **임시 면허:** 임시 라이센스를 요청하세요 [Aspose 웹사이트](https://purchase.aspose.com/temporary-license).
- **구입:** 진행 중인 프로젝트의 경우 구독 구매를 고려하세요.

### 기본 초기화

Java 애플리케이션에서 Aspose.Slides를 초기화하는 방법은 다음과 같습니다.
```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // 라이센스가 있는 경우 Aspose.Slides를 초기화합니다.
        Presentation pres = new Presentation();
        try {
            // 여기에 코드를 입력하세요...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## 구현 가이드

### 프레젠테이션을 만들고 선버스트 차트를 추가하세요

#### 개요

이 기능은 처음부터 PowerPoint 프레젠테이션을 만들고 선버스트 차트를 추가하는 방법을 보여줍니다.

#### 단계:
##### 1단계: 프레젠테이션 초기화
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // 경로로 대체하세요
```

##### 2단계: 선버스트 차트 추가
첫 번째 슬라이드에 위치(100, 100)와 크기(450x400)의 선버스트 차트를 추가합니다.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

##### 3단계: 프레젠테이션 저장
모든 변경 사항이 저장되도록 프레젠테이션을 저장하세요.
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### 차트의 데이터 포인트 수정

#### 개요
레이블과 색상을 포함한 선버스트 차트 내의 데이터 포인트를 수정하는 방법을 알아보세요.

#### 단계:
##### 1단계: 데이터 포인트 수집에 액세스
차트에서 첫 번째 시리즈의 데이터 포인트 컬렉션에 액세스합니다.
```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

##### 2단계: 특정 데이터 포인트의 값 표시
레이블을 수정하여 특정 수준의 값을 표시합니다.
```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

##### 3단계: 레이블 형식 수정
카테고리 이름 표시 여부, 텍스트 색상 등의 라벨 설정을 조정합니다.
```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

##### 4단계: 데이터 포인트에 대한 채우기 색상 설정
특정 데이터 포인트의 채우기 색상을 사용자 지정합니다.
```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

##### 5단계: 수정된 프레젠테이션 저장
변경 사항은 반드시 저장하여 마무리하세요.
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## 실제 응용 프로그램

1. **비즈니스 분석:** 지역 및 범주별 판매 데이터와 같은 복잡한 데이터 계층을 시각화하려면 선버스트 차트를 사용하세요.
2. **프로젝트 관리:** 쉽게 시각화할 수 있도록 방사형 차트를 사용하여 프로젝트 작업을 하위 작업으로 구분하여 표시합니다.
3. **교육:** 교육 프레젠테이션에서 과정 모듈과 해당 강의를 표현합니다.

## 성능 고려 사항

- **리소스 사용 최적화:** 특히 대용량 데이터 세트나 여러 차트를 처리할 때 애플리케이션이 메모리를 효율적으로 관리하는지 확인하세요.
- **자바 메모리 관리:** 메모리 누수를 방지하려면 객체를 즉시 폐기하는 등의 모범 사례를 활용하세요.

## 결론

Aspose.Slides for Java를 사용하여 선버스트 차트를 만들고 맞춤 설정하는 것은 프레젠테이션을 더욱 풍성하게 만드는 강력한 방법입니다. 이 가이드를 따라 하면 환경 설정, 차트 기능 구현, 데이터 포인트의 효과적인 수정에 필요한 핵심 사항을 배우게 됩니다.

**다음 단계:**
- Aspose.Slides에서 사용할 수 있는 더 많은 차트 유형을 살펴보세요.
- 차트에 대한 다양한 사용자 정의 옵션을 실험해 보세요.

**행동 촉구:** 다음 프레젠테이션 프로젝트에 이러한 솔루션을 구현하여 데이터 시각화 활동을 어떻게 향상시킬 수 있는지 확인해 보세요!

## FAQ 섹션

1. **선버스트 차트란 무엇인가요?**
   - 선버스트 차트는 계층적 데이터를 방사형으로 표시하므로 중첩된 관계를 보여주는 데 적합합니다.
2. **Maven을 사용하여 Java용 Aspose.Slides를 어떻게 설치합니까?**
   - 종속성을 추가하세요 `pom.xml` 위의 설정 섹션에 표시된 대로 파일입니다.
3. **Aspose.Slides로 다른 유형의 차트를 수정할 수 있나요?**
   - 네, Aspose.Slides는 막대형 차트, 선형 차트, 원형 차트 등 다양한 차트 유형을 지원합니다.
4. **프레젠테이션이 제대로 저장되지 않으면 어떻게 해야 하나요?**
   - 파일 경로가 올바른지, 그리고 디렉토리에 대한 쓰기 권한이 있는지 확인하세요.
5. **Aspose.Slides에 대해 더 많은 도움을 받으려면 어떻게 해야 하나요?**
   - 방문하세요 [Aspose 포럼](https://forum.aspose.com/c/slides/11) 또는 문서를 확인하세요 [Aspose.Slides 참조](https://reference.aspose.com/slides/java/).

## 자원
- **선적 서류 비치:** [Aspose.Slides 참조](https://reference.aspose.com/slides/java)
- **법정:** [Aspose 포럼](https://forum.aspose.com/c/slides)
- **다운로드:** [Aspose.Slides 다운로드](https://releases.aspose.com/slides/java)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}