---
title: قم بتحديث خصائص العرض التقديمي باستخدام عرض تقديمي آخر كقالب في شرائح Java
linktitle: قم بتحديث خصائص العرض التقديمي باستخدام عرض تقديمي آخر كقالب في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحسين عروض PowerPoint التقديمية باستخدام بيانات التعريف المحدثة باستخدام Aspose.Slides لـ Java. تعرف على كيفية تحديث خصائص مثل المؤلف والعنوان والكلمات الرئيسية باستخدام القوالب في Java Slides.
type: docs
weight: 14
url: /ar/java/media-controls/update-presentation-properties-using-another-presentation-as-a-template-in-java-slides/
---

## مقدمة لتحديث خصائص العرض التقديمي باستخدام عرض تقديمي آخر كقالب في شرائح Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية تحديث خصائص العرض التقديمي (بيانات التعريف) لعروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. يمكنك استخدام عرض تقديمي آخر كقالب لتحديث خصائص مثل المؤلف والعنوان والكلمات الأساسية والمزيد. سنزودك بتعليمات خطوة بخطوة وأمثلة على التعليمات البرمجية المصدر.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من دمج مكتبة Aspose.Slides for Java في مشروع Java الخاص بك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: قم بإعداد مشروعك

تأكد من إنشاء مشروع Java وإضافة مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.

## الخطوة 2: استيراد الحزم المطلوبة

ستحتاج إلى استيراد حزم Aspose.Slides اللازمة للعمل مع خصائص العرض التقديمي. قم بتضمين عبارات الاستيراد التالية في بداية فئة Java الخاصة بك:

```java
import com.aspose.slides.DocumentProperties;
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.IPresentationInfo;
import com.aspose.slides.PresentationFactory;
```

## الخطوة 3: تحديث خصائص العرض التقديمي

الآن، لنقم بتحديث خصائص العرض التقديمي باستخدام عرض تقديمي آخر كقالب. في هذا المثال، سنقوم بتحديث الخصائص لعروض تقديمية متعددة، ولكن يمكنك تعديل هذا الرمز ليناسب حالة الاستخدام المحددة الخاصة بك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// قم بتحميل العرض التقديمي للقالب الذي تريد نسخ الخصائص منه
DocumentProperties template;
IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
template = (DocumentProperties) info.readDocumentProperties();

// قم بتعيين الخصائص التي تريد تحديثها
template.setAuthor("Template Author");
template.setTitle("Template Title");
template.setCategory("Template Category");
template.setKeywords("Keyword1, Keyword2, Keyword3");
template.setCompany("Our Company");
template.setComments("Created from template");
template.setContentType("Template Content");
template.setSubject("Template Subject");

// قم بتحديث العروض التقديمية المتعددة باستخدام نفس القالب
updateByTemplate(dataDir + "doc1.pptx", template);
updateByTemplate(dataDir + "doc2.odp", template);
updateByTemplate(dataDir + "doc3.ppt", template);
```

##  الخطوة 4: تحديد`updateByTemplate` Method

دعونا نحدد طريقة لتحديث خصائص العروض التقديمية الفردية باستخدام القالب. ستأخذ هذه الطريقة مسار العرض التقديمي المراد تحديثه وخصائص القالب كمعلمات.

```java
private static void updateByTemplate(String path, IDocumentProperties template)
{
    // قم بتحميل العرض التقديمي ليتم تحديثه
    IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
    
    // قم بتحديث خصائص المستند باستخدام القالب
    toUpdate.updateDocumentProperties(template);
    
    // احفظ العرض التقديمي المحدث
    toUpdate.writeBindedPresentation(path);
}
```

## أكمل كود المصدر لتحديث خصائص العرض التقديمي باستخدام عرض تقديمي آخر كقالب في شرائح Java

```java
	// المسار إلى دليل المستندات.
	String dataDir = "Your Document Directory";
	DocumentProperties template;
	IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
	template = (DocumentProperties) info.readDocumentProperties();
	template.setAuthor("Template Author");
	template.setTitle("Template Title");
	template.setCategory("Template Category");
	template.setKeywords("Keyword1, Keyword2, Keyword3");
	template.setCompany("Our Company");
	template.setComments("Created from template");
	template.setContentType("Template Content");
	template.setSubject("Template Subject");
	updateByTemplate(dataDir + "doc1.pptx", template);
	updateByTemplate(dataDir + "doc2.odp", template);
	updateByTemplate(dataDir + "doc3.ppt", template);
}
private static void updateByTemplate(String path, IDocumentProperties template)
{
	IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
	toUpdate.updateDocumentProperties(template);
	toUpdate.writeBindedPresentation(path);
```

## خاتمة

في هذا البرنامج التعليمي الشامل، اكتشفنا كيفية تحديث خصائص العرض التقديمي في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. لقد ركزنا بشكل خاص على استخدام عرض تقديمي آخر كقالب لتحديث البيانات التعريفية بكفاءة مثل أسماء المؤلفين والعناوين والكلمات الرئيسية والمزيد.

## الأسئلة الشائعة

### كيف يمكنني تحديث الخصائص لمزيد من العروض التقديمية؟

 يمكنك تحديث خصائص عروض تقديمية متعددة عن طريق استدعاء`updateByTemplate` طريقة لكل عرض تقديمي بالمسار المطلوب.

### هل يمكنني تخصيص هذا الرمز لخصائص مختلفة؟

نعم، يمكنك تخصيص الكود لتحديث خصائص معينة بناءً على متطلباتك. ببساطة قم بتعديل`template` كائن بقيم الخصائص المطلوبة.

### هل هناك أي قيود على نوع العروض التقديمية التي يمكن تحديثها؟

لا، يمكنك تحديث خصائص العروض التقديمية بتنسيقات مختلفة، بما في ذلك PPTX وODP وPPT.