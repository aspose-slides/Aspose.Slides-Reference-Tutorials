---
"date": "2025-04-16"
"description": "Aspose.Slides for .NET에서 글꼴 대체 규칙을 구현하여 다양한 언어와 스크립트에서 프레젠테이션의 텍스트가 올바르게 표시되는지 확인하는 방법을 알아보세요."
"title": "Aspose.Slides for .NET에서 글꼴 대체 규칙을 설정하는 방법 - 포괄적인 가이드"
"url": "/ko/net/shapes-text-frames/implement-font-fallback-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET에서 글꼴 대체 규칙을 설정하는 방법: 포괄적인 가이드

## 소개

Aspose.Slides for .NET을 사용하여 프레젠테이션을 제작할 때 타밀어나 일본어 히라가나처럼 특정 글꼴에서 지원하지 않는 문자를 처리해야 하는 경우가 있습니다. 다양한 언어와 기호에서 프레젠테이션의 텍스트가 올바르게 표시되도록 하려면 글꼴 대체 규칙을 설정하는 것이 필수적입니다.

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 글꼴 대체 규칙을 구현하는 방법을 안내합니다. 설치부터 실제 적용까지, 이 가이드를 통해 콘텐츠와 관계없이 프레젠테이션의 시각적 일관성을 유지할 수 있습니다.

**배울 내용:**
- 다양한 스크립트에 대한 유니코드 범위를 정의합니다.
- 지원되지 않는 문자에 대한 대체 글꼴을 설정합니다.
- 실제 프레젠테이션 시나리오에서 글꼴 대체를 적용합니다.
- 성능 최적화 및 다른 시스템과의 통합을 위한 팁.

먼저 전제 조건을 검토해 보겠습니다.

## 필수 조건

시작하기 전에 다음 사항을 확인하세요.

- **.NET용 Aspose.Slides** 라이브러리가 설치되었습니다. 다음 방법 중 하나를 사용하여 설치하세요.
  - **.NET CLI**: 달리다 `dotnet add package Aspose.Slides`
  - **패키지 관리자**: 실행하다 `Install-Package Aspose.Slides`
  - **NuGet 패키지 관리자 UI**: 최신 버전을 검색하여 설치하세요.
- .NET Core 또는 .NET Framework(버전 4.5 이상)로 설정된 개발 환경입니다.
- C# 프로그래밍에 대한 기본적인 이해.

## .NET용 Aspose.Slides 설정

Aspose.Slides를 사용하려면 다음에서 라이센스를 취득하세요. [Aspose 웹사이트](https://purchase.aspose.com/buy)설정 방법은 다음과 같습니다.

1. **설치**: 위에 언급된 설치 단계를 따르세요.
2. **라이센스 설정**:
   - 다음을 사용하여 프로젝트에 라이선스 파일을 로드합니다.
     ```csharp
     License license = new License();
     license.SetLicense("path_to_your_license_file.lic");
     ```

이 설정을 사용하면 .NET용 Aspose.Slides 작업을 시작할 수 있습니다.

## 구현 가이드

이 섹션에서는 명확한 단계별로 글꼴 대체 규칙을 설정하는 과정을 간략하게 설명합니다.

### 1. 유니코드 범위 및 대체 글꼴 정의

각 스크립트나 기호 집합에는 적절한 표시를 보장하기 위해 특정 유니코드 범위와 해당 대체 글꼴이 필요합니다.

#### 타밀어 문자

- **개요**: 기본 글꼴에서 타밀어를 지원하지 않는 경우 타밀어 문자의 경우 "Vijaya"를 사용하세요.

**구현 단계:**

##### 1단계: 유니코드 범위 정의
```csharp
uint startUnicodeIndexTamil = 0x0B80; // 타밀어 범위의 시작
uint endUnicodeIndexTamil = 0x0BFF;   // 타밀어 범위의 끝
```
이 스니펫은 타밀어 문자의 유니코드 범위를 정의합니다.

##### 2단계: 대체 규칙 만들기
```csharp
IFontFallBackRule tamilFallbackRule = new FontFallBackRule(startUnicodeIndexTamil, endUnicodeIndexTamil, "Vijaya");
```
여기서는 "Vijaya"를 대체 글꼴로 사용하여 대체 규칙을 만듭니다.

#### 일본어 히라가나

- **개요**: 지원되지 않는 히라가나 문자의 경우 "MS Mincho" 또는 "MS Gothic"을 사용하세요.

**구현 단계:**

##### 1단계: 유니코드 범위 정의
```csharp
uint startUnicodeIndexHiragana = 0x3040; // 히라가나 범위의 시작
uint endUnicodeIndexHiragana = 0x309F;   // 히라가나 범위의 끝
```
이 스니펫은 히라가나에 대한 유니코드 경계를 설정합니다.

##### 2단계: 대체 규칙 만들기
```csharp
IFontFallBackRule hiraganaFallbackRule = new FontFallBackRule(startUnicodeIndexHiragana, endUnicodeIndexHiragana, "MS Mincho, MS Gothic");
```
이 규칙은 히라가나 문자에 대한 여러 대체 글꼴을 지정합니다.

#### 이모티콘 문자

- **개요**: "Segoe UI Emoji"와 같은 적절한 글꼴을 사용하여 이모티콘이 표시되도록 하세요.

**구현 단계:**

##### 1단계: 유니코드 범위 정의
```csharp
uint startUnicodeIndexEmoji = 0x1F300; // 이모티콘 범위의 시작
uint endUnicodeIndexEmoji = 0x1F64F;   // 이모티콘 범위의 끝
```
이는 이모티콘의 유니코드 범위를 정의합니다.

##### 2단계: 대체 규칙 만들기
```csharp
string[] fontNamesEmoji = { "Segoe UI Emoji, Segoe UI Symbol\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}