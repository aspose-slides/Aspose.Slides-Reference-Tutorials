---
title: जावा स्लाइड्स में प्रेजेंटेशन में ब्लॉब इमेज जोड़ें
linktitle: जावा स्लाइड्स में प्रेजेंटेशन में ब्लॉब इमेज जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि Java स्लाइड्स प्रेजेंटेशन में ब्लॉब इमेज को आसानी से कैसे जोड़ा जाए। Aspose.Slides for Java का उपयोग करके कोड उदाहरणों के साथ हमारे चरण-दर-चरण गाइड का पालन करें।
weight: 10
url: /hi/java/image-handling/add-blob-image-to-presentation-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में प्रेजेंटेशन में ब्लॉब इमेज जोड़ने का परिचय

इस विस्तृत गाइड में, हम जावा स्लाइड्स का उपयोग करके किसी प्रेजेंटेशन में ब्लॉब इमेज जोड़ने का तरीका जानेंगे। Aspose.Slides for Java प्रोग्रामेटिक रूप से PowerPoint प्रेजेंटेशन में हेरफेर करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है। इस ट्यूटोरियल के अंत तक, आपको अपनी प्रेजेंटेशन में ब्लॉब इमेज को शामिल करने के तरीके के बारे में स्पष्ट समझ हो जाएगी। आइए शुरू करते हैं!

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- एक ब्लॉब छवि जिसे आप अपनी प्रस्तुति में जोड़ना चाहते हैं।

## चरण 1: आवश्यक लाइब्रेरीज़ आयात करें

अपने जावा कोड में, आपको Aspose.Slides के लिए आवश्यक लाइब्रेरीज़ आयात करने की आवश्यकता है। आप इसे इस प्रकार कर सकते हैं:

```java
import com.aspose.slides.*;
import java.io.FileInputStream;
```

## चरण 2: पथ सेट करें

 अपने दस्तावेज़ निर्देशिका का पथ निर्धारित करें जहाँ आपने ब्लॉब छवि संग्रहीत की है।`"Your Document Directory"` वास्तविक पथ के साथ.

```java
String dataDir = "Your Document Directory";
String pathToBlobImage = dataDir + "blob_image.jpg";
```

## चरण 3: ब्लॉब छवि लोड करें

इसके बाद, निर्दिष्ट पथ से ब्लॉब छवि लोड करें।

```java
FileInputStream fip = new FileInputStream(pathToBlobImage);
```

## चरण 4: एक नई प्रस्तुति बनाएँ

Aspose.Slides का उपयोग करके एक नई प्रस्तुति बनाएं।

```java
Presentation pres = new Presentation();
```

## चरण 5: ब्लॉब छवि जोड़ें

 अब, प्रेजेंटेशन में ब्लॉब इमेज जोड़ने का समय आ गया है। हम इसका उपयोग करते हैं`addImage`इसे प्राप्त करने की विधि.

```java
IPPImage img = pres.getImages().addImage(fip, LoadingStreamBehavior.KeepLocked);
pres.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, 300, 200, img);
```

## चरण 6: प्रेजेंटेशन सहेजें

अंत में, जोड़ी गई ब्लॉब छवि के साथ प्रस्तुति को सहेजें।

```java
pres.save(dataDir + "presentationWithBlobImage.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में प्रेजेंटेशन में ब्लॉब इमेज जोड़ने के लिए पूरा स्रोत कोड

```java
        // दस्तावेज़ निर्देशिका का पथ.
        String dataDir = "Your Document Directory";
        String pathToLargeImage = dataDir + "large_image.jpg";
        // एक नई प्रस्तुति बनाएं जिसमें यह छवि होगी
        Presentation pres = new Presentation();
        try
        {
            // मान लीजिए कि हमारे पास बड़ी छवि फ़ाइल है जिसे हम प्रस्तुति में शामिल करना चाहते हैं
            FileInputStream fip = new FileInputStream(dataDir + "large_image.jpg");
            try
            {
                // आइए प्रस्तुति में छवि जोड़ें - हम KeepLocked व्यवहार चुनते हैं, क्योंकि हम नहीं
                // "largeImage.png" फ़ाइल तक पहुँचने का इरादा है।
                IPPImage img = pres.getImages().addImage(fip, LoadingStreamBehavior.KeepLocked);
                pres.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, 300, 200, img);
                // प्रेजेंटेशन को सेव करें। इसके बावजूद आउटपुट प्रेजेंटेशन होगा
                // बड़ा, प्रेस ऑब्जेक्ट के पूरे जीवनकाल में मेमोरी की खपत कम होगी
                pres.save(dataDir + "presentationWithLargeImage.pptx", SaveFormat.Pptx);
            }
            finally
            {
                fip.close();
            }
        }
        catch (java.io.IOException e)
        {
            e.printStackTrace();
        }
        finally
        {
            pres.dispose();
        }
```

## निष्कर्ष

बधाई हो! आपने Aspose.Slides का उपयोग करके Java Slides में प्रेजेंटेशन में ब्लॉब इमेज जोड़ना सफलतापूर्वक सीख लिया है। यह कौशल तब अमूल्य हो सकता है जब आपको कस्टम इमेज के साथ अपनी प्रेजेंटेशन को बेहतर बनाने की आवश्यकता हो। दिखने में आकर्षक स्लाइड बनाने के लिए अलग-अलग इमेज और लेआउट के साथ प्रयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Slides कैसे स्थापित करूं?

Aspose.Slides for Java को वेबसाइट से लाइब्रेरी डाउनलोड करके आसानी से स्थापित किया जा सकता है[यहाँ](https://releases.aspose.com/slides/java/)इसे अपने जावा प्रोजेक्ट में एकीकृत करने के लिए दिए गए इंस्टॉलेशन निर्देशों का पालन करें।

### क्या मैं एक ही प्रस्तुति में एकाधिक ब्लॉब छवियाँ जोड़ सकता हूँ?

हां, आप एक ही प्रस्तुति में कई ब्लॉब इमेज जोड़ सकते हैं। बस इस ट्यूटोरियल में बताए गए चरणों को हर उस इमेज के लिए दोहराएँ जिसे आप शामिल करना चाहते हैं।

### प्रस्तुतियों के लिए अनुशंसित छवि प्रारूप क्या है?

प्रस्तुतियों के लिए JPEG या PNG जैसे सामान्य छवि प्रारूपों का उपयोग करना उचित है। Aspose.Slides for Java विभिन्न छवि प्रारूपों का समर्थन करता है, जो अधिकांश प्रस्तुति सॉफ़्टवेयर के साथ संगतता सुनिश्चित करता है।

### मैं जोड़े गए ब्लॉब चित्र की स्थिति और आकार को कैसे अनुकूलित कर सकता हूँ?

 आप पैरामीटर्स को संशोधित करके जोड़े गए ब्लॉब चित्र की स्थिति और आकार को समायोजित कर सकते हैं`addPictureFrame` विधि। चार मान (x-निर्देशांक, y-निर्देशांक, चौड़ाई और ऊँचाई) छवि फ़्रेम की स्थिति और आयाम निर्धारित करते हैं।

### क्या Aspose.Slides उन्नत पावरपॉइंट स्वचालन कार्यों के लिए उपयुक्त है?

बिल्कुल! Aspose.Slides PowerPoint स्वचालन के लिए उन्नत क्षमताएँ प्रदान करता है, जिसमें स्लाइड निर्माण, संशोधन और डेटा निष्कर्षण शामिल है। यह आपके PowerPoint-संबंधित कार्यों को सुव्यवस्थित करने के लिए एक शक्तिशाली उपकरण है।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
