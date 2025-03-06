---
title: जावा स्लाइड्स में व्यक्तिगत स्लाइड को परिवर्तित करें
linktitle: जावा स्लाइड्स में व्यक्तिगत स्लाइड को परिवर्तित करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके कोड उदाहरणों के साथ चरण दर चरण व्यक्तिगत PowerPoint स्लाइड्स को HTML में परिवर्तित करना सीखें।
weight: 12
url: /hi/java/presentation-conversion/convert-individual-slide-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## जावा स्लाइड्स में व्यक्तिगत स्लाइड को परिवर्तित करने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन से अलग-अलग स्लाइड को HTML में बदलने की प्रक्रिया के बारे में जानेंगे। यह चरण-दर-चरण मार्गदर्शिका आपको इस कार्य को पूरा करने में मदद करने के लिए स्रोत कोड और स्पष्टीकरण प्रदान करेगी।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- Aspose.Slides for Java लाइब्रेरी स्थापित की गई।
- एक पावरपॉइंट प्रस्तुति फ़ाइल (`Individual-Slide.pptx`) जिसे आप परिवर्तित करना चाहते हैं.
- जावा विकास वातावरण की स्थापना.

## चरण 1: प्रोजेक्ट सेट अप करें

1. अपने पसंदीदा विकास वातावरण में एक जावा प्रोजेक्ट बनाएं।
2. अपने प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी जोड़ें।

## चरण 2: आवश्यक कक्षाएं आयात करें

अपने जावा क्लास में, आवश्यक क्लासेस आयात करें और प्रारंभिक कॉन्फ़िगरेशन सेट करें।

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.IHtmlFormattingController;
import com.aspose.slides.IHtmlGenerator;
import com.aspose.slides.ISlide;
import com.aspose.slides.IShape;
```

## चरण 3: मुख्य रूपांतरण विधि निर्धारित करें

 अलग-अलग स्लाइड्स का रूपांतरण करने के लिए एक विधि बनाएँ। सुनिश्चित करें कि प्रतिस्थापित करें`"Your Document Directory"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // फ़ाइल सहेजना
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## चरण 4: कस्टमफ़ॉर्मेटिंगकंट्रोलर को लागू करें

 बनाएं`CustomFormattingController` रूपांतरण के दौरान कस्टम स्वरूपण को संभालने के लिए क्लास।

```java
public static class CustomFormattingController implements IHtmlFormattingController {
    public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeSlideStart(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
    }
    
    public void writeSlideEnd(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(SlideFooter);
    }
    
    public void writeShapeStart(IHtmlGenerator generator, IShape shape) {
    }
    
    public void writeShapeEnd(IHtmlGenerator generator, IShape shape) {
    }
    
    private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
    private static String SlideFooter = "</div>";
}
```

## चरण 5: रूपांतरण निष्पादित करें

 अंत में, कॉल करें`convertIndividualSlides` रूपांतरण प्रक्रिया को निष्पादित करने की विधि.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## जावा स्लाइड्स में व्यक्तिगत स्लाइड को परिवर्तित करने के लिए पूर्ण स्रोत कोड

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// फ़ाइल सहेजना
		for (int i = 0; i < presentation.getSlides().size(); i++)
			presentation.save(dataDir + "Individual Slide" + i + 1 + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
	}
	finally
	{
		if (presentation != null) presentation.dispose();
	}
}
public static class CustomFormattingController implements IHtmlFormattingController
{
	public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeSlideStart(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
	}
	public void writeSlideEnd(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(SlideFooter);
	}
	public void writeShapeStart(IHtmlGenerator generator, IShape shape)
	{
	}
	public void writeShapeEnd(IHtmlGenerator generator, IShape shape)
	{
	}
	private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
	private static String SlideFooter = "</div>";
```

## निष्कर्ष

आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति से अलग-अलग स्लाइड को HTML में सफलतापूर्वक परिवर्तित कर लिया है। इस ट्यूटोरियल ने आपको इस कार्य को पूरा करने के लिए आवश्यक कोड और चरण प्रदान किए हैं। अपनी विशिष्ट आवश्यकताओं के अनुसार आउटपुट और फ़ॉर्मेटिंग को अनुकूलित करने के लिए स्वतंत्र महसूस करें।

## अक्सर पूछे जाने वाले प्रश्न

### मैं HTML आउटपुट को और अधिक अनुकूलित कैसे कर सकता हूं?

 आप HTML आउटपुट को संशोधित करके अनुकूलित कर सकते हैं`CustomFormattingController` वर्ग समायोजित करें।`writeSlideStart` और`writeSlideEnd` स्लाइड की HTML संरचना और स्टाइलिंग को बदलने के तरीके।

### क्या मैं एक बार में कई पावरपॉइंट प्रस्तुतियों को परिवर्तित कर सकता हूँ?

 हां, आप एकाधिक प्रस्तुति फ़ाइलों के माध्यम से लूप करने के लिए कोड को संशोधित कर सकते हैं और उन्हें कॉल करके व्यक्तिगत रूप से परिवर्तित कर सकते हैं`convertIndividualSlides` प्रत्येक प्रस्तुति के लिए विधि।

### मैं स्लाइडों में आकृतियों और पाठ के लिए अतिरिक्त स्वरूपण कैसे प्रबंधित करूँ?

 आप विस्तार कर सकते हैं`CustomFormattingController` वर्ग को कार्यान्वित करके आकार-विशिष्ट स्वरूपण को संभालने के लिए`writeShapeStart` और`writeShapeEnd` विधियों और उनके भीतर कस्टम स्वरूपण तर्क लागू करना।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
