---
"description": "Aspose.Slides for .NET का उपयोग करके अपने PowerPoint प्रस्तुतियों में इंटरैक्टिव टिप्पणियाँ और उत्तर जोड़ना सीखें। सहभागिता और सहयोग बढ़ाएँ।"
"linktitle": "स्लाइड में मूल टिप्पणियाँ जोड़ें"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": "Aspose.Slides का उपयोग करके स्लाइड में मूल टिप्पणियाँ जोड़ें"
"url": "/hi/net/slide-comments-manipulation/add-parent-comments/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides का उपयोग करके स्लाइड में मूल टिप्पणियाँ जोड़ें


क्या आप अपने पावरपॉइंट प्रेजेंटेशन को इंटरैक्टिव सुविधाओं के साथ बेहतर बनाना चाहते हैं? Aspose.Slides for .NET आपको टिप्पणियों और उत्तरों को शामिल करने की अनुमति देता है, जिससे आपके दर्शकों के लिए एक गतिशील और आकर्षक अनुभव बनता है। इस चरण-दर-चरण ट्यूटोरियल में, हम आपको दिखाएंगे कि Aspose.Slides for .NET का उपयोग करके स्लाइड में पैरेंट टिप्पणियाँ कैसे जोड़ें। आइए इस रोमांचक सुविधा को देखें और जानें।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. Aspose.Slides for .NET: सुनिश्चित करें कि आपके पास Aspose.Slides for .NET इंस्टॉल है। आप इसे डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/slides/net/).

2. विज़ुअल स्टूडियो: आपको अपना .NET अनुप्रयोग बनाने और चलाने के लिए विज़ुअल स्टूडियो की आवश्यकता होगी।

3. C# का बुनियादी ज्ञान: यह ट्यूटोरियल मानता है कि आपको C# प्रोग्रामिंग की बुनियादी समझ है।

अब जब हमने सभी पूर्वापेक्षाएँ पूरी कर ली हैं, तो चलिए आवश्यक नेमस्पेस को आयात करने के लिए आगे बढ़ते हैं।

## नामस्थान आयात करना

सबसे पहले, आपको अपने प्रोजेक्ट में प्रासंगिक नेमस्पेस को आयात करना होगा। ये नेमस्पेस .NET के लिए Aspose.Slides के साथ काम करने के लिए आवश्यक क्लास और विधियाँ प्रदान करते हैं।

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

पूर्वावश्यकताओं और नामस्थानों के साथ, आइए स्लाइड में मूल टिप्पणियाँ जोड़ने के लिए प्रक्रिया को कई चरणों में विभाजित करें।

## चरण 1: एक प्रस्तुति बनाएं

आरंभ करने के लिए, आपको .NET के लिए Aspose.Slides का उपयोग करके एक नई प्रस्तुति बनानी होगी। यह प्रस्तुति वह कैनवास होगी जिस पर आप अपनी टिप्पणियाँ जोड़ेंगे।

```csharp
// आउटपुट निर्देशिका का पथ.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // टिप्पणियाँ जोड़ने के लिए आपका कोड यहां जाएगा।
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

उपरोक्त कोड में, प्रतिस्थापित करें `"Output Path"` अपने आउटपुट प्रेजेंटेशन के लिए वांछित पथ के साथ।

## चरण 2: टिप्पणी लेखक जोड़ें

टिप्पणियाँ जोड़ने से पहले, आपको इन टिप्पणियों के लेखकों को परिभाषित करना होगा। इस उदाहरण में, हमारे पास दो लेखक हैं, "Author_1" और "Author_2", जिनमें से प्रत्येक को एक उदाहरण द्वारा दर्शाया गया है `ICommentAuthor`.

```csharp
// टिप्पणी जोड़ना
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// टिप्पणी1 के लिए उत्तर जोड़ें
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

इस चरण में, हम दो टिप्पणी लेखक बनाते हैं और प्रारंभिक टिप्पणी तथा टिप्पणी पर उत्तर जोड़ते हैं।

## चरण 3: अधिक उत्तर जोड़ें

टिप्पणियों की पदानुक्रमिक संरचना बनाने के लिए, आप मौजूदा टिप्पणियों में और अधिक उत्तर जोड़ सकते हैं। यहाँ, हम "टिप्पणी 1" में दूसरा उत्तर जोड़ते हैं।

```csharp
// टिप्पणी1 के लिए उत्तर जोड़ें
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

इससे आपकी प्रस्तुति में वार्तालाप का प्रवाह स्थापित होता है।

## चरण 4: नेस्टेड उत्तर जोड़ें

टिप्पणियों में नेस्टेड उत्तर भी हो सकते हैं। इसे प्रदर्शित करने के लिए, हम "टिप्पणी 1 के लिए उत्तर 2" में एक उत्तर जोड़ते हैं, जिससे एक उप-उत्तर बनता है।

```csharp
// उत्तर में उत्तर जोड़ें
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

