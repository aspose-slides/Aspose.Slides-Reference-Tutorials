---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET을 사용하여 외부 Excel 통합 문서로 차트를 설정하는 방법을 알아보고 프레젠테이션과 데이터 관리를 개선하세요."
"title": "Aspose.Slides .NET에서 외부 통합 문서를 차트 데이터 소스로 설정하는 방법"
"url": "/ko/net/charts-graphs/set-external-workbook-charts-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides .NET을 사용하여 외부 통합 문서를 차트 데이터 소스로 설정하는 방법
## 소개
프레젠테이션에서 시각적으로 매력적인 차트를 만드는 것은 데이터 기반 인사이트를 효과적으로 전달하는 데 필수적입니다. 차트 데이터를 프레젠테이션 파일과 별도로 관리하는 것은 번거로울 수 있습니다. Aspose.Slides for .NET을 사용하면 외부 통합 문서를 차트의 데이터 소스로 연결하여 워크플로를 간소화하고 데이터를 체계적으로 정리할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides .NET을 사용하여 "외부 통합 문서에서 차트 데이터 설정" 기능을 구현하는 방법을 안내합니다.

**배울 내용:**
- Aspose.Slides for .NET을 사용하여 외부 통합 문서를 차트의 데이터 소스로 설정하는 방법.
- 외부 데이터를 사용하여 프레젠테이션에 차트를 추가하고 구성하는 단계입니다.
- Aspose.Slides 기능을 .NET 프로젝트에 통합합니다.

