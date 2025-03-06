---
title: PPT를 PPTX 형식으로 변환
linktitle: PPT를 PPTX 형식으로 변환
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PPT를 PPTX로 쉽게 변환하는 방법을 알아보세요. 원활한 형식 변환을 위한 코드 예제가 포함된 단계별 가이드입니다.
weight: 25
url: /ko/net/presentation-manipulation/convert-ppt-to-pptx-format/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


.NET을 사용하여 PowerPoint 파일을 이전 PPT 형식에서 최신 PPTX 형식으로 변환해야 한다면 잘 찾아오셨습니다. 이 단계별 튜토리얼에서는 Aspose.Slides for .NET API를 사용하는 프로세스를 안내합니다. 이 강력한 라이브러리를 사용하면 이러한 변환을 쉽게 처리할 수 있습니다. 시작하자!

## 전제 조건

코드를 살펴보기 전에 다음이 설정되어 있는지 확인하세요.

- Visual Studio: Visual Studio가 설치되어 있고 .NET 개발을 위한 준비가 되어 있는지 확인하세요.
-  .NET용 Aspose.Slides: 다음에서 .NET용 Aspose.Slides 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/slides/net/).

## 프로젝트 설정

1. 새 프로젝트 만들기: Visual Studio를 열고 새 C# 프로젝트를 만듭니다.

2. Aspose.Slides에 참조 추가: 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택한 다음 "Aspose.Slides"를 검색합니다. 패키지를 설치합니다.

3. 필수 네임스페이스 가져오기:

```csharp
using Aspose.Slides;
```

## PPT를 PPTX로 변환

이제 프로젝트를 설정했으므로 PPT 파일을 PPTX로 변환하는 코드를 작성해 보겠습니다.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// PPT 파일을 나타내는 Presentation 개체를 인스턴스화합니다.
Presentation pres = new Presentation(srcFileName);

//프레젠테이션을 PPTX 형식으로 저장
pres.Save(outPath, SaveFormat.Pptx);
```

이 코드 조각에서:

- `dataDir` PPT 파일이 있는 디렉터리 경로로 바꿔야 합니다.
- `outPath` 변환된 PPTX 파일을 저장하려는 디렉터리로 바꿔야 합니다.
- `srcFileName` 입력 PPT 파일의 이름입니다.
- `destFileName` 출력 PPTX 파일에 원하는 이름입니다.

## 결론

축하해요! Aspose.Slides for .NET API를 사용하여 PowerPoint 프레젠테이션을 PPT에서 PPTX 형식으로 성공적으로 변환했습니다. 이 강력한 라이브러리는 이와 같은 복잡한 작업을 단순화하여 .NET 개발 환경을 더욱 원활하게 만듭니다.

 아직 참여하지 않으셨다면,[.NET용 Aspose.Slides 다운로드](https://releases.aspose.com/slides/net/) 그 기능을 더 자세히 살펴보세요.

 더 많은 튜토리얼과 팁을 보려면 당사를 방문하세요.[선적 서류 비치](https://reference.aspose.com/slides/net/).

## 자주 묻는 질문

### 1. .NET용 Aspose.Slides란 무엇입니까?
Aspose.Slides for .NET은 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 조작 및 변환할 수 있는 .NET 라이브러리입니다.

### 2. Aspose.Slides for .NET을 사용하여 다른 형식을 PPTX로 변환할 수 있나요?
예, .NET용 Aspose.Slides는 PPT, PPTX, ODP 등을 포함한 다양한 형식을 지원합니다.

### 3. Aspose.Slides for .NET은 무료로 사용할 수 있나요?
 아니요, 상업용 도서관입니다. 하지만 다음을 탐색할 수 있습니다.[무료 시험판](https://releases.aspose.com/) 그 기능을 평가합니다.

### 4. Aspose.Slides for .NET에서 지원하는 다른 문서 형식이 있습니까?
예, .NET용 Aspose.Slides는 Word 문서, Excel 스프레드시트 및 기타 파일 형식 작업도 지원합니다.

### 5. Aspose.Slides for .NET에 대한 지원이나 질문은 어디서 받을 수 있나요?
 질문에 대한 답변을 찾고 지원을 요청할 수 있습니다.[Aspose.Slides 포럼](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
