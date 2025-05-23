---
"date": "2025-04-17"
"description": "Aspose.Slides for Java का उपयोग करके श्रेणी अक्षों के लिए दिनांक प्रारूपों को अनुकूलित करना सीखें। कस्टम डेटा प्रस्तुति के साथ अपने चार्ट को बेहतर बनाएँ, वार्षिक रिपोर्ट और बहुत कुछ के लिए एकदम सही।"
"title": "Aspose.Slides Java में श्रेणी अक्ष पर कस्टम दिनांक प्रारूप कैसे सेट करें | डेटा विज़ुअलाइज़ेशन गाइड"
"url": "/hi/java/shapes-text-frames/aspose-slides-java-custom-date-format-category-axis/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java में श्रेणी अक्ष पर कस्टम दिनांक प्रारूप कैसे सेट करें | डेटा विज़ुअलाइज़ेशन गाइड

आज की डेटा-संचालित दुनिया में, प्रभावशाली निर्णय लेने के लिए जानकारी को स्पष्ट रूप से प्रस्तुत करना महत्वपूर्ण है। Aspose.Slides for Java का उपयोग करके चार्ट बनाते समय, श्रेणी अक्ष पर दिनांक प्रारूप को अनुकूलित करने से समझ और प्रस्तुति गुणवत्ता दोनों में बहुत सुधार हो सकता है। यह मार्गदर्शिका आपको Aspose.Slides में कस्टम दिनांक प्रारूप सेट करने के बारे में बताएगी ताकि आपकी स्लाइड की दृश्य अपील और डेटा स्पष्टता बढ़े।

**आप क्या सीखेंगे:**
- Java के लिए Aspose.Slides सेट अप करना
- श्रेणी अक्ष पर कस्टम दिनांक प्रारूप लागू करना
- ग्रेगोरियन कैलेंडर तिथियों को OLE स्वचालन तिथि प्रारूप में परिवर्तित करना
- वास्तविक दुनिया के परिदृश्यों में इन सुविधाओं के व्यावहारिक अनुप्रयोग

आइये जानें कि आप इसे आसानी से कैसे प्राप्त कर सकते हैं!

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपने निम्नलिखित पूर्वापेक्षाएँ पूरी कर ली हैं:

### आवश्यक लाइब्रेरी और संस्करण:
- **जावा के लिए Aspose.Slides**आपको संस्करण 25.4 या बाद के संस्करण की आवश्यकता होगी.

### पर्यावरण सेटअप आवश्यकताएँ:
- एक विकास वातावरण जो जावा कोड चलाने में सक्षम है (जैसे कि इंटेलीज आईडिया, एक्लिप्स, या नेटबीन्स)।
- निर्भरताओं को प्रबंधित करने के लिए आपके प्रोजेक्ट में Maven या Gradle कॉन्फ़िगर किया गया है।

### ज्ञान पूर्वापेक्षाएँ:
- जावा प्रोग्रामिंग की बुनियादी समझ.
- प्रस्तुतियों में चार्ट घटकों के उपयोग से परिचित होना।

## Java के लिए Aspose.Slides सेट अप करना

Aspose.Slides for Java के साथ काम करने के लिए, इसे अपने प्रोजेक्ट में निर्भरता के रूप में शामिल करें। नीचे इंस्टॉलेशन निर्देश दिए गए हैं:

**मावेन:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**ग्रेडेल:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

वैकल्पिक रूप से, आप [नवीनतम रिलीज़ डाउनलोड करें](https://releases.aspose.com/slides/java/) सीधे Aspose की आधिकारिक साइट से.

### लाइसेंस प्राप्ति:
- **मुफ्त परीक्षण**: सुविधाओं का पता लगाने के लिए निःशुल्क परीक्षण से शुरुआत करें।
- **अस्थायी लाइसेंस**विस्तारित परीक्षण के लिए अस्थायी लाइसेंस का अनुरोध करें।
- **खरीदना**: लंबे समय तक उपयोग के लिए, सदस्यता खरीदने पर विचार करें। [Aspose खरीद](https://purchase.aspose.com/buy) जानकारी के लिए।

### बुनियादी आरंभीकरण:

यहां बताया गया है कि आप अपने प्रोजेक्ट में Aspose.Slides को कैसे आरंभ कर सकते हैं:
```java
import com.aspose.slides.Presentation;
// एक प्रस्तुति ऑब्जेक्ट को इंस्टैंसिएट करें जो एक प्रस्तुति फ़ाइल का प्रतिनिधित्व करता है
Presentation pres = new Presentation();
```

अब, आइये इस गाइड के मूल पर आते हैं!

## कार्यान्वयन मार्गदर्शिका

### श्रेणी अक्ष के लिए दिनांक प्रारूप सेट करना

यह सुविधा आपको यह कस्टमाइज़ करने की अनुमति देती है कि आपके चार्ट की श्रेणी अक्ष पर दिनांक कैसे प्रदर्शित हों। नीचे एक विस्तृत मार्गदर्शिका दी गई है:

#### 1. एक नया प्रेजेंटेशन और चार्ट बनाएं
इसका एक उदाहरण बनाकर शुरू करें `Presentation` और एक नया क्षेत्र चार्ट जोड़ना।
```java
import com.aspose.slides.*;
import java.text.ParseException;
import java.util.GregorianCalendar;

public class DateFormatFeature {
    public static void main(String[] args) throws ParseException {
        // प्रस्तुति आरंभ करें
        Presentation pres = new Presentation();
        
        try {
            // निर्दिष्ट स्थान और आकार पर पहली स्लाइड में एक क्षेत्र चार्ट जोड़ें
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);

            // चार्ट डेटा में हेरफेर करने के लिए चार्ट डेटा कार्यपुस्तिका तक पहुँचें
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0); // चार्ट में मौजूद कोई भी डेटा साफ़ करें

            // किसी भी पूर्व-मौजूद श्रेणियों और श्रृंखला को हटाएँ
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();

            // परिवर्तित OLE स्वचालन तिथियों का उपयोग करके श्रेणी अक्ष में तिथियां जोड़ें
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

            // एक नई श्रृंखला बनाएं और उसमें डेटा बिंदु जोड़ें
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));

            // श्रेणी अक्ष प्रकार को दिनांक पर सेट करें और उसका संख्या प्रारूप कॉन्फ़िगर करें
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false); 
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy"); // तिथियों को केवल वर्ष के रूप में प्रारूपित करें

            // प्रस्तुति को निर्दिष्ट निर्देशिका में सहेजें
            pres.save("YOUR_OUTPUT_DIRECTORY/test.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // OLE स्वचालन रूपांतरण के लिए आधार तिथि
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60)); // OLE स्वचालन तिथि में परिवर्तित करें
        return String.valueOf(oaDate);
    }
}
```

#### 2. ग्रेगोरियन कैलेंडर तिथि को OLE ऑटोमेशन तिथि प्रारूप में परिवर्तित करना

Aspose.Slides को OLE ऑटोमेशन प्रारूप में दिनांकों की आवश्यकता होती है, जो एक मानक Excel दिनांक प्रारूप है। यहाँ बताया गया है कि आप अपने Java को कैसे परिवर्तित करते हैं `GregorianCalendar` खजूर:
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;
import java.util.concurrent.TimeUnit;

public class OADateConversionFeature {
    public static void main(String[] args) throws ParseException {
        GregorianCalendar date = new GregorianCalendar(2021, 0, 15); // 15 जनवरी 2021
        String oaDate = convertToOADate(date);
        System.out.println("OLE Automation Date: " + oaDate); 
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // OLE स्वचालन के लिए एक्सेल की आधार तिथि
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
    }
}
```

### समस्या निवारण युक्तियों:
- रूपांतरण के लिए आधार तिथि सुनिश्चित करें (`30 Dec 1899`) सही ढंग से पार्स किया गया है.
- सत्यापित करें कि आपका जावा वातावरण आवश्यक लाइब्रेरीज़ और क्लासेस का समर्थन करता है।
- यदि कोई समस्या उत्पन्न हो तो Aspose.Slides के लिए उपलब्ध किसी भी अपडेट या पैच की जांच करें।

### व्यावहारिक अनुप्रयोगों

दिनांक प्रारूपों को अनुकूलित करना विशेष रूप से निम्नलिखित परिदृश्यों में उपयोगी हो सकता है:
- **वार्षिक रिपोर्ट:** वार्षिक डेटा प्रवृत्तियों को स्पष्ट रूप से प्रदर्शित करना।
- **वित्तीय चार्ट:** वित्तीय अवधियों को सटीक रूप से प्रस्तुत करना।
- **परियोजना समयसीमा:** विशिष्ट समय-सीमा या मील के पत्थर पर प्रकाश डालना।

इस गाइड का पालन करके, आप Aspose.Slides for Java का उपयोग करके अपनी प्रस्तुतियों को सटीक और आकर्षक दिनांक प्रारूपों के साथ बेहतर बना सकेंगे।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}