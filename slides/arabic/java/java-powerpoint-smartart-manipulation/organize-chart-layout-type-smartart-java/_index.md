---
"description": "أتقن أنواع تخطيطات المخططات التنظيمية في SmartArt باستخدام Java مع Aspose.Slides، مما يعزز الصور المرئية للعرض التقديمي بسهولة."
"linktitle": "تنظيم نوع تخطيط الرسم البياني في SmartArt باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تنظيم نوع تخطيط الرسم البياني في SmartArt باستخدام Java"
"url": "/ar/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تنظيم نوع تخطيط الرسم البياني في SmartArt باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، سنشرح عملية تنظيم تخطيط المخططات في SmartArt باستخدام Java، مع التركيز بشكل خاص على مكتبة Aspose.Slides. يُحسّن SmartArt في العروض التقديمية من المظهر المرئي ووضوح البيانات بشكل كبير، مما يجعل إتقان التعامل معه أمرًا ضروريًا.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2. تم تنزيل مكتبة Aspose.Slides وإعدادها. إذا لم تقم بذلك، نزّلها من [هنا](https://releases.aspose.com/slides/java/).
3. فهم أساسيات برمجة جافا.

## استيراد الحزم
أولاً، قم باستيراد الحزم اللازمة:
```java
import com.aspose.slides.*;
```
دعونا نقسم المثال المقدم إلى خطوات متعددة:
## الخطوة 1: تهيئة كائن العرض التقديمي
```java
Presentation presentation = new Presentation();
```
إنشاء كائن عرض تقديمي جديد.
## الخطوة 2: إضافة SmartArt إلى الشريحة
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
قم بإضافة SmartArt إلى الشريحة المطلوبة بالأبعاد ونوع التخطيط المحددين.
## الخطوة 3: تعيين تخطيط المخطط التنظيمي
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
حدّد نوع تخطيط مخطط التنظيم. في هذا المثال، نستخدم تخطيط "التعليق الأيسر".
## الخطوة 4: حفظ العرض التقديمي
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
احفظ العرض التقديمي باستخدام تخطيط المخطط المنظم.

## خاتمة
إن إتقان تنظيم أنواع تخطيطات المخططات في SmartArt باستخدام Java يُمكّنك من إنشاء عروض تقديمية جذابة بصريًا بسهولة. مع Aspose.Slides، تصبح العملية مبسطة وفعالة، مما يتيح لك التركيز على صياغة محتوى مؤثر.
## الأسئلة الشائعة
### هل Aspose.Slides متوافق مع بيئات تطوير Java المختلفة؟
نعم، Aspose.Slides متوافق مع بيئات تطوير Java المختلفة، مما يضمن المرونة للمطورين.
### هل يمكنني تخصيص مظهر عناصر SmartArt باستخدام Aspose.Slides؟
بالتأكيد، يوفر Aspose.Slides خيارات تخصيص واسعة لعناصر SmartArt، مما يتيح لك تخصيصها وفقًا لمتطلباتك المحددة.
### هل يوفر Aspose.Slides توثيقًا شاملاً للمطورين؟
نعم، يمكن للمطورين الرجوع إلى الوثائق التفصيلية التي يوفرها Aspose.Slides لـ Java، والتي تقدم رؤى حول وظائفه واستخداماته.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides؟
نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Slides لاستكشاف ميزاتها قبل اتخاذ قرار الشراء.
### أين يمكنني الحصول على الدعم للاستفسارات المتعلقة بـ Aspose.Slides؟
لأي مساعدة أو استفسارات بخصوص Aspose.Slides، يمكنك زيارة منتدى الدعم [هنا](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}