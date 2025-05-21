---
"description": "تعرف على كيفية تطبيق تأثيرات الظل الخارجي بسهولة في عروض PowerPoint بتنسيق Java باستخدام Aspose.Slides من خلال دليلنا المفصل خطوة بخطوة."
"linktitle": "تطبيق تأثيرات الظل الخارجي في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تطبيق تأثيرات الظل الخارجي في Java PowerPoint"
"url": "/ar/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تطبيق تأثيرات الظل الخارجي في Java PowerPoint

## مقدمة
غالبًا ما يتطلب إنشاء عروض تقديمية جذابة إضافة تأثيرات متنوعة لتعزيز الجاذبية البصرية لشرائحك. ومن هذه التأثيرات الظل الخارجي، الذي يُبرز عناصرك ويضيف عمقًا إلى محتواك. في هذا البرنامج التعليمي، سنشرح عملية تطبيق تأثيرات الظل الخارجي على الأشكال في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا.
## المتطلبات الأساسية
قبل أن نتعمق في الدليل خطوة بخطوة، دعنا نتأكد من أن لديك كل ما تحتاجه:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من [موقع أوراكل](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides لمكتبة Java: قم بتنزيل الإصدار الأحدث من [Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم بيئة التطوير المتكاملة مثل IntelliJ IDEA أو Eclipse لكتابة وتنفيذ كود Java الخاص بك.
4. ترخيص Aspose صالح: يمكنك شراء ترخيص من [أسبوزي](https://purchase.aspose.com/buy) أو احصل على [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) للتقييم.
## استيراد الحزم
أولاً، ستحتاج إلى استيراد الحزم اللازمة لمكتبة Aspose.Slides. هذا يُمهّد الطريق للاستفادة من الوظائف الفعّالة التي تُقدّمها المكتبة.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
دعونا نقسم عملية تطبيق تأثيرات الظل الخارجي إلى خطوات يمكن التحكم فيها:
## الخطوة 1: إعداد دليل المشروع
قبل أن تبدأ في كتابة الكود الخاص بك، تحتاج إلى إعداد دليل المشروع الذي سيتم تخزين ملفات PowerPoint الخاصة بك فيه والوصول إليها.
تأكد من وجود دليل مشروعك. إذا لم يكن موجودًا، فأنشئه باستخدام الكود التالي:
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## الخطوة 2: تهيئة العرض التقديمي
الآن، نحتاج إلى تهيئة العرض التقديمي حيث سنضيف الأشكال والتأثيرات الخاصة بنا.

إنشاء مثيل جديد من `Presentation` الصف لبدء العمل مع ملف PowerPoint جديد.
```java
// إنشاء مثيل لفئة PPTX
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة شريحة وشكل
بعد ذلك، أضف شريحة إلى العرض التقديمي الخاص بك، ثم أضف الشكل الذي ستطبق عليه تأثير الظل.
### الحصول على مرجع للشريحة
استرجاع مرجع للشريحة الأولى في العرض التقديمي.
```java
// احصل على مرجع الشريحة
ISlide sld = pres.getSlides().get_Item(0);
```
### إضافة شكل تلقائي
أضف شكلًا مستطيلًا تلقائيًا إلى الشريحة عند الإحداثيات المحددة.
```java
// إضافة شكل تلقائي من نوع المستطيل
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## الخطوة 4: تخصيص الشكل
أضف نصًا إلى الشكل الخاص بك واضبط إعدادات التعبئة الخاصة به لجعل تأثير الظل أكثر وضوحًا.
### إضافة إطار نص إلى الشكل
إدراج النص في شكل المستطيل.
```java
// إضافة إطار نصي إلى المستطيل
aShp.addTextFrame("Aspose TextBox");
```
### تعطيل تعبئة الشكل
قم بتعطيل تعبئة الشكل للتأكيد على ظل النص.
```java
// تعطيل ملء الشكل في حالة رغبتنا في الحصول على ظل للنص
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## الخطوة 5: تطبيق تأثير الظل الخارجي
الآن حان الوقت لتطبيق تأثير الظل الخارجي على الشكل.
### تمكين تأثير الظل الخارجي
تمكين تأثير الظل الخارجي للشكل.
```java
// أضف ظلًا خارجيًا واضبط جميع المعلمات الضرورية
aShp.getEffectFormat().enableOuterShadowEffect();
```
### تكوين معلمات الظل
قم بتعيين خصائص مختلفة للظل مثل نصف قطر التمويه، والاتجاه، والمسافة، والمحاذاة، واللون.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## الخطوة 6: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي على القرص.
```java
//اكتب العرض التقديمي على القرص
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## الخطوة 7: التخلص من الموارد
تأكد من تحرير الموارد عن طريق التخلص من كائن العرض التقديمي.
```java
// تنظيف الموارد
if (pres != null) pres.dispose();
```
## خاتمة
وها قد انتهيت! لقد نجحت في تطبيق تأثير ظل خارجي على شكل في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. يُحسّن هذا التأثير المظهر المرئي لشرائحك بشكل ملحوظ، مما يُبرز محتواك.
إذا واجهت أي مشاكل أو كنت بحاجة إلى مزيد من المساعدة، فلا تتردد في الاطلاع على [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/) أو قم بزيارة [منتدى الدعم](https://forum.aspose.com/c/slides/11).برمجة سعيدة!
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي مكتبة قوية تسمح لك بإنشاء عروض PowerPoint ومعالجتها وتحويلها في تطبيقات Java.
### كيف يمكنني الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ Java؟
يمكنك تنزيل نسخة تجريبية مجانية من [موقع Aspose](https://releases.aspose.com/).
### هل يمكنني استخدام Aspose.Slides لـ Java مع أي IDE؟
نعم، يمكنك استخدام Aspose.Slides لـ Java مع أي Java IDE مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
يمكنك الحصول على ترخيص مؤقت من [موقع Aspose](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Slides؟
يمكنك العثور على المزيد من الأمثلة والوثائق التفصيلية على [صفحة توثيق Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}