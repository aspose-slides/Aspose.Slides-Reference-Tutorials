---
date: '2026-06-13'
description: Excel을 PowerPoint에 추가하고, Aspose.Slides for Java를 사용하여 동적 파이 차트를 만들면서
  Excel에서 PowerPoint를 생성하는 방법을 배웁니다.
keywords:
- add excel to powerpoint
- generate powerpoint from excel
- import excel into powerpoint
- create pie chart java
- set chart data range
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  headline: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  type: TechArticle
- description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  name: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  steps:
  - name: Initialize Presentation
    text: '- **Purpose:** Creates an empty PowerPoint file in memory.'
  - name: Access First Slide
    text: '- **Explanation:** Retrieves the automatically created first slide.'
  - name: Add Pie Chart to Slide
    text: The `IChart` object represents a chart shape on a slide. - **Parameters:**
      Position (`x`, `y`) and size (`width`, `height`). - **Purpose:** Places a pie
      chart shape on the slide.
  - name: Define Document Directory
    text: '- Set this to the folder containing `book1.xlsx`.'
  - name: Open Workbook
    text: The `Workbook` class from Aspose.Cells loads an Excel file into memory.
      - **Purpose:** Reads the Excel file into memory.
  - name: Create ByteArrayOutputStream
    text: '`ByteArrayOutputStream` provides an in‑memory buffer for binary data. -
      **Purpose:** Provides an in‑memory stream for temporary storage.'
  - name: Save Workbook to Stream
    text: '- **Explanation:** Writes the workbook as an XLSX byte stream.'
  - name: Feed Data into Chart
    text: '- **Purpose:** Links the chart to the Excel data.'
  - name: Define Data Range
    text: The `setRange` method defines the Excel cells used as the chart’s data source.
      - **Explanation:** Points the chart to the exact range on *Sheet2*.
  - name: Configure Series Properties
    text: '- **Purpose:** Enables varied colors for each slice of the pie chart.'
  type: HowTo
- questions:
  - answer: Yes, but evaluation mode adds watermarks and limits some features. For
      production, obtain a temporary or full license.
    question: Can I use Aspose.Slides without a license?
  - answer: Use efficient resource management, split the presentation into smaller
      parts, and dispose of unused objects promptly.
    question: How do I handle large presentations in Aspose.Slides?
  - answer: PPTX, PDF, XPS, ODP, HTML, and image formats such as PNG, JPEG, and BMP.
    question: What file formats can Aspose.Slides export to?
  - answer: Absolutely. Load an existing file with `new Presentation("existing.pptx")`,
      modify slides/charts, then save.
    question: Is it possible to update an existing PowerPoint file instead of creating
      a new one?
  - answer: Yes – after retrieving the series, you can set `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);`
      and assign a `Color`.
    question: Does the library support setting custom colors for individual pie slices?
  type: FAQPage
title: 'Excel을 PowerPoint에 추가: Aspose.Slides for Java를 사용한 파이 차트 동적 프레젠테이션'
url: /ko/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Excel을 PowerPoint에 추가: Aspose.Slides for Java를 사용한 파이 차트 동적 프레젠테이션

오늘날 데이터 중심 환경에서 **Excel을 PowerPoint에 추가**를 빠르고 안정적으로 수행하여 청중이 숫자를 시각적으로 확인할 수 있습니다. 이 튜토리얼에서는 Excel에서 PowerPoint를 생성하고, Java로 파이 차트를 만들며, 차트 데이터 범위를 구성하는 방법을 Aspose.Slides for Java와 함께 안내합니다. 끝까지 따라 하면 Excel 워크북에서 실시간 데이터를 직접 가져오는 프레젠테이션을 바로 만들 수 있습니다.

## 빠른 답변
- **Java에서 차트를 생성하는 라이브러리는 무엇인가요?** Aspose.Slides for Java.  
- **Excel 데이터를 PowerPoint 차트에 직접 가져올 수 있나요?** 예 – Aspose.Cells를 사용해 워크북을 읽고 차트에 전달합니다.  
- **시연된 차트 유형은 무엇인가요?** 파이 차트.  
- **차트의 데이터 범위를 어떻게 설정하나요?** `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`를 호출합니다.  
- **이 접근 방식의 주요 이점은 무엇인가요?** “Excel을 PowerPoint에 추가” 워크플로를 자동화하여 수동 복사‑붙여넣기를 없앱니다.

## **Excel을 PowerPoint에 추가**란 무엇인가요?
Excel을 PowerPoint에 추가한다는 것은 스프레드시트 데이터를 프로그래밍 방식으로 가져와 슬라이드에 시각화하는 것을 의미합니다. 이를 통해 원본 데이터를 Excel 형식 그대로 유지하면서도 깔끔한 차트 형태로 프레젠테이션에 표시할 수 있어 워크북이 업데이트될 때마다 프레젠테이션도 즉시 반영됩니다.

## Aspose.Slides for Java를 사용하여 Excel에서 PowerPoint를 생성하는 이유는?
Aspose.Slides for Java를 사용하면 Excel에서 직접 데이터를 끌어와 수초 만에 슬라이드 덱을 만들 수 있습니다. 이 라이브러리는 50개 이상의 입력·출력 형식을 지원하고, 전체 파일을 메모리에 로드하지 않아도 수백 페이지 워크북을 처리할 수 있으며, 차트 스타일, 색상 및 데이터 범위에 대한 완전한 프로그래밍 제어를 제공합니다.

## Aspose.Slides for Java를 사용하여 Excel에서 PowerPoint를 생성하는 방법?
Aspose.Cells로 Excel 워크북을 로드하고, 새 `Presentation`을 만든 뒤 슬라이드에 파이 차트 모양을 추가하고 차트를 워크북의 데이터 범위에 바인딩합니다. 몇 줄의 Java 코드만으로 최신 스프레드시트 값을 반영하는 완전한 `.pptx` 파일을 만들 수 있습니다.

## Aspose.Slides를 사용하여 Excel을 PowerPoint에 가져오는 방법?
Excel 파일을 `Workbook` 객체로 읽고, 워크북을 바이트 배열로 변환한 뒤 해당 바이트 배열을 차트의 데이터 소스로 전달하면 됩니다. 차트는 지정된 범위를 자동으로 읽어 스프레드시트와 시각적 내용이 동기화됩니다.

## Aspose.Slides for Java에서 차트 데이터 범위를 설정하는 방법?
`chart.getChartData().setRange("SheetName!$StartCell:$EndCell")` 메서드를 사용해 차트가 카테고리와 값이 들어 있는 정확한 셀을 가리키도록 지정합니다. 이 한 번의 호출로 데이터 소스와 레이아웃을 동시에 정의해 수동 시리즈 구성을 없앨 수 있습니다.

## 전제 조건

시작하기 전에 다음이 설치되어 있는지 확인하십시오:

- **Java Development Kit (JDK) 1.8+** 설치
- **Aspose.Slides for Java** 및 **Aspose.Cells for Java** 라이브러리 (Maven, Gradle 또는 직접 JAR 다운로드)
- 시각화하려는 데이터를 포함한 Excel 워크북(`book1.xlsx`)
- 유효한 Aspose 라이선스(무료 체험판은 평가용으로 작동)

### 필수 라이브러리
Aspose.Slides와 Aspose.Cells가 필요합니다. 다음 의존성 관리 도구 중 하나를 사용하십시오:

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

또는 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 JAR를 직접 다운로드하십시오.

### 라이선스 획득
- **무료 체험:** [Aspose 다운로드 페이지](https://releases.aspose.com/slides/java/)에서 제공됩니다.  
- **임시 라이선스:** 평가 제한 없이 테스트하려면 [Aspose의 임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)에서 신청하십시오.  
- **구매 라이선스:** 제품을 프로덕션에서 사용하려면 전체 라이선스를 구매하십시오.

## Aspose.Slides for Java 설정

빌드 도구를 사용하지 않는 경우 Maven/Gradle 스니펫을 참고해 프로젝트에 Aspose.Slides 의존성을 추가하고 JAR 파일을 클래스패스에 배치하십시오.

### 기본 초기화 및 설정
PowerPoint 파일을 나타내는 핵심 클래스를 가져옵니다:  
```java
import com.aspose.slides.Presentation;
```  

## 구현 가이드

아래는 **create pie chart java**, **set chart data range**, **add Excel to PowerPoint**를 한 흐름으로 다루는 단계별 안내입니다.

### 프레젠테이션에 차트 생성 및 추가

**Overview:** 새 프레젠테이션을 초기화하고, 첫 번째 슬라이드를 가져온 뒤 파이 차트를 삽입합니다.

#### 단계 1: 프레젠테이션 초기화  
```java
Presentation pres = new Presentation();
```  
- **목적:** 메모리 내에 빈 PowerPoint 파일을 생성합니다.

#### 단계 2: 첫 슬라이드 접근  
```java
ISlide slide = pres.getSlides().get_Item(0);
```  
- **설명:** 자동으로 생성된 첫 번째 슬라이드를 가져옵니다.

#### 단계 3: 슬라이드에 파이 차트 추가  
`IChart` 객체는 슬라이드에 차트 형태를 나타냅니다.  
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```  
- **매개변수:** 위치(`x`, `y`)와 크기(`width`, `height`).  
- **목적:** 슬라이드에 파이 차트 형태를 배치합니다.

### 파일에서 워크북 로드

**Overview:** 차트에 사용할 데이터를 담은 Excel 워크북을 로드합니다.

#### 단계 1: 문서 디렉터리 정의  
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```  
- 이 값을 `book1.xlsx`가 있는 폴더로 설정합니다.

#### 단계 2: 워크북 열기  
Aspose.Cells의 `Workbook` 클래스가 Excel 파일을 메모리로 로드합니다.  
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```  
- **목적:** Excel 파일을 메모리로 읽어들입니다.

### 워크북을 ByteArrayOutputStream에 저장

**Overview:** Aspose.Slides가 사용할 수 있도록 워크북을 바이트 배열로 변환합니다.

#### 단계 1: ByteArrayOutputStream 생성  
`ByteArrayOutputStream`은 바이너리 데이터를 위한 메모리 버퍼를 제공합니다.  
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```  
- **목적:** 임시 저장을 위한 메모리 내 스트림을 제공합니다.

#### 단계 2: 워크북을 스트림에 저장  
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```  
- **설명:** 워크북을 XLSX 바이트 스트림으로 씁니다.

### 워크북 데이터를 차트에 쓰기

**Overview:** Excel 바이트 배열을 차트의 데이터 소스로 공급합니다.

#### 단계 1: 차트에 데이터 공급  
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```  
- **목적:** 차트를 Excel 데이터에 연결합니다.

### 차트 데이터 범위 설정 및 시리즈 구성

**Overview:** 차트가 읽을 셀을 정의하고 시각적 스타일을 향상시킵니다.

#### 단계 1: 데이터 범위 정의  
`setRange` 메서드는 차트 데이터 소스로 사용할 Excel 셀을 정의합니다.  
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```  
- **설명:** 차트를 *Sheet2*의 정확한 범위에 지정합니다.

#### 단계 2: 시리즈 속성 구성  
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```  
- **목적:** 파이 차트 각 조각에 다양한 색상을 적용합니다.

### 프레젠테이션을 파일에 저장

**Overview:** 완성된 프레젠테이션을 디스크에 영구 저장합니다.

#### 단계 1: 출력 경로 정의  
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```  
- 최종 PowerPoint 파일을 저장할 폴더를 선택합니다.

#### 단계 2: 프레젠테이션 저장  
```java
pres.save(outPath, SaveFormat.Pptx);
```  
- **설명:** 프레젠테이션을 `.pptx` 파일로 저장합니다.

## 실용적인 적용 사례

1. **비즈니스 보고:** 월간 판매 스프레드시트를 단일 명령으로 깔끔한 슬라이드 덱으로 변환합니다.  
2. **교육 도구:** 수동 차트 생성 없이 교실 프레젠테이션에 통계 분석을 보여줍니다.  
3. **대시보드 통합:** Excel 워크북에서 실시간 데이터를 가져오는 슬라이드 기반 대시보드 생성을 자동화합니다.

## 성능 고려 사항

- **메모리 관리:** 스트림을 try‑with‑resources로 감싸거나 `finally` 블록에서 닫아 메모리 누수를 방지합니다.  
- **대용량 데이터셋:** 데이터를 청크로 처리하거나 필요한 값을 추출한 후 `Workbook.getWorksheets().clear()`를 사용합니다.  
- **지연 로딩:** 차트를 채워야 할 때만 워크북을 로드하고 애플리케이션 시작 시에는 로드하지 않습니다.

## 일반적인 문제와 해결책

| 문제 | 해결책 |
|------|--------|
| **차트에 데이터가 표시되지 않음** | 범위 문자열이 시트 이름 및 셀 주소와 정확히 일치하는지 확인합니다 (`Sheet2!$A$1:$B$3`). |
| **OutOfMemoryError** | `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }`를 사용하여 스트림이 즉시 해제되도록 합니다. |
| **라이선스가 적용되지 않음** | Aspose 클래스를 인스턴스화하기 전에 라이선스를 로드합니다: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## 자주 묻는 질문

**Q: Aspose.Slides를 라이선스 없이 사용할 수 있나요?**  
A: 예, 가능하지만 평가 모드에서는 워터마크가 추가되고 일부 기능에 제한이 있습니다. 프로덕션에서는 임시 또는 전체 라이선스를 획득하세요.

**Q: Aspose.Slides에서 대용량 프레젠테이션을 어떻게 처리하나요?**  
A: 효율적인 리소스 관리를 사용하고, 프레젠테이션을 작은 부분으로 나누며, 사용하지 않는 객체를 즉시 해제합니다.

**Q: Aspose.Slides가 내보낼 수 있는 파일 형식은 무엇인가요?**  
A: PPTX, PDF, XPS, ODP, HTML 및 PNG, JPEG, BMP와 같은 이미지 형식.

**Q: 새 파일을 만들지 않고 기존 PowerPoint 파일을 업데이트할 수 있나요?**  
A: 가능합니다. `new Presentation("existing.pptx")`로 기존 파일을 로드하고 슬라이드/차트를 수정한 뒤 저장합니다.

**Q: 라이브러리가 개별 파이 조각에 대한 사용자 정의 색상 설정을 지원하나요?**  
A: 예. 시리즈를 가져온 후 `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);`를 사용해 `Color`를 지정하면 됩니다.

## 리소스
- **문서:** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **다운로드:** [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)
- **라이선스 구매:** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **무료 체험:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **임시 라이선스:** [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**마지막 업데이트:** 2026-06-13  
**테스트 환경:** Aspose.Slides 25.4 for Java (JDK 16) 및 Aspose.Cells 25.4  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Slides for Java를 사용하여 PowerPoint 차트 데이터 범위 업데이트하는 방법](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)
- [Aspose.Slides for Java로 파이 차트 PowerPoint 추가하는 방법](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Aspose.Slides for Java를 사용하여 PowerPoint에 차트 추가하기: 단계별 가이드](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}