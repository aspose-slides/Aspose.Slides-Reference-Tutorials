---
date: '2026-03-02'
description: Aspose.Slides for Java를 사용하여 동적 파이 차트를 만들면서 Excel을 PowerPoint에 추가하고 Excel에서
  PowerPoint를 생성하는 방법을 배워보세요.
keywords:
- Aspose.Slides for Java
- Java PowerPoint automation
- Excel data integration
title: 'Excel을 PowerPoint에 추가: Aspose.Slides for Java를 사용한 파이 차트 동적 프레젠테이션'
url: /ko/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Excel을 PowerPoint에 추가하기: Aspose.Slides for Java를 사용한 파이 차트 동적 프레젠테이션

오늘날 데이터‑드리븐 환경에서 **add Excel to PowerPoint**를 빠르고 안정적으로 수행하여 청중이 숫자를 시각적인 형식으로 볼 수 있도록 합니다. 이 튜토리얼에서는 Excel에서 PowerPoint를 생성하고, Java로 파이 차트를 만들며, 차트 데이터 범위를 구성하는 과정을 Aspose.Slides for Java와 함께 안내합니다. 최종적으로 Excel 워크북에서 실시간 데이터를 직접 가져오는 사용 가능한 프레젠테이션을 얻게 됩니다.

## 빠른 답변
- **Java로 차트를 생성하는 라이브러리는 무엇입니까?** Aspose.Slides for Java.
- **Excel 데이터를 PowerPoint 차트로 직접 가져올 수 있나요?** 예 – Aspose.Cells를 사용하여 통합 문서를 읽고 차트에 공급합니다.
- **어떤 차트 유형을 보여주나요?** 원형 차트입니다.
- **차트의 데이터 범위는 어떻게 설정합니까?** `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`를 호출합니다.
- **이 접근 방식의 주요 이점은 무엇입니까?** "PowerPoint에 Excel 추가" 작업 흐름을 자동화하여 수동으로 복사하여 붙여넣을 필요가 없습니다.

## **PowerPoint에 Excel 추가**란 무엇인가요?
Excel을 PowerPoint에 추가한다는 것은 진정한 시트 데이터의 프로그래밍 방식으로 슬라이드 데크에 참여하는 것을 의미합니다. Aspose.Slides와 Aspose.Cells를 사용하면 모든 Excel 파일을 이해하고 셀을 차트 시리즈에 매핑하여 PowerPoint를 수동으로 열지 많은 프레젠테이션을 만들 수 있습니다.

## Aspose.Slides for Java를 사용하여 Excel에서 PowerPoint를 생성해야 하는 이유

- **속도:** 보고서를 몇 분이 아닌 몇 초 만에 생성합니다.

- **정확성:** 원본 통합 문서에서 데이터를 직접 읽어와서 전사 오류를 제거합니다.

- **유연성:** 차트 색상, 스타일 및 데이터 범위를 즉시 사용자 지정할 수 있습니다.

- **확장성:** 배치 작업, 웹 서비스 또는 예약된 보고 파이프라인에 통합할 수 있습니다.

## 필수 조건

시작하기 전에 다음 항목을 확인하십시오.

- **Java Development Kit (JDK) 1.8 이상**이 설치되어 있어야 합니다.

- **Aspose.Slides for Java** 및 **Aspose.Cells for Java** 라이브러리(Maven, Gradle 또는 JAR 직접 다운로드)

- 시각화할 데이터가 포함된 Excel 통합 문서(`book1.xlsx`)

- 유효한 Aspose 라이선스(평가를 위해 무료 평가판을 사용할 수 있습니다.)

### 필수 라이브러리
Aspose.Slides와 Aspose.Cells가 필요합니다. 다음 종속성 관리 도구 중 하나를 사용하세요.

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

