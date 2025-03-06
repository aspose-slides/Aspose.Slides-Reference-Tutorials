---
title: Aspose.Slides के साथ प्रेजेंटेशन में OLE ऑब्जेक्ट डेटा बदलना
linktitle: Aspose.Slides के साथ प्रेजेंटेशन में OLE ऑब्जेक्ट डेटा बदलना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: OLE ऑब्जेक्ट डेटा को आसानी से बदलने में Aspose.Slides for .NET की शक्ति का अन्वेषण करें। गतिशील सामग्री के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ।
weight: 25
url: /hi/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
आज की डिजिटल दुनिया में गतिशील और इंटरैक्टिव पावरपॉइंट प्रेजेंटेशन बनाना एक आम ज़रूरत है। इसे हासिल करने के लिए एक शक्तिशाली टूल है Aspose.Slides for .NET, एक मज़बूत लाइब्रेरी जो डेवलपर्स को प्रोग्रामेटिक रूप से पावरपॉइंट प्रेजेंटेशन में हेरफेर करने और उसे बेहतर बनाने की अनुमति देती है। इस ट्यूटोरियल में, हम Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड के भीतर OLE (ऑब्जेक्ट लिंकिंग और एम्बेडिंग) ऑब्जेक्ट डेटा को बदलने की प्रक्रिया में गहराई से उतरेंगे।
## आवश्यक शर्तें
इससे पहले कि आप .NET के लिए Aspose.Slides के साथ काम करना शुरू करें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1. विकास परिवेश: .NET स्थापित करके विकास परिवेश स्थापित करें।
2.  Aspose.Slides लाइब्रेरी: .NET लाइब्रेरी के लिए Aspose.Slides डाउनलोड करें और इंस्टॉल करें। आप लाइब्रेरी पा सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
3. बुनियादी समझ: C# प्रोग्रामिंग और पावरपॉइंट प्रस्तुतियों की बुनियादी अवधारणाओं से खुद को परिचित कराएं।
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, Aspose.Slides कार्यक्षमताओं का उपयोग करने के लिए आवश्यक नामस्थान आयात करें:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
एक नया C# प्रोजेक्ट बनाकर और Aspose.Slides लाइब्रेरी को आयात करके शुरू करें। सुनिश्चित करें कि आपका प्रोजेक्ट सही तरीके से कॉन्फ़िगर किया गया है, और आपके पास आवश्यक निर्भरताएँ मौजूद हैं।
## चरण 2: प्रस्तुति और स्लाइड तक पहुंचें
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## चरण 3: OLE ऑब्जेक्ट का पता लगाएँ
OLE ऑब्जेक्ट फ़्रेम ढूंढने के लिए स्लाइड में सभी आकृतियों को पार करें:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## चरण 4: कार्यपुस्तिका डेटा पढ़ें और संशोधित करें
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // कार्यपुस्तिका में ऑब्जेक्ट डेटा पढ़ना
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // कार्यपुस्तिका डेटा संशोधित करना
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // ओले फ्रेम ऑब्जेक्ट डेटा बदलना
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## चरण 5: प्रस्तुति सहेजें
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## निष्कर्ष
इन चरणों का पालन करके, आप .NET के लिए Aspose.Slides का उपयोग करके प्रस्तुति स्लाइड के भीतर OLE ऑब्जेक्ट डेटा को सहजता से बदल सकते हैं। यह आपकी विशिष्ट आवश्यकताओं के अनुरूप गतिशील और अनुकूलित प्रस्तुति बनाने की संभावनाओं की दुनिया को खोलता है।
## अक्सर पूछे जाने वाले प्रश्नों
### .NET के लिए Aspose.Slides क्या है?
Aspose.Slides for .NET एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को पावरपॉइंट प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने में सक्षम बनाती है, जिससे आसान हेरफेर और संवर्द्धन की अनुमति मिलती है।
### मैं Aspose.Slides दस्तावेज़ कहां पा सकता हूं?
 .NET के लिए Aspose.Slides का दस्तावेज़ यहां पाया जा सकता है[यहाँ](https://reference.aspose.com/slides/net/).
### मैं .NET के लिए Aspose.Slides कैसे डाउनलोड करूं?
 आप रिलीज़ पेज से लाइब्रेरी डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
### क्या Aspose.Slides के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप निःशुल्क परीक्षण का लाभ उठा सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे Aspose.Slides for .NET के लिए समर्थन कहां मिल सकता है?
 समर्थन और चर्चा के लिए, यहां जाएं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
