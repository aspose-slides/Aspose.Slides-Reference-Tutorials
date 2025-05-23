---
"description": ".NET के लिए Aspose.Slides का उपयोग करके स्पीकर नोट्स के साथ प्रेजेंटेशन स्लाइड्स को आसानी से PDF में बदलें। सामग्री और संदर्भ को सहजता से संरक्षित करें।"
"linktitle": "नोट्स के साथ स्लाइड्स को पीडीएफ में बदलें"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": "नोट्स के साथ स्लाइड्स को पीडीएफ में बदलें"
"url": "/hi/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# नोट्स के साथ स्लाइड्स को पीडीएफ में बदलें


# .NET के लिए Aspose.Slides का उपयोग करके नोट्स के साथ स्लाइड्स को PDF में परिवर्तित करने पर चरण दर चरण ट्यूटोरियल गाइड लिखें

क्या आप अपने पावरपॉइंट स्लाइड्स को पीडीएफ फॉर्मेट में बदलने का एक विश्वसनीय तरीका खोज रहे हैं, जबकि सभी महत्वपूर्ण नोट्स सुरक्षित हैं? आगे मत देखो! इस व्यापक ट्यूटोरियल में, हम आपको इस कार्य को चरण दर चरण पूरा करने के लिए .NET के लिए Aspose.Slides का उपयोग करने की प्रक्रिया के माध्यम से मार्गदर्शन करेंगे।

## 1 परिचय

नोट्स के साथ पावरपॉइंट स्लाइड्स को पीडीएफ में बदलना प्रेजेंटेशन को साझा करने के लिए एक मूल्यवान उपकरण हो सकता है, जबकि यह सुनिश्चित करता है कि महत्वपूर्ण संदर्भ और टिप्पणियाँ बरकरार रहें। Aspose.Slides for .NET इस कार्य के लिए एक शक्तिशाली समाधान प्रदान करता है।

## 2. अपना वातावरण स्थापित करना

इससे पहले कि हम कोडिंग प्रक्रिया में उतरें, सुनिश्चित करें कि आपके पास आवश्यक वातावरण सेट अप है। आपको इसकी आवश्यकता होगी:

- विज़ुअल स्टूडियो या आपका पसंदीदा .NET विकास वातावरण।
- Aspose.Slides for .NET लाइब्रेरी स्थापित की गई।
- एक पावरपॉइंट प्रस्तुति जिसमें वे नोट्स हों जिन्हें आप परिवर्तित करना चाहते हैं।

## 3. प्रेजेंटेशन लोड करना

अपने C# कोड में, आपको वह PowerPoint प्रेजेंटेशन लोड करना होगा जिसे आप कनवर्ट करना चाहते हैं। आप इसे इस प्रकार कर सकते हैं:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. स्लाइड की क्लोनिंग

यह सुनिश्चित करने के लिए कि आपके PDF में नोट्स के साथ सभी आवश्यक स्लाइड शामिल हैं, आप उन्हें मूल प्रस्तुति से क्लोन कर सकते हैं। यहाँ बताया गया है कि कैसे:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. स्लाइड का आकार समायोजित करना

आप अपनी PDF में फ़िट होने के लिए स्लाइड का आकार समायोजित करना चाह सकते हैं। Aspose.Slides for .NET आपको यह आसानी से करने की अनुमति देता है:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. पीडीएफ विकल्प कॉन्फ़िगर करना

यह नियंत्रित करने के लिए कि आपके नोट्स PDF में कैसे प्रदर्शित होंगे, आप PDF विकल्प कॉन्फ़िगर कर सकते हैं:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. नोट्स के साथ पीडीएफ के रूप में सहेजना

अंत में, आप अपनी प्रस्तुति को नोट्स के साथ PDF के रूप में सहेज सकते हैं:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. निष्कर्ष

बधाई हो! आपने सभी महत्वपूर्ण नोट्स को सुरक्षित रखते हुए अपनी PowerPoint स्लाइड्स को सफलतापूर्वक PDF प्रारूप में परिवर्तित कर लिया है। Aspose.Slides for .NET इस प्रक्रिया को सरल और कुशल बनाता है।

## 9. अक्सर पूछे जाने वाले प्रश्न

### प्रश्न 1: क्या मैं पीडीएफ में नोट्स के लेआउट को अनुकूलित कर सकता हूं?

हां, आप नोट्स के लेआउट को अनुकूलित कर सकते हैं `INotesCommentsLayoutingOptions` पीडीएफ विकल्पों में.

### प्रश्न 2: क्या Aspose.Slides for .NET PDF के अलावा अन्य आउटपुट प्रारूपों का समर्थन करता है?

हां, Aspose.Slides for .NET विभिन्न आउटपुट प्रारूपों का समर्थन करता है, जिसमें PPTX, DOCX, आदि शामिल हैं।

### प्रश्न 3: क्या .NET के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?

हां, आप .NET के लिए Aspose.Slides का निःशुल्क परीक्षण प्राप्त कर सकते हैं [https://releases.aspose.com/](https://releases.aspose.com/).

### प्रश्न 4: मुझे .NET के लिए Aspose.Slides का समर्थन कहां मिल सकता है?

आप समर्थन और सामुदायिक चर्चाएं यहां पा सकते हैं [https://forum.aspose.com/](https://forum.aspose.com/).

### प्रश्न 5: क्या मैं Aspose.Slides for .NET के लिए अस्थायी लाइसेंस खरीद सकता हूँ?

हां, आप यहां से अस्थायी लाइसेंस खरीद सकते हैं [https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

निष्कर्ष में, Aspose.Slides for .NET का उपयोग करके, आप आसानी से PowerPoint स्लाइड्स को नोट्स के साथ PDF प्रारूप में परिवर्तित कर सकते हैं। यह उन पेशेवरों के लिए एक मूल्यवान उपकरण है जिन्हें सहकर्मियों और ग्राहकों के साथ प्रस्तुतियाँ साझा करने की आवश्यकता होती है, जबकि यह सुनिश्चित करना होता है कि महत्वपूर्ण संदर्भ खो न जाए।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}