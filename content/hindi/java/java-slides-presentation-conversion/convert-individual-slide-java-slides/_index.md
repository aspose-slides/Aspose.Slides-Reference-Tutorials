---
title: व्यक्तिगत स्लाइड को जावा स्लाइड में बदलें
linktitle: व्यक्तिगत स्लाइड को जावा स्लाइड में बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके कोड उदाहरणों के साथ चरण दर चरण व्यक्तिगत पावरपॉइंट स्लाइड्स को HTML में परिवर्तित करना सीखें।
type: docs
weight: 12
url: /hi/java/presentation-conversion/convert-individual-slide-java-slides/
---

## जावा स्लाइड में व्यक्तिगत स्लाइड को परिवर्तित करने का परिचय

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन से व्यक्तिगत स्लाइड्स को HTML में परिवर्तित करने की प्रक्रिया के बारे में जानेंगे। यह चरण-दर-चरण मार्गदर्शिका आपको इस कार्य को प्राप्त करने में सहायता के लिए स्रोत कोड और स्पष्टीकरण प्रदान करेगी।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- जावा लाइब्रेरी के लिए Aspose.Slides स्थापित।
- एक पॉवरपॉइंट प्रेजेंटेशन फ़ाइल (`Individual-Slide.pptx`) जिसे आप परिवर्तित करना चाहते हैं।
- जावा विकास पर्यावरण की स्थापना।

## चरण 1: प्रोजेक्ट सेट करें

1. अपने पसंदीदा विकास परिवेश में एक जावा प्रोजेक्ट बनाएं।
2. अपने प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी जोड़ें।

## चरण 2: आवश्यक कक्षाएं आयात करें

अपनी जावा क्लास में, आवश्यक कक्षाएं आयात करें और प्रारंभिक कॉन्फ़िगरेशन सेट करें।

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

## चरण 3: मुख्य रूपांतरण विधि को परिभाषित करें

 अलग-अलग स्लाइडों का रूपांतरण करने के लिए एक विधि बनाएं। प्रतिस्थापित करना सुनिश्चित करें`"Your Document Directory"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // फ़ाइल सहेजा जा रहा है
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## चरण 4: CustomFormattingController लागू करें

 बनाएं`CustomFormattingController` रूपांतरण के दौरान कस्टम फ़ॉर्मेटिंग को संभालने के लिए क्लास।

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

 अंत में, कॉल करें`convertIndividualSlides` रूपांतरण प्रक्रिया निष्पादित करने की विधि.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## व्यक्तिगत स्लाइड को जावा स्लाइड में बदलने के लिए संपूर्ण स्रोत कोड

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// फ़ाइल सहेजा जा रहा है
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

आपने जावा के लिए Aspose.Slides का उपयोग करके अलग-अलग स्लाइडों को PowerPoint प्रेजेंटेशन से HTML में सफलतापूर्वक परिवर्तित कर लिया है। इस ट्यूटोरियल ने आपको इस कार्य को प्राप्त करने के लिए आवश्यक कोड और चरण प्रदान किए हैं। अपनी विशिष्ट आवश्यकताओं के लिए आवश्यकतानुसार आउटपुट और फ़ॉर्मेटिंग को अनुकूलित करने के लिए स्वतंत्र महसूस करें।

## अक्सर पूछे जाने वाले प्रश्न

### मैं HTML आउटपुट को और अधिक कैसे अनुकूलित कर सकता हूँ?

 आप HTML आउटपुट को संशोधित करके कस्टमाइज़ कर सकते हैं`CustomFormattingController` कक्षा। समायोजित`writeSlideStart` और`writeSlideEnd` स्लाइड HTML संरचना और स्टाइल को बदलने के तरीके।

### क्या मैं एक ही बार में एकाधिक पावरपॉइंट प्रस्तुतियों को परिवर्तित कर सकता हूँ?

 हां, आप एकाधिक प्रेजेंटेशन फ़ाइलों के माध्यम से लूप करने के लिए कोड को संशोधित कर सकते हैं और कॉल करके उन्हें व्यक्तिगत रूप से परिवर्तित कर सकते हैं`convertIndividualSlides` प्रत्येक प्रस्तुति के लिए विधि.

### मैं स्लाइड के भीतर आकृतियों और पाठ के लिए अतिरिक्त स्वरूपण कैसे संभाल सकता हूँ?

आप इसे बढ़ा सकते हैं`CustomFormattingController` वर्ग को लागू करके आकार-विशिष्ट स्वरूपण को संभालने के लिए`writeShapeStart` और`writeShapeEnd` विधियाँ और उनके भीतर कस्टम फ़ॉर्मेटिंग तर्क लागू करना।