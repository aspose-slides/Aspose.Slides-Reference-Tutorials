---
title: Aspose.Slides를 사용하여 슬라이드에 상위 댓글 추가
linktitle: 슬라이드에 상위 댓글 추가
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에 대화형 댓글과 응답을 추가하는 방법을 알아보세요. 참여와 협업을 강화하세요.
weight: 12
url: /ko/net/slide-comments-manipulation/add-parent-comments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides를 사용하여 슬라이드에 상위 댓글 추가


대화형 기능으로 PowerPoint 프레젠테이션을 향상시키고 싶으십니까? .NET용 Aspose.Slides를 사용하면 댓글과 답변을 통합하여 청중에게 역동적이고 매력적인 경험을 선사할 수 있습니다. 이 단계별 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 슬라이드에 상위 댓글을 추가하는 방법을 보여줍니다. 이 흥미로운 기능을 자세히 살펴보겠습니다.

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  .NET용 Aspose.Slides: .NET용 Aspose.Slides가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/slides/net/).

2. Visual Studio: .NET 애플리케이션을 만들고 실행하려면 Visual Studio가 필요합니다.

3. C#에 대한 기본 지식: 이 자습서에서는 사용자가 C# 프로그래밍에 대한 기본 지식을 가지고 있다고 가정합니다.

이제 필수 구성 요소를 다루었으므로 필요한 네임스페이스를 가져오는 작업을 진행해 보겠습니다.

## 네임스페이스 가져오기

먼저 관련 네임스페이스를 프로젝트로 가져와야 합니다. 이러한 네임스페이스는 .NET용 Aspose.Slides 작업에 필요한 클래스와 메서드를 제공합니다.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

전제 조건과 네임스페이스가 준비되었으므로 프로세스를 슬라이드에 상위 댓글을 추가하는 여러 단계로 나누어 보겠습니다.

## 1단계: 프레젠테이션 만들기

시작하려면 Aspose.Slides for .NET을 사용하여 새 프레젠테이션을 만들어야 합니다. 이 프레젠테이션은 귀하의 의견을 추가할 캔버스가 될 것입니다.

```csharp
// 출력 디렉터리의 경로입니다.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // 댓글을 추가하기 위한 코드가 여기에 표시됩니다.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 위의 코드에서`"Output Path"` 출력 프리젠테이션에 원하는 경로를 사용하세요.

## 2단계: 댓글 작성자 추가

주석을 추가하기 전에 해당 주석의 작성자를 정의해야 합니다. 이 예에는 "Author_1"과 "Author_2"라는 두 명의 작성자가 있으며 각각은 다음 인스턴스로 표시됩니다.`ICommentAuthor`.

```csharp
// 댓글 추가
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// comment1에 대한 답글 추가
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

이 단계에서는 두 명의 댓글 작성자를 생성하고 초기 댓글과 댓글에 대한 답변을 추가합니다.

## 3단계: 더 많은 답변 추가

댓글의 계층적 구조를 만들려면 기존 댓글에 더 많은 답글을 추가할 수 있습니다. 여기서는 "comment1"에 두 번째 응답을 추가합니다.

```csharp
// comment1에 대한 답글 추가
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

이렇게 하면 프레젠테이션 내에서 대화 흐름이 설정됩니다.

## 4단계: 중첩된 응답 추가

댓글에는 중첩된 답변도 있을 수 있습니다. 이를 입증하기 위해 "댓글 1에 대한 응답 2"에 응답을 추가하여 하위 응답을 만듭니다.

```csharp
// 답글에 답글 추가
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

이 단계에서는 댓글 계층 관리에 있어 Aspose.Slides for .NET의 다양성을 강조합니다.

## 5단계: 추가 댓글 및 답변

필요에 따라 계속해서 더 많은 댓글과 답글을 추가할 수 있습니다. 이 예에서는 댓글 두 개를 더 추가하고 그 중 하나에 답글을 추가합니다.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

이 단계에서는 프레젠테이션을 위한 매력적이고 대화형 콘텐츠를 만드는 방법을 보여줍니다.

## 6단계: 계층 구조 표시

댓글 계층 구조를 시각화하기 위해 콘솔에 표시할 수 있습니다. 이 단계는 선택 사항이지만 구조를 디버깅하고 이해하는 데 도움이 될 수 있습니다.

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## 7단계: 댓글 제거

어떤 경우에는 댓글과 댓글을 삭제해야 할 수도 있습니다. 아래 코드 조각은 "comment1"과 모든 응답을 제거하는 방법을 보여줍니다.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

이 단계는 프레젠테이션 콘텐츠를 관리하고 업데이트하는 데 유용합니다.

이러한 단계를 통해 Aspose.Slides for .NET을 사용하여 대화형 댓글과 답글이 포함된 프레젠테이션을 만들 수 있습니다. 청중의 참여를 유도하거나 팀 구성원과 협력하려는 경우 이 기능은 다양한 가능성을 제공합니다.

## 결론

.NET용 Aspose.Slides는 PowerPoint 프레젠테이션을 향상시키기 위한 강력한 도구 세트를 제공합니다. 댓글과 답글을 추가하는 기능을 사용하면 청중의 관심을 끄는 역동적이고 대화형 콘텐츠를 만들 수 있습니다. 이 단계별 가이드에서는 슬라이드에 상위 댓글을 추가하고, 계층 구조를 설정하고, 필요한 경우 댓글을 제거하는 방법도 보여주었습니다. 다음 단계를 수행하고 Aspose.Slides 문서를 탐색하여[여기](https://reference.aspose.com/slides/net/)를 사용하면 프레젠테이션을 한 단계 더 발전시킬 수 있습니다.

## 자주 묻는 질문

### 내 프레젠테이션 내의 특정 슬라이드에 댓글을 추가할 수 있나요?
예, 댓글을 작성할 때 대상 슬라이드를 지정하여 프레젠테이션의 모든 슬라이드에 댓글을 추가할 수 있습니다.

### 프레젠테이션의 댓글 모양을 사용자 정의할 수 있나요?
.NET용 Aspose.Slides를 사용하면 텍스트, 작성자 정보, 슬라이드에서의 위치 등 주석의 모양을 사용자 정의할 수 있습니다.

### 댓글과 답글을 별도의 파일로 내보낼 수 있나요?
예, 7단계에서 설명한 대로 댓글과 답글을 별도의 프레젠테이션 파일로 내보낼 수 있습니다.

### Aspose.Slides for .NET은 최신 버전의 PowerPoint와 호환됩니까?
Aspose.Slides for .NET은 다양한 PowerPoint 버전에서 작동하도록 설계되어 최신 릴리스와의 호환성을 보장합니다.

### .NET용 Aspose.Slides에 사용할 수 있는 라이선스 옵션이 있습니까?
 예, Aspose 웹사이트에서 임시 라이선스를 포함한 라이선스 옵션을 탐색할 수 있습니다.[여기](https://purchase.aspose.com/buy) 또는 무료 평가판을 사용해 보세요[여기](https://releases.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
