---
"description": "تعرف على كيفية إنشاء تكبير/تصغير ملخص في PowerPoint باستخدام Aspose.Slides لـ Java من خلال هذا البرنامج التعليمي الشامل خطوة بخطوة."
"linktitle": "إنشاء ملخص التكبير في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إنشاء ملخص التكبير في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-thumbnail-creation/create-summary-zoom-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء ملخص التكبير في PowerPoint

## مقدمة
مرحبًا بكم في برنامجنا التعليمي الشامل حول إنشاء تكبير/تصغير موجز في PowerPoint باستخدام Aspose.Slides لجافا. إذا كنت ترغب في إضافة عنصر ديناميكي وتفاعلي إلى عروضك التقديمية، فإن ميزة "تكبير/تصغير الموجز" ميزة رائعة. فهي تتيح لك إنشاء شريحة واحدة تُمكّنك من تكبير/تصغير أقسام مختلفة من عرضك التقديمي، مما يوفر تجربة تفاعلية وسهلة التصفح لجمهورك.
في هذا الدليل المُفصّل، سنشرح لك العملية بأكملها، بدءًا من إعداد بيئة التطوير وصولًا إلى إنشاء وتخصيص إطار تكبير مُلخص. سواءً كنتَ مطور جافا مُحنّكًا أو مبتدئًا، ستجد هذا الدليل سهل المتابعة وغنيًا بالمعلومات القيّمة.
## المتطلبات الأساسية
قبل الغوص في الكود، دعنا نتأكد من أن لديك كل ما تحتاجه للبدء:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من [موقع أوراكل](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides لـ Java: قم بتنزيل المكتبة من [صفحة إصدارات Aspose](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم بيئة التطوير المتكاملة مثل IntelliJ IDEA، أو Eclipse، أو NetBeans للحصول على تجربة تطوير أكثر سلاسة.
4. المعرفة الأساسية بلغة جافا: ستساعدك المعرفة بمفاهيم برمجة جافا على فهم الخطوات الواردة في هذا الدليل وتنفيذها.
## استيراد الحزم
قبل أن نبدأ، عليك استيراد الحزم اللازمة. تأكد من تضمين Aspose.Slides لجافا في تبعيات مشروعك.
```java
import com.aspose.slides.*;

import java.awt.*;
```
## الخطوة 1: إعداد مشروعك
أولاً، تأكد من إعداد بيئة التطوير لديك بشكل صحيح. اتبع الخطوات التالية لتكوين مشروعك:
### إنشاء مشروع جديد
1. افتح IDE الخاص بك.
2. إنشاء مشروع Java جديد.
3. أضف مكتبة Aspose.Slides لجافا إلى مسار بناء مشروعك. يمكنك تنزيل ملف JAR من [صفحة إصدارات Aspose](https://releases.aspose.com/slides/java/) وأدرجها في مشروعك.
### تهيئة العرض التقديمي
بعد ذلك، قم بإنشاء كائن عرض تقديمي جديد حيث ستضيف الشرائح والأقسام الخاصة بك.
```java
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة الشرائح والأقسام
في هذه الخطوة، سنضيف شرائح إلى العرض التقديمي ونُنظّمها في أقسام. هذا التنظيم أساسي لإنشاء عرض تقديمي موجز.
### إضافة شريحة وقسم جديدين
1. إضافة شريحة فارغة: إضافة شريحة جديدة إلى العرض التقديمي.
2. تخصيص خلفية الشريحة: قم بتعيين لون تعبئة ثابت لخلفية الشريحة.
3. إضافة قسم: قم بتجميع الشريحة في قسم.
إليك الكود لتحقيق ذلك:
```java
// أضف الشريحة الأولى
ISlide slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
slide.getBackground().setType(BackgroundType.OwnBackground);
// أضف القسم الأول
pres.getSections().addSection("Section 1", slide);
```
### كرر ذلك للأقسام الإضافية
كرر العملية لإضافة المزيد من الشرائح والأقسام:
```java
// أضف الشريحة الثانية والقسم الثاني
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 2", slide);
// أضف الشريحة الثالثة والقسم الثالث
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 3", slide);
// أضف الشريحة والقسم الرابع
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 4", slide);
```
## الخطوة 3: إنشاء إطار التكبير/التصغير الموجز
الآن، سننشئ إطارًا لتكبير/تصغير الملخص على الشريحة الأولى. سيعمل هذا الإطار كعنصر تفاعلي يسمح للمستخدمين بتكبير/تصغير أقسام مختلفة.

1. حدد الشريحة الأولى: استرد الشريحة الأولى التي ستضيف إليها إطار التكبير/التصغير الموجز.
2. أضف إطار التكبير/التصغير الموجز: استخدم `addSummaryZoomFrame` طريقة إضافة الإطار.
```java
ISummaryZoomFrame summaryZoomFrame = pres.getSlides().get_Item(0).getShapes().addSummaryZoomFrame(150, 50, 300, 200);
```
## الخطوة 4: حفظ العرض التقديمي
أخيرًا، احفظ العرض التقديمي في المكان الذي تريده. تضمن هذه الخطوة تسجيل جميع تغييراتك في ملف.
### حفظ الملف
1. تحديد مسار الإخراج: حدد المسار الذي سيتم حفظ العرض التقديمي فيه.
2. حفظ العرض التقديمي: استخدم `save` طريقة حفظ الملف بصيغة PPTX.
```java
String resultPath = "Your Output Directory" + "SummaryZoomPresentation.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
### التخلص من كائن العرض التقديمي
تخلص من كائن العرض لتحرير أي موارد يستخدمها:
```java
if (pres != null) pres.dispose();
```
## خاتمة
تهانينا! لقد نجحت في إنشاء تكبير/تصغير موجز في PowerPoint باستخدام Aspose.Slides لجافا. تُحسّن هذه الميزة عروضك التقديمية بجعلها أكثر تفاعلية وجاذبية. باتباع هذا الدليل، ستمتلك الآن المهارات اللازمة لتطبيق هذه الميزة في مشاريعك الخاصة. تذكر استكشاف [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/) لمزيد من الميزات المتقدمة وخيارات التخصيص.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint وتعديلها والتلاعب بها برمجيًا باستخدام Java.
### هل يمكنني استخدام Aspose.Slides لـ Java لإنشاء أنواع أخرى من المحتوى في PowerPoint؟
نعم، يدعم Aspose.Slides for Java مجموعة واسعة من الميزات، بما في ذلك إنشاء الشرائح وإضافة الأشكال والمخططات والجداول وغير ذلك الكثير.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لنظام Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides for Java من [موقع إلكتروني](https://releases.aspose.com/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
يمكنك الحصول على ترخيص مؤقت من [صفحة شراء Aspose](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على المزيد من الأمثلة والدعم لـ Aspose.Slides لـ Java؟
يمكنك العثور على المزيد من الأمثلة وطلب الدعم على [منتدى دعم Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}