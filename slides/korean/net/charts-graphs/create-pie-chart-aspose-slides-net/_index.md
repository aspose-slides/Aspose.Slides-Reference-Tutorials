---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET을 사용하여 프레젠테이션에 파이 차트를 프로그래밍 방식으로 추가하는 방법을 배우고, 손쉽게 데이터 시각화를 향상시켜 보세요."
"title": "Aspose.Slides for .NET을 사용하여 PowerPoint에서 원형 차트 만들기"
"url": "/ko/net/charts-graphs/create-pie-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET을 사용하여 프레젠테이션에 원형 차트를 만들고 추가하는 방법
## 소개
매력적인 프레젠테이션을 만드는 데는 텍스트만으로는 부족할 때가 많습니다. 차트와 같은 시각적 요소는 데이터 스토리텔링의 효과를 크게 향상시킬 수 있습니다. PowerPoint 프레젠테이션에 프로그래밍 방식으로 동적 원형 차트를 추가하려면 **.NET용 Aspose.Slides** 이 작업을 원활하고 효율적으로 수행할 수 있도록 도와주는 강력한 도구입니다. 이 튜토리얼에서는 프레젠테이션 슬라이드에 원형 차트를 추가하고 외부 데이터 원본을 사용하여 구성하는 방법을 안내합니다.

