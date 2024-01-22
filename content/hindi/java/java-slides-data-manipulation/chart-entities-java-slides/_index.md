---
title: जावा स्लाइड्स में चार्ट इकाइयाँ
linktitle: जावा स्लाइड्स में चार्ट इकाइयाँ
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ जावा स्लाइड चार्ट बनाना और अनुकूलित करना सीखें। शक्तिशाली चार्ट इकाइयों के साथ अपनी प्रस्तुतियाँ बढ़ाएँ।
type: docs
weight: 13
url: /hi/java/data-manipulation/chart-entities-java-slides/
---

## जावा स्लाइड्स में चार्ट संस्थाओं का परिचय

प्रस्तुतियों में डेटा को विज़ुअलाइज़ करने के लिए चार्ट शक्तिशाली उपकरण हैं। चाहे आप व्यावसायिक रिपोर्ट, अकादमिक प्रस्तुतियाँ, या किसी अन्य प्रकार की सामग्री बना रहे हों, चार्ट जानकारी को प्रभावी ढंग से संप्रेषित करने में मदद करते हैं। जावा के लिए Aspose.Slides चार्ट के साथ काम करने के लिए मजबूत सुविधाएँ प्रदान करता है, जिससे यह जावा डेवलपर्स के लिए पसंदीदा विकल्प बन जाता है।

## आवश्यक शर्तें

इससे पहले कि हम चार्ट संस्थाओं की दुनिया में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

- जावा डेवलपमेंट किट (जेडीके) स्थापित किया गया
- जावा लाइब्रेरी के लिए Aspose.Slides डाउनलोड किया गया और आपके प्रोजेक्ट में जोड़ा गया
- जावा प्रोग्रामिंग का बुनियादी ज्ञान

अब, आइए जावा के लिए Aspose.Slides का उपयोग करके चार्ट बनाना और अनुकूलित करना शुरू करें।

## चरण 1: एक प्रस्तुति बनाना

पहला कदम एक नई प्रस्तुति बनाना है जहां आप अपना चार्ट जोड़ेंगे। प्रेजेंटेशन बनाने के लिए यहां कोड का एक स्निपेट दिया गया है:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 2: एक चार्ट जोड़ना

एक बार जब आपकी प्रस्तुति तैयार हो जाए, तो चार्ट जोड़ने का समय आ गया है। इस उदाहरण में, हम मार्करों के साथ एक सरल लाइन चार्ट जोड़ेंगे। यहां बताया गया है कि आप यह कैसे कर सकते हैं:

```java
// पहली स्लाइड तक पहुँचना
ISlide slide = pres.getSlides().get_Item(0);

// नमूना चार्ट जोड़ा जा रहा है
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

आप अपने चार्ट की बड़ी और छोटी ग्रिड लाइनों को प्रारूपित कर सकते हैं। आइए ऊर्ध्वाधर अक्ष ग्रिड लाइनों के लिए कुछ स्वरूपण सेट करें:

```java
// मान अक्ष के लिए प्रमुख ग्रिड लाइन प्रारूप सेट करना
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// मान अक्ष के लिए माइनर ग्रिड लाइन प्रारूप सेट करना
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## चरण 5: मूल्य अक्ष को अनुकूलित करना

मान अक्ष के संख्या प्रारूप, अधिकतम और न्यूनतम मानों पर आपका नियंत्रण होता है। इसे अनुकूलित करने का तरीका यहां बताया गया है:

```java
// मान अक्ष संख्या स्वरूप सेट करना
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// चार्ट को अधिकतम, न्यूनतम मान सेट करना
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

अपने चार्ट को अधिक जानकारीपूर्ण बनाने के लिए, आप मान अक्ष पर एक शीर्षक जोड़ सकते हैं:

```java
// मान अक्ष शीर्षक सेट करना
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## चरण 7: श्रेणी अक्ष का स्वरूपण

श्रेणी अक्ष, जो आम तौर पर डेटा श्रेणियों का प्रतिनिधित्व करती है, को भी अनुकूलित किया जा सकता है:

