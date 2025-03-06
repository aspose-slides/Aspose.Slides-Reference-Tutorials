---
title: احصل على إحداثيات موضع الجزء في شرائح Java
linktitle: احصل على إحداثيات موضع الجزء في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعلم كيفية استرداد إحداثيات جزء النص في شرائح Java باستخدام Aspose.Slides for Java API. احصل على تحكم دقيق في موضع النص في عروض PowerPoint التقديمية.
weight: 12
url: /ar/java/additional-utilities/get-position-coordinates-of-portion-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة للحصول على إحداثيات موضع الجزء في شرائح Java

في هذا الدليل الشامل، سنستكشف كيفية استرداد إحداثيات موضع جزء ما داخل شرائح Java باستخدام Aspose.Slides for Java API. ستتعلم كيفية الوصول إلى أجزاء النص في الشريحة ومعالجتها واستخراج إحداثيات X وY الخاصة بها. يتضمن هذا البرنامج التعليمي خطوة بخطوة أمثلة على التعليمات البرمجية المصدر ورؤى قيمة لمساعدتك على إتقان هذه المهمة.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت مجموعة أدوات تطوير Java (JDK).
- تم تنزيل Aspose.Slides لمكتبة Java وتكوينها
- بيئة تطوير متكاملة لجافا (IDE) من اختيارك

والآن لنبدأ بالتنفيذ.

## الخطوة 1: إعداد مشروعك

قبل أن نتمكن من العمل مع Aspose.Slides لـ Java، نحتاج إلى إعداد مشروع Java وتهيئة المكتبة. اتبع هذه الخطوات لتجهيز مشروعك:

1. قم بإنشاء مشروع Java جديد في IDE الخاص بك.
2. أضف مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.
3. قم باستيراد فئات Aspose.Slides الضرورية في بداية ملف Java الخاص بك.

```java
import com.aspose.slides.*;
import java.awt.geom.Point2D;
```

## الخطوة 2: تحميل العرض التقديمي

 في هذه الخطوة، سنقوم بتحميل عرض PowerPoint التقديمي الذي يحتوي على الشريحة التي نريد العمل بها. يستبدل`"Your Document Directory"` بالمسار الفعلي لملف PowerPoint الخاص بك.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
```

## الخطوة 3: الوصول إلى أجزاء النص والإحداثيات

الآن، سوف نصل إلى أجزاء النص الموجودة داخل الشريحة ونستعيد إحداثيات X وY الخاصة بها. سنقوم بالتكرار عبر الفقرات والأجزاء لتحقيق ذلك. إليك مقتطف الشفرة:

```java
try
{
    IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
    ITextFrame textFrame = shape.getTextFrame();
    for (IParagraph paragraph : textFrame.getParagraphs())
    {
        for (IPortion portion : paragraph.getPortions())
        {
            Point2D.Float point = portion.getCoordinates();
            System.out.println("Coordinates X =" + point.getX() + " Coordinates Y =" + point.getY());
        }
    }
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

يسترد هذا الرمز إحداثيات X وY لكل جزء من النص في الشريحة المحددة. ويمكنك تعديله ليناسب متطلباتك المحددة.

## أكمل كود المصدر للحصول على إحداثيات موضع الجزء في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
try
{
	IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
	ITextFrame textFrame = shape.getTextFrame();
	for (IParagraph paragraph : textFrame.getParagraphs())
	{
		for (IPortion portion : paragraph.getPortions())
		{
			Point2D.Float point = portion.getCoordinates();
			System.out.println("Corrdinates X =" + point.getX() + " Corrdinates Y =" + point.getY());
		}
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تناولنا كيفية الحصول على إحداثيات موضع أجزاء النص داخل شرائح Java باستخدام Aspose.Slides for Java API. يمكن أن تكون هذه المعرفة مفيدة بشكل خاص عندما تحتاج إلى تحكم دقيق في موضع عناصر النص في عروض PowerPoint التقديمية.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لجافا؟

 يمكنك تنزيل Aspose.Slides for Java من الموقع باستخدام الرابط التالي:[تنزيل Aspose.Slides للجافا](https://releases.aspose.com/slides/java/)

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟

 تتوفر وثائق Aspose.Slides لـ Java على:[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/)

### هل يمكنني استخدام Aspose.Slides for Java في مشاريعي التجارية؟

نعم، يمكن استخدام Aspose.Slides for Java في المشاريع التجارية. ومع ذلك، تأكد من مراجعة شروط الترخيص المقدمة من Aspose.

### هل Aspose.Slides for Java متوافق مع تنسيقات ملفات PowerPoint المختلفة؟

نعم، يدعم Aspose.Slides for Java تنسيقات ملفات PowerPoint المتنوعة، بما في ذلك PPTX وPPT والمزيد.

### كيف يمكنني الحصول على مزيد من الدعم أو المساعدة فيما يتعلق بـ Aspose.Slides لـ Java؟

يمكنك الوصول إلى الدعم والموارد الإضافية على موقع Aspose. أنها توفر المنتديات والوثائق وخيارات الدعم المتميز للمستخدمين.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
