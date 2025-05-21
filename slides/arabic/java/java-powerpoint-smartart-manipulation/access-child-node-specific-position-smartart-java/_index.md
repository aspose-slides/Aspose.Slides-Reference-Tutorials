---
"description": "تعلم كيفية التعامل مع SmartArt في Aspose.Slides لجافا مع هذا الدليل المفصل. يتضمن تعليمات خطوة بخطوة، وأمثلة، وأفضل الممارسات."
"linktitle": "الوصول إلى العقدة الفرعية في موضع محدد في SmartArt"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "الوصول إلى العقدة الفرعية في موضع محدد في SmartArt"
"url": "/ar/java/java-powerpoint-smartart-manipulation/access-child-node-specific-position-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# الوصول إلى العقدة الفرعية في موضع محدد في SmartArt

## مقدمة
هل تتطلع إلى الارتقاء بعروضك التقديمية إلى مستوى جديد باستخدام رسومات SmartArt المتطورة؟ لا داعي للبحث أكثر! يوفر Aspose.Slides لجافا حزمة أدوات فعّالة لإنشاء شرائح العروض التقديمية ومعالجتها وإدارتها، بما في ذلك إمكانية العمل مع كائنات SmartArt. في هذا البرنامج التعليمي الشامل، سنشرح لك كيفية الوصول إلى عقدة فرعية في موضع محدد داخل رسومات SmartArt ومعالجتها، باستخدام مكتبة Aspose.Slides لجافا.

## المتطلبات الأساسية
قبل أن نبدأ، هناك بعض المتطلبات الأساسية التي يجب أن تتوفر لديك:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من [صفحة Oracle JDK](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides لمكتبة Java: قم بتنزيل مكتبة Aspose.Slides لمكتبة Java من [صفحة التحميل](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم أي بيئة تطوير متكاملة Java من اختيارك. IntelliJ IDEA، أو Eclipse، أو NetBeans خيارات شائعة.
4. ترخيص Aspose: على الرغم من أنه يمكنك البدء بإصدار تجريبي مجاني، للحصول على الإمكانيات الكاملة، فكر في الحصول على [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) أو شراء ترخيص كامل من [هنا](https://purchase.aspose.com/buy).
## استيراد الحزم
أولاً، لنستورد الحزم اللازمة لمشروع جافا. هذا ضروري لاستخدام وظائف Aspose.Slides.
```java
import com.aspose.slides.*;
import java.io.File;
```
الآن، دعونا نقسم المثال إلى خطوات مفصلة:
## الخطوة 1: إنشاء الدليل
الخطوة الأولى هي إعداد المجلد الذي ستُخزَّن فيه ملفات العرض التقديمي. هذا يضمن وجود مساحة مخصصة في تطبيقك لإدارة الملفات.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
هنا، نتحقق من وجود الدليل، وإن لم يكن، نقوم بإنشائه. هذه ممارسة شائعة لتجنب أخطاء معالجة الملفات.
## الخطوة 2: إنشاء العرض التقديمي

بعد ذلك، سننشئ نموذج عرض تقديمي جديد. هذا هو أساس مشروعنا، حيث سنضيف جميع الشرائح والأشكال.
```java
// إنشاء العرض التقديمي
Presentation pres = new Presentation();
```
يقوم هذا السطر من التعليمات البرمجية بتهيئة كائن عرض تقديمي جديد باستخدام Aspose.Slides.
## الخطوة 3: الوصول إلى الشريحة الأولى

الآن، علينا الوصول إلى الشريحة الأولى من العرض التقديمي. الشرائح هي المكان الذي يُعرض فيه محتوى العرض التقديمي.
```java
// الوصول إلى الشريحة الأولى
ISlide slide = pres.getSlides().get_Item(0);
```
يتيح لك هذا الوصول إلى الشريحة الأولى في العرض التقديمي، مما يسمح لنا بإضافة محتوى إليها.
## الخطوة 4: إضافة شكل SmartArt
### إضافة شكل SmartArt
بعد ذلك، سنضيف شكل SmartArt إلى الشريحة. يُعد SmartArt وسيلة رائعة لتمثيل المعلومات بصريًا.
```java
// إضافة شكل SmartArt في الشريحة الأولى
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
هنا نقوم بتحديد موضع وأبعاد شكل SmartArt واختيار نوع التخطيط، في هذه الحالة، `StackedList`.
## الخطوة 5: الوصول إلى عقدة SmartArt

الآن، نصل إلى عقدة محددة ضمن رسم SmartArt. العقد هي عناصر فردية ضمن شكل SmartArt.
```java
// الوصول إلى عقدة SmartArt في الفهرس 0
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
يؤدي هذا إلى استرداد العقدة الأولى في رسم SmartArt، والتي سنقوم بمعالجتها لاحقًا.
## الخطوة 6: الوصول إلى العقدة الفرعية

في هذه الخطوة، نقوم بالوصول إلى عقدة فرعية في موضع محدد داخل العقدة الأصلية.
```java
// الوصول إلى العقدة الفرعية في الموضع 1 في العقدة الأصلية
int position = 1;
SmartArtNode chNode = (SmartArtNode) node.getChildNodes().get_Item(position);
```
يؤدي هذا إلى استرداد العقدة الفرعية في الموضع المحدد، مما يسمح لنا بالتلاعب بخصائصها.
## الخطوة 7: طباعة معلمات العقدة الفرعية

أخيرًا، دعنا نطبع معلمات العقدة الفرعية للتحقق من معالجاتنا.
```java
// طباعة معلمات عقدة SmartArt الفرعية
String outString = String.format("j = {0},.Text{1},  Level = {2}, Position = {3}", position, chNode.getTextFrame().getText(), chNode.getLevel(), chNode.getPosition());
System.out.println(outString);
```
يقوم هذا السطر من التعليمات البرمجية بتنسيق وطباعة تفاصيل العقدة الفرعية، مثل النص والمستوى والموضع.
## خاتمة
تهانينا! لقد نجحت في الوصول إلى عقدة فرعية ضمن رسم SmartArt ومعالجتها باستخدام Aspose.Slides لجافا. شرح لك هذا الدليل خطوات إعداد مشروعك، وإضافة SmartArt، ومعالجة عقده خطوة بخطوة. بفضل هذه المعرفة، يمكنك الآن إنشاء عروض تقديمية أكثر ديناميكية وجاذبية بصريًا.
لمزيد من القراءة واستكشاف المزيد من الميزات المتقدمة، راجع [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/)إذا كان لديك أي أسئلة أو تحتاج إلى دعم، [منتدى مجتمع Aspose](https://forum.aspose.com/c/slides/11) يعد مكانًا رائعًا لطلب المساعدة.
## الأسئلة الشائعة
### كيف يمكنني تثبيت Aspose.Slides لـ Java؟
يمكنك تنزيله من [صفحة التحميل](https://releases.aspose.com/slides/java/) واتبع تعليمات التثبيت المقدمة.
### هل يمكنني تجربة Aspose.Slides لـJava قبل الشراء؟
نعم يمكنك الحصول على [نسخة تجريبية مجانية](https://releases.aspose.com/) أو أ [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) لاختبار الميزات.
### ما هي أنواع تخطيطات SmartArt المتوفرة في Aspose.Slides؟
يدعم Aspose.Slides تخطيطات SmartArt متنوعة، مثل القائمة، والعملية، والدورة، والتسلسل الهرمي، وغيرها. يمكنك الاطلاع على معلومات مفصلة في [التوثيق](https://reference.aspose.com/slides/java/).
### كيف أحصل على الدعم لـ Aspose.Slides لـ Java؟
يمكنك الحصول على الدعم من [منتدى مجتمع Aspose](https://forum.aspose.com/c/slides/11) أو الرجوع إلى واسعة النطاق [التوثيق](https://reference.aspose.com/slides/java/).
### هل يمكنني شراء ترخيص كامل لـ Aspose.Slides لـ Java؟
نعم، يمكنك شراء ترخيص كامل من [صفحة الشراء](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}