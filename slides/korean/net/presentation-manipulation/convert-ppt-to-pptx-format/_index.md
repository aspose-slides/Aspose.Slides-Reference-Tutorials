---
"description": "Aspose.Slides for .NET을 사용하여 PPTX로 손쉽게 변환하는 방법을 알아보세요. 원활한 형식 변환을 위한 코드 예제가 포함된 단계별 가이드입니다."
"linktitle": "PPT를 PPTX 형식으로 변환"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "PPT를 PPTX 형식으로 변환"
"url": "/ko/net/presentation-manipulation/convert-ppt-to-pptx-format/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PPT를 PPTX 형식으로 변환


.NET을 사용하여 PowerPoint 파일을 이전 PPT 형식에서 최신 PPTX 형식으로 변환해야 했던 적이 있다면, 여기가 바로 정답입니다. 이 단계별 튜토리얼에서는 Aspose.Slides for .NET API를 사용하여 변환 과정을 안내해 드립니다. 이 강력한 라이브러리를 사용하면 이러한 변환 작업을 손쉽게 처리할 수 있습니다. 시작해 볼까요!

## 필수 조건

코드를 살펴보기 전에 다음 사항이 설정되어 있는지 확인하세요.

- Visual Studio: Visual Studio가 설치되어 있고 .NET 개발을 위해 준비되었는지 확인하세요.
- .NET용 Aspose.Slides: .NET용 Aspose.Slides 라이브러리를 다운로드하여 설치하세요. [여기](https://releases.aspose.com/slides/net/).

## 프로젝트 설정

1. 새 프로젝트 만들기: Visual Studio를 열고 새 C# 프로젝트를 만듭니다.

2. Aspose.Slides에 대한 참조를 추가하려면 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택한 다음 "Aspose.Slides"를 검색하세요. 패키지를 설치하세요.

3. 필요한 네임스페이스 가져오기:

```csharp
using Aspose.Slides;
```

## PPT를 PPTX로 변환

이제 프로젝트가 설정되었으므로 PPT 파일을 PPTX로 변환하는 코드를 작성해 보겠습니다.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// PPT 파일을 나타내는 Presentation 객체를 인스턴스화합니다.
Presentation pres = new Presentation(srcFileName);

// PPTX 형식으로 프레젠테이션 저장
pres.Save(outPath, SaveFormat.Pptx);
```

이 코드 조각에서:

- `dataDir` PPT 파일이 있는 디렉토리 경로로 바꿔야 합니다.
- `outPath` 변환된 PPTX 파일을 저장하려는 디렉토리로 바꿔야 합니다.
- `srcFileName` 는 입력 PPT 파일의 이름입니다.
- `destFileName` 출력 PPTX 파일에 대한 원하는 이름입니다.

## 결론

축하합니다! Aspose.Slides for .NET API를 사용하여 PowerPoint 프레젠테이션을 PPT에서 PPTX 형식으로 변환했습니다. 이 강력한 라이브러리는 이처럼 복잡한 작업을 간소화하여 .NET 개발 환경을 더욱 원활하게 만들어 줍니다.

아직 하지 않았다면, [.NET용 Aspose.Slides 다운로드](https://releases.aspose.com/slides/net/) 그리고 그 기능을 더욱 탐색해보세요.

더 많은 튜토리얼과 팁을 보려면 다음을 방문하세요. [선적 서류 비치](https://reference.aspose.com/slides/net/).

## 자주 묻는 질문

### 1. Aspose.Slides for .NET이란 무엇인가요?
Aspose.Slides for .NET은 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고, 조작하고, 변환할 수 있는 .NET 라이브러리입니다.

### 2. Aspose.Slides for .NET을 사용하여 다른 형식을 PPTX로 변환할 수 있나요?
네, Aspose.Slides for .NET은 PPT, PPTX, ODP 등 다양한 형식을 지원합니다.

### 3. Aspose.Slides for .NET은 무료로 사용할 수 있나요?
아니요, 상업용 도서관이지만 탐색할 수 있습니다. [무료 체험](https://releases.aspose.com/) 그 기능을 평가합니다.

### 4. Aspose.Slides for .NET에서 지원하는 다른 문서 형식이 있나요?
네, Aspose.Slides for .NET은 Word 문서, Excel 스프레드시트 및 기타 파일 형식 작업도 지원합니다.

### 5. Aspose.Slides for .NET에 대한 지원이나 질문은 어디에서 받을 수 있나요?
귀하의 질문에 대한 답변을 찾고 지원을 요청할 수 있습니다. [Aspose.Slides 포럼](https://forum.aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}