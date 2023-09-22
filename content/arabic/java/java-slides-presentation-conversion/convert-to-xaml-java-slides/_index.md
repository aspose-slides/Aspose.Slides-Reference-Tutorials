---
title: تحويل إلى XAML في شرائح جافا
linktitle: تحويل إلى XAML في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحويل عروض PowerPoint التقديمية إلى XAML في Java باستخدام Aspose.Slides. اتبع دليلنا خطوة بخطوة للتكامل السلس.
type: docs
weight: 28
url: /ar/java/presentation-conversion/convert-to-xaml-java-slides/
---

## مقدمة تحويل إلى XAML في شرائح جافا

في هذا الدليل الشامل، سنستكشف كيفية تحويل العروض التقديمية إلى تنسيق XAML باستخدام Aspose.Slides for Java API. XAML (لغة ترميز التطبيقات القابلة للتوسيع) هي لغة ترميزية مستخدمة على نطاق واسع لإنشاء واجهات المستخدم. يمكن أن يكون تحويل العروض التقديمية إلى XAML خطوة حاسمة في دمج محتوى PowerPoint الخاص بك في العديد من التطبيقات، خاصة تلك التي تم إنشاؤها باستخدام تقنيات مثل WPF (Windows Presentation Foundation).

## المتطلبات الأساسية

قبل أن نتعمق في عملية التحويل، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Slides for Java API: يجب أن يكون Aspose.Slides for Java مثبتًا وإعداده في بيئة التطوير الخاصة بك. إذا لم يكن الأمر كذلك، يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: تحميل العرض التقديمي

للبدء، نحتاج إلى تحميل عرض PowerPoint التقديمي المصدر الذي نريد تحويله إلى XAML. يمكنك القيام بذلك عن طريق توفير المسار إلى ملف العرض التقديمي الخاص بك. إليك مقتطف الشفرة للبدء:

```java
// المسار إلى العرض التقديمي المصدر
String presentationFileName = "XamlEtalon.pptx";
Presentation pres = new Presentation(presentationFileName);
```

## الخطوة 2: تكوين خيارات التحويل

قبل تحويل العرض التقديمي، يمكنك تكوين خيارات تحويل متنوعة لتخصيص الإخراج وفقًا لاحتياجاتك. في حالتنا، سنقوم بإنشاء خيارات تحويل XAML وإعدادها على النحو التالي:

```java
// إنشاء خيارات التحويل
XamlOptions xamlOptions = new XamlOptions();
xamlOptions.setExportHiddenSlides(true);
```

تتيح لنا هذه الخيارات تصدير الشرائح المخفية وتخصيص عملية التحويل.

## الخطوة 3: تنفيذ توفير المخرجات

لحفظ محتوى XAML المحول، نحتاج إلى تحديد موفر الإخراج. فيما يلي تطبيق مخصص لموفر الإخراج لـ XAML:

```java
class NewXamlSaver implements IXamlOutputSaver
{
    private Map<String, String> m_result = new HashMap<String, String>();

    public Map<String, String> getResults()
    {
        return m_result;
    }

    public void save(String path, byte[] data)
    {
        String name = new File(path).getName();
        m_result.put(name, new String(data, StandardCharsets.UTF_8));
    }
}
```

يقوم موفر المخرجات المخصص هذا بتخزين بيانات XAML المحولة في الخريطة.

## الخطوة 4: تحويل الشرائح وحفظها

بعد تحميل العرض التقديمي وتعيين خيارات التحويل، يمكننا الآن متابعة تحويل الشرائح وحفظها كملفات XAML. وإليك كيف يمكنك القيام بذلك:

```java
try {
    // حدد خدمة توفير المخرجات الخاصة بك
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.setOutputSaver(newXamlSaver);
    
    // تحويل الشرائح
    pres.save(xamlOptions);
    
    // احفظ ملفات XAML في دليل الإخراج
    for (Map.Entry<String, String> pair : newXamlSaver.getResults().entrySet()) {
        FileWriter writer = new FileWriter(pair.getKey(), true);
        writer.append(pair.getValue());
        writer.close();
    }
} catch(IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```

في هذه الخطوة، نقوم بإعداد موفر المخرجات المخصص وإجراء التحويل وحفظ ملفات XAML الناتجة.

## أكمل كود المصدر للتحويل إلى XAML في شرائح Java

```java
	// المسار إلى العرض التقديمي المصدر
	String presentationFileName = RunExamples.getDataDir_Conversion() + "XamlEtalon.pptx";
	Presentation pres = new Presentation(presentationFileName);
	try {
		// إنشاء خيارات التحويل
		XamlOptions xamlOptions = new XamlOptions();
		xamlOptions.setExportHiddenSlides(true);
		// حدد خدمة توفير المخرجات الخاصة بك
		NewXamlSaver newXamlSaver = new NewXamlSaver();
		xamlOptions.setOutputSaver(newXamlSaver);
		// تحويل الشرائح
		pres.save(xamlOptions);
		// احفظ ملفات XAML في دليل الإخراج
		for (Map.Entry<String, String> pair : newXamlSaver.getResults().entrySet()) {
			FileWriter writer = new FileWriter(RunExamples.getOutPath() + pair.getKey(), true);
			writer.append(pair.getValue());
			writer.close();
		}
	} catch(IOException e) {
		e.printStackTrace();
	} finally {
		if (pres != null) pres.dispose();
	}
}
/
 * Represents an output saver implementation for transfer data to the external storage.
 */
static class NewXamlSaver implements IXamlOutputSaver
{
	private Map<String, String> m_result =  new HashMap<String, String>();
	public Map<String, String> getResults()
	{
		return m_result;
	}
	public void save(String path, byte[] data)
	{
		String name = new File(path).getName();
		m_result.put(name, new String(data, StandardCharsets.UTF_8));
	}
```

## خاتمة

يعد تحويل العروض التقديمية إلى XAML في Java باستخدام Aspose.Slides for Java API طريقة فعالة لدمج محتوى PowerPoint الخاص بك في التطبيقات التي تعتمد على واجهات المستخدم المستندة إلى XAML. باتباع الخطوات الموضحة في هذا الدليل، يمكنك إنجاز هذه المهمة بسهولة وتحسين سهولة استخدام تطبيقاتك.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

 يمكنك تنزيل Aspose.Slides for Java من موقع الويب على[هنا](https://releases.aspose.com/slides/java/).

### هل يمكنني تخصيص مخرجات XAML بشكل أكبر؟

نعم، يمكنك تخصيص مخرجات XAML عن طريق ضبط خيارات التحويل التي توفرها Aspose.Slides for Java API. يتيح لك ذلك تخصيص الإخراج لتلبية متطلباتك المحددة.

### ما هو استخدام XAML؟

XAML (لغة ترميز التطبيقات القابلة للتوسيع) هي لغة ترميز تستخدم لإنشاء واجهات المستخدم في التطبيقات، خاصة تلك المبنية بتقنيات مثل WPF (Windows Presentation Foundation) وUWP (النظام الأساسي العالمي لـ Windows).

### كيف يمكنني التعامل مع الشرائح المخفية أثناء التحويل؟

لتصدير الشرائح المخفية أثناء التحويل، قم بتعيين`setExportHiddenSlides` خيار ل`true` في خيارات تحويل XAML، كما هو موضح في هذا الدليل.

### هل هناك أي تنسيقات إخراج أخرى يدعمها Aspose.Slides؟

نعم، يدعم Aspose.Slides مجموعة واسعة من تنسيقات الإخراج، بما في ذلك PDF وHTML والصور والمزيد. يمكنك استكشاف هذه الخيارات في وثائق API.