यह कदम टिप्पणी पदानुक्रमों के प्रबंधन में Aspose.Slides for .NET की बहुमुखी प्रतिभा पर प्रकाश डालता है।

## चरण 5: अधिक टिप्पणियाँ और उत्तर

आप आवश्यकतानुसार और टिप्पणियाँ और उत्तर जोड़ना जारी रख सकते हैं। इस उदाहरण में, हम दो और टिप्पणियाँ और उनमें से एक पर उत्तर जोड़ते हैं।

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

यह चरण दर्शाता है कि आप अपनी प्रस्तुतियों के लिए आकर्षक और इंटरैक्टिव सामग्री कैसे बना सकते हैं।

## चरण 6: पदानुक्रम प्रदर्शित करें

टिप्पणी पदानुक्रम को विज़ुअलाइज़ करने के लिए, आप इसे कंसोल पर प्रदर्शित कर सकते हैं। यह चरण वैकल्पिक है लेकिन संरचना को डीबग करने और समझने के लिए सहायक हो सकता है।

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

## चरण 7: टिप्पणियाँ हटाएँ

कुछ मामलों में, आपको टिप्पणियाँ और उनके उत्तरों को हटाने की आवश्यकता हो सकती है। नीचे दिया गया कोड स्निपेट दर्शाता है कि "comment1" और उसके सभी उत्तरों को कैसे हटाया जाए।

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

यह चरण आपकी प्रस्तुति सामग्री को प्रबंधित करने और अद्यतन करने के लिए उपयोगी है।

इन चरणों के साथ, आप .NET के लिए Aspose.Slides का उपयोग करके इंटरैक्टिव टिप्पणियों और उत्तरों के साथ प्रस्तुतियाँ बना सकते हैं। चाहे आप अपने दर्शकों को जोड़ना चाहते हों या टीम के सदस्यों के साथ सहयोग करना चाहते हों, यह सुविधा संभावनाओं की एक विस्तृत श्रृंखला प्रदान करती है।

## निष्कर्ष

Aspose.Slides for .NET आपके PowerPoint प्रेजेंटेशन को बेहतर बनाने के लिए उपकरणों का एक शक्तिशाली सेट प्रदान करता है। टिप्पणियाँ और उत्तर जोड़ने की क्षमता के साथ, आप गतिशील और इंटरैक्टिव सामग्री बना सकते हैं जो आपके दर्शकों को आकर्षित करती है। इस चरण-दर-चरण मार्गदर्शिका ने आपको दिखाया है कि स्लाइड में मूल टिप्पणियाँ कैसे जोड़ें, पदानुक्रम स्थापित करें और आवश्यकता पड़ने पर टिप्पणियाँ हटाएँ भी। इन चरणों का पालन करके और Aspose.Slides दस्तावेज़ों की खोज करके [यहाँ](https://reference.aspose.com/slides/net/), आप अपनी प्रस्तुतियों को अगले स्तर तक ले जा सकते हैं।

## पूछे जाने वाले प्रश्न

### क्या मैं अपनी प्रस्तुति में विशिष्ट स्लाइडों पर टिप्पणियाँ जोड़ सकता हूँ?
हां, आप टिप्पणी बनाते समय लक्ष्य स्लाइड निर्दिष्ट करके अपनी प्रस्तुति में किसी भी स्लाइड पर टिप्पणी जोड़ सकते हैं।

### क्या प्रस्तुति में टिप्पणियों के स्वरूप को अनुकूलित करना संभव है?
.NET के लिए Aspose.Slides आपको टिप्पणियों के स्वरूप को अनुकूलित करने की अनुमति देता है, जिसमें उनका पाठ, लेखक की जानकारी और स्लाइड पर उनकी स्थिति शामिल है।

### क्या मैं टिप्पणियों और उत्तरों को एक अलग फ़ाइल में निर्यात कर सकता हूँ?
हां, आप टिप्पणियों और उत्तरों को एक अलग प्रस्तुति फ़ाइल में निर्यात कर सकते हैं, जैसा कि चरण 7 में दिखाया गया है।

### क्या Aspose.Slides for .NET PowerPoint के नवीनतम संस्करणों के साथ संगत है?
Aspose.Slides for .NET को PowerPoint संस्करणों की एक विस्तृत श्रृंखला के साथ काम करने के लिए डिज़ाइन किया गया है, जो नवीनतम रिलीज़ के साथ संगतता सुनिश्चित करता है।

### क्या .NET के लिए Aspose.Slides के लिए कोई लाइसेंसिंग विकल्प उपलब्ध हैं?
हां, आप Aspose वेबसाइट पर अस्थायी लाइसेंस सहित लाइसेंसिंग विकल्पों का पता लगा सकते हैं [यहाँ](https://purchase.aspose.com/buy) या निःशुल्क परीक्षण का प्रयास करें [यहाँ](https://releases.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}