먼저, 필요한 전제 조건을 설정해 보겠습니다.
## 필수 조건
시작하기 전에 다음 설정이 있는지 확인하세요.
### 필수 라이브러리
- **.NET용 Aspose.Slides**이 라이브러리는 .NET 애플리케이션에서 PowerPoint 프레젠테이션을 만들고 조작하는 기능을 지원합니다. 개발 환경과의 호환성을 확보하세요.
### 환경 설정 요구 사항
- Visual Studio와 같은 AC# 개발 환경.
- 외부 통합 문서(예: `externalWorkbook.xlsx`) 차트 데이터를 포함합니다.
### 지식 전제 조건
- C# 프로그래밍과 .NET 프레임워크 개념에 대한 기본적인 이해.
- 프로그래밍 방식으로 PowerPoint 프레젠테이션 작업에 익숙함.
## .NET용 Aspose.Slides 설정
Aspose.Slides를 프로젝트에 통합하려면 다음 설치 방법 중 하나를 사용하세요.
**.NET CLI**
```bash
dotnet add package Aspose.Slides
```
**패키지 관리자**
```powershell
Install-Package Aspose.Slides
```
**NuGet 패키지 관리자 UI**
- IDE에서 NuGet 패키지 관리자를 엽니다.
- "Aspose.Slides"를 검색하여 최신 버전을 설치하세요.
### 라이센스 취득
Aspose.Slides를 최대한 활용하려면 라이선스를 취득해야 할 수 있습니다. 방법은 다음과 같습니다.
- **무료 체험**제한 없이 모든 기능을 탐색할 수 있는 임시 라이선스로 시작하세요.
- **임시 면허**: Aspose 웹사이트에서 평가 목적으로 신청하세요.
- **구입**: 장기적으로 이용하려면 구독을 구매하세요.
**기본 초기화:**
```csharp
// Aspose.Slides 라이선스가 있으면 초기화하세요.
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("path_to_your_license.lic");
```
## 구현 가이드
### 차트에 대한 외부 통합 문서 설정
이 기능을 사용하면 차트 데이터를 외부 Excel 통합 문서에 연결하여 통합 문서의 모든 업데이트가 프레젠테이션에 자동으로 반영되도록 할 수 있습니다.
#### 1단계: 프레젠테이션 초기화 및 차트 추가
새로운 프레젠테이션 인스턴스를 만들고 첫 번째 슬라이드에 파이 차트를 추가합니다.
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public class Feature_SetExternalWorkbook {
    public static void Run() {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        using (Presentation pres = new Presentation()) {
            // 첫 번째 슬라이드에 50,50 위치에 400x600 크기의 원형 차트를 추가합니다.
            IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Pie, 50, 50, 400, 600, false);
```
#### 2단계: 차트 데이터 액세스 및 외부 통합 문서 설정
차트 데이터 컬렉션에 액세스하여 외부 통합 문서를 데이터 원본으로 지정합니다.
```csharp
            // 조작을 위해 차트 데이터에 접근합니다.
            IChartData chartData = chart.ChartData;
            
            // 차트 데이터가 포함된 외부 통합 문서를 설정합니다.
            chartData.SetExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```
#### 3단계: 외부 통합 문서에서 시리즈 및 데이터 포인트 추가
범주와 값 모두에 대한 외부 통합 문서의 특정 셀에 연결하여 차트에 새 시리즈를 추가합니다.
```csharp
            // 외부 통합 문서의 셀 B1의 데이터를 사용하여 새 시리즈 추가
            chartData.Series.Add(chartData.ChartDataWorkbook.GetCell(0, "B1"), ChartType.Pie);

            // 셀 B2, B3 및 B4에서 시리즈의 데이터 포인트를 추가합니다.
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B2"));
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B3"));
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B4"));

            // A2, A3, A4 셀의 데이터를 사용하여 시리즈의 범주를 정의합니다.
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A2"));
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A3"));
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A4"));

            // 지정된 파일 이름으로 프레젠테이션을 저장합니다.
            pres.Save(dataDir + "Presentation_with_externalWorkbook.pptx");
        }
    }
}
```
### 문제 해결 팁
- 외부 통합 문서 경로가 올바르고 접근 가능한지 확인하세요.
- 코드의 셀 참조가 Excel 파일의 셀 참조와 일치하는지 확인하세요.
## 실제 응용 프로그램
차트에 외부 통합 문서를 설정하는 것이 매우 유용한 몇 가지 시나리오는 다음과 같습니다.
1. **재무 보고서**: 스프레드시트의 재무 데이터가 변경되면 차트를 자동으로 업데이트합니다.
2. **프로젝트 관리 대시보드**별도의 통합 문서에 저장된 진행률 지표를 프레젠테이션 슬라이드에 연결합니다.
3. **마케팅 분석**: 최신 캠페인 성과 데이터로 프레젠테이션을 최신 상태로 유지하세요.
## 성능 고려 사항
Aspose.Slides를 사용할 때 최적의 성능을 위해 다음 팁을 고려하세요.
- 가능하다면 필요한 데이터를 미리 로드하여 외부 통합 문서 호출을 최소화합니다.
- .NET에서 효율적인 메모리 관리 방식을 사용하여 대규모 프레젠테이션을 처리합니다.
- 최적화 및 버그 수정의 이점을 얻으려면 Aspose.Slides 라이브러리를 정기적으로 업데이트하세요.
## 결론
이 튜토리얼을 따라 Aspose.Slides for .NET을 사용하여 외부 통합 문서를 차트 데이터 원본으로 설정하는 방법을 알아보았습니다. 이 기능은 데이터 관리를 향상시키고 기본 데이터 변경 사항에 따라 프레젠테이션을 최신 상태로 유지할 수 있도록 해줍니다.
**다음 단계:**
- Aspose.Slides의 추가 기능을 살펴보고 프레젠테이션을 더욱 향상시켜 보세요.
- 다양한 차트 유형과 데이터 구성을 실험해 보세요.
여러분의 프로젝트에 이러한 기술을 구현해 보시기를 권장합니다. 더 자세히 알아보려면 [Aspose.Slides 문서](https://reference.aspose.com/slides/net/) 또는 커뮤니티 지원을 위해 포럼을 탐색해 보세요.
## FAQ 섹션
1. **네트워크 드라이브에 있는 외부 통합 문서를 연결하려면 어떻게 해야 하나요?**
   - 애플리케이션 환경에서 액세스하기 위한 적절한 권한과 경로가 설정되어 있는지 확인하세요.
2. **실시간으로 차트 데이터를 업데이트할 수 있나요?**
   - Aspose.Slides는 실시간 업데이트를 직접 지원하지 않지만, 자주 새로 고침하면 이 효과를 시뮬레이션할 수 있습니다.
3. **연결할 수 있는 외부 통합 문서의 수에 제한이 있습니까?**
   - 본질적인 제한은 없지만 성능은 시스템 성능과 통합 문서의 복잡성에 따라 달라질 수 있습니다.
4. **차트에 데이터가 올바르게 표시되지 않으면 어떻게 문제를 해결하나요?**
   - Excel 파일에서 코드의 셀 참조가 정확한지 확인하세요.
5. **외부 통합 문서에는 어떤 형식이 지원됩니까?**
   - Aspose.Slides는 주로 다음을 지원합니다. `.xlsx` 파일을 공유하지만, 특정 통합 문서 설정에 따라 호환성을 보장합니다.
## 자원
- [Aspose.Slides 문서](https://reference.aspose.com/slides/net/)
- [Aspose.Slides 다운로드](https://releases.aspose.com/slides/net/)
- [Aspose.Slides 라이선스 구매](https://purchase.aspose.com/buy)
- [무료 평가판](https://releases.aspose.com/slides/net/)
- [임시 면허 신청](https://purchase.aspose.com/temporary-license/)
- [Aspose 지원 포럼](https://forum.aspose.com/c/slides/14)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}