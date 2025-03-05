---
title: वेब स्रोत से PowerPoint में वीडियो फ़्रेम जोड़ें
linktitle: वेब स्रोत से PowerPoint में वीडियो फ़्रेम जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि Aspose.Slides for Java का उपयोग करके वेब स्रोतों से वीडियो फ़्रेम जोड़कर अपने पावरपॉइंट प्रस्तुतीकरण को कैसे बेहतर बनाया जाए।
type: docs
weight: 18
url: /hi/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---
## परिचय
इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java का उपयोग करके YouTube जैसे वेब स्रोत से वीडियो फ़्रेम को PowerPoint प्रेजेंटेशन में कैसे जोड़ा जाए। इन चरण-दर-चरण निर्देशों का पालन करके, आप आकर्षक मल्टीमीडिया तत्वों को शामिल करके अपनी प्रस्तुतियों को बेहतर बनाने में सक्षम होंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- आपके सिस्टम पर JDK (जावा डेवलपमेंट किट) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई और आपके Java प्रोजेक्ट में जोड़ दी गई। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- वेब स्रोत (जैसे, यूट्यूब) तक पहुंचने के लिए एक सक्रिय इंटरनेट कनेक्शन।

## पैकेज आयात करें
सबसे पहले, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## चरण 1: पावरपॉइंट प्रेजेंटेशन ऑब्जेक्ट बनाएँ
एक प्रस्तुति ऑब्जेक्ट आरंभ करें, जो एक PowerPoint प्रस्तुति का प्रतिनिधित्व करता है:
```java
Presentation pres = new Presentation();
```
## चरण 2: वीडियो फ़्रेम जोड़ें
अब, आइए प्रस्तुति में एक वीडियो फ़्रेम जोड़ें। इस फ़्रेम में वेब स्रोत से वीडियो होगा। हम addVideoFrame विधि का उपयोग करेंगे:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
"VIDEO_ID" को उस YouTube वीडियो की ID से बदलें जिसे आप एम्बेड करना चाहते हैं.
## चरण 3: वीडियो प्ले मोड सेट करें
वीडियो फ़्रेम के लिए प्ले मोड सेट करें। इस उदाहरण में, हम इसे ऑटो पर सेट करेंगे:
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## चरण 4: थंबनेल लोड करें
दृश्य अपील को बढ़ाने के लिए, हम वीडियो का थंबनेल लोड करेंगे। इस चरण में वेब स्रोत से थंबनेल छवि प्राप्त करना शामिल है:
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## चरण 5: प्रस्तुति सहेजें
अंत में, संशोधित प्रस्तुति को सहेजें:
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
"YOUR_DIRECTORY" को उस निर्देशिका से बदलें जहां आप प्रस्तुति को सहेजना चाहते हैं।

## निष्कर्ष
बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint में वेब स्रोत से वीडियो फ़्रेम जोड़ना सफलतापूर्वक सीख लिया है। वीडियो जैसे मल्टीमीडिया तत्वों को शामिल करने से आपकी प्रस्तुतियों का प्रभाव और जुड़ाव काफ़ी हद तक बढ़ सकता है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं यूट्यूब के अलावा अन्य स्रोतों से वीडियो जोड़ सकता हूँ?
हां, आप विभिन्न वेब स्रोतों से वीडियो जोड़ सकते हैं, बशर्ते वे एम्बेड करने योग्य लिंक प्रदान करें।
### क्या मुझे एम्बेड किए गए वीडियो को चलाने के लिए इंटरनेट कनेक्शन की आवश्यकता है?
हां, वेब स्रोत से वीडियो स्ट्रीम करने के लिए सक्रिय इंटरनेट कनेक्शन की आवश्यकता होती है।
### क्या मैं वीडियो फ्रेम के स्वरूप को अनुकूलित कर सकता हूँ?
बिल्कुल! Aspose.Slides वीडियो फ्रेम की उपस्थिति और व्यवहार को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है।
### क्या Aspose.Slides PowerPoint के सभी संस्करणों के साथ संगत है?
Aspose.Slides PowerPoint संस्करणों की एक विस्तृत श्रृंखला का समर्थन करता है, जो विभिन्न प्लेटफार्मों पर संगतता सुनिश्चित करता है।
### मैं Aspose.Slides के लिए अधिक संसाधन और समर्थन कहां पा सकता हूं?
 आप यहां जा सकते हैं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) सहायता, दस्तावेज़ीकरण और सामुदायिक समर्थन के लिए।