---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET을 사용하여 외부 Excel 데이터를 연결하여 프레젠테이션을 개선하는 방법을 알아보세요. 이 가이드에서는 동적 차트를 설정, 구성 및 구현하는 방법을 안내합니다."
"title": "Aspose.Slides .NET에서 차트에 외부 통합 문서를 설정하는 방법 - 단계별 가이드"
"url": "/ko/net/data-integration/set-external-workbook-chart-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides .NET에서 차트에 대한 외부 통합 문서를 설정하는 방법: 단계별 가이드

## 소개

외부 소스의 데이터를 프레젠테이션에 직접 통합하면 프레젠테이션의 가치를 크게 높일 수 있습니다. Aspose.Slides for .NET을 사용하면 슬라이드 내 차트에 외부 통합 문서를 원활하게 설정하여 동적이고 업데이트된 시각화를 구현할 수 있습니다. 이 튜토리얼에서는 네트워크 기반 Excel 파일을 프레젠테이션의 차트에 연결하는 과정을 안내합니다.

**배울 내용:**
- Aspose.Slides .NET 환경 구성.
- 차트를 위한 네트워크 위치에서 외부 통합 문서를 설정합니다.
- C#에서 사용자 정의 리소스 로딩 핸들러를 구현합니다.
- 외부 데이터 소스를 프레젠테이션과 통합하는 실용적인 응용 프로그램입니다.

시작해 볼까요!

## 필수 조건

코딩을 시작하기 전에 다음 요구 사항을 충족하는지 확인하세요.

- **필수 라이브러리 및 종속성**: 프로젝트에 Aspose.Slides for .NET을 설치합니다.
- **환경 설정 요구 사항**: C# 개발 환경을 설정합니다(예: Visual Studio).
- **지식 전제 조건**: C# 프로그래밍에 대한 기본 지식이 있고 Aspose.Slides에 익숙합니다.

## .NET용 Aspose.Slides 설정

먼저 프로젝트에 Aspose.Slides 라이브러리를 설치하세요. 다음 방법 중 하나를 사용할 수 있습니다.

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**패키지 관리자 콘솔**
```bash
Install-Package Aspose.Slides
```

**NuGet 패키지 관리자 UI**: "Aspose.Slides"를 검색하여 최신 버전을 설치하세요.

### 라이센스 취득

Aspose.Slides를 사용하려면 무료 체험판을 이용하거나 임시 라이선스를 요청하세요. 장기간 사용하려면 공식 사이트에서 정식 라이선스를 구매하는 것이 좋습니다.

### 기본 초기화

애플리케이션에서 Aspose.Slides를 초기화하는 방법은 다음과 같습니다.
```csharp
using Aspose.Slides;

// Presentation 객체를 초기화합니다
Presentation pres = new Presentation();
```

## 구현 가이드

구현을 주요 기능으로 나누어 살펴보겠습니다.

### 네트워크에서 외부 통합 문서 설정

이 기능을 사용하면 네트워크 기반 Excel 파일을 프레젠테이션의 차트에 대한 외부 통합 문서로 연결할 수 있습니다.

#### 1단계: 외부 통합 문서 경로 지정
네트워크 드라이브에 있는 외부 통합 문서의 경로를 지정하세요.
```csharp
string externalWbPath = "http://귀하의_문서_디렉토리/스타일/2.xlsx";
```
바꾸다 `YOUR_DOCUMENT_DIRECTORY` Excel 파일이 호스팅되는 실제 디렉토리와 함께.

#### 2단계: 로드 옵션 구성
로드 옵션을 설정하고 사용자 정의 리소스 로딩 콜백을 지정합니다.
```csharp
LoadOptions opts = new LoadOptions();
opts.ResourceLoadingCallback = new WorkbookLoadingHandler();
```

#### 3단계: 프레젠테이션 만들기 및 차트 추가
프레젠테이션 인스턴스를 만들고 첫 번째 슬라이드에 차트를 추가합니다.
```csharp
using (Presentation pres = new Presentation(opts))
{
    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Pie, 50, 50, 400, 600, false);
    IChartData chartData = chart.ChartData;
    
    // 차트 데이터에 대한 외부 통합 문서 경로 설정
    (chartData as ChartData).SetExternalWorkbook(externalWbPath);
}
```

### 통합 문서 로딩 핸들러

이 기능은 지정된 네트워크 위치에서 Excel 파일을 가져오기 위해 사용자 정의 리소스 로딩 핸들러를 만드는 것을 포함합니다.

#### 1단계: 리소스 로딩 콜백 구현
구현하는 클래스를 만듭니다. `IResourceLoadingCallback`:
```csharp
class WorkbookLoadingHandler : IResourceLoadingCallback
{
    public ResourceLoadingAction ResourceLoading(IResourceLoadingArgs args)
    {
        string workbookPath = args.OriginalUri;
        
        // 경로가 네트워크 위치인지(로컬 파일 경로가 아닌지) 확인하세요.
        if (workbookPath.IndexOf(':') > 1 && !workbookPath.StartsWith("file:///"))
        {
            try
            {
                WebRequest request = WebRequest.Create(workbookPath);
                request.Credentials = new NetworkCredential("testuser", "testuser");
                
                using (WebResponse response = request.GetResponse())
                using (Stream responseStream = response.GetResponseStream())
                {
                    // 가져온 데이터를 Aspose.Slides에 제공합니다.
                    return ResourceLoadingAction.UserProvided;
                }
            }
            catch (Exception ex)
            {
                throw new InvalidOperationException(ex.ToString());
            }
        }
        else
        {
            return ResourceLoadingAction.Default;
        }
    }
}
```

## 실제 응용 프로그램

Aspose.Slides 프레젠테이션에 외부 데이터 소스를 통합하는 실제 사용 사례는 다음과 같습니다.
1. **동적 보고**: 최신 네트워크 데이터를 기반으로 재무 또는 성과 보고서의 차트를 자동으로 업데이트합니다.
2. **비즈니스 대시보드**: 기업 데이터베이스나 원격 서버에서 실시간 데이터를 가져오는 대화형 대시보드를 만듭니다.
3. **교육 콘텐츠**: 경제나 인구통계와 같은 과목에 대한 최신 통계 데이터를 사용하여 교육 자료를 개발합니다.

## 성능 고려 사항

외부 통합 문서를 사용할 때 다음과 같은 성능 팁을 고려하세요.
- **네트워크 요청 최적화**: 네트워크 요청 빈도를 최소화하여 지연 시간과 대역폭 사용량을 줄입니다.
- **자원 관리**더 이상 필요하지 않은 스트림을 즉시 해제하여 효율적인 메모리 사용을 보장합니다.
- **오류 처리**: 원활한 애플리케이션 작동을 보장하기 위해 네트워크 문제에 대한 강력한 오류 처리를 구현합니다.

## 결론

이제 Aspose.Slides for .NET을 사용하여 네트워크 위치에서 외부 통합 문서를 설정하는 방법을 확실히 이해하셨을 것입니다. 이 기능은 프레젠테이션의 상호작용성과 데이터 관련성을 크게 향상시킬 수 있습니다. 더 자세히 알아보려면 다른 Aspose 라이브러리를 통합하거나 Aspose.Slides에서 지원하는 추가 차트 유형을 살펴보는 것을 고려해 보세요. 이 솔루션을 여러분의 프로젝트 중 하나에 구현하여 그 이점을 직접 확인해 보세요!

## FAQ 섹션

**1. Aspose.Slides for .NET이란 무엇인가요?**
.NET용 Aspose.Slides는 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고, 조작하고, 변환할 수 있는 강력한 라이브러리입니다.

**2. Aspose.Slides를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**
네, Aspose는 Java, C++, Python 등에 대한 유사한 라이브러리를 제공합니다.

**3. 외부 통합 문서를 로드할 때 네트워크 오류가 발생하면 어떻게 처리합니까?**
귀하의 시스템 내에서 강력한 예외 처리를 구현하십시오. `WorkbookLoadingHandler` 잠재적인 네트워크 문제를 원활하게 관리합니다.

**4. 네트워크 위치 대신 로컬 파일을 사용할 수 있나요?**
네, 경로를 수정할 수 있습니다. `externalWbPath` 필요한 경우 로컬 파일을 가리킵니다.

**5. 새로운 데이터로 차트를 자동으로 업데이트할 수 있나요?**
네, 주기적으로 외부 통합 문서를 다시 가져와 설정하면 차트에 원본 데이터에 대한 모든 업데이트가 반영됩니다.

## 자원
- **선적 서류 비치**: [Aspose.Slides .NET 문서](https://reference.aspose.com/slides/net/)
- **다운로드**: [.NET용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/net/)
- **구입**: [Aspose.Slides 구매](https://purchase.aspose.com/buy)
- **무료 체험**: [Aspose.Slides 무료 체험판](https://releases.aspose.com/slides/net/)
- **임시 면허**: [Aspose.Slides에 대한 임시 라이선스 받기](https://purchase.aspose.com/temporary-license/)
- **지원하다**: [Aspose 지원 포럼](https://forum.aspose.com/c/slides/11)

이러한 리소스를 활용하면 .NET 프로젝트에서 Aspose.Slides의 잠재력을 최대한 활용할 수 있습니다. 즐거운 코딩 되세요!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}