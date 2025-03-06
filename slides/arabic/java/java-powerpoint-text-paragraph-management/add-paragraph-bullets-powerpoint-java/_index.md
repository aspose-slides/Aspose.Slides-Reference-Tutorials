---
title: إضافة تعداد نقطي للفقرة في PowerPoint باستخدام Java
linktitle: إضافة تعداد نقطي للفقرة في PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة تعداد نقطي للفقرات في شرائح PowerPoint باستخدام Aspose.Slides لـ Java. يرشدك هذا البرنامج التعليمي خطوة بخطوة مع أمثلة التعليمات البرمجية.
weight: 15
url: /ar/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
تؤدي إضافة تعداد نقطي للفقرة إلى تحسين إمكانية قراءة عروض PowerPoint التقديمية وبنيتها. يوفر Aspose.Slides for Java أدوات قوية للتعامل مع العروض التقديمية برمجيًا، بما في ذلك القدرة على تنسيق النص باستخدام أنماط تعداد نقطي مختلفة. في هذا البرنامج التعليمي، ستتعلم كيفية دمج النقاط النقطية في شرائح PowerPoint باستخدام كود Java، مع الاستفادة من Aspose.Slides.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- JDK (Java Development Kit) مثبت على نظامك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## حزم الاستيراد
للبدء، قم باستيراد حزم Aspose.Slides الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## الخطوة 1: قم بإعداد مشروعك
أولاً، قم بإنشاء مشروع Java جديد وأضف مكتبة Aspose.Slides for Java إلى مسار بناء مشروعك.
## الخطوة 2: تهيئة العرض التقديمي
تهيئة كائن العرض التقديمي (`Presentation`) لبدء العمل مع الشرائح.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل العرض التقديمي
Presentation pres = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة وإطار النص
الوصول إلى الشريحة (`ISlide`وإطار النص الخاص به (`ITextFrame`) حيث تريد إضافة التعداد النقطي.
```java
// الوصول إلى الشريحة الأولى
ISlide slide = pres.getSlides().get_Item(0);
// إضافة الشكل التلقائي والوصول إليه
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// الوصول إلى إطار النص للشكل التلقائي الذي تم إنشاؤه
ITextFrame txtFrm = aShp.getTextFrame();
```
## الخطوة 4: إنشاء وتنسيق الفقرات باستخدام التعداد النقطي
إنشاء فقرات (`Paragraph`) وتعيين أنماط التعداد النقطي والمسافات البادئة والنص.
```java
// إنشاء فقرة
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// إنشاء فقرة أخرى
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## الخطوة 5: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل في ملف PowerPoint (`PPTX`).
```java
// كتابة العرض التقديمي كملف PPTX
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## الخطوة 6: تنظيف الموارد
تخلص من كائن العرض التقديمي لتحرير الموارد.
```java
// التخلص من كائن العرض التقديمي
if (pres != null) {
    pres.dispose();
}
```

## خاتمة
تعد إضافة تعداد نقطي للفقرات في PowerPoint باستخدام Aspose.Slides لـ Java أمرًا مباشرًا باستخدام أمثلة التعليمات البرمجية المتوفرة. قم بتخصيص أنماط التعداد النقطي وتنسيقه ليناسب احتياجات العرض التقديمي الخاص بك بسلاسة.

## الأسئلة الشائعة
### هل يمكنني تخصيص ألوان التعداد النقطي؟
نعم، يمكنك تعيين ألوان مخصصة للتعداد النقطي باستخدام Aspose.Slides API.
### كيف أقوم بإضافة تعداد نقطي متداخل؟
يتضمن تداخل التعداد النقطي إضافة فقرات داخل الفقرات، وضبط المسافة البادئة وفقًا لذلك.
### هل يمكنني إنشاء أنماط نقطية مختلفة لشرائح مختلفة؟
نعم، يمكنك تطبيق أنماط نقطية فريدة على شرائح مختلفة برمجيًا.
### هل Aspose.Slides متوافق مع Java 11؟
نعم، يدعم Aspose.Slides الإصدار 11 من Java والإصدارات الأحدث.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
 يزور[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/) للحصول على أدلة وأمثلة شاملة.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
