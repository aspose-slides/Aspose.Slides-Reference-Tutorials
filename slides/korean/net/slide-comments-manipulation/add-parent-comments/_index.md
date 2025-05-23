---
"description": "Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션에 대화형 댓글과 답글을 추가하는 방법을 알아보세요. 참여도와 협업을 향상시키세요."
"linktitle": "슬라이드에 부모 의견 추가"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "Aspose.Slides를 사용하여 슬라이드에 부모 주석 추가"
"url": "/ko/net/slide-comments-manipulation/add-parent-comments/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides를 사용하여 슬라이드에 부모 주석 추가


인터랙티브 기능으로 PowerPoint 프레젠테이션을 더욱 풍성하게 만들고 싶으신가요? Aspose.Slides for .NET을 사용하면 댓글과 답글을 추가하여 청중에게 역동적이고 매력적인 경험을 선사할 수 있습니다. 이 단계별 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 슬라이드에 부모 댓글을 추가하는 방법을 보여드립니다. 이 흥미로운 기능을 자세히 살펴보겠습니다.

## 필수 조건

시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.

1. Aspose.Slides for .NET: Aspose.Slides for .NET이 설치되어 있는지 확인하세요. 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/net/).

2. Visual Studio: .NET 애플리케이션을 만들고 실행하려면 Visual Studio가 필요합니다.

3. C#에 대한 기본 지식: 이 튜토리얼에서는 사용자가 C# 프로그래밍에 대한 기본적인 이해가 있다고 가정합니다.

이제 전제 조건을 충족했으므로 필요한 네임스페이스를 가져오겠습니다.

## 네임스페이스 가져오기

먼저 관련 네임스페이스를 프로젝트에 가져와야 합니다. 이 네임스페이스는 Aspose.Slides for .NET 작업에 필요한 클래스와 메서드를 제공합니다.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

필수 구성 요소와 네임스페이스가 준비되었으니, 슬라이드에 부모 주석을 추가하는 과정을 여러 단계로 나누어 보겠습니다.

## 1단계: 프레젠테이션 만들기

시작하려면 Aspose.Slides for .NET을 사용하여 새 프레젠테이션을 만들어야 합니다. 이 프레젠테이션은 댓글을 추가할 캔버스가 됩니다.

```csharp
// 출력 디렉토리의 경로입니다.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // 댓글을 추가하는 코드는 여기에 입력하세요.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

위의 코드에서 다음을 바꾸세요. `"Output Path"` 원하는 출력 프레젠테이션 경로를 선택하세요.

## 2단계: 댓글 작성자 추가

댓글을 추가하기 전에 해당 댓글의 작성자를 정의해야 합니다. 이 예시에서는 "Author_1"과 "Author_2"라는 두 명의 작성자가 있으며, 각 작성자는 다음 인스턴스로 표현됩니다. `ICommentAuthor`.

```csharp
// 댓글 추가
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// 댓글1에 대한 답글 추가
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

이 단계에서는 두 명의 댓글 작성자를 만들고, 최초 댓글과 댓글에 대한 답변을 추가합니다.

## 3단계: 답변 추가

댓글의 계층 구조를 만들려면 기존 댓글에 답글을 더 추가할 수 있습니다. 여기서는 "comment1"에 두 번째 답글을 추가합니다.

```csharp
// 댓글1에 대한 답글 추가
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

이렇게 하면 프레젠테이션 내에서 대화의 흐름이 형성됩니다.

## 4단계: 중첩된 답변 추가

댓글에는 중첩된 답글이 있을 수 있습니다. 이를 보여주기 위해 "댓글 1에 대한 답글 2"에 답글을 추가하여 하위 답글을 만들어 보겠습니다.

```csharp
// 답글에 답글 추가
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

이 단계에서는 .NET용 Aspose.Slides가 주석 계층 구조를 관리하는 데 얼마나 다양한지 보여줍니다.

## 5단계: 더 많은 댓글과 답변

필요에 따라 댓글과 답글을 더 추가할 수 있습니다. 이 예시에서는 댓글 두 개와 그 중 하나에 답글 하나를 추가합니다.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

이 단계에서는 프레젠테이션을 위해 매력적이고 대화형 콘텐츠를 만드는 방법을 보여줍니다.

## 6단계: 계층 구조 표시

주석 계층 구조를 시각화하려면 콘솔에 표시할 수 있습니다. 이 단계는 선택 사항이지만 디버깅 및 구조 이해에 도움이 될 수 있습니다.

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

경우에 따라 댓글과 댓글에 달린 답글을 삭제해야 할 수도 있습니다. 아래 코드 조각은 "comment1"과 그 댓글에 달린 모든 답글을 삭제하는 방법을 보여줍니다.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

이 단계는 프레젠테이션 콘텐츠를 관리하고 업데이트하는 데 유용합니다.

이 단계를 따라 Aspose.Slides for .NET을 사용하여 대화형 댓글 및 답글 기능이 포함된 프레젠테이션을 만들 수 있습니다. 청중의 참여를 유도하거나 팀원과 협업할 때 이 기능은 다양한 가능성을 제공합니다.

## 결론

Aspose.Slides for .NET은 PowerPoint 프레젠테이션을 개선하는 강력한 도구 세트를 제공합니다. 댓글과 답글을 추가할 수 있는 기능을 통해 청중을 사로잡는 역동적이고 인터랙티브한 콘텐츠를 제작할 수 있습니다. 이 단계별 가이드에서는 슬라이드에 상위 댓글을 추가하고, 계층 구조를 설정하고, 필요한 경우 댓글을 제거하는 방법을 보여줍니다. 다음 단계를 따르고 Aspose.Slides 설명서를 살펴보세요. [여기](https://reference.aspose.com/slides/net/), 프레젠테이션을 한 단계 더 발전시킬 수 있습니다.

## 자주 묻는 질문

### 프레젠테이션 내 특정 슬라이드에 주석을 추가할 수 있나요?
네, 댓글을 만들 때 대상 슬라이드를 지정하여 프레젠테이션의 모든 슬라이드에 댓글을 추가할 수 있습니다.

### 프레젠테이션에서 댓글의 모양을 사용자 지정할 수 있나요?
.NET용 Aspose.Slides를 사용하면 텍스트, 작성자 정보, 슬라이드에서의 위치 등 주석의 모양을 사용자 지정할 수 있습니다.

### 댓글과 답변을 별도의 파일로 내보낼 수 있나요?
네, 7단계에서 설명한 대로 댓글과 답변을 별도의 프레젠테이션 파일로 내보낼 수 있습니다.

### Aspose.Slides for .NET은 최신 버전의 PowerPoint와 호환됩니까?
Aspose.Slides for .NET은 다양한 PowerPoint 버전에서 작동하도록 설계되어 최신 릴리스와의 호환성을 보장합니다.

### Aspose.Slides for .NET에 사용할 수 있는 라이선스 옵션이 있나요?
예, Aspose 웹사이트에서 임시 라이선스를 포함한 라이선스 옵션을 살펴볼 수 있습니다. [여기](https://purchase.aspose.com/buy) 또는 무료 체험판을 사용해 보세요 [여기](https://releases.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}