### 당신이 배울 것
- Aspose.Slides for .NET을 사용하여 새 프레젠테이션을 만드는 방법
- 첫 번째 슬라이드에 파이 차트 추가하기
- 차트의 데이터 소스로 외부 통합 문서 URL 설정
- PPTX 형식으로 프레젠테이션 저장하기
먼저, 전제 조건부터 시작해서 이를 쉽게 달성할 수 있는 방법을 알아보겠습니다.
## 필수 조건
시작하기에 앞서 다음 사항을 준비하세요.
- **.NET용 Aspose.Slides** 라이브러리가 설치되어 있어야 합니다. .NET Framework 또는 .NET Core/.NET 5 이상과 호환되는 버전이 필요합니다.
- C# 프로그래밍에 대한 기본 지식과 Visual Studio IDE에 대한 익숙함이 필요합니다.
- 귀하의 컴퓨터(Windows, macOS 또는 Linux)에 개발 환경을 설정합니다.
## .NET용 Aspose.Slides 설정
### 설치 지침
다음과 같은 다양한 방법을 사용하여 .NET용 Aspose.Slides를 프로젝트에 추가할 수 있습니다.
**.NET CLI**
```shell
dotnet add package Aspose.Slides
```
**패키지 관리자 콘솔**
```powershell
Install-Package Aspose.Slides
```
**NuGet 패키지 관리자 UI**
1. Visual Studio에서 NuGet 패키지 관리자를 엽니다.
2. "Aspose.Slides"를 검색하세요.
3. 최신 버전을 설치하세요.
### 라이센스 취득
Aspose.Slides를 사용하려면 무료 체험판 라이선스로 시작하여 제한 없이 기능을 체험해 보세요. 운영 환경에서는 상업용 라이선스를 구매하거나 장기 테스트를 위해 임시 라이선스를 구매하는 것이 좋습니다. 여기를 방문하세요. [Aspose 구매 페이지](https://purchase.aspose.com/buy) 자세한 내용은.
### 기본 초기화
프로젝트에서 Aspose.Slides를 사용하려면 라이선스가 있는 경우 라이선스로 초기화해야 합니다.
```csharp
// 라이브러리 초기화
License license = new License();
license.SetLicense("path/to/your/license.lic");
```
## 구현 가이드
이제 설정이 끝났으니 각 기능을 단계별로 살펴보겠습니다.
### 프레젠테이션에 차트 만들기 및 추가
#### 개요
먼저 프레젠테이션을 만들고 첫 번째 슬라이드에 파이 차트를 추가해 보겠습니다.
#### 단계:
1. **프레젠테이션 초기화**
   인스턴스를 생성하여 시작하세요. `Presentation` PowerPoint 파일을 나타내는 클래스입니다.
   ```csharp
   using Aspose.Slides;
   
   string dataDir = "YOUR_DOCUMENT_DIRECTORY";
   
   using (Presentation pres = new Presentation())
   {
       // 여기에 차트를 추가하겠습니다.
   }
   ```
2. **파이 차트 추가**
   사용하세요 `Shapes.AddChart` 슬라이드의 특정 좌표에 원형 차트를 삽입하는 방법입니다.
   ```csharp
   IChart chart = pres.Slides[0].Shapes.AddChart(
       ChartType.Pie, 50, 50, 400, 600, true);
   ```
### 차트 데이터에 대한 외부 통합 문서 설정
#### 개요
이제 외부 통합 문서의 데이터를 사용하여 원형 차트를 구성해 보겠습니다.
#### 단계:
1. **차트 데이터 액세스**
   외부 데이터 소스 URL을 지정할 차트 데이터 인터페이스를 검색합니다.
   ```csharp
   IChartData chartData = chart.ChartData;
   ```
2. **외부 통합 문서 URL 설정**
   다음을 사용하여 데이터 소스의 URL을 설정하세요. `SetExternalWorkbook`이 예제에서는 플레이스홀더 URL을 사용하는데, 이는 실제 데이터 소스 경로로 바꿔야 합니다.
   ```csharp
   (chartData as ChartData).SetExternalWorkbook("http://경로가 존재하지 않습니다", false);
   ```
### 프레젠테이션을 파일로 저장
#### 개요
마지막으로, 원하는 위치에 PPTX 형식으로 프레젠테이션을 저장합니다.
#### 단계:
1. **프레젠테이션 저장**
   사용하세요 `Save` 방법 `Presentation` 파일을 디스크에 쓰는 클래스입니다.
   ```csharp
   pres.Save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
   ```
## 실제 응용 프로그램
- **사업 보고서**: 분기별 성과 평가를 위한 차트를 자동으로 생성합니다.
- **데이터 대시보드**: 데이터 소스와 통합하여 시각적 보고서를 실시간으로 업데이트합니다.
- **교육 콘텐츠**: 외부 연구나 연구 논문에서 최신 데이터를 가져와 역동적인 프레젠테이션을 만듭니다.
Aspose.Slides를 통합하면 다양한 도메인에서 프레젠테이션 제작 프로세스를 자동화하고 향상시킬 수 있습니다.
## 성능 고려 사항
대규모 데이터 세트나 수많은 차트를 작업할 때:
- .NET 내에서 메모리를 효과적으로 관리하여 리소스 사용을 최적화합니다.
- 폐기하다 `Presentation` 객체를 적절하게 해제하여 리소스를 확보합니다.
- 가능한 경우 비동기 작업을 사용하여 애플리케이션 응답성을 개선하세요.
## 결론
이 튜토리얼을 따라오시면 Aspose.Slides for .NET을 사용하여 원형 차트가 포함된 프레젠테이션을 프로그래밍 방식으로 만드는 방법을 배우실 수 있습니다. 이제 차트 생성을 자동화하고 외부 데이터 소스를 효율적으로 관리할 수 있는 도구를 갖추게 되셨습니다.
### 다음 단계
차트 스타일을 사용자 지정하고, 차트 유형을 추가하거나, Aspose.Cells와 같은 다른 Aspose 구성 요소를 통합하여 데이터 조작 기능을 향상시켜 더욱 깊이 있게 살펴보세요.
## FAQ 섹션
1. **Aspose.Slides란 무엇인가요?**  
   .NET에서 PowerPoint 프레젠테이션을 프로그래밍 방식으로 조작하기 위한 강력한 라이브러리입니다.
2. **라이선스 없이 Aspose.Slides를 사용할 수 있나요?**  
   네, 하지만 제약이 있습니다. 무료 체험판을 이용하거나 모든 기능을 사용하려면 라이선스를 구매하는 것을 고려해 보세요.
3. **차트 데이터를 동적으로 업데이트하려면 어떻게 해야 하나요?**  
   외부 통합 문서를 활용하고 해당 URL을 설정합니다. `SetExternalWorkbook` 방법.
4. **Aspose.Slides를 여러 플랫폼에서 사용할 수 있나요?**  
   네, Windows, macOS, Linux에서 .NET Framework와 .NET Core/.NET 5+를 지원합니다.
5. **어떤 다른 차트 유형이 지원되나요?**  
   Aspose.Slides를 사용하면 원형 차트 외에도 막대 그래프, 선형 차트 등 다양한 차트를 만들 수 있습니다.
## 자원
- [Aspose.Slides 문서](https://reference.aspose.com/slides/net/)
- [최신 버전 다운로드](https://releases.aspose.com/slides/net/)
- [라이센스 구매](https://purchase.aspose.com/buy)
- [무료 체험](https://releases.aspose.com/slides/net/)
- [임시 면허](https://purchase.aspose.com/temporary-license/)
- [지원 포럼](https://forum.aspose.com/c/slides/11)
오늘부터 Aspose.Slides를 프로젝트에 통합하여 PowerPoint 프레젠테이션을 향상시키고 자동화하세요!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}