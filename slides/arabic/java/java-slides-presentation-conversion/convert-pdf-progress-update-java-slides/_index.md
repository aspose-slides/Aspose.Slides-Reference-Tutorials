---
"description": "حوّل ملفات PowerPoint إلى PDF مع تحديثات التقدم في جافا باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدري وتتبع التقدم لضمان تحويل سلس."
"linktitle": "تحويل إلى PDF باستخدام تحديث التقدم في Java Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحويل إلى PDF باستخدام تحديث التقدم في Java Slides"
"url": "/ar/java/presentation-conversion/convert-pdf-progress-update-java-slides/"
"weight": 36
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل إلى PDF باستخدام تحديث التقدم في Java Slides


## مقدمة لتحويل PowerPoint إلى PDF مع تحديثات التقدم في Java باستخدام Aspose.Slides لـ Java

في هذا الدليل التفصيلي، سنوضح كيفية تحويل عرض تقديمي من PowerPoint (PPTX) إلى ملف PDF بلغة Java باستخدام Aspose.Slides for Java. كما سنُضيف تحديثات حول التقدم أثناء عملية التحويل.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- تم إعداد بيئة تطوير Java.
- تمت إضافة مكتبة Aspose.Slides لجافا إلى مشروعك. يمكنك تنزيلها من [هنا](https://downloads.aspose.com/slides/java).

## الخطوة 1: استيراد Aspose.Slides لمكتبة Java

للبدء، عليك استيراد مكتبة Aspose.Slides إلى مشروع Java. تأكد من إضافة ملفات Aspose.Slides JAR إلى مسار فئتك.

```java
import com.aspose.slides.*;
```

## الخطوة 2: إنشاء فئة Java

أنشئ فئة جافا لتحويل PowerPoint إلى PDF. لنسمِّها `PowerPointToPdfConverter`.

```java
public class PowerPointToPdfConverter {
    public static void main(String[] args) {
        // المسار إلى دليل المستندات.
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation(dataDir + "ConvertToPDF.pptx");
        try {
            ISaveOptions saveOptions = new PdfOptions();
            saveOptions.setProgressCallback(new ExportProgressHandler());
            presentation.save(dataDir + "ConvertToPDF.pdf", SaveFormat.Pdf, saveOptions);
        } finally {
            if (presentation != null) presentation.dispose();
        }
    }
}
```

## الخطوة 3: تنفيذ استدعاء التقدم

سنُنفِّذ مُعالِج استدعاء التقدم لتلقي التحديثات أثناء عملية التحويل. لنُنشئ فئةً باسم `ExportProgressHandler` لهذا الغرض.

```java
class ExportProgressHandler implements IProgressCallback {
    public void reporting(double progressValue) {
        // استخدم قيمة النسبة المئوية للتقدم هنا
        long progress = Math.round(progressValue);
        System.out.println(progress + "% file converted");
    }
}
```

## الخطوة 4: استبدال "دليل المستندات الخاص بك"

يستبدل `"Your Document Directory"` في `PowerPointToPdfConverter` الفئة التي تحتوي على المسار الفعلي لملف PowerPoint الخاص بك ودليل الإخراج المطلوب.

## الخطوة 5: التجميع والتشغيل

قم بتجميع فئة Java الخاصة بك وتشغيلها `PowerPointToPdfConverter` سيتم تحويل عرض PowerPoint إلى ملف PDF مع توفير تحديثات التقدم في وحدة التحكم.

## كود المصدر الكامل لتحويل إلى PDF مع تحديث التقدم في شرائح Java

```java
        // المسار إلى دليل المستندات.
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation(dataDir + "ConvertToPDF.pptx");
        try
        {
            ISaveOptions saveOptions = new PdfOptions();
            saveOptions.setProgressCallback(new ExportProgressHandler());
            presentation.save(dataDir + "ConvertToPDF.pdf", SaveFormat.Pdf, saveOptions);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
    }
}
class ExportProgressHandler implements IProgressCallback
{
    public void reporting(double progressValue)
    {
        // استخدم قيمة النسبة المئوية للتقدم هنا
        long progress = Math.round(progressValue);
        System.out.println(progress + "% file converted");
```

## خاتمة

في هذا الدليل التفصيلي، استكشفنا كيفية تحويل عرض تقديمي من PowerPoint (PPTX) إلى ملف PDF في Java باستخدام Aspose.Slides for Java. بالإضافة إلى ذلك، قمنا بتحديث تقدم العملية أثناء عملية التحويل لمتابعة حالة العملية.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لـ Java؟

يمكنك تنزيل Aspose.Slides لـ Java من موقع Aspose على الويب على [هنا](https://downloads.aspose.com/slides/java).

### ما هو الغرض من `IProgressCallback`؟

`IProgressCallback` واجهة Aspose.Slides لجافا تُتيح لك إعداد تقارير التقدم أثناء عمليات التصدير. تتيح لك هذه الواجهة تتبُّع تقدم مهام مثل تحويل العروض التقديمية إلى PDF.

### هل يمكنني استخدام Aspose.Slides لـ Java لعمليات PowerPoint الأخرى؟

نعم، يوفر Aspose.Slides for Java وظائف واسعة النطاق للعمل مع عروض PowerPoint، بما في ذلك إنشاء العروض التقديمية وتعديلها وتحويلها إلى تنسيقات مختلفة.

### كيف يمكنني تخصيص خيارات تحويل PDF؟

يمكنك تخصيص خيارات تحويل PDF عن طريق تعديل `PdfOptions` الكائن قبل استدعاء `presentation.save` تتضمن هذه الطريقة ضبط خصائص مثل حجم الصفحة والجودة والمزيد.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}