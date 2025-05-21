---
"date": "2025-04-17"
"description": "تعرّف على كيفية تخصيص تنسيقات التاريخ لمحاور الفئات باستخدام Aspose.Slides لجافا. حسّن مخططاتك البيانية بعرض بيانات مخصص، مثالي للتقارير السنوية وغيرها."
"title": "كيفية تعيين تنسيق تاريخ مخصص على محور الفئة في Aspose.Slides Java | دليل تصور البيانات"
"url": "/ar/java/shapes-text-frames/aspose-slides-java-custom-date-format-category-axis/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تعيين تنسيق تاريخ مخصص على محور الفئة في Aspose.Slides Java | دليل تصور البيانات

في عالمنا اليوم الذي يعتمد على البيانات، يُعدّ عرض المعلومات بوضوح أمرًا بالغ الأهمية لاتخاذ قرارات مؤثرة. عند إنشاء مخططات بيانية باستخدام Aspose.Slides لجافا، يُمكن لتخصيص تنسيق التاريخ على محور الفئة أن يُحسّن بشكل كبير من فهم العرض وجودته. سيرشدك هذا الدليل إلى كيفية إعداد تنسيق تاريخ مُخصّص في Aspose.Slides لتحسين مظهر شرائحك ووضوح بياناتها.

**ما سوف تتعلمه:**
- إعداد Aspose.Slides لـ Java
- تنفيذ تنسيقات التاريخ المخصصة على محور الفئة
- تحويل تواريخ التقويم الميلادي إلى تنسيق تاريخ أتمتة OLE
- التطبيقات العملية لهذه الميزات في سيناريوهات العالم الحقيقي

دعونا نتعمق في كيفية تحقيق ذلك بسهولة!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أنك قمت بتغطية المتطلبات الأساسية التالية:

### المكتبات والإصدارات المطلوبة:
- **Aspose.Slides لـ Java**:ستحتاج إلى الإصدار 25.4 أو أحدث.

### متطلبات إعداد البيئة:
- بيئة تطوير قادرة على تشغيل كود Java (مثل IntelliJ IDEA، أو Eclipse، أو NetBeans).
- تم تكوين Maven أو Gradle في مشروعك لإدارة التبعيات.

### المتطلبات المعرفية:
- فهم أساسيات برمجة جافا.
- - المعرفة بكيفية استخدام مكونات المخطط داخل العروض التقديمية.

## إعداد Aspose.Slides لـ Java

للعمل مع Aspose.Slides لجافا، أضفه كاعتمادية في مشروعك. إليك تعليمات التثبيت:

**مافن:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**جرادل:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

بدلا من ذلك، يمكنك [تنزيل أحدث إصدار](https://releases.aspose.com/slides/java/) مباشرة من الموقع الرسمي لـ Aspose.

### الحصول على الترخيص:
- **نسخة تجريبية مجانية**:ابدأ بإصدار تجريبي مجاني لاستكشاف الميزات.
- **رخصة مؤقتة**:اطلب ترخيصًا مؤقتًا لإجراء اختبار ممتد.
- **شراء**للاستخدام طويل الأمد، فكّر في شراء اشتراك. تفضل بزيارة [شراء Aspose](https://purchase.aspose.com/buy) لمزيد من التفاصيل.

### التهيئة الأساسية:

إليك كيفية تهيئة Aspose.Slides في مشروعك:
```java
import com.aspose.slides.Presentation;
// إنشاء كائن عرض تقديمي يمثل ملف عرض تقديمي
Presentation pres = new Presentation();
```

والآن دعونا ننتقل إلى جوهر هذا الدليل!

## دليل التنفيذ

### ضبط تنسيق التاريخ لمحور الفئة

تتيح لك هذه الميزة تخصيص طريقة عرض التواريخ على محور فئة مخططك البياني. فيما يلي دليل مفصل:

#### 1. إنشاء عرض تقديمي ومخطط جديدين
ابدأ بإنشاء مثيل لـ `Presentation` وإضافة مخطط منطقة جديد.
```java
import com.aspose.slides.*;
import java.text.ParseException;
import java.util.GregorianCalendar;

public class DateFormatFeature {
    public static void main(String[] args) throws ParseException {
        // تهيئة العرض التقديمي
        Presentation pres = new Presentation();
        
        try {
            // إضافة مخطط منطقة إلى الشريحة الأولى في الموضع والحجم المحددين
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);

            // مصنف بيانات مخطط Access لمعالجة بيانات المخطط
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0); // مسح أي بيانات موجودة في الرسم البياني

            // إزالة أي فئات وسلاسل موجودة مسبقًا
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();

            // إضافة تواريخ إلى محور الفئة باستخدام تواريخ OLE Automation المحولة
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

            // إنشاء سلسلة جديدة وإضافة نقاط البيانات إليها
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));

            // تعيين نوع محور الفئة إلى التاريخ وتكوين تنسيق الأرقام الخاص به
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false); 
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy"); // تنسيق التواريخ على أنها سنة فقط

            // حفظ العرض التقديمي في الدليل المحدد
            pres.save("YOUR_OUTPUT_DIRECTORY/test.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // التاريخ الأساسي لتحويل OLE Automation
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60)); // تحويل إلى تاريخ أتمتة OLE
        return String.valueOf(oaDate);
    }
}
```

#### 2. تحويل تاريخ التقويم الميلادي إلى تنسيق تاريخ أتمتة OLE

يتطلب Aspose.Slides تواريخ بتنسيق OLE Automation، وهو تنسيق تاريخ قياسي في Excel. إليك كيفية تحويل بيانات Java الخاصة بك `GregorianCalendar` بلح:
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;
import java.util.concurrent.TimeUnit;

public class OADateConversionFeature {
    public static void main(String[] args) throws ParseException {
        GregorianCalendar date = new GregorianCalendar(2021, 0, 15); // 15 يناير 2021
        String oaDate = convertToOADate(date);
        System.out.println("OLE Automation Date: " + oaDate); 
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // التاريخ الأساسي لبرنامج Excel لأتمتة OLE
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
    }
}
```

### نصائح استكشاف الأخطاء وإصلاحها:
- تأكد من تاريخ الأساس للتحويل (`30 Dec 1899`) تم تحليلها بشكل صحيح.
- تأكد من أن بيئة Java الخاصة بك تدعم المكتبات والفئات الضرورية.
- في حالة ظهور مشكلات، تحقق من وجود أي تحديثات أو تصحيحات متوفرة لـ Aspose.Slides.

### التطبيقات العملية

يمكن أن يكون تخصيص تنسيقات التاريخ مفيدًا بشكل خاص في السيناريوهات مثل:
- **التقارير السنوية:** عرض اتجاهات البيانات السنوية بشكل واضح.
- **المخططات المالية:** عرض الفترات المالية بدقة.
- **الجدول الزمني للمشروع:** تسليط الضوء على أطر زمنية أو معالم محددة.

من خلال اتباع هذا الدليل، ستتمكن من تحسين عروضك التقديمية بتنسيقات تاريخ دقيقة وجذابة بصريًا باستخدام Aspose.Slides for Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}