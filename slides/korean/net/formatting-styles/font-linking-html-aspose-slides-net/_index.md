---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET을 사용하여 프레젠테이션을 HTML로 변환할 때 글꼴을 직접 포함시켜 일관된 글꼴 렌더링을 보장하는 방법을 알아보세요."
"title": "Aspose.Slides for .NET을 사용하여 HTML에서 글꼴을 연결하는 방법 - 단계별 가이드"
"url": "/ko/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET을 사용하여 HTML에서 글꼴을 연결하는 방법

## 소개

플랫폼 전반에 걸쳐 일관된 글꼴 렌더링을 유지하면서 프레젠테이션을 HTML로 변환하는 것은 어려울 수 있습니다. **.NET용 Aspose.Slides** HTML 출력에 내장된 글꼴 파일을 통해 프레젠테이션에 사용된 모든 글꼴을 직접 연결할 수 있도록 하여 원활한 솔루션을 제공합니다.

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 글꼴 연결을 구현하고 다양한 플랫폼에서 디자인의 일관성을 보장하는 방법을 살펴보겠습니다. 

**배울 내용:**
- Aspose.Slides for .NET으로 환경 설정하기
- HTML 변환에서 글꼴 연결
- 글꼴 임베딩을 위한 사용자 정의 컨트롤러 작성
- 실제 응용 프로그램 및 성능 고려 사항

이를 달성하기 위해 필요한 단계를 자세히 살펴보겠습니다.

## 필수 조건

시작하기에 앞서 다음 사항이 있는지 확인하세요.

### 필수 라이브러리 및 종속성
- **.NET용 Aspose.Slides** 라이브러리: 구현을 위한 핵심 구성 요소입니다.

### 환경 설정 요구 사항
- .NET Framework 또는 .NET Core가 설치된 개발 환경.

### 지식 전제 조건
- C# 프로그래밍에 대한 기본적인 이해.
- HTML 및 CSS에 대한 지식, 특히 `@font-face` 규칙.

## .NET용 Aspose.Slides 설정

.NET 프로젝트에서 Aspose.Slides를 사용하려면 라이브러리를 설치해야 합니다. 다음과 같은 몇 가지 방법을 소개합니다.

### .NET CLI 사용
```bash
dotnet add package Aspose.Slides
```

### 패키지 관리자 콘솔 사용
```powershell
Install-Package Aspose.Slides
```

### NuGet 패키지 관리자 UI를 통해
- Visual Studio에서 프로젝트를 엽니다.
- "NuGet 패키지 관리자"로 이동합니다.
- "Aspose.Slides"를 검색하여 최신 버전을 설치하세요.

### 라이센스 취득 단계
다음 단계에 따라 제한 없이 모든 기능을 테스트해 볼 수 있는 무료 평가판 라이선스를 얻으세요.
1. **무료 체험**: 임시 라이센스 다운로드 [여기](https://releases.aspose.com/slides/net/).
2. **임시 면허**: 확장된 접근 권한을 신청하세요 [여기](https://purchase.aspose.com/temporary-license/).
3. **구입**: 모든 기능을 사용하려면 라이센스를 구매하세요. [여기](https://purchase.aspose.com/buy).

### 기본 초기화 및 설정
```csharp
// License 클래스의 인스턴스를 생성합니다.
easpose.slides.License license = new aspose.slides.License();

// 파일 경로에서 라이센스를 적용합니다.
license.SetLicense("Aspose.Slides.lic");
```

## 구현 가이드

이제 HTML 변환에서 글꼴 연결을 구현해 보겠습니다. **.NET용 Aspose.Slides**.

### 기능 개요: HTML 변환에서 글꼴 연결
이 기능은 프레젠테이션에 사용된 모든 글꼴을 결과 HTML 파일에 직접 연결하여 글꼴 파일을 임베드합니다. 이 방법은 다양한 브라우저와 플랫폼에서 디자인 일관성을 유지하는 강력한 솔루션을 제공합니다.

#### 1단계: 사용자 정의 컨트롤러 만들기
사용자 정의 컨트롤러 클래스 만들기 `LinkAllFontsHtmlController` ~로부터 상속받는다 `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // 글꼴 파일이 저장될 디렉토리를 설정합니다.
    }
}
```
#### 2단계: 글꼴 쓰기 방법 구현
그만큼 `WriteFont` 이 방법은 글꼴 데이터를 파일에 쓰고 임베드를 위한 해당 HTML 코드를 생성합니다.
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // 사용할 글꼴 이름을 결정하고, 가능하다면 대체 글꼴을 사용하는 것이 좋습니다.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // .woff 글꼴 파일의 파일 경로를 구성합니다.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // 지정된 파일 경로에 글꼴 데이터를 씁니다.
    File.WriteAllBytes(path, fontData);

    // @font-face 규칙을 사용하여 글꼴을 포함하는 HTML 스타일 블록을 생성합니다.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}