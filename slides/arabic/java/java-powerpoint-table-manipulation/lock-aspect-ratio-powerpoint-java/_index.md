---
"description": "تعرّف على كيفية تثبيت نسبة العرض إلى الارتفاع في عروض PowerPoint التقديمية باستخدام Java مع Aspose.Slides. مثالي لمطوري Java الذين يرغبون في تحكم دقيق في تصميم الشرائح."
"linktitle": "قفل نسبة العرض إلى الارتفاع في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "قفل نسبة العرض إلى الارتفاع في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-table-manipulation/lock-aspect-ratio-powerpoint-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# قفل نسبة العرض إلى الارتفاع في PowerPoint باستخدام Java

## مقدمة
في مجال تطوير جافا، يُمكن للتلاعب بعروض PowerPoint التقديمية برمجيًا أن يُبسط سير العمل ويُعزز الإنتاجية بشكل ملحوظ. يُوفر Aspose.Slides for Java مجموعة أدوات فعّالة لمطوري جافا لأتمتة مهام مثل تعديل الشرائح، وإضافة المحتوى، وتطبيق التنسيق مباشرةً من شفرة جافا. يُركز هذا البرنامج التعليمي على جانب أساسي من إدارة عروض PowerPoint التقديمية: تثبيت نسب العرض إلى الارتفاع.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على جهازك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- تم إعداد بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## استيراد الحزم
للبدء، قم باستيراد الحزم الضرورية من Aspose.Slides لـ Java:
```java
import com.aspose.slides.ITable;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
## الخطوة 1: تحميل العرض التقديمي
أولاً، قم بتحميل عرض PowerPoint حيث تريد قفل نسبة العرض إلى الارتفاع للكائن.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```
## الخطوة 2: الوصول إلى الكائن وقفل نسبة العرض إلى الارتفاع
بعد ذلك، قم بالوصول إلى الشكل (الكائن) داخل الشريحة وقم بقفل نسبة العرض إلى الارتفاع الخاصة به.
```java
try {
    ITable table = (ITable) pres.getSlides().get_Item(0).getShapes().get_Item(0);
    System.out.println("Lock aspect ratio set: " + table.getGraphicalObjectLock().getAspectRatioLocked());
    // تبديل قفل نسبة العرض إلى الارتفاع (عكس الحالة الحالية)
    table.getGraphicalObjectLock().setAspectRatioLocked(!table.getGraphicalObjectLock().getAspectRatioLocked());
    System.out.println("Lock aspect ratio set: " + table.getGraphicalObjectLock().getAspectRatioLocked());
} finally {
    if (pres != null) pres.dispose();
}
```
## الخطوة 3: حفظ العرض التقديمي المعدّل
بعد إجراء التغييرات، احفظ العرض التقديمي المعدّل.
```java
pres.save(dataDir + "pres-out.pptx", SaveFormat.Pptx);
```

## خاتمة
في الختام، يُمكّن استخدام Aspose.Slides لجافا مطوري جافا من أتمتة مهام PowerPoint بفعالية. يضمن تثبيت نسب العرض إلى الارتفاع سلامة تصميم عرضك التقديمي، مما يوفر تناسقًا بين مختلف الأجهزة وأحجام الشاشات.
## الأسئلة الشائعة
### لماذا يعد قفل نسبة العرض إلى الارتفاع أمرًا مهمًا في العروض التقديمية؟
يضمن قفل نسبة العرض إلى الارتفاع أن الصور والأشكال تحافظ على نسبها عند تغيير حجمها، مما يمنع التشويه.
### هل يمكنني إلغاء قفل نسبة العرض إلى الارتفاع لاحقًا إذا لزم الأمر؟
نعم، يمكنك تبديل قفل نسبة العرض إلى الارتفاع برمجيًا باستخدام Aspose.Slides لـ Java.
### هل Aspose.Slides for Java مناسب لتطبيقات مستوى المؤسسة؟
نعم، تم تصميم Aspose.Slides for Java للتعامل مع السيناريوهات المعقدة في تطبيقات المؤسسات بشكل فعال.
### أين يمكنني الحصول على الدعم إذا واجهت مشاكل مع Aspose.Slides لـ Java؟
يمكنك طلب الدعم من مجتمع Aspose.Slides [هنا](https://forum.aspose.com/c/slides/11).
### كيف يمكنني تجربة Aspose.Slides لـ Java قبل الشراء؟
يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}