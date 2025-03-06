---
title: 프레젠테이션을 XAML 형식으로 내보내기
linktitle: 프레젠테이션을 XAML 형식으로 내보내기
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 프레젠테이션을 XAML 형식으로 내보내는 방법을 알아보세요. 대화형 콘텐츠를 손쉽게 제작해보세요!
weight: 27
url: /ko/net/presentation-conversion/export-presentation-to-xaml-format/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


소프트웨어 개발 세계에서는 복잡한 작업을 단순화할 수 있는 도구를 갖추는 것이 필수적입니다. Aspose.Slides for .NET은 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업할 수 있는 도구 중 하나입니다. 이 단계별 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션을 XAML 형식으로 내보내는 방법을 살펴보겠습니다. 

## .NET용 Aspose.Slides 소개

튜토리얼을 시작하기 전에 Aspose.Slides for .NET에 대해 간략하게 소개하겠습니다. 개발자가 Microsoft PowerPoint 자체 없이도 PowerPoint 프레젠테이션을 생성, 수정, 변환 및 관리할 수 있는 강력한 라이브러리입니다. Aspose.Slides for .NET을 사용하면 PowerPoint 프레젠테이션과 관련된 다양한 작업을 자동화하여 개발 프로세스를 더욱 효율적으로 만들 수 있습니다.

## 전제 조건

이 튜토리얼을 진행하려면 다음이 필요합니다.

1. .NET용 Aspose.Slides: .NET용 Aspose.Slides 라이브러리가 설치되어 있고 .NET 프로젝트에서 사용할 준비가 되어 있는지 확인하세요.

2. 소스 프레젠테이션: XAML 형식으로 내보내려는 PowerPoint 프레젠테이션(PPTX)이 있습니다. 이 프레젠테이션의 경로를 알고 있는지 확인하세요.

3. 출력 디렉터리: 생성된 XAML 파일을 저장할 디렉터리를 선택합니다.

## 1단계: 프로젝트 설정

첫 번째 단계에서는 프로젝트를 설정하고 필요한 모든 구성 요소가 준비되었는지 확인합니다. 프로젝트에 Aspose.Slides for .NET 라이브러리에 대한 참조를 추가했는지 확인하세요.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// 소스 프레젠테이션 경로
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

 바꾸다`"Your Document Directory"` 소스 PowerPoint 프리젠테이션이 포함된 디렉터리 경로를 사용하세요. 또한 생성된 XAML 파일이 저장될 출력 디렉터리를 지정합니다.

## 2단계: 프레젠테이션을 XAML로 내보내기

이제 PowerPoint 프레젠테이션을 XAML 형식으로 내보내 보겠습니다. 이를 달성하기 위해 .NET용 Aspose.Slides를 사용하겠습니다. 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // 변환 옵션 생성
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // 나만의 출력 저장 서비스 정의
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // 슬라이드 변환
    pres.Save(xamlOptions);

    // XAML 파일을 출력 디렉터리에 저장
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

 이 코드 조각에서는 소스 프레젠테이션을 로드하고, XAML 변환 옵션을 생성하고, 다음을 사용하여 사용자 지정 출력 저장 서비스를 정의합니다.`NewXamlSaver`. 그런 다음 XAML 파일을 지정된 출력 디렉터리에 저장합니다.

## 3단계: 사용자 지정 XAML 보호기 클래스

 사용자 지정 XAML 보호기를 구현하기 위해 다음과 같은 클래스를 만듭니다.`NewXamlSaver` 구현하는 것은`IXamlOutputSaver` 상호 작용.

```csharp
class NewXamlSaver : IXamlOutputSaver
{
    private Dictionary<string, string> m_result = new Dictionary<string, string>();

    public Dictionary<string, string> Results
    {
        get { return m_result; }
    }

    public void Save(string path, byte[] data)
    {
        string name = Path.GetFileName(path);
        Results[name] = Encoding.UTF8.GetString(data);
    }
}
```

이 클래스는 XAML 파일을 출력 디렉터리에 저장하는 작업을 처리합니다.

## 결론

축하해요! Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션을 XAML 형식으로 내보내는 방법을 성공적으로 배웠습니다. 이는 프레젠테이션 조작이 포함된 프로젝트에서 작업할 때 귀중한 기술이 될 수 있습니다.

PowerPoint 자동화 작업을 향상시키기 위해 Aspose.Slides for .NET의 더 많은 기능을 자유롭게 탐색해 보세요.

## 자주 묻는 질문

1. ### .NET용 Aspose.Slides란 무엇입니까?
Aspose.Slides for .NET은 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업하기 위한 .NET 라이브러리입니다.

2. ### .NET용 Aspose.Slides는 어디서 구할 수 있나요?
 .NET용 Aspose.Slides는 다음에서 다운로드할 수 있습니다.[여기](https://purchase.aspose.com/buy).

3. ### 무료 평가판이 제공되나요?
 예, .NET용 Aspose.Slides의 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

4. ### .NET용 Aspose.Slides의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).

5. ### .NET용 Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 지원 및 커뮤니티 토론을 찾을 수 있습니다.[여기](https://forum.aspose.com/).

 더 많은 튜토리얼과 리소스를 보려면 다음을 방문하세요.[Aspose.Slides API 문서](https://reference.aspose.com/slides/net/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
