---
date: '2026-02-09'
description: Aspose.Slides for Java를 사용하여 차트를 만들고 차트를 Excel로 내보내는 방법을 배웁니다. 데이터 시각화,
  비즈니스 보고서 슬라이드 및 워크북 생성에 능숙해지세요.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Aspose.Slides Java로 차트 만들기
url: /ko/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용하여 차트 만들기

**Aspose.Slides for Java와 함께 데이터 시각화 기술 마스터**

오늘날 데이터 중심 환경에서 프로그래밍으로 *how to create chart*는 원시 데이터를 설득력 있는 시각 스토리로 바꾸는 기술입니다. 비즈니스 보고서 슬라이드덱이나 인터랙티브 분석 대시보드를 구축하든, Aspose.Slides for Java는 코드에서 직접 차트를 생성, 맞춤화 및 내보낼 수 있는 기능을 제공합니다. 이 튜토리얼에서는 차트 객체를 만드는 방법, 차트 데이터를 Excel로 내보내는 방법, 외부 워크북에 차트를 연결하여 원활한 데이터 관리를 하는 방법을 배웁니다.

## 빠른 답변
- **필요한 라이브러리는 무엇인가요?** Aspose.Slides for Java (v25.4+).  
- **차트 데이터를 Excel로 내보낼 수 있나요?** Yes – use `readWorkbookStream()` and write the bytes to an *.xlsx* file.  
- **필요한 Java 버전은 무엇인가요?** JDK 16 or higher.  
- **라이선스가 필요합니까?** A free trial works for evaluation; a permanent license is required for production.  
- **시연된 차트 유형은 무엇인가요?** A Pie chart, but the same approach works for Bar, Line, and other chart types.

## Aspose.Slides for Java란 무엇인가요?
Aspose.Slides for Java는 Microsoft Office 없이도 개발자가 PowerPoint 프레젠테이션을 생성, 편집 및 변환할 수 있게 해주는 순수 Java API입니다. 차트 유형, 데이터 바인딩 및 내보내기 기능을 모두 지원하여 **data visualization java** 프로젝트에 이상적입니다.

## 왜 Aspose.Slides를 사용해 차트를 만들고 Excel로 내보내야 할까요?
- **Office 설치 불필요** – works on any server or cloud environment.  
- **풍부한 차트 라이브러리** – dozens of chart types and full styling control.  
- **직접 Excel 내보내기** – generate an external workbook for downstream analysis.  
- **성능 중심** – low memory footprint and fast processing for large decks.

## 전제 조건
시작하기 전에 다음 항목을 준비하세요:

### 필수 라이브러리 및 버전
- **Aspose.Slides for Java** version 25.4 이상

### 환경 설정 요구 사항
- Java Development Kit (JDK) 16 이상  
- IntelliJ IDEA 또는 Eclipse와 같은 IDE(또는 선호하는 텍스트 편집기)

### 지식 전제 조건
- 기본 Java 프로그래밍 기술  
- Maven 또는 Gradle 빌드 도구에 대한 이해

## Aspose.Slides for Java 설정
선호하는 빌드 시스템을 사용해 라이브러리를 프로젝트에 추가하세요.

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

또는 [최신 버전을 직접 다운로드](https://releases.aspose.com/slides/java/)할 수 있습니다.

### 라이선스 획득 단계
Aspose.Slides는 전체 기능을 체험할 수 있는 무료 체험 라이선스를 제공합니다. 임시 라이선스를 신청하거나 장기 사용을 위해 구매할 수도 있습니다. 다음 단계를 따르세요:

1. 라이선스를 받으려면 [Aspose 구매 페이지](https://purchase.aspose.com/buy)를 방문하세요.  
2. 무료 체험은 [Releases](https://releases.aspose.com/slides/java/)에서 다운로드하세요.  
3. 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 신청하세요.

라이선스 파일을 받으면 Java 애플리케이션에서 초기화하세요:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## 단계별 가이드

### 차트 만들기 – 프레젠테이션 로드
기존 PowerPoint 파일을 로드하는 것이 차트를 추가하거나 수정하기 전에 첫 번째 단계입니다.

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

**설명:**  
- `Presentation`은 PowerPoint 파일을 나타냅니다.  
- 항상 `dispose()`를 호출하여 네이티브 리소스를 해제하세요.

### 차트 만들기 – 슬라이드에 파이 차트 추가
이제 비례 데이터를 표시하기에 적합한 파이 차트를 삽입합니다.

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**설명:**  
- `addChart`는 차트를 첫 번째 슬라이드에 삽입합니다.  
- 매개변수는 차트 유형, X/Y 위치 및 크기를 정의합니다.

### Excel로 차트 내보내기 – 차트 데이터 내보내기
차트 데이터를 내보내면 분석가가 Excel에서 숫자를 다룰 수 있어 더 깊은 인사이트를 얻을 수 있습니다.

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**설명:**  
- `readWorkbookStream()`은 차트의 기본 Excel 워크북을 바이트 배열로 추출합니다.  
- 바이트 배열을 `externalWorkbook1.xlsx`에 기록하여 바로 사용할 수 있는 Excel 파일을 생성합니다.

### 차트 만들기 – 동적 데이터를 위한 외부 워크북 설정
차트를 외부 워크북에 연결하면 Excel 파일을 편집하는 것만으로 차트를 업데이트할 수 있습니다.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**설명:**  
- `setExternalWorkbook`는 차트를 지정된 Excel 파일에 연결하여 슬라이드를 다시 만들 필요 없이 실시간 데이터 업데이트를 가능하게 합니다.

## 실제 적용 사례
Aspose.Slides는 다양한 실제 시나리오에 대한 다목적 솔루션을 제공합니다:

1. **Business Report Slides:** 데이터 파이프라인에서 분기별 성과 차트를 자동으로 생성합니다.  
2. **Academic Presentations:** 연구 데이터를 수동 차트 없이 명확한 시각화로 변환합니다.  
3. **Financial Analysis:** 차트 데이터를 Excel로 내보내어 감사인이 숫자를 검증할 수 있도록 합니다.  
4. **Marketing Analytics:** 캠페인 지표를 시각화하고 이해관계자와 편집 가능한 워크북을 공유합니다.

## 일반적인 문제 및 해결 방법
- **`FileNotFoundException`** – `dataDir`가 유효한 폴더를 가리키고 출력 경로에 쓰기 권한이 있는지 확인하세요.  
- **Memory leaks** – `finally` 블록에서 항상 `pres.dispose()`를 호출하여 네이티브 리소스를 해제하세요.  
- **Chart not appearing** – 슬라이드 인덱스(`get_Item(0)`)가 실제 존재하는 슬라이드와 일치하는지 확인하세요.

## 자주 묻는 질문

**Q: 동일한 코드로 다른 차트 유형(예: Bar, Line)을 사용할 수 있나요?**  
A: 예. `ChartType.Pie`를 `ChartType.Bar` 또는 `ChartType.Line`과 같은 다른 `ChartType` 열거값으로 교체하면 됩니다.

**Q: 차트가 생성된 후 외부 워크북을 업데이트할 수 있나요?**  
A: 물론 가능합니다. Excel 파일을 직접 수정하면, 연결된 차트가 다음에 프레젠테이션을 열 때 변경 사항을 반영합니다.

**Q: Excel 내보내기 기능에 별도의 라이선스가 필요합니까?**  
A: 필요 없습니다. Excel 내보내기 기능은 표준 Aspose.Slides for Java 라이선스에 포함되어 있습니다.

**Q: 지원되는 Java 버전은 무엇인가요?**  
A: Aspose.Slides for Java는 JDK 16 및 그 이후 버전을 지원합니다; 이전 버전도 동작할 수 있지만 공식적으로 테스트되지 않았습니다.

**Q: 생성된 Excel 워크북을 PPTX 파일에 포함시키려면 어떻게 해야 하나요?**  
A: `chart.getChartData().setExternalWorkbook(null)`를 사용해 워크북을 포함시키거나, 동적 업데이트를 위해 외부 링크를 유지하세요.

---

**마지막 업데이트:** 2026-02-09  
**테스트 환경:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}