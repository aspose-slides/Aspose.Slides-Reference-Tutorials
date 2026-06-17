---
date: '2026-06-03'
description: Aspose.Slides for Java를 사용하여 차트를 Excel로 내보내고 Java 차트를 만드는 방법을 배웁니다. 데이터
  시각화, 비즈니스 보고서 슬라이드 및 워크북 생성에 능숙해지세요.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Excel로 차트 내보내기 및 Aspose.Slides로 차트 만들기
url: /ko/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Excel로 차트 내보내기 및 Aspose.Slides로 차트 만들기

**Aspose.Slides for Java와 함께하는 마스터 데이터 시각화 기술**

오늘날 데이터 중심의 환경에서 *export chart to excel* 프로그램matically는 원시 데이터를 설득력 있는 시각 스토리로 전환할 수 있는 기술입니다. 비즈니스 보고서 슬라이드덱을 만들든 인터랙티브 분석 대시보드를 만들든, Aspose.Slides for Java는 코드에서 직접 차트를 생성, 맞춤화 및 내보낼 수 있는 힘을 제공합니다. 이 튜토리얼에서는 차트 객체를 만들고, 차트 데이터를 Excel로 내보내며, 외부 워크북에 차트를 연결하여 원활한 데이터 관리를 수행하는 방법을 배웁니다.

## 빠른 답변
- **필요한 라이브러리는 무엇인가요?** Aspose.Slides for Java (v25.4+).  
- **차트 데이터를 Excel로 내보낼 수 있나요?** 예 – `readWorkbookStream()`을 사용하고 바이트를 *.xlsx* 파일에 씁니다.  
- **필요한 Java 버전은?** JDK 16 이상.  
- **라이선스가 필요합니까?** 평가용 무료 체험판으로 사용할 수 있으며, 프로덕션에서는 영구 라이선스가 필요합니다.  
- **시연된 차트 유형은?** 파이 차트이지만 동일한 접근 방식으로 막대, 선 및 기타 차트 유형에도 적용됩니다.

## Aspose.Slides for Java란?
Aspose.Slides for Java는 Microsoft Office 없이도 개발자가 PowerPoint 프레젠테이션을 생성, 편집 및 변환할 수 있게 해주는 순수 Java API입니다. 슬라이드 조작, 차트 생성 및 포맷 변환을 위한 포괄적인 클래스 집합을 제공하여 자동화된 보고 솔루션을 가능하게 합니다. **50+ chart types**를 지원하고, 전체 데이터 바인딩 및 직접 Excel 내보내기를 제공하여 **data visualization java** 프로젝트에 이상적입니다.

## 차트를 만들고 Excel로 차트를 내보내기 위해 Aspose.Slides를 사용하는 이유
Excel로 차트를 빠르고 안정적으로 내보냅니다. Aspose.Slides는 Office 설치 필요성을 없애고 **over 50‑built‑in chart styles**를 제공하며, 표준 서버 하드웨어에서 **up to 300 MB in under 30 seconds**의 속도로 프레젠테이션을 처리합니다. 또한 네이티브 Excel 워크북 생성을 제공하여 다운스트림 분석가가 수동 복사‑붙여넣기 없이 원시 숫자를 직접 다룰 수 있습니다.

## 사전 요구 사항
시작하기 전에 다음을 확인하십시오:

### 필수 라이브러리 및 버전
- **Aspose.Slides for Java** version 25.4 or later (supports JDK 16+)

### 환경 설정 요구 사항
- Java Development Kit (JDK) 16 or higher  
- IntelliJ IDEA 또는 Eclipse와 같은 IDE(또는 선호하는 텍스트 편집기)

### 지식 사전 요구 사항
- 기본 Java 프로그래밍 기술  
- Maven 또는 Gradle 빌드 도구에 대한 친숙함

## Aspose.Slides for Java 설정
선호하는 빌드 시스템을 사용하여 라이브러리를 프로젝트에 추가합니다.

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

또는 [download the latest version directly](https://releases.aspose.com/slides/java/)를 통해 직접 다운로드할 수 있습니다.

### 라이선스 획득 단계
Aspose.Slides는 전체 기능을 탐색할 수 있는 무료 체험 라이선스를 제공합니다. 임시 라이선스를 신청하거나 장기 사용을 위해 구매할 수도 있습니다. 다음 단계를 따르세요:

1. [Aspose Purchase page](https://purchase.aspose.com/buy)에서 라이선스를 받으세요.  
2. 무료 체험은 [Releases](https://releases.aspose.com/slides/java/)에서 다운로드하세요.  
3. [here](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 신청하세요.

라이선스 파일을 확보한 후 Java 애플리케이션에서 초기화합니다:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## 단계별 가이드

### 차트 만들기 – 프레젠테이션 로드
차트를 추가하거나 수정하기 전에 기존 PowerPoint 파일을 로드합니다.  
`Presentation` 클래스는 메모리 내 PowerPoint 파일을 나타내며 슬라이드, 도형 및 차트 객체를 노출합니다.  
`new Presentation("input.pptx")`로 파일을 로드한 뒤 `presentation.getSlides().get_Item(0)`을 사용해 첫 번째 슬라이드와 작업합니다. 네이티브 리소스를 해제하려면 `finally` 블록에서 항상 `presentation.dispose()`를 호출하십시오.

### 차트 만들기 – 슬라이드에 파이 차트 추가
비례 데이터를 표시하기에 완벽한 파이 차트를 삽입합니다.  
`IChart` 인터페이스는 차트 조작을 위한 주요 진입점이며, `addChart`는 대상 슬라이드에 새 차트를 생성합니다. 차트 유형(`ChartType.Pie`), X/Y 좌표 및 너비/높이를 지정합니다. 생성 후 `ChartData` 객체를 통해 제목, 범례 및 데이터 시리즈를 맞춤화할 수 있습니다.

### 차트를 Excel로 내보내기 – 차트 데이터 내보내기
차트 데이터를 내보내면 분석가가 Excel에서 숫자를 직접 다룰 수 있어 더 깊은 인사이트를 얻을 수 있습니다.  
`readWorkbookStream()`은 차트의 기본 Excel 워크북을 바이트 배열로 반환합니다. `chart.getChartData().readWorkbookStream()`을 호출해 워크북을 가져오고 표준 Java I/O를 사용해 `externalWorkbook1.xlsx` 파일에 이 배열을 씁니다. 결과 Excel 파일에는 차트에 사용된 정확한 데이터가 포함되어 있어 추가 분석이 가능합니다.

### 차트 만들기 – 동적 데이터를 위한 외부 워크북 설정
슬라이드를 재구성하지 않고도 실시간 데이터 업데이트를 위해 차트를 외부 워크북에 연결합니다.  
`setExternalWorkbook()`은 차트를 외부 Excel 파일에 바인딩하여 동적 데이터 업데이트를 가능하게 합니다. `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")`를 사용해 차트를 외부 파일에 연결합니다. Excel 워크북을 편집하면 프레젠테이션을 다음에 열 때 차트가 자동으로 변경 사항을 반영하여 동적 보고 시나리오를 지원합니다.

## 실용적인 적용 사례
Aspose.Slides는 다양한 실제 시나리오에 적용 가능한 다목적 솔루션을 제공합니다:

1. **비즈니스 보고서 슬라이드:** 데이터 파이프라인에서 분기별 성과 차트를 자동으로 생성합니다.  
2. **학술 프레젠테이션:** 연구 데이터를 수동 차트 작성 없이 명확한 시각화로 전환합니다.  
3. **재무 분석:** 차트 데이터를 Excel로 내보내 감사인이 숫자를 검증하도록 하여 수동 오류를 줄입니다.  
4. **마케팅 분석:** 캠페인 지표를 시각화하고 이해관계자와 편집 가능한 워크북을 공유하여 협업 의사결정을 지원합니다.  
5. **자동 대시보드 생성:** 차트 생성 API와 예약 작업을 결합해 매일 아침 최신 슬라이드덱을 생산합니다.

## 일반적인 문제 및 해결 방법
- **`FileNotFoundException`** – `dataDir`가 유효한 폴더를 가리키고 출력 경로에 쓰기 권한이 있는지 확인하십시오.  
- **Memory leaks** – 네이티브 리소스를 해제하려면 `finally` 블록에서 항상 `presentation.dispose()`를 호출하십시오.  
- **Chart not appearing** – 슬라이드 인덱스(`get_Item(0)`)가 존재하는 슬라이드와 일치하는지, 차트 크기가 슬라이드 경계 내에 있는지 확인하십시오.  
- **Excel export produces empty file** – `readWorkbookStream()`을 호출하기 전에 차트에 실제 데이터 시리즈가 포함되어 있는지 확인하십시오.

## 자주 묻는 질문

**Q: 동일한 코드로 다른 차트 유형(예: Bar, Line)을 사용할 수 있나요?**  
A: 예. `ChartType.Pie`를 `ChartType.Bar` 또는 `ChartType.Line`과 같은 다른 `ChartType` 열거값으로 교체하면 됩니다.

**Q: 차트 생성 후 외부 워크북을 업데이트할 수 있나요?**  
A: 물론 가능합니다. Excel 파일을 직접 수정하면 차트가 다음에 프레젠테이션을 열 때 변경 사항을 반영합니다.

**Q: Excel 내보내기 기능에 별도의 라이선스가 필요합니까?**  
A: 필요 없습니다. Excel 내보내기 기능은 표준 Aspose.Slides for Java 라이선스에 포함되어 있습니다.

**Q: 지원되는 Java 버전은 무엇인가요?**  
A: Aspose.Slides for Java는 JDK 16 및 이후 버전을 지원합니다; 이전 버전도 작동할 수 있지만 공식적으로 테스트되지 않았습니다.

**Q: 생성된 Excel 워크북을 PPTX 파일에 포함시킬 수 있나요?**  
A: `chart.getChartData().setExternalWorkbook(null)`을 사용해 워크북을 포함시키거나, 동적 업데이트를 위해 외부 링크를 유지할 수 있습니다.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

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

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Java에서 Aspose.Slides로 차트 만들기 – 차트 추가 및 검증]( /slides/java/charts-graphs/aspose-slides-java-create-validate-charts/ )
- [Aspose.Slides Java를 사용하여 PowerPoint 차트에서 워크북 데이터 복구]( /slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/ )
- [Aspose.Slides for Java를 사용하여 PowerPoint 차트 데이터 범위 업데이트 방법]( /slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/ )

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}