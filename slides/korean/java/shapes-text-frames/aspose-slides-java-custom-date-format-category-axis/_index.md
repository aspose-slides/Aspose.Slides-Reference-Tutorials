---
"date": "2025-04-17"
"description": "Aspose.Slides for Java를 사용하여 범주 축의 날짜 형식을 사용자 지정하는 방법을 알아보세요. 사용자 지정 데이터 프레젠테이션으로 차트를 더욱 풍성하게 만들고, 연례 보고서 등에도 활용하세요."
"title": "Aspose.Slides Java에서 범주 축에 사용자 지정 날짜 형식을 설정하는 방법 | 데이터 시각화 가이드"
"url": "/ko/java/shapes-text-frames/aspose-slides-java-custom-date-format-category-axis/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java에서 범주 축에 사용자 지정 날짜 형식을 설정하는 방법 | 데이터 시각화 가이드

오늘날 데이터 중심 세상에서 효과적인 의사 결정을 위해서는 정보를 명확하게 표현하는 것이 매우 중요합니다. Aspose.Slides for Java를 사용하여 차트를 만들 때 범주 축의 날짜 형식을 사용자 지정하면 이해도와 프레젠테이션 품질을 크게 향상시킬 수 있습니다. 이 가이드에서는 Aspose.Slides에서 사용자 지정 날짜 형식을 설정하여 슬라이드의 시각적 매력과 데이터 명확성을 향상시키는 방법을 안내합니다.

**배울 내용:**
- Java용 Aspose.Slides 설정
- 카테고리 축에 사용자 정의 날짜 형식 구현
- GregorianCalendar 날짜를 OLE 자동화 날짜 형식으로 변환
- 실제 시나리오에서 이러한 기능의 실용적인 응용 프로그램

이를 쉽게 달성할 수 있는 방법을 알아보겠습니다!

## 필수 조건

시작하기에 앞서 다음 전제 조건이 충족되었는지 확인하세요.

### 필수 라이브러리 및 버전:
- **Java용 Aspose.Slides**: 25.4 버전 이상이 필요합니다.

### 환경 설정 요구 사항:
- Java 코드를 실행할 수 있는 개발 환경(예: IntelliJ IDEA, Eclipse 또는 NetBeans).
- 종속성을 관리하기 위해 프로젝트에서 Maven 또는 Gradle을 구성했습니다.

### 지식 전제 조건:
- Java 프로그래밍에 대한 기본적인 이해.
- 프레젠테이션 내에서 차트 구성 요소를 사용하는 방법에 익숙합니다.

## Java용 Aspose.Slides 설정

Java용 Aspose.Slides를 사용하려면 프로젝트에 종속성으로 포함해야 합니다. 설치 지침은 다음과 같습니다.

**메이븐:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**그래들:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

또는 다음을 수행할 수 있습니다. [최신 릴리스를 다운로드하세요](https://releases.aspose.com/slides/java/) Aspose 공식 사이트에서 직접 확인하세요.

### 라이센스 취득:
- **무료 체험**: 무료 체험판을 통해 기능을 살펴보세요.
- **임시 면허**: 장기 테스트를 위해 임시 라이센스를 요청하세요.
- **구입**: 장기적으로 사용하려면 구독 구매를 고려해 보세요. 방문하세요 [Aspose 구매](https://purchase.aspose.com/buy) 자세한 내용은.

### 기본 초기화:

프로젝트에서 Aspose.Slides를 초기화하는 방법은 다음과 같습니다.
```java
import com.aspose.slides.Presentation;
// 프레젠테이션 파일을 나타내는 Presentation 객체를 인스턴스화합니다.
Presentation pres = new Presentation();
```

이제 이 가이드의 핵심으로 넘어가 보겠습니다!

## 구현 가이드

### 카테고리 축에 대한 날짜 형식 설정

이 기능을 사용하면 차트의 범주 축에 날짜가 표시되는 방식을 사용자 지정할 수 있습니다. 자세한 안내는 다음과 같습니다.

#### 1. 새로운 프레젠테이션과 차트 만들기
인스턴스를 생성하여 시작하세요 `Presentation` 새로운 면적 차트를 추가합니다.
```java
import com.aspose.slides.*;
import java.text.ParseException;
import java.util.GregorianCalendar;

public class DateFormatFeature {
    public static void main(String[] args) throws ParseException {
        // 프레젠테이션 초기화
        Presentation pres = new Presentation();
        
        try {
            // 지정된 위치와 크기의 첫 번째 슬라이드에 영역 차트를 추가합니다.
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);

            // 차트 데이터 조작을 위한 Access 차트 데이터 통합 문서
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0); // 차트에 있는 기존 데이터를 지웁니다.

            // 기존 카테고리 및 시리즈를 제거합니다.
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();

            // 변환된 OLE 자동화 날짜를 사용하여 범주 축에 날짜 추가
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

            // 새로운 시리즈를 만들고 여기에 데이터 포인트를 추가합니다.
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));

            // 카테고리 축 유형을 날짜로 설정하고 숫자 형식을 구성합니다.
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false); 
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy"); // 날짜를 연도로만 형식화합니다.

            // 지정된 디렉토리에 프레젠테이션을 저장합니다.
            pres.save("YOUR_OUTPUT_DIRECTORY/test.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // OLE 자동화 변환을 위한 기준 날짜
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60)); // OLE 자동화 날짜로 변환
        return String.valueOf(oaDate);
    }
}
```

#### 2. GregorianCalendar 날짜를 OLE 자동화 날짜 형식으로 변환

Aspose.Slides는 표준 Excel 날짜 형식인 OLE 자동화 형식의 날짜를 필요로 합니다. Java에서 날짜를 변환하는 방법은 다음과 같습니다. `GregorianCalendar` 날짜:
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;
import java.util.concurrent.TimeUnit;

public class OADateConversionFeature {
    public static void main(String[] args) throws ParseException {
        GregorianCalendar date = new GregorianCalendar(2021, 0, 15); // 2021년 1월 15일
        String oaDate = convertToOADate(date);
        System.out.println("OLE Automation Date: " + oaDate); 
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // OLE 자동화를 위한 Excel의 기준 날짜
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
    }
}
```

### 문제 해결 팁:
- 변환을 위한 기준 날짜를 확인하세요(`30 Dec 1899`)이 올바르게 구문 분석되었습니다.
- Java 환경이 필요한 라이브러리와 클래스를 지원하는지 확인하세요.
- 문제가 발생하면 Aspose.Slides에 사용 가능한 업데이트나 패치가 있는지 확인하세요.

### 실제 응용 프로그램

날짜 형식을 사용자 지정하는 기능은 다음과 같은 시나리오에서 특히 유용할 수 있습니다.
- **연례 보고서:** 연간 데이터 추세를 명확하게 표시합니다.
- **재무 차트:** 회계 기간을 정확하게 제시합니다.
- **프로젝트 일정:** 특정 기간이나 이정표를 강조합니다.

이 가이드를 따르면 Aspose.Slides for Java를 사용하여 정확하고 시각적으로 매력적인 날짜 형식으로 프레젠테이션을 향상시킬 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}