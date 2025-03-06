---
title: الوصول إلى عقدة الطفل في موضع محدد في SmartArt
linktitle: الوصول إلى عقدة الطفل في موضع محدد في SmartArt
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعلم كيفية التعامل مع SmartArt في Aspose.Slides لـ Java باستخدام هذا الدليل التفصيلي. تم تضمين التعليمات والأمثلة وأفضل الممارسات خطوة بخطوة.
weight: 11
url: /ar/java/java-powerpoint-smartart-manipulation/access-child-node-specific-position-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
هل تتطلع إلى الارتقاء بعروضك التقديمية إلى المستوى التالي باستخدام رسومات SmartArt المتطورة؟ لا مزيد من البحث! يقدم Aspose.Slides for Java مجموعة قوية لإنشاء شرائح العرض التقديمي ومعالجتها وإدارتها، بما في ذلك القدرة على العمل مع كائنات SmartArt. في هذا البرنامج التعليمي الشامل، سنرشدك خلال الوصول إلى العقدة الفرعية ومعالجتها في موضع محدد داخل رسم SmartArt، باستخدام مكتبة Aspose.Slides for Java.

## المتطلبات الأساسية
قبل أن نبدأ، هناك بعض المتطلبات الأساسية التي يجب أن تتوفر لديك:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من[صفحة أوراكل JDK](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides لمكتبة Java: قم بتنزيل مكتبة Aspose.Slides لـ Java من[صفحة التحميل](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم أي Java IDE من اختيارك. تعد IntelliJ IDEA أو Eclipse أو NetBeans من الخيارات الشائعة.
4.  ترخيص Aspose: بينما يمكنك البدء بنسخة تجريبية مجانية، للحصول على الإمكانات الكاملة، فكر في الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) أو شراء ترخيص كامل من[هنا](https://purchase.aspose.com/buy).
## حزم الاستيراد
أولاً، لنستورد الحزم الضرورية في مشروع Java الخاص بك. يعد هذا أمرًا بالغ الأهمية لاستخدام وظائف Aspose.Slides.
```java
import com.aspose.slides.*;
import java.io.File;
```
الآن، دعونا نقسم المثال إلى خطوات تفصيلية:
## الخطوة 1: إنشاء الدليل
الخطوة الأولى هي إعداد الدليل حيث سيتم تخزين ملفات العرض التقديمي الخاص بك. وهذا يضمن أن التطبيق الخاص بك لديه مساحة مخصصة لإدارة الملفات.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
نحن هنا نتحقق من وجود الدليل، وإذا لم يكن موجودًا، فإننا نقوم بإنشائه. يعد هذا من أفضل الممارسات الشائعة لتجنب أخطاء معالجة الملفات.
## الخطوة 2: إنشاء مثيل للعرض التقديمي

بعد ذلك، سنقوم بإنشاء مثيل عرض تقديمي جديد. هذا هو العمود الفقري لمشروعنا حيث سيتم إضافة كافة الشرائح والأشكال.
```java
//إنشاء مثيل للعرض التقديمي
Presentation pres = new Presentation();
```
يقوم هذا السطر من التعليمات البرمجية بتهيئة كائن عرض تقديمي جديد باستخدام Aspose.Slides.
## الخطوة 3: الوصول إلى الشريحة الأولى

الآن، نحن بحاجة للوصول إلى الشريحة الأولى في العرض التقديمي. الشرائح هي المكان الذي يتم فيه وضع كافة محتويات العرض التقديمي.
```java
// الوصول إلى الشريحة الأولى
ISlide slide = pres.getSlides().get_Item(0);
```
يؤدي هذا إلى الوصول إلى الشريحة الأولى في العرض التقديمي، مما يسمح لنا بإضافة محتوى إليها.
## الخطوة 4: إضافة شكل SmartArt
### إضافة شكل SmartArt
بعد ذلك، سنقوم بإضافة شكل SmartArt إلى الشريحة. يعد SmartArt طريقة رائعة لتمثيل المعلومات بشكل مرئي.
```java
// إضافة شكل SmartArt في الشريحة الأولى
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
 هنا نحدد موضع وأبعاد شكل SmartArt ونختار نوع التخطيط، في هذه الحالة،`StackedList`.
## الخطوة 5: الوصول إلى عقدة SmartArt

الآن، يمكننا الوصول إلى عقدة محددة داخل رسم SmartArt. العقد هي عناصر فردية ضمن شكل SmartArt.
```java
// الوصول إلى عقدة SmartArt في الفهرس 0
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
يؤدي هذا إلى استرداد العقدة الأولى في رسم SmartArt، والتي سنقوم بمعالجتها بشكل أكبر.
## الخطوة 6: الوصول إلى عقدة الطفل

في هذه الخطوة، نصل إلى عقدة فرعية في موضع محدد داخل العقدة الأصلية.
```java
// الوصول إلى العقدة الفرعية في الموضع 1 في العقدة الأصلية
int position = 1;
SmartArtNode chNode = (SmartArtNode) node.getChildNodes().get_Item(position);
```
يؤدي هذا إلى استرداد العقدة الفرعية في الموضع المحدد، مما يسمح لنا بمعالجة خصائصها.
## الخطوة 7: طباعة معلمات العقدة التابعة

أخيرًا، دعونا نطبع معلمات العقدة الفرعية للتحقق من معالجاتنا.
```java
// طباعة معلمات عقدة SmartArt التابعة
String outString = String.format("j = {0},.Text{1},  Level = {2}, Position = {3}", position, chNode.getTextFrame().getText(), chNode.getLevel(), chNode.getPosition());
System.out.println(outString);
```
يقوم هذا السطر من التعليمات البرمجية بتنسيق وطباعة تفاصيل العقدة الفرعية، مثل النص والمستوى والموضع.
## خاتمة
تهانينا! لقد نجحت في الوصول إلى عقدة فرعية ومعالجتها داخل رسم SmartArt باستخدام Aspose.Slides لـ Java. يرشدك هذا الدليل خلال إعداد مشروعك وإضافة SmartArt ومعالجة العقد الخاصة به خطوة بخطوة. بفضل هذه المعرفة، يمكنك الآن إنشاء عروض تقديمية أكثر ديناميكية وجاذبية من الناحية المرئية.
 لمزيد من القراءة واستكشاف المزيد من الميزات المتقدمة، قم بمراجعة[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/) إذا كانت لديك أي أسئلة أو كنت بحاجة إلى الدعم، فإن[Aspose منتدى المجتمع](https://forum.aspose.com/c/slides/11) مكان عظيم لطلب المساعدة.
## الأسئلة الشائعة
### كيف يمكنني تثبيت Aspose.Slides لجافا؟
 يمكنك تنزيله من[صفحة التحميل](https://releases.aspose.com/slides/java/) واتبع تعليمات التثبيت المقدمة.
### هل يمكنني تجربة Aspose.Slides لـ Java قبل الشراء؟
 نعم يمكنك الحصول على[تجربة مجانية](https://releases.aspose.com/) أو أ[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) لاختبار الميزات.
### ما أنواع تخطيطات SmartArt المتوفرة في Aspose.Slides؟
 يدعم Aspose.Slides العديد من تخطيطات SmartArt مثل القائمة والعملية والدورة والتسلسل الهرمي والمزيد. يمكنك العثور على معلومات مفصلة في[توثيق](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على دعم Aspose.Slides لـ Java؟
 يمكنك الحصول على الدعم من[Aspose منتدى المجتمع](https://forum.aspose.com/c/slides/11) أو الرجوع إلى واسعة النطاق[توثيق](https://reference.aspose.com/slides/java/).
### هل يمكنني شراء ترخيص كامل لـ Aspose.Slides لـ Java؟
 نعم، يمكنك شراء ترخيص كامل من[صفحة الشراء](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