또는 [Aspose.Slides for Java 릴리스](https://releases.aspose.com/slides/java/)에서 JAR 파일을 직접 다운로드할 수도 있습니다.

### 라이선스 취득
- **무료 평가판:** [Aspose 다운로드 페이지](https://releases.aspose.com/slides/java/)에서 이용 가능합니다.

- **임시 라이선스:** 평가 제한 없이 테스트하려면 [Aspose 임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)에서 신청하세요.

- **정식 라이선스:** Aspose 제품을 실제 운영 환경에서 사용하려면 정식 라이선스를 구매하세요.

## Aspose.Slides for Java 설정

프로젝트에 Aspose.Slides 종속성을 추가하고(위의 Maven/Gradle 코드 조각 참조), 빌드 도구를 사용하지 않는 경우 JAR 파일을 클래스 경로에 추가하세요.

### 기본 초기화 및 설정
파워포인트 파일을 나타내는 핵심 클래스를 가져옵니다.

```java
import com.aspose.slides.Presentation;
```

## 구현 가이드

아래는 **Java를 이용한 파이 차트 생성**, **차트 데이터 범위 설정**, **Excel 데이터를 PowerPoint에 추가**하는 과정을 하나의 워크플로로 단계별로 안내합니다.

### 차트 생성 및 프레젠테이션에 추가

**개요:** 새 프레젠테이션을 열고 첫 번째 슬라이드를 선택한 후 파이 차트를 삽입합니다.

#### 1단계: 프레젠테이션 초기화
```java
Presentation pres = new Presentation();
```
- **목적:** 메모리에 빈 PowerPoint 파일을 생성합니다.

#### 2단계: 첫 번째 슬라이드 열기
```java
ISlide slide = pres.getSlides().get_Item(0);
```
- **설명:** 자동으로 생성된 첫 번째 슬라이드를 불러옵니다.

#### 3단계: 슬라이드에 원형 차트 추가
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```
- **매개변수:** 위치(`x`, `y`) 및 크기(`width`, `height`)

- **용도:** 슬라이드에 원형 차트 도형을 배치합니다.

### 파일에서 통합 문서 불러오기

**개요:** 차트에 사용할 데이터가 포함된 Excel 통합 문서를 불러옵니다.

#### 1단계: 문서 디렉터리 정의
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```
- `book1.xlsx` 파일이 있는 폴더로 설정하세요.

#### 2단계: 통합 문서 열기
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```
- **목적:** Excel 파일을 메모리로 읽어들입니다.

### 통합 문서를 ByteArrayOutputStream으로 저장

**개요:** Aspose.Slides에서 사용할 수 있도록 통합 문서를 바이트 배열로 변환합니다.

#### 1단계: ByteArrayOutputStream 생성
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```
- **목적:** 임시 저장을 위한 메모리 스트림을 제공합니다.

#### 2단계: 통합 문서를 스트림에 저장
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```
- **설명:** 통합 문서를 XLSX 바이트 스트림으로 차트에 씁니다.

### 통합 문서 데이터를 차트에 쓰기

**개요:** Excel 바이트 배열을 차트의 데이터 소스로 사용합니다.

#### 1단계: 차트에 데이터 입력
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```
- **목적:** 차트를 Excel 데이터에 연결합니다.

### 차트 데이터 범위 설정 및 계열 구성

**개요:** 차트에 표시할 셀을 정의하고 시각적 스타일을 향상시킵니다.

#### 1단계: 데이터 범위 정의
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```
- **설명:** 차트를 *Sheet2*의 정확한 범위로 지정합니다.

#### 2단계: 계열 속성 구성
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```
- **목적:** 원형 차트의 각 조각에 다양한 색상을 적용할 수 있습니다.

### 프레젠테이션을 파일로 저장

**개요:** 완성된 프레젠테이션을 디스크에 저장합니다.

#### 1단계: 출력 경로 정의
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```
- 최종 PowerPoint 파일을 저장할 폴더를 선택하세요.

#### 2단계: 프레젠테이션 저장
```java
pres.save(outPath, SaveFormat.Pptx);
```
- **설명:** 프레젠테이션을 `.pptx` 파일로 저장합니다.

## 실제 활용 사례

1. **비즈니스 보고:** 월별 매출 스프레드시트를 단 한 번의 명령으로 세련된 슬라이드 자료로 변환합니다.

2. **교육 도구:** 차트를 수동으로 만들 필요 없이 수업 발표를 위한 통계 분석 자료를 제공합니다.

3. **대시보드 통합:** Excel 통합 문서에서 실시간 데이터를 가져와 슬라이드 기반 대시보드를 자동으로 생성합니다.

## 성능 고려 사항

- **메모리 관리:** 메모리 누수를 방지하기 위해 스트림을 `try-with-resources` 블록으로 묶거나 `finally` 블록에서 닫습니다.

- **대규모 데이터 세트:** 데이터를 청크 단위로 처리하거나 필요한 값을 추출한 후 `Workbook.getWorksheets().clear()`를 사용합니다.

- **지연 로딩:** 애플리케이션 시작 시가 아닌 차트를 채울 때만 통합 문서를 로드합니다.

## 일반적인 문제 및 해결 방법

| 문제 | 해결 방법 |

|-------|----------|

| **차트에 데이터가 표시되지 않음** | 범위 문자열이 시트 이름과 셀 주소(`Sheet2!$A$1:$B$3`)와 정확히 일치하는지 확인하십시오. |

| **메모리 부족 오류** | 스트림이 즉시 해제되도록 `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }`를 사용하십시오. |

| **라이선스가 적용되지 않음** | Aspose 클래스를 인스턴스화하기 전에 라이선스를 로드하십시오. `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## 자주 묻는 질문

**Q: 라이선스 없이 Aspose.Slides를 사용할 수 있습니까?**
A: 예, 하지만 평가 모드에서는 워터마크가 추가되고 일부 기능이 제한됩니다. 실제 운영 환경에서 사용하려면 임시 또는 정식 라이선스를 취득하십시오.

**질문: Aspose.Slides에서 대규모 프레젠테이션을 어떻게 처리하나요?**
답변: 효율적인 리소스 관리를 통해 프레젠테이션을 더 작은 부분으로 나누고 사용하지 않는 개체를 즉시 제거하세요.

**질문: Aspose.Slides에서 내보낼 수 있는 파일 형식은 무엇인가요?**
답변: PPTX, PDF, XPS, ODP, HTML 및 PNG, JPEG, BMP와 같은 이미지 형식을 지원합니다.

**질문: 새 PowerPoint 파일을 만드는 대신 기존 파일을 업데이트할 수 있나요?**
답변: 네, 가능합니다. `new Presentation("existing.pptx")`를 사용하여 기존 파일을 불러온 후 슬라이드/차트를 수정하고 저장하면 됩니다.

**질문: 라이브러리에서 개별 파이 조각에 사용자 지정 색상을 설정할 수 있나요?**
답변: 네, 가능합니다. 시리즈를 가져온 후 `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);`를 사용하여 `Color`를 설정하고 원하는 색상을 지정할 수 있습니다.

## 리소스
- **문서:** [Aspose.Slides Java API 참조](https://reference.aspose.com/slides/java/)
- **다운로드:** [Aspose.Slides Java 릴리스](https://releases.aspose.com/slides/java/)
- **라이선스 구매:** [Aspose 제품 구매](https://purchase.aspose.com/buy)
- **무료 체험:** [Aspose.Slides 무료 체험](https://releases.aspose.com/slides/java/)
- **임시 라이선스:** [임시 라이선스 받기](https://purchase.aspose.com/temporary-license)

---

**최종 업데이트:** 2026년 3월 2일
**테스트 환경:** Aspose.Slides 25.4 for Java (JDK16) 및 Aspose.Cells 25.4
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}