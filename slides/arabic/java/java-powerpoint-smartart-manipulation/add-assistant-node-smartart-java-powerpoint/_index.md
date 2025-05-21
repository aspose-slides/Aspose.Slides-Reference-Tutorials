---
"description": "تعلّم كيفية إضافة عقدة مساعدة إلى SmartArt في عروض PowerPoint التقديمية بلغة Java باستخدام Aspose.Slides. حسّن مهاراتك في تحرير PowerPoint."
"linktitle": "إضافة عقدة مساعد إلى SmartArt في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة عقدة مساعد إلى SmartArt في Java PowerPoint"
"url": "/ar/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة عقدة مساعد إلى SmartArt في Java PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة عقدة مساعدة إلى SmartArt في عروض PowerPoint بتنسيق Java باستخدام Aspose.Slides.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت جافا على نظامك. يمكنك تنزيل أحدث إصدار من JDK وتثبيته من [هنا](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides for Java: قم بتنزيل وتثبيت مكتبة Aspose.Slides for Java من [هذا الرابط](https://releases.aspose.com/slides/java/).

## استيراد الحزم
للبدء، قم باستيراد الحزم الضرورية في كود Java الخاص بك:
```java
import com.aspose.slides.*;
```
## الخطوة 1: إعداد العرض التقديمي
ابدأ بإنشاء مثيل للعرض التقديمي باستخدام المسار إلى ملف PowerPoint الخاص بك:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## الخطوة 2: التنقل عبر الأشكال
انتقل عبر كل الأشكال الموجودة داخل الشريحة الأولى من العرض التقديمي:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## الخطوة 3: التحقق من أشكال SmartArt
تحقق مما إذا كان الشكل من نوع SmartArt:
```java
if (shape instanceof ISmartArt)
```
## الخطوة 4: التنقل عبر عقد SmartArt
الانتقال عبر جميع عقد شكل SmartArt:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## الخطوة 5: التحقق من وجود عقدة المساعد
التحقق مما إذا كانت العقدة هي عقدة مساعدة:
```java
if (node.isAssistant())
```
## الخطوة 6: تعيين عقدة المساعد إلى الوضع العادي
إذا كانت العقدة عبارة عن عقدة مساعدة، فقم بتعيينها إلى عقدة عادية:
```java
node.setAssistant(false);
```
## الخطوة 7: حفظ العرض التقديمي
حفظ العرض التقديمي المعدل:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## خاتمة
تهانينا! لقد نجحت في إضافة عقدة مساعدة إلى SmartArt في عرض PowerPoint التقديمي باستخدام Aspose.Slides.

## الأسئلة الشائعة
### هل يمكنني إضافة عقد مساعدة متعددة إلى SmartArt في العرض التقديمي؟
نعم، يمكنك إضافة عقد مساعدة متعددة عن طريق تكرار العملية لكل عقدة.
### هل يعمل هذا البرنامج التعليمي لكل من PowerPoint وقوالب PowerPoint؟
نعم، يمكنك تطبيق هذا البرنامج التعليمي على كل من عروض PowerPoint والقوالب.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides إصدارات PowerPoint من 97 إلى 2003 إلى الإصدار الأحدث.
### هل يمكنني تخصيص مظهر العقدة المساعدة؟
نعم، يمكنك تخصيص المظهر باستخدام الخصائص والطرق المختلفة التي يوفرها Aspose.Slides.
### هل هناك حد لعدد العقد في SmartArt؟
يدعم SmartArt في PowerPoint عددًا كبيرًا من العقد، ولكن يوصى بالحفاظ عليه بشكل معقول لتحسين إمكانية القراءة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}