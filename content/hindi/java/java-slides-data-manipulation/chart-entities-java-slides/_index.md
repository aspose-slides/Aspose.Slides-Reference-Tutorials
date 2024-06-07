---
title: जावा स्लाइड्स में चार्ट इकाइयाँ
linktitle: जावा स्लाइड्स में चार्ट इकाइयाँ
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ Java स्लाइड चार्ट बनाना और उन्हें कस्टमाइज़ करना सीखें। शक्तिशाली चार्ट इकाइयों के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ।
type: docs
weight: 13
url: /hi/java/data-manipulation/chart-entities-java-slides/
---

## जावा स्लाइड्स में चार्ट एंटिटीज़ का परिचय

चार्ट प्रेजेंटेशन में डेटा को विज़ुअलाइज़ करने के लिए शक्तिशाली उपकरण हैं। चाहे आप व्यावसायिक रिपोर्ट, अकादमिक प्रेजेंटेशन या किसी अन्य प्रकार की सामग्री बना रहे हों, चार्ट जानकारी को प्रभावी ढंग से व्यक्त करने में मदद करते हैं। Aspose.Slides for Java चार्ट के साथ काम करने के लिए मज़बूत सुविधाएँ प्रदान करता है, जो इसे Java डेवलपर्स के लिए एक पसंदीदा विकल्प बनाता है।

## आवश्यक शर्तें

इससे पहले कि हम चार्ट इकाइयों की दुनिया में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- जावा डेवलपमेंट किट (JDK) स्थापित
- Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई और आपके प्रोजेक्ट में जोड़ी गई
- जावा प्रोग्रामिंग का बुनियादी ज्ञान

अब, आइए Aspose.Slides for Java का उपयोग करके चार्ट बनाना और अनुकूलित करना शुरू करें।

## चरण 1: प्रेजेंटेशन बनाना

पहला कदम एक नया प्रेजेंटेशन बनाना है, जहाँ आप अपना चार्ट जोड़ेंगे। प्रेजेंटेशन बनाने के लिए कोड का एक स्निपेट यहाँ दिया गया है:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 2: चार्ट जोड़ना

एक बार जब आप अपनी प्रस्तुति तैयार कर लें, तो चार्ट जोड़ने का समय आ गया है। इस उदाहरण में, हम मार्कर के साथ एक सरल रेखा चार्ट जोड़ेंगे। यहाँ बताया गया है कि आप इसे कैसे कर सकते हैं:

```java
// पहली स्लाइड तक पहुँचना
ISlide slide = pres.getSlides().get_Item(0);

// नमूना चार्ट जोड़ना
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## चरण 3: चार्ट शीर्षक को अनुकूलित करना

एक अच्छी तरह से परिभाषित चार्ट में एक शीर्षक होना चाहिए। आइए अपने चार्ट के लिए एक शीर्षक निर्धारित करें:

```java
// चार्ट शीर्षक सेट करना
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## चरण 4: ग्रिड लाइनों को फ़ॉर्मेट करना

आप अपने चार्ट की प्रमुख और छोटी ग्रिड लाइनों को फ़ॉर्मेट कर सकते हैं। आइए ऊर्ध्वाधर अक्ष ग्रिड लाइनों के लिए कुछ फ़ॉर्मेटिंग सेट करें:

```java
// मान अक्ष के लिए प्रमुख ग्रिड लाइन प्रारूप सेट करना
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// मान अक्ष के लिए लघु ग्रिड रेखा प्रारूप सेट करना
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## चरण 5: मूल्य अक्ष को अनुकूलित करना

आपके पास मान अक्ष के संख्या प्रारूप, अधिकतम और न्यूनतम मानों पर नियंत्रण है। इसे कस्टमाइज़ करने का तरीका यहां बताया गया है:

```java
// मान अक्ष संख्या प्रारूप सेट करना
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// चार्ट के अधिकतम, न्यूनतम मान सेट करना
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## चरण 6: मूल्य अक्ष शीर्षक जोड़ना

अपने चार्ट को अधिक जानकारीपूर्ण बनाने के लिए, आप मान अक्ष में एक शीर्षक जोड़ सकते हैं:

```java
// मान अक्ष शीर्षक सेट करना
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## चरण 7: श्रेणी अक्ष का प्रारूपण

श्रेणी अक्ष, जो आम तौर पर डेटा श्रेणियों का प्रतिनिधित्व करता है, को भी अनुकूलित किया जा सकता है:

```java
// श्रेणी अक्ष के लिए प्रमुख ग्रिड लाइन प्रारूप सेट करना
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

//श्रेणी अक्ष के लिए लघु ग्रिड रेखा प्रारूप सेट करना
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## चरण 8: लेजेंड जोड़ना

लेजेंड आपके चार्ट में डेटा सीरीज़ को समझाने में मदद करते हैं। आइए लेजेंड को कस्टमाइज़ करें:

```java
// लेजेंड टेक्स्ट गुण सेट करना
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// चार्ट को ओवरलैप किए बिना चार्ट लेजेंड दिखाने के लिए सेट करें
chart.getLegend().setOverlay(true);
```

## चरण 9: प्रस्तुति को सहेजना

अंत में, चार्ट के साथ अपनी प्रस्तुति सहेजें:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में चार्ट एंटिटीज़ के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// प्रस्तुति को त्वरित बनाना// प्रस्तुति को त्वरित बनाना
Presentation pres = new Presentation();
try
{
	// पहली स्लाइड तक पहुँचना
	ISlide slide = pres.getSlides().get_Item(0);
	// नमूना चार्ट जोड़ना
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// चार्ट शीर्षक सेट करना
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// मान अक्ष के लिए प्रमुख ग्रिड लाइन प्रारूप सेट करना
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// मान अक्ष के लिए लघु ग्रिड रेखा प्रारूप सेट करना
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// मान अक्ष संख्या प्रारूप सेट करना
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// चार्ट के अधिकतम, न्यूनतम मान सेट करना
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// मान अक्ष पाठ गुण सेट करना
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// मान अक्ष शीर्षक सेट करना
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// अक्ष रेखा प्रारूप मान सेट करना : अब अप्रचलित
	// चार्ट.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// चार्ट.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// चार्ट.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().रंग = रंग.लाल;
	// श्रेणी अक्ष के लिए प्रमुख ग्रिड लाइन प्रारूप सेट करना
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	//श्रेणी अक्ष के लिए लघु ग्रिड रेखा प्रारूप सेट करना
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// श्रेणी अक्ष पाठ गुण सेट करना
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// श्रेणी शीर्षक सेट करना
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// श्रेणी अक्ष लेबल स्थिति सेट करना
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// श्रेणी अक्ष लेबल रोटेशन कोण सेट करना
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// लेजेंड टेक्स्ट गुण सेट करना
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// चार्ट को ओवरलैप किए बिना चार्ट लेजेंड दिखाने के लिए सेट करें
	chart.getLegend().setOverlay(true);
	// द्वितीयक मान अक्ष पर प्रथम श्रृंखला का आलेखन
	//चार्ट.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = सत्य;
	// चार्ट बैक वॉल रंग सेट करना
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// प्लॉट क्षेत्र का रंग सेट करना
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// प्रस्तुति सहेजें
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस लेख में, हमने Aspose.Slides for Java का उपयोग करके Java Slides में चार्ट इकाइयों की दुनिया का पता लगाया है। आपने सीखा है कि अपनी प्रस्तुतियों को बेहतर बनाने के लिए चार्ट कैसे बनाएं, कस्टमाइज़ करें और उनमें हेरफेर करें। चार्ट न केवल आपके डेटा को आकर्षक बनाते हैं, बल्कि आपके दर्शकों को जटिल जानकारी को अधिक आसानी से समझने में भी मदद करते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट का प्रकार कैसे बदलूं?

 चार्ट प्रकार बदलने के लिए, का उपयोग करें`chart.setType()` विधि का चयन करें और वांछित चार्ट प्रकार निर्दिष्ट करें।

### क्या मैं एक चार्ट में एकाधिक डेटा श्रृंखलाएं जोड़ सकता हूं?

 हां, आप इसका उपयोग करके चार्ट में एकाधिक डेटा श्रृंखलाएं जोड़ सकते हैं`chart.getChartData().getSeries().addSeries()` तरीका।

### मैं चार्ट के रंगों को कैसे अनुकूलित करूँ?

आप विभिन्न चार्ट तत्वों, जैसे ग्रिड लाइन, शीर्षक और लेजेंड के लिए भरण प्रारूप सेट करके चार्ट रंगों को अनुकूलित कर सकते हैं।

### क्या मैं 3D चार्ट बना सकता हूँ?

 हां, Aspose.Slides for Java 3D चार्ट के निर्माण का समर्थन करता है। आप सेट कर सकते हैं`ChartType` एक 3D चार्ट प्रकार बनाने के लिए।

### क्या Aspose.Slides for Java नवीनतम Java संस्करणों के साथ संगत है?

हां, Aspose.Slides for Java को नवीनतम Java संस्करणों का समर्थन करने के लिए नियमित रूप से अपडेट किया जाता है और यह Java वातावरण की एक विस्तृत श्रृंखला में संगतता प्रदान करता है।