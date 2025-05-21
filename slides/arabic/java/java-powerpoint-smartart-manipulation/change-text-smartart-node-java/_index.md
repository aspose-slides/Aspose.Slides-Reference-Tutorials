---
"description": "اكتشف كيفية تحديث نص عقدة SmartArt في PowerPoint باستخدام Java مع Aspose.Slides، مما يعزز تخصيص العرض التقديمي."
"linktitle": "تغيير النص على عقدة SmartArt باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تغيير النص على عقدة SmartArt باستخدام Java"
"url": "/ar/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تغيير النص على عقدة SmartArt باستخدام Java

## مقدمة
يُعد SmartArt في PowerPoint ميزة فعّالة لإنشاء مخططات جذابة بصريًا. يوفر Aspose.Slides لـ Java دعمًا شاملاً للتعامل مع عناصر SmartArt برمجيًا. في هذا البرنامج التعليمي، سنرشدك خلال عملية تغيير النص في عقدة SmartArt باستخدام Java.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK) على نظامك.
- تم تنزيل Aspose.Slides لمكتبة Java والإشارة إليها في مشروع Java الخاص بك.
- فهم أساسيات برمجة جافا.

## استيراد الحزم
أولاً، قم باستيراد الحزم اللازمة للوصول إلى وظيفة Aspose.Slides داخل كود Java الخاص بك.
```java
import com.aspose.slides.*;
```
دعونا نقسم المثال إلى خطوات متعددة:
## الخطوة 1: تهيئة كائن العرض التقديمي
```java
Presentation presentation = new Presentation();
```
إنشاء مثيل جديد من `Presentation` صف للعمل على عرض تقديمي باستخدام PowerPoint.
## الخطوة 2: إضافة SmartArt إلى الشريحة
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
أضف SmartArt إلى الشريحة الأولى. في هذا المثال، نستخدم `BasicCycle` تَخطِيط.
## الخطوة 3: الوصول إلى عقدة SmartArt
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
احصل على مرجع إلى العقدة الجذرية الثانية لـ SmartArt.
## الخطوة 4: تعيين النص على العقدة
```java
node.getTextFrame().setText("Second root node");
```
تعيين النص لعقدة SmartArt المحددة.
## الخطوة 5: حفظ العرض التقديمي
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
احفظ العرض التقديمي المعدّل في الموقع المحدد.

## خاتمة
في هذا البرنامج التعليمي، شرحنا كيفية تغيير النص في عقدة SmartArt باستخدام Java وAspose.Slides. بفضل هذه المعرفة، يمكنك التحكم ديناميكيًا بعناصر SmartArt في عروض PowerPoint التقديمية، مما يعزز جاذبيتها البصرية ووضوحها.
## الأسئلة الشائعة
### هل يمكنني تغيير تخطيط SmartArt بعد إضافته إلى الشريحة؟
نعم، يمكنك تغيير التخطيط عن طريق الوصول إلى `SmartArt.setAllNodes(LayoutType)` طريقة.
### هل Aspose.Slides متوافق مع Java 11؟
نعم، Aspose.Slides for Java متوافق مع Java 11 والإصدارات الأحدث.
### هل يمكنني تخصيص مظهر عقد SmartArt برمجيًا؟
بالتأكيد، يمكنك تعديل خصائص مختلفة مثل اللون والحجم والشكل باستخدام واجهة برمجة تطبيقات Aspose.Slides.
### هل يدعم Aspose.Slides أنواعًا أخرى من تخطيطات SmartArt؟
نعم، يدعم Aspose.Slides مجموعة واسعة من تخطيطات SmartArt، مما يسمح لك باختيار التخطيط الذي يناسب احتياجات العرض التقديمي لديك بشكل أفضل.
### أين يمكنني العثور على المزيد من الموارد والدعم لـ Aspose.Slides؟
يمكنك زيارة [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/) للحصول على مراجع مفصلة لواجهة برمجة التطبيقات (API) ودروس تعليمية. بالإضافة إلى ذلك، يمكنك طلب المساعدة من [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) أو فكر في شراء [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) للحصول على الدعم المهني.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}