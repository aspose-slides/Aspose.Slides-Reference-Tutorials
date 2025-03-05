---
title: قفل نسبة العرض إلى الارتفاع في PowerPoint باستخدام Java
linktitle: قفل نسبة العرض إلى الارتفاع في PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية قفل نسبة العرض إلى الارتفاع في عروض PowerPoint التقديمية باستخدام Java مع Aspose.Slides. مثالي لمطوري Java الذين يريدون التحكم الدقيق في تصميم الشرائح.
type: docs
weight: 16
url: /ar/java/java-powerpoint-table-manipulation/lock-aspect-ratio-powerpoint-java/
---
## مقدمة
في مجال تطوير Java، يمكن أن يؤدي التعامل مع عروض PowerPoint التقديمية برمجياً إلى تبسيط سير العمل وتحسين الإنتاجية بشكل كبير. يقدم Aspose.Slides for Java مجموعة أدوات قوية لمطوري Java لأتمتة المهام مثل تعديل الشرائح وإضافة المحتوى وتطبيق التنسيق مباشرةً من تعليمات Java البرمجية. يركز هذا البرنامج التعليمي على جانب أساسي لإدارة عروض PowerPoint التقديمية: تأمين نسب العرض إلى الارتفاع.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على جهازك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- إعداد بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية من Aspose.Slides لـ Java:
```java
import com.aspose.slides.ITable;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
## الخطوة 1: قم بتحميل العرض التقديمي
أولاً، قم بتحميل عرض PowerPoint التقديمي حيث تريد قفل نسبة العرض إلى الارتفاع للكائن.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```
## الخطوة 2: الوصول إلى نسبة العرض إلى الارتفاع للكائن والقفل
بعد ذلك، قم بالوصول إلى الشكل (الكائن) الموجود داخل الشريحة وقم بتأمين نسبة العرض إلى الارتفاع الخاصة به.
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
## الخطوة 3: احفظ العرض التقديمي المعدل
بعد إجراء التغييرات، قم بحفظ العرض التقديمي المعدل.
```java
pres.save(dataDir + "pres-out.pptx", SaveFormat.Pptx);
```

## خاتمة
في الختام، فإن الاستفادة من Aspose.Slides for Java تمكن مطوري Java من أتمتة مهام PowerPoint بشكل فعال. يضمن قفل نسب العرض إلى الارتفاع بقاء سلامة تصميم العرض التقديمي الخاص بك سليمة، مما يوفر الاتساق عبر الأجهزة وأحجام الشاشات المختلفة.
## الأسئلة الشائعة
### لماذا يعتبر تأمين نسبة العرض إلى الارتفاع أمرًا مهمًا في العروض التقديمية؟
يضمن قفل نسبة العرض إلى الارتفاع أن تحافظ الصور والأشكال على نسبها عند تغيير حجمها، مما يمنع التشوه.
### هل يمكنني فتح نسبة العرض إلى الارتفاع لاحقًا إذا لزم الأمر؟
نعم، يمكنك تبديل قفل نسبة العرض إلى الارتفاع برمجيًا باستخدام Aspose.Slides لـ Java.
### هل Aspose.Slides for Java مناسب للتطبيقات على مستوى المؤسسة؟
نعم، تم تصميم Aspose.Slides for Java للتعامل مع السيناريوهات المعقدة في تطبيقات المؤسسات بفعالية.
### أين يمكنني الحصول على الدعم إذا واجهت مشاكل مع Aspose.Slides لـ Java؟
 يمكنك طلب الدعم من مجتمع Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11).
### كيف يمكنني تجربة Aspose.Slides لـ Java قبل الشراء؟
 يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).