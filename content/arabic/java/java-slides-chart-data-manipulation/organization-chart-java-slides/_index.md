---
title: المخطط التنظيمي في شرائح جافا
linktitle: المخطط التنظيمي في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء مخططات تنظيمية مذهلة في Java Slides من خلال البرامج التعليمية خطوة بخطوة في Aspose.Slides. قم بتخصيص وتصور الهيكل التنظيمي الخاص بك دون عناء.
type: docs
weight: 22
url: /ar/java/chart-data-manipulation/organization-chart-java-slides/
---

## مقدمة لإنشاء مخطط هيكلي في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، سنوضح كيفية إنشاء مخطط هيكلي في Java Slides باستخدام Aspose.Slides for Java API. المخطط الهيكلي هو تمثيل مرئي للهيكل الهرمي للمؤسسة، ويستخدم عادةً لتوضيح العلاقات والتسلسل الهرمي بين الموظفين أو الأقسام.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- [Aspose.Slides لجافا](https://products.aspose.com/slides/java) المكتبة المثبتة في مشروع Java الخاص بك.
- بيئة تطوير متكاملة لـ Java (IDE) مثل IntelliJ IDEA أو Eclipse.

## الخطوة 1: قم بإعداد مشروع Java الخاص بك

1. قم بإنشاء مشروع Java جديد في IDE المفضل لديك.
2.  أضف مكتبة Aspose.Slides for Java إلى مشروعك. يمكنك تحميل المكتبة من[موقع أسبوز](https://products.aspose.com/slides/java)وإدراجه باعتباره تبعية.

## الخطوة 2: استيراد المكتبات المطلوبة
في صف Java الخاص بك، قم باستيراد المكتبات اللازمة للعمل مع Aspose.Slides:

```java
import com.aspose.slides.*;
```

## الخطوة 3: إنشاء مخطط هيكلي

الآن، لنقم بإنشاء مخطط هيكلي باستخدام Aspose.Slides. سنتبع الخطوات التالية:

1. حدد المسار إلى دليل المستند الخاص بك.
2. قم بتحميل عرض PowerPoint تقديمي موجود أو أنشئ عرضًا جديدًا.
3. إضافة شكل مخطط هيكلي إلى شريحة.
4. احفظ العرض التقديمي باستخدام المخطط الهيكلي.

إليك الكود لإنجاز هذا:

```java
// حدد المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// قم بتحميل عرض تقديمي موجود أو قم بإنشاء عرض تقديمي جديد.
Presentation pres = new Presentation(dataDir + "test.pptx");
try {
    // أضف شكل مخطط هيكلي إلى الشريحة الأولى.
    ISmartArt smartArt = pres.getSlides().get_Item(0).getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.PictureOrganizationChart);

    // احفظ العرض التقديمي باستخدام المخطط الهيكلي.
    pres.save(dataDir + "OrganizationChart.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 يستبدل`"Your Document Directory"` بالمسار الفعلي إلى دليل المستندات الخاص بك و`"test.pptx"` مع اسم العرض التقديمي الذي أدخلته في PowerPoint.

## الخطوة 4: قم بتشغيل الكود

الآن بعد أن قمت بإضافة التعليمات البرمجية لإنشاء مخطط هيكلي، قم بتشغيل تطبيق Java الخاص بك. تأكد من إضافة مكتبة Aspose.Slides بشكل صحيح إلى مشروعك، ومن حل التبعيات الضرورية.

## أكمل كود المصدر للمخطط الهيكلي في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	ISmartArt smartArt = pres.getSlides().get_Item(0).getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.PictureOrganizationChart);
	pres.save(dataDir + "OrganizationChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مخطط هيكلي في Java Slides باستخدام Aspose.Slides for Java API. يمكنك تخصيص مظهر المخطط الهيكلي ومحتواه وفقًا لمتطلباتك المحددة. يوفر Aspose.Slides مجموعة واسعة من الميزات للعمل مع عروض PowerPoint التقديمية، مما يجعله أداة قوية لإدارة المحتوى المرئي وإنشائه.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر المخطط الهيكلي؟

يمكنك تخصيص مظهر المخطط الهيكلي عن طريق تعديل خصائصه مثل الألوان والأنماط والخطوط. راجع وثائق Aspose.Slides للحصول على تفاصيل حول كيفية تخصيص أشكال SmartArt.

### هل يمكنني إضافة أشكال أو نص إضافي إلى المخطط الهيكلي؟

نعم، يمكنك إضافة أشكال ونصوص وموصلات إضافية إلى المخطط الهيكلي لتمثيل الهيكل التنظيمي الخاص بك بدقة. استخدم Aspose.Slides API لإضافة الأشكال وتنسيقها داخل مخطط SmartArt.

### كيف يمكنني تصدير المخطط الهيكلي إلى تنسيقات أخرى، مثل PDF أو صورة؟

 يمكنك تصدير العرض التقديمي الذي يحتوي على المخطط الهيكلي إلى تنسيقات مختلفة باستخدام Aspose.Slides. على سبيل المثال، للتصدير إلى PDF، استخدم الملف`SaveFormat.Pdf` الخيار عند حفظ العرض التقديمي. وبالمثل، يمكنك التصدير إلى تنسيقات الصور مثل PNG أو JPEG.

### هل يمكن إنشاء هياكل تنظيمية معقدة ذات مستويات متعددة؟

نعم، يتيح لك Aspose.Slides إنشاء هياكل تنظيمية معقدة ذات مستويات متعددة عن طريق إضافة الأشكال وترتيبها داخل المخطط الهيكلي. يمكنك تحديد العلاقات الهرمية بين الأشكال لتمثيل البنية المطلوبة.