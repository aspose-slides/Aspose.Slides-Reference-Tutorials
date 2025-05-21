---
"description": "تعلّم كيفية إضافة فقرات نقطية في شرائح PowerPoint باستخدام Aspose.Slides لجافا. يرشدك هذا البرنامج التعليمي خطوة بخطوة مع أمثلة برمجية."
"linktitle": "إضافة فقرات نقطية في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة فقرات نقطية في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة فقرات نقطية في PowerPoint باستخدام Java

## مقدمة
تُحسّن إضافة نقاط الفقرات سهولة قراءة عروض PowerPoint التقديمية وبنيتها. يوفر Aspose.Slides لجافا أدوات فعّالة لإدارة العروض التقديمية برمجيًا، بما في ذلك إمكانية تنسيق النص بأنماط نقاط متنوعة. في هذا البرنامج التعليمي، ستتعلم كيفية دمج النقاط في شرائح PowerPoint باستخدام شفرة جافا، مستفيدًا من Aspose.Slides.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت JDK (Java Development Kit) على نظامك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## استيراد الحزم
للبدء، قم باستيراد حزم Aspose.Slides الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## الخطوة 1: إعداد مشروعك
أولاً، قم بإنشاء مشروع Java جديد وأضف مكتبة Aspose.Slides for Java إلى مسار بناء مشروعك.
## الخطوة 2: تهيئة العرض التقديمي
تهيئة كائن العرض التقديمي (`Presentation`) لبدء العمل مع الشرائح.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل للعرض التقديمي
Presentation pres = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة وإطار النص
الوصول إلى الشريحة (`ISlide`) وإطار النص الخاص به (`ITextFrame`) حيث تريد إضافة النقاط.
```java
// الوصول إلى الشريحة الأولى
ISlide slide = pres.getSlides().get_Item(0);
// إضافة الشكل التلقائي والوصول إليه
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// الوصول إلى إطار النص للشكل التلقائي الذي تم إنشاؤه
ITextFrame txtFrm = aShp.getTextFrame();
```
## الخطوة 4: إنشاء فقرات وتنسيقها باستخدام النقاط
إنشاء فقرات (`Paragraph`) وتعيين أنماط النقاط والمسافة البادئة والنص.
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
## الخطوة 5: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل في ملف PowerPoint (`PPTX`).
```java
// كتابة العرض التقديمي كملف PPTX
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## الخطوة 6: تنظيف الموارد
تخلص من كائن العرض لتحرير الموارد.
```java
// التخلص من كائن العرض التقديمي
if (pres != null) {
    pres.dispose();
}
```

## خاتمة
إضافة نقاط فقرات في PowerPoint باستخدام Aspose.Slides لـ Java أمر سهل للغاية مع أمثلة التعليمات البرمجية المرفقة. خصّص أنماط النقاط وتنسيقها بما يتناسب مع احتياجات عرضك التقديمي بسلاسة.

## الأسئلة الشائعة
### هل يمكنني تخصيص ألوان الرصاص؟
نعم، يمكنك تعيين ألوان مخصصة للنقاط باستخدام واجهة برمجة التطبيقات Aspose.Slides.
### كيف أضيف نقاطًا متداخلة؟
تتضمن عملية تعشيش النقاط إضافة فقرات داخل فقرات، وضبط المسافة البادئة وفقًا لذلك.
### هل يمكنني إنشاء أنماط نقطية مختلفة لشرائح مختلفة؟
نعم، يمكنك تطبيق أنماط نقطية فريدة على شرائح مختلفة برمجيًا.
### هل Aspose.Slides متوافق مع Java 11؟
نعم، يدعم Aspose.Slides إصدار Java 11 والإصدارات الأحدث.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
يزور [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/) للحصول على أدلة وأمثلة شاملة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}