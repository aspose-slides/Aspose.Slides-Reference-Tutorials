---
title: تنظيم نوع تخطيط المخطط في SmartArt باستخدام Java
linktitle: تنظيم نوع تخطيط المخطط في SmartArt باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: أتقن تنظيم أنواع تخطيطات المخططات في SmartArt باستخدام Java مع Aspose.Slides، مما يعزز مرئيات العرض التقديمي دون عناء.
type: docs
weight: 13
url: /ar/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---
## مقدمة
في هذا البرنامج التعليمي، سنتعرف على عملية تنظيم نوع تخطيط المخطط في SmartArt باستخدام Java، مع الاستفادة بشكل خاص من مكتبة Aspose.Slides. يمكن لـ SmartArt في العروض التقديمية أن يعزز المظهر المرئي لبياناتك ووضوحها بشكل كبير، مما يجعل من الضروري إتقان التعامل معها.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2.  تم تنزيل وإعداد مكتبة Aspose.Slides. إذا لم تقم بذلك بالفعل، قم بتنزيله من[هنا](https://releases.aspose.com/slides/java/).
3. الفهم الأساسي لبرمجة جافا.

## حزم الاستيراد
أولاً، قم باستيراد الحزم اللازمة:
```java
import com.aspose.slides.*;
```
دعنا نقسم المثال المقدم إلى خطوات متعددة:
## الخطوة 1: تهيئة كائن العرض التقديمي
```java
Presentation presentation = new Presentation();
```
إنشاء كائن عرض تقديمي جديد.
## الخطوة 2: إضافة SmartArt إلى الشريحة
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
أضف SmartArt إلى الشريحة المطلوبة بأبعاد ونوع تخطيط محددين.
## الخطوة 3: تعيين تخطيط المخطط الهيكلي
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
قم بتعيين نوع تخطيط المخطط الهيكلي. في هذا المثال، نحن نستخدم التخطيط المعلق لليسار.
## الخطوة 4: حفظ العرض التقديمي
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
احفظ العرض التقديمي باستخدام تخطيط المخطط المنظم.

## خاتمة
إن إتقان تنظيم أنواع تخطيطات المخططات في SmartArt باستخدام Java يمكّنك من إنشاء عروض تقديمية جذابة بصريًا بسهولة. مع Aspose.Slides، تصبح العملية مبسطة وفعالة، مما يسمح لك بالتركيز على صياغة محتوى مؤثر.
## الأسئلة الشائعة
### هل Aspose.Slides متوافق مع بيئات تطوير Java المختلفة؟
نعم، Aspose.Slides متوافق مع بيئات تطوير Java المختلفة، مما يضمن المرونة للمطورين.
### هل يمكنني تخصيص مظهر عناصر SmartArt باستخدام Aspose.Slides؟
بالتأكيد، يوفر Aspose.Slides خيارات تخصيص واسعة النطاق لعناصر SmartArt، مما يتيح لك تخصيصها وفقًا لمتطلباتك المحددة.
### هل يقدم Aspose.Slides وثائق شاملة للمطورين؟
نعم، يمكن للمطورين الرجوع إلى الوثائق التفصيلية المقدمة من Aspose.Slides لـ Java، والتي تقدم نظرة ثاقبة حول وظائفها واستخدامها.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides؟
نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Slides لاستكشاف ميزاته قبل اتخاذ قرار الشراء.
### أين يمكنني طلب الدعم للاستفسارات المتعلقة بـ Aspose.Slides؟
 للحصول على أي مساعدة أو استفسارات بخصوص Aspose.Slides، يمكنك زيارة منتدى الدعم[هنا](https://forum.aspose.com/c/slides/11).