---
title: Aspose.Slides .NET में डेटा पॉइंट पर चार्ट मार्कर विकल्पों का उपयोग करना
linktitle: डेटा पॉइंट पर चार्ट मार्कर विकल्प
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: जानें कि .NET के लिए Aspose.Slides का उपयोग करके अपने PowerPoint चार्ट को कैसे बेहतर बनाया जाए। छवियों के साथ डेटा पॉइंट मार्कर को कस्टमाइज़ करें। आकर्षक प्रस्तुतियाँ बनाएँ।
weight: 11
url: /hi/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


प्रस्तुतियों और डेटा विज़ुअलाइज़ेशन के साथ काम करते समय, Aspose.Slides for .NET चार्ट बनाने, कस्टमाइज़ करने और हेरफेर करने के लिए कई शक्तिशाली सुविधाएँ प्रदान करता है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि अपने चार्ट प्रस्तुतियों को बेहतर बनाने के लिए डेटा पॉइंट्स पर चार्ट मार्कर विकल्पों का उपयोग कैसे करें। यह चरण-दर-चरण मार्गदर्शिका आपको प्रक्रिया के माध्यम से ले जाएगी, जो कि पूर्वापेक्षाओं से शुरू होकर नामस्थानों को आयात करने से लेकर प्रत्येक उदाहरण को कई चरणों में विभाजित करने तक है।

## आवश्यक शर्तें

इससे पहले कि हम डेटा बिंदुओं पर चार्ट मार्कर विकल्पों का उपयोग करना शुरू करें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

-  Aspose.Slides for .NET: सुनिश्चित करें कि आपके पास Aspose.Slides for .NET इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/slides/net/).

- नमूना प्रस्तुति: इस ट्यूटोरियल के लिए, हम "Test.pptx" नामक एक नमूना प्रस्तुति का उपयोग करेंगे। यह प्रस्तुति आपके दस्तावेज़ निर्देशिका में होनी चाहिए।

अब, आइए आवश्यक नेमस्पेस को आयात करके शुरू करें।

## नामस्थान आयात करें

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

हमने आवश्यक नेमस्पेस आयात कर लिए हैं और अपनी प्रस्तुति आरंभ कर दी है। अब, चलिए डेटा पॉइंट पर चार्ट मार्कर विकल्पों का उपयोग करना शुरू करते हैं।

## चरण 1: डिफ़ॉल्ट चार्ट बनाना

```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//डिफ़ॉल्ट चार्ट बनाना
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

हम स्लाइड पर निर्दिष्ट स्थान और आकार पर "LineWithMarkers" प्रकार का एक डिफ़ॉल्ट चार्ट बनाते हैं।

## चरण 2: डिफ़ॉल्ट चार्ट डेटा वर्कशीट इंडेक्स प्राप्त करना

```csharp
// डिफ़ॉल्ट चार्ट डेटा वर्कशीट इंडेक्स प्राप्त करना
int defaultWorksheetIndex = 0;
```

यहां, हम डिफ़ॉल्ट चार्ट डेटा वर्कशीट का सूचकांक प्राप्त करते हैं।

## चरण 3: चार्ट डेटा वर्कशीट प्राप्त करना

```csharp
// चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

हम चार्ट डेटा के साथ काम करने के लिए चार्ट डेटा कार्यपुस्तिका लाते हैं।

## चरण 4: चार्ट श्रृंखला को संशोधित करना

```csharp
// डेमो श्रृंखला हटाएं
chart.ChartData.Series.Clear();

// नई श्रृंखला जोड़ें
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

इस चरण में, हम किसी भी मौजूदा डेमो श्रृंखला को हटाते हैं और चार्ट में "श्रृंखला 1" नामक एक नई श्रृंखला जोड़ते हैं।

## चरण 5: डेटा बिंदुओं के लिए चित्र भरण सेट करना

```csharp
// मार्करों के लिए चित्र सेट करें
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// पहली चार्ट श्रृंखला लें
IChartSeries series = chart.ChartData.Series[0];

// चित्र भरण के साथ नए डेटा बिंदु जोड़ें
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

हम डेटा बिंदुओं के लिए चित्र मार्कर सेट करते हैं, जिससे आप चार्ट पर प्रत्येक डेटा बिंदु को प्रदर्शित करने के तरीके को अनुकूलित कर सकते हैं।

## चरण 6: चार्ट श्रृंखला मार्कर का आकार बदलना

```csharp
// चार्ट श्रृंखला मार्कर का आकार बदलना
series.Marker.Size = 15;
```

यहां, हम चार्ट श्रृंखला मार्कर के आकार को समायोजित करते हैं ताकि इसे दृश्य रूप से आकर्षक बनाया जा सके।

## चरण 7: प्रस्तुति को सहेजना

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

अंत में, हम नई चार्ट सेटिंग्स के साथ प्रस्तुति को सेव करते हैं।

## निष्कर्ष

Aspose.Slides for .NET आपको विभिन्न अनुकूलन विकल्पों के साथ शानदार चार्ट प्रेजेंटेशन बनाने की शक्ति देता है। इस ट्यूटोरियल में, हमने आपके डेटा के विज़ुअल प्रतिनिधित्व को बढ़ाने के लिए डेटा पॉइंट्स पर चार्ट मार्कर विकल्पों का उपयोग करने पर ध्यान केंद्रित किया। Aspose.Slides for .NET के साथ, आप अपनी प्रस्तुतियों को अगले स्तर तक ले जा सकते हैं, उन्हें अधिक आकर्षक और जानकारीपूर्ण बना सकते हैं।

यदि आपके पास कोई प्रश्न है या .NET के लिए Aspose.Slides के बारे में सहायता की आवश्यकता है, तो कृपया यहां जाएं[Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/net/) या संपर्क करें[असपोज़ समुदाय](https://forum.aspose.com/) समर्थन के लिए।

## अक्सर पूछे जाने वाले प्रश्न (एफएक्यू)

### क्या मैं Aspose.Slides for .NET में डेटा बिंदुओं के लिए मार्कर के रूप में कस्टम छवियों का उपयोग कर सकता हूं?
हां, आप Aspose.Slides for .NET में डेटा बिंदुओं के लिए मार्कर के रूप में कस्टम छवियों का उपयोग कर सकते हैं, जैसा कि इस ट्यूटोरियल में दिखाया गया है।

### मैं .NET के लिए Aspose.Slides में चार्ट प्रकार कैसे बदल सकता हूँ?
 आप एक अलग चार्ट प्रकार निर्दिष्ट करके चार्ट प्रकार बदल सकते हैं`ChartType` चार्ट बनाते समय, जैसे "बार," "पाई," या "क्षेत्र।"

### क्या Aspose.Slides for .NET PowerPoint के नवीनतम संस्करणों के साथ संगत है?
Aspose.Slides for .NET को विभिन्न PowerPoint प्रारूपों के साथ काम करने के लिए डिज़ाइन किया गया है और नवीनतम PowerPoint संस्करणों के साथ संगतता बनाए रखने के लिए इसे नियमित रूप से अपडेट किया जाता है।

### मैं .NET के लिए Aspose.Slides के अधिक ट्यूटोरियल और संसाधन कहां पा सकता हूं?
 आप अतिरिक्त ट्यूटोरियल और संसाधनों का पता लगा सकते हैं[Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/net/).

### क्या .NET के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड करके .NET के लिए Aspose.Slides आज़मा सकते हैं।[यहाँ](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
