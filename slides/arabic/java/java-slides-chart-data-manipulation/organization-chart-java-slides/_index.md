---
"description": "تعلّم كيفية إنشاء مخططات تنظيمية رائعة باستخدام Java Slides من خلال دروس Aspose.Slides التعليمية خطوة بخطوة. خصّص هيكلك التنظيمي وصوّره بسهولة."
"linktitle": "مخطط تنظيمي في شرائح جافا"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مخطط تنظيمي في شرائح جافا"
"url": "/ar/java/chart-data-manipulation/organization-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مخطط تنظيمي في شرائح جافا


## مقدمة لإنشاء مخطط تنظيمي في Java Slides باستخدام Aspose.Slides

في هذا البرنامج التعليمي، سنوضح كيفية إنشاء مخطط تنظيمي في Java Slides باستخدام واجهة برمجة تطبيقات Aspose.Slides لـ Java. المخطط التنظيمي هو تمثيل مرئي للهيكل الهرمي للمؤسسة، ويُستخدم عادةً لتوضيح العلاقات والتسلسل الهرمي بين الموظفين أو الأقسام.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية لديك:

- [Aspose.Slides لـ Java](https://products.aspose.com/slides/java) المكتبة المثبتة في مشروع Java الخاص بك.
- بيئة تطوير Java المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## الخطوة 1: إعداد مشروع Java الخاص بك

1. قم بإنشاء مشروع Java جديد في IDE المفضل لديك.
2. أضف مكتبة Aspose.Slides لجافا إلى مشروعك. يمكنك تنزيل المكتبة من [موقع Aspose](https://products.aspose.com/slides/java) وتضمينه كاعتمادية.

## الخطوة 2: استيراد المكتبات المطلوبة
في فئة Java الخاصة بك، قم باستيراد المكتبات الضرورية للعمل مع Aspose.Slides:

```java
import com.aspose.slides.*;
```

## الخطوة 3: إنشاء مخطط تنظيمي

الآن، لنُنشئ مخططًا تنظيميًا باستخدام Aspose.Slides. سنتبع الخطوات التالية:

1. حدد المسار إلى دليل المستند الخاص بك.
2. قم بتحميل عرض تقديمي PowerPoint موجود أو قم بإنشاء عرض تقديمي جديد.
3. إضافة شكل مخطط تنظيمي إلى شريحة.
4. احفظ العرض التقديمي مع مخطط التنظيم.

إليك الكود لإنجاز هذا:

```java
// حدد المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// قم بتحميل عرض تقديمي موجود أو قم بإنشاء عرض تقديمي جديد.
Presentation pres = new Presentation(dataDir + "test.pptx");
try {
    // أضف شكل مخطط تنظيمي إلى الشريحة الأولى.
    ISmartArt smartArt = pres.getSlides().get_Item(0).getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.PictureOrganizationChart);

    // احفظ العرض التقديمي مع مخطط التنظيم.
    pres.save(dataDir + "OrganizationChart.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

يستبدل `"Your Document Directory"` مع المسار الفعلي إلى دليل المستند الخاص بك و `"test.pptx"` مع اسم عرض PowerPoint المدخل الخاص بك.

## الخطوة 4: تشغيل الكود

بعد إضافة الكود لإنشاء مخطط تنظيمي، شغّل تطبيق جافا. تأكد من إضافة مكتبة Aspose.Slides بشكل صحيح إلى مشروعك، ومن حل التبعيات اللازمة.

## كود المصدر الكامل للمخطط التنظيمي في شرائح Java

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

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مخطط تنظيمي في Java Slides باستخدام واجهة برمجة تطبيقات Aspose.Slides لـ Java. يمكنك تخصيص مظهر ومحتوى المخطط التنظيمي وفقًا لاحتياجاتك الخاصة. يوفر Aspose.Slides مجموعة واسعة من الميزات للعمل مع عروض PowerPoint التقديمية، مما يجعله أداة فعّالة لإدارة وإنشاء المحتوى المرئي.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر المخطط التنظيمي؟

يمكنك تخصيص مظهر المخطط التنظيمي بتعديل خصائصه، مثل الألوان والأنماط والخطوط. راجع وثائق Aspose.Slides لمزيد من التفاصيل حول كيفية تخصيص أشكال SmartArt.

### هل يمكنني إضافة أشكال أو نصوص إضافية إلى مخطط التنظيم؟

نعم، يمكنك إضافة أشكال ونصوص وموصلات إضافية إلى مخططك التنظيمي لعرض هيكلك التنظيمي بدقة. استخدم واجهة برمجة تطبيقات Aspose.Slides لإضافة الأشكال وتنسيقها داخل مخطط SmartArt.

### كيف يمكنني تصدير مخطط التنظيم إلى تنسيقات أخرى، مثل PDF أو صورة؟

يمكنك تصدير العرض التقديمي الذي يحتوي على مخطط التنظيم إلى تنسيقات مختلفة باستخدام Aspose.Slides. على سبيل المثال، للتصدير إلى PDF، استخدم `SaveFormat.Pdf` عند حفظ العرض التقديمي. وبالمثل، يمكنك تصديره إلى صيغ صور مثل PNG أو JPEG.

### هل من الممكن إنشاء هياكل تنظيمية معقدة ذات مستويات متعددة؟

نعم، يتيح لك Aspose.Slides إنشاء هياكل تنظيمية معقدة ذات مستويات متعددة عن طريق إضافة الأشكال وترتيبها داخل المخطط التنظيمي. يمكنك تحديد علاقات هرمية بين الأشكال لتمثيل الهيكل المطلوب.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}