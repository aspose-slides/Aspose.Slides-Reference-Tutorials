---
"description": "تعلم كيفية استرداد إحداثيات أجزاء النص في شرائح جافا باستخدام Aspose.Slides لـ Java API. تحكم بدقة في موضع النص في عروض PowerPoint التقديمية."
"linktitle": "الحصول على إحداثيات موضع الجزء في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "الحصول على إحداثيات موضع الجزء في شرائح Java"
"url": "/ar/java/additional-utilities/get-position-coordinates-of-portion-in-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# الحصول على إحداثيات موضع الجزء في شرائح Java


## مقدمة للحصول على إحداثيات موضع الجزء في شرائح Java

في هذا الدليل الشامل، سنستكشف كيفية استرداد إحداثيات موضع جزء من شرائح جافا باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. ستتعلم كيفية الوصول إلى أجزاء النص في الشريحة ومعالجتها، واستخراج إحداثياتها X وY. يتضمن هذا البرنامج التعليمي خطوة بخطوة أمثلة على الكود المصدري ومعلومات قيّمة لمساعدتك على إتقان هذه المهمة.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK)
- تم تنزيل وتكوين مكتبة Aspose.Slides لـ Java
- بيئة تطوير Java المتكاملة (IDE) حسب اختيارك

الآن، دعونا نبدأ بالتنفيذ.

## الخطوة 1: إعداد مشروعك

قبل أن نتمكن من استخدام Aspose.Slides لجافا، علينا إعداد مشروع جافا وتكوين المكتبة. اتبع الخطوات التالية لتجهيز مشروعك:

1. قم بإنشاء مشروع Java جديد في IDE الخاص بك.
2. أضف مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.
3. قم باستيراد فئات Aspose.Slides الضرورية في بداية ملف Java الخاص بك.

```java
import com.aspose.slides.*;
import java.awt.geom.Point2D;
```

## الخطوة 2: تحميل العرض التقديمي

في هذه الخطوة، سنقوم بتحميل عرض PowerPoint الذي يحتوي على الشريحة التي نريد العمل عليها. استبدل `"Your Document Directory"` مع المسار الفعلي لملف PowerPoint الخاص بك.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
```

## الخطوة 3: الوصول إلى أجزاء النص والإحداثيات

الآن، سنصل إلى أجزاء النص داخل الشريحة ونحصل على إحداثياتها X وY. سنكرر الفقرات والأجزاء لتحقيق ذلك. إليك مقتطف الكود:

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

يسترجع هذا الكود إحداثيات X وY لكل جزء من النص في الشريحة المحددة. يمكنك تعديله ليناسب احتياجاتك الخاصة.

## كود المصدر الكامل للحصول على إحداثيات موضع الجزء في شرائح Java

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

في هذا البرنامج التعليمي، تناولنا كيفية الحصول على إحداثيات مواقع أجزاء النص في شرائح جافا باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. تُعد هذه المعرفة مفيدة بشكل خاص عند الحاجة إلى تحكم دقيق في مواقع عناصر النص في عروض PowerPoint التقديمية.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لـ Java؟

يمكنك تنزيل Aspose.Slides for Java من الموقع الإلكتروني باستخدام الرابط التالي: [تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/)

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟

تتوفر وثائق Aspose.Slides لـ Java على: [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/)

### هل يمكنني استخدام Aspose.Slides لـ Java في مشاريعي التجارية؟

نعم، يُمكن استخدام Aspose.Slides لجافا في المشاريع التجارية. مع ذلك، يُرجى مراجعة شروط الترخيص المُقدّمة من Aspose.

### هل Aspose.Slides for Java متوافق مع تنسيقات ملفات PowerPoint المختلفة؟

نعم، يدعم Aspose.Slides for Java تنسيقات ملفات PowerPoint المختلفة، بما في ذلك PPTX وPPT والمزيد.

### كيف يمكنني الحصول على مزيد من الدعم أو المساعدة مع Aspose.Slides لـ Java؟

يمكنك الوصول إلى دعم وموارد إضافية على موقع Aspose الإلكتروني. يوفر الموقع منتديات ووثائق وخيارات دعم مميزة للمستخدمين.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}