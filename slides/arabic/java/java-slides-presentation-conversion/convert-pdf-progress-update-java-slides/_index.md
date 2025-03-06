---
title: تحويل إلى PDF مع تحديث التقدم في شرائح جافا
linktitle: تحويل إلى PDF مع تحديث التقدم في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تحويل PowerPoint إلى PDF مع تحديثات التقدم في Java باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع الكود المصدري وتتبع التقدم من أجل تحويل سلس.
weight: 36
url: /ar/java/presentation-conversion/convert-pdf-progress-update-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل إلى PDF مع تحديث التقدم في شرائح جافا


## مقدمة لتحويل PowerPoint إلى PDF مع تحديثات التقدم في Java باستخدام Aspose.Slides لـ Java

في هذا الدليل خطوة بخطوة، سنوضح كيفية تحويل عرض PowerPoint التقديمي (PPTX) إلى ملف PDF في Java باستخدام Aspose.Slides for Java. بالإضافة إلى ذلك، سنقوم بتضمين تحديثات التقدم أثناء عملية التحويل.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

- إعداد بيئة تطوير جافا.
-  تمت إضافة مكتبة Aspose.Slides لـ Java إلى مشروعك. يمكنك تنزيله من[هنا](https://downloads.aspose.com/slides/java).

## الخطوة 1: استيراد Aspose.Slides لمكتبة Java

للبدء، تحتاج إلى استيراد مكتبة Aspose.Slides إلى مشروع Java الخاص بك. تأكد من إضافة ملفات Aspose.Slides JAR إلى مسار الفصل الدراسي الخاص بك.

```java
import com.aspose.slides.*;
```

## الخطوة 2: إنشاء فئة جافا

 قم بإنشاء فئة Java حيث ستقوم بإجراء تحويل PowerPoint إلى PDF. دعونا نسميها`PowerPointToPdfConverter`.

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

## الخطوة 3: تنفيذ رد الاتصال التقدمي

 سنقوم بتنفيذ معالج رد اتصال التقدم لتلقي التحديثات أثناء عملية التحويل. لنقم بإنشاء فئة تسمى`ExportProgressHandler` لهذا الغرض.

```java
class ExportProgressHandler implements IProgressCallback {
    public void reporting(double progressValue) {
        // استخدم قيمة النسبة المئوية للتقدم هنا
        long progress = Math.round(progressValue);
        System.out.println(progress + "% file converted");
    }
}
```

## الخطوة 4: استبدل "دليل المستندات الخاص بك"

 يستبدل`"Your Document Directory"` في ال`PowerPointToPdfConverter` فئة بالمسار الفعلي لملف PowerPoint الخاص بك ودليل الإخراج المطلوب.

## الخطوة 5: تجميع وتشغيل

قم بتجميع فئة Java الخاصة بك وتشغيل ملف`PowerPointToPdfConverter` فصل. سيقوم بتحويل عرض PowerPoint التقديمي إلى ملف PDF مع توفير تحديثات التقدم في وحدة التحكم.

## أكمل كود المصدر للتحويل إلى PDF مع تحديث التقدم في شرائح Java

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

في هذا الدليل التفصيلي، اكتشفنا كيفية تحويل عرض PowerPoint التقديمي (PPTX) إلى ملف PDF في Java باستخدام Aspose.Slides for Java. بالإضافة إلى ذلك، قمنا بتنفيذ تحديثات التقدم أثناء عملية التحويل لتتبع حالة العملية.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لنظام Java؟

 يمكنك تنزيل Aspose.Slides for Java من موقع Aspose على الويب[هنا](https://downloads.aspose.com/slides/java).

###  ما هو الغرض من`IProgressCallback`?

`IProgressCallback` هي واجهة مقدمة من Aspose.Slides لـ Java لتنفيذ التقارير المرحلية أثناء عمليات التصدير. يسمح لك بتتبع التقدم المحرز في المهام مثل تحويل العروض التقديمية إلى PDF.

### هل يمكنني استخدام Aspose.Slides for Java لعمليات PowerPoint الأخرى؟

نعم، يوفر Aspose.Slides for Java وظائف واسعة النطاق للعمل مع عروض PowerPoint التقديمية، بما في ذلك إنشاءها وتعديلها وتحويلها إلى تنسيقات مختلفة.

### كيف يمكنني تخصيص خيارات تحويل PDF؟

 يمكنك تخصيص خيارات تحويل PDF عن طريق تعديل ملف`PdfOptions` كائن قبل استدعاء`presentation.save` طريقة. يتضمن ذلك تعيين خصائص مثل حجم الصفحة والجودة والمزيد.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