```java
// श्रेणी अक्ष के लिए प्रमुख ग्रिड लाइन प्रारूप सेट करना
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

//श्रेणी अक्ष के लिए माइनर ग्रिड लाइन प्रारूप सेट करना
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## चरण 8: किंवदंतियाँ जोड़ना

किंवदंतियाँ आपके चार्ट में डेटा श्रृंखला को समझाने में मदद करती हैं। आइए किंवदंतियों को अनुकूलित करें:

```java
// महापुरूष पाठ गुण सेट करना
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// ओवरलैपिंग चार्ट के बिना शो चार्ट लेजेंड्स सेट करें
chart.getLegend().setOverlay(true);
```

## चरण 9: प्रस्तुति सहेजना

अंत में, अपनी प्रस्तुति को चार्ट के साथ सहेजें:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में चार्ट संस्थाओं के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// यदि यह पहले से मौजूद नहीं है तो निर्देशिका बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// त्वरित प्रस्तुति// त्वरित प्रस्तुति
Presentation pres = new Presentation();
try
{
	// पहली स्लाइड तक पहुँचना
	ISlide slide = pres.getSlides().get_Item(0);
	// नमूना चार्ट जोड़ा जा रहा है
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// चार्ट टाइटल सेट करना
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
	// मान अक्ष के लिए माइनर ग्रिड लाइन प्रारूप सेट करना
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// मान अक्ष संख्या स्वरूप सेट करना
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// चार्ट को अधिकतम, न्यूनतम मान सेट करना
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// वैल्यू एक्सिस टेक्स्ट गुण सेट करना
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
	// मान अक्ष रेखा प्रारूप सेट करना: अब अप्रचलित
	// Chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// श्रेणी अक्ष के लिए प्रमुख ग्रिड लाइन प्रारूप सेट करना
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	//श्रेणी अक्ष के लिए माइनर ग्रिड लाइन प्रारूप सेट करना
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// श्रेणी अक्ष टेक्स्ट गुण सेट करना
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
	// श्रेणी अक्ष योग्य स्थिति निर्धारित करना
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// श्रेणी अक्ष योग्य घूर्णन कोण सेट करना
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// महापुरूष पाठ गुण सेट करना
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// ओवरलैपिंग चार्ट के बिना शो चार्ट लेजेंड्स सेट करें
	chart.getLegend().setOverlay(true);
	// द्वितीयक मान अक्ष पर प्रथम श्रृंखला आलेखित करना
	//Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// चार्ट पीछे की दीवार का रंग सेट करना
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

इस लेख में, हमने जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में चार्ट इकाइयों की दुनिया का पता लगाया है। आपने अपनी प्रस्तुतियों को बेहतर बनाने के लिए चार्ट बनाना, अनुकूलित करना और उनमें हेरफेर करना सीख लिया है। चार्ट न केवल आपके डेटा को आकर्षक बनाते हैं बल्कि आपके दर्शकों को जटिल जानकारी को अधिक आसानी से समझने में भी मदद करते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट प्रकार कैसे बदलूं?

 चार्ट प्रकार बदलने के लिए, का उपयोग करें`chart.setType()` विधि और वांछित चार्ट प्रकार निर्दिष्ट करें।

### क्या मैं एक चार्ट में एकाधिक डेटा शृंखला जोड़ सकता हूँ?

 हां, आप इसका उपयोग करके चार्ट में एकाधिक डेटा श्रृंखला जोड़ सकते हैं`chart.getChartData().getSeries().addSeries()` तरीका।

### मैं चार्ट के रंगों को कैसे अनुकूलित करूँ?

आप ग्रिड लाइनों, शीर्षक और लेजेंड्स जैसे विभिन्न चार्ट तत्वों के लिए भरण प्रारूप सेट करके चार्ट रंगों को अनुकूलित कर सकते हैं।

### क्या मैं 3D चार्ट बना सकता हूँ?

 हाँ, Java के लिए Aspose.Slides 3D चार्ट के निर्माण का समर्थन करता है। आप सेट कर सकते हैं`ChartType` एक 3D चार्ट प्रकार बनाने के लिए।

### क्या जावा के लिए Aspose.Slides नवीनतम जावा संस्करणों के साथ संगत है?

हां, जावा के लिए Aspose.Slides को नवीनतम जावा संस्करणों का समर्थन करने के लिए नियमित रूप से अपडेट किया जाता है और जावा वातावरण की एक विस्तृत श्रृंखला में अनुकूलता प्रदान करता है।