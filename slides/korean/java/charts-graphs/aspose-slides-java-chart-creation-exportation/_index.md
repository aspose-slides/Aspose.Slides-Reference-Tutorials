---
date: '2026-01-14'
description: Aspose.Slides for Java를 사용하여 차트를 Excel로 내보내는 방법과 프레젠테이션에 파이 차트 슬라이드를
  추가하는 방법을 배웁니다. 코드와 함께하는 단계별 가이드.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Aspose.Slides Java를 사용하여 차트를 Excel로 내보내기
url: /ko/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export Chart to Excel Using Aspose.Slides for Java

**Aspose.Slides for Java 로 마스터하는 데이터 시각화 기술**

오늘날 데이터 중심의 환경에서 **export chart to excel** 를 Java 애플리케이션에서 직접 수행하면 정적인 PowerPoint 시각화를 재사용 가능하고 분석 가능한 데이터 세트로 전환할 수 있습니다. 보고서를 생성하거나, 분석 파이프라인에 데이터를 공급하거나, 단순히 비즈니스 사용자가 Excel에서 차트 데이터를 편집하도록 할 때, Aspose.Slides가 이를 간단하게 만들어 줍니다. 이 튜토리얼에서는 차트를 만들고, 파이 차트 슬라이드를 추가한 뒤, 해당 차트 데이터를 Excel 워크북으로 내보내는 과정을 단계별로 안내합니다.

**배우게 될 내용:**
- 프레젠테이션 파일을 손쉽게 로드하고 조작하기
- **Add pie chart slide** 및 기타 차트 유형을 슬라이드에 추가하기
- **Export chart to excel** (차트에서 Excel 생성) 로 다운스트림 분석 수행하기
- 외부 워크북 경로를 설정하여 **embed chart in presentation** 하고 데이터 동기화 유지하기

시작해 보겠습니다!

## Quick Answers
- **주된 목적은 무엇인가요?** PowerPoint 슬라이드의 차트 데이터를 Excel 파일로 내보내는 것입니다.  
- **필요한 라이브러리 버전은?** Aspose.Slides for Java 25.4 이상.  
- **라이선스가 필요한가요?** 평가용 무료 체험판을 사용할 수 있지만, 프로덕션에서는 상용 라이선스가 필요합니다.  
- **파이 차트 슬라이드를 추가할 수 있나요?** 예 – 튜토리얼에 파이 차트 추가 방법이 나와 있습니다.  
- **Java 16이 최소 요구사항인가요?** 예, JDK 16 이상을 권장합니다.

## How to export chart to excel using Aspose.Slides?
차트 데이터를 Excel로 내보내는 과정은 프레젠테이션을 로드하고, 차트를 만든 뒤, 차트의 워크북 스트림을 파일에 기록하는 것만큼 간단합니다. 아래 단계에서는 프로젝트 설정부터 최종 검증까지 전체 과정을 안내합니다.

## Prerequisites
시작하기 전에 다음 항목을 준비하십시오:

### Required Libraries and Versions
- **Aspose.Slides for Java** 버전 25.4 이상

### Environment Setup Requirements
- Java Development Kit (JDK) 16 이상
- IntelliJ IDEA 또는 Eclipse와 같은 코드 편집기 또는 IDE

### Knowledge Prerequisites
- 기본 Java 프로그래밍 능력
- Maven 또는 Gradle 빌드 시스템에 대한 이해

## Setting Up Aspose.Slides for Java
Aspose.Slides를 사용하려면 Maven 또는 Gradle을 통해 프로젝트에 포함시킵니다.

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

또는 [최신 버전을 직접 다운로드](https://releases.aspose.com/slides/java/)하십시오.

### License Acquisition Steps
Aspose.Slides는 전체 기능을 체험할 수 있는 무료 체험 라이선스를 제공합니다. 임시 라이선스를 신청하거나 장기 사용을 위한 라이선스를 구매할 수도 있습니다. 다음 절차를 따르세요:
1. 라이선스를 받으려면 [Aspose 구매 페이지](https://purchase.aspose.com/buy)로 이동하십시오.  
2. 무료 체험은 [Releases](https://releases.aspose.com/slides/java/)에서 다운로드하십시오.  
3. 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 신청하십시오.

라이선스 파일을 확보한 후 Java 애플리케이션에서 초기화합니다:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Implementation Guide

### Feature 1: Load Presentation
프레젠테이션 로드는 모든 조작 작업의 첫 단계입니다.

#### Overview
이 기능은 Aspose.Slides for Java를 사용해 기존 PowerPoint 파일을 로드하는 방법을 보여줍니다.

#### Step‑by‑Step Implementation
**Load Presentation**
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
**Explanation:**  
- `Presentation` 은 `.pptx` 파일 경로를 인자로 초기화됩니다.  
- 네이티브 리소스를 해제하려면 `Presentation` 객체를 반드시 dispose 해야 합니다.

### Feature 2: Add Pie Chart Slide
차트를 추가하면 데이터 표현력이 크게 향상되며, 많은 개발자가 **how to add chart slide** 를 Java에서 구현하는 방법을 궁금해합니다.

#### Overview
이 기능은 프레젠테이션의 첫 번째 슬라이드에 **pie chart slide** (전형적인 “add pie chart slide” 시나리오)를 추가하는 방법을 보여줍니다.

#### Step‑by‑Step Implementation
**Add Pie Chart**
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
**Explanation:**  
- `addChart` 는 파이 차트를 삽입합니다.  
- 매개변수는 차트 유형과 슬라이드 내 위치/크기를 정의합니다.

### Feature 3: Generate Excel from Chart
차트 데이터를 내보내면 **generate excel from chart** 로 보다 심층적인 분석이 가능합니다.

#### Overview
이 기능은 프레젠테이션의 차트 데이터를 외부 Excel 워크북으로 내보내는 방법을 시연합니다.

#### Step‑by‑Step Implementation
**Export Data**
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
**Explanation:**  
- `readWorkbookStream` 은 차트의 워크북 데이터를 추출합니다.  
- 바이트 배열을 `FileOutputStream` 으로 `.xlsx` 파일에 기록합니다.

### Feature 4: Embed Chart in Presentation with External Workbook
차트를 외부 워크북에 연결하면 **embed chart in presentation** 하면서 데이터 동기화를 유지할 수 있습니다.

#### Overview
이 기능은 외부 워크북 경로를 설정해 차트가 Excel 파일에서 직접 읽고 쓸 수 있도록 하는 방법을 보여줍니다.

#### Step‑by‑Step Implementation
**Set External Workbook Path**
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
**Explanation:**  
- `setExternalWorkbook` 은 차트를 Excel 파일에 연결하여 슬라이드를 재구성하지 않아도 동적 업데이트가 가능하게 합니다.

## Practical Applications
Aspose.Slides는 다양한 시나리오에 적용 가능한 다목적 솔루션을 제공합니다:

1. **Business Reports:** Java 애플리케이션에서 차트가 포함된 상세 보고서를 생성합니다.  
2. **Academic Presentations:** 인터랙티브 파이 차트 슬라이드로 강의를 강화합니다.  
3. **Financial Analysis:** **Export chart to excel** 로 심층 재무 모델링을 수행합니다.  
4. **Marketing Analytics:** 캠페인 성과를 시각화하고 **generate excel from chart** 로 분석 팀에 제공합니다.

## Frequently Asked Questions

**Q: 다른 차트 유형(예: Bar, Line)에도 이 방법을 사용할 수 있나요?**  
A: 물론입니다. `ChartType.Pie` 를 원하는 다른 `ChartType` 열거값으로 교체하면 됩니다.

**Q: 내보낸 파일을 읽기 위해 별도의 Excel 라이브러리가 필요합니까?**  
A: 필요 없습니다. 내보낸 `.xlsx` 파일은 표준 Excel 워크북이며, 모든 스프레드시트 프로그램에서 열 수 있습니다.

**Q: 외부 워크북이 슬라이드 크기에 영향을 줍니까?**  
A: 외부 워크북을 연결해도 PPTX 파일 크기가 크게 증가하지 않으며, 차트는 실행 시 워크북을 참조합니다.

**Q: Excel 데이터를 업데이트하면 슬라이드가 자동으로 변경 사항을 반영하나요?**  
A: 네. `setExternalWorkbook` 을 호출한 뒤 워크북을 저장하면, 프레젠테이션을 다시 열 때 변경 내용이 반영됩니다.

**Q: 동일한 프레젠테이션에서 여러 차트를 내보내려면 어떻게 해야 하나요?**  
A: 각 슬라이드의 차트 컬렉션을 순회하면서 `readWorkbookStream()` 을 호출하고, 각각을 별도 워크북 파일로 저장하면 됩니다.

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides 25.4 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}