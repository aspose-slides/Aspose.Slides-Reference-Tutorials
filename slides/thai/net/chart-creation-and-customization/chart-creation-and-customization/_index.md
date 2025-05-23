---
"description": "เรียนรู้วิธีการสร้างและปรับแต่งแผนภูมิใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอนสำหรับการสร้างการนำเสนอแบบไดนามิก"
"linktitle": "การสร้างและปรับแต่งแผนภูมิใน Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การสร้างและปรับแต่งแผนภูมิใน Aspose.Slides"
"url": "/th/net/chart-creation-and-customization/chart-creation-and-customization/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การสร้างและปรับแต่งแผนภูมิใน Aspose.Slides


## การแนะนำ

ในโลกแห่งการนำเสนอข้อมูล สื่อช่วยสอนแบบภาพมีบทบาทสำคัญในการนำเสนอข้อมูลอย่างมีประสิทธิภาพ การนำเสนอ PowerPoint ถูกใช้กันอย่างแพร่หลายเพื่อจุดประสงค์นี้ และ Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้คุณสร้างและปรับแต่งสไลด์ด้วยโปรแกรมได้ ในคู่มือทีละขั้นตอนนี้ เราจะมาสำรวจวิธีการสร้างและปรับแต่งแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกการสร้างและปรับแต่งแผนภูมิ คุณต้องมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก [หน้าดาวน์โหลด](https://releases-aspose.com/slides/net/).

2. ไฟล์การนำเสนอ: เตรียมไฟล์การนำเสนอ PowerPoint ที่คุณต้องการเพิ่มและปรับแต่งแผนภูมิ

ตอนนี้ มาแบ่งขั้นตอนออกเป็นหลายขั้นตอนเพื่อให้เป็นบทช่วยสอนที่ครอบคลุม

## ขั้นตอนที่ 1: เพิ่มสไลด์เค้าโครงลงในงานนำเสนอ

```csharp
string FilePath = @"..\..\..\Sample Files\";
string FileName = FilePath + "Adding Layout Slides.pptx";

using (Presentation p = new Presentation(FileName))
{
    // ลองค้นหาตามประเภทสไลด์เค้าโครง
    IMasterLayoutSlideCollection layoutSlides = p.Masters[0].LayoutSlides;
    ILayoutSlide layoutSlide =
        layoutSlides.GetByType(SlideLayoutType.TitleAndObject) ??
        layoutSlides.GetByType(SlideLayoutType.Title);

    if (layoutSlide == null)
    {
        // สถานการณ์ที่การนำเสนอไม่มีรูปแบบบางอย่าง
        // -

        // การเพิ่มสไลด์เปล่าพร้อมเพิ่มเค้าโครงสไลด์ 
        p.Slides.InsertEmptySlide(0, layoutSlide);

        // บันทึกการนำเสนอ    
        p.Save(FileName, SaveFormat.Pptx);
    }
}
```

ในขั้นตอนนี้ เราจะสร้างการนำเสนอใหม่ ค้นหาสไลด์เค้าโครงที่เหมาะสม และเพิ่มสไลด์ว่างโดยใช้ Aspose.Slides

## ขั้นตอนที่ 2: รับตัวอย่างตัวแทนฐาน

```csharp
string presentationName = Path.Combine("Your Document Directory", "placeholder.pptx");

using (Presentation presentation = new Presentation(presentationName))
{
    ISlide slide = presentation.Slides[0];
    IShape shape = slide.Shapes[0];

    // -

    IShape masterShape = layoutShape.GetBasePlaceholder();

    // -
}
```

ขั้นตอนนี้เกี่ยวข้องกับการเปิดงานนำเสนอที่มีอยู่และการแยกตัวแทนฐาน ซึ่งจะทำให้คุณสามารถทำงานกับตัวแทนในสไลด์ของคุณได้

## ขั้นตอนที่ 3: จัดการส่วนหัวและส่วนท้ายในสไลด์

```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation(dataDir + "presentation.ppt"))
{
    IBaseSlideHeaderFooterManager headerFooterManager = presentation.Slides[0].HeaderFooterManager;

    // -

    presentation.Save(dataDir + "Presentation.ppt", SaveFormat.Ppt);
}
```

ในขั้นตอนสุดท้ายนี้ เราจะจัดการส่วนหัวและส่วนท้ายของสไลด์ด้วยการสลับการมองเห็น ตั้งค่าข้อความ และปรับแต่งตัวแทนวันที่และเวลา

ตอนนี้เราได้แบ่งตัวอย่างแต่ละตัวอย่างออกเป็นหลายขั้นตอนแล้ว คุณสามารถใช้ Aspose.Slides สำหรับ .NET เพื่อสร้าง ปรับแต่ง และจัดการการนำเสนอ PowerPoint ได้ด้วยโปรแกรม ไลบรารีอันทรงพลังนี้มีความสามารถมากมาย ช่วยให้คุณสร้างการนำเสนอที่น่าสนใจและให้ข้อมูลได้อย่างง่ายดาย

## บทสรุป

การสร้างและปรับแต่งแผนภูมิใน Aspose.Slides สำหรับ .NET จะเปิดโลกแห่งความเป็นไปได้สำหรับการนำเสนอแบบไดนามิกและขับเคลื่อนด้วยข้อมูล ด้วยคำแนะนำทีละขั้นตอนเหล่านี้ คุณสามารถใช้ประโยชน์จากศักยภาพทั้งหมดของไลบรารีนี้เพื่อปรับปรุงการนำเสนอ PowerPoint ของคุณและถ่ายทอดข้อมูลได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### Aspose.Slides รองรับ .NET เวอร์ชันใดบ้างสำหรับ .NET?
Aspose.Slides สำหรับ .NET รองรับเวอร์ชัน .NET มากมาย รวมถึง .NET Framework และ .NET Core ตรวจสอบเอกสารประกอบสำหรับรายละเอียดเฉพาะ

### ฉันสามารถสร้างแผนภูมิที่ซับซ้อนโดยใช้ Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถสร้างแผนภูมิได้หลากหลายประเภท รวมถึงแผนภูมิแท่ง แผนภูมิวงกลม และแผนภูมิเส้น พร้อมด้วยตัวเลือกการปรับแต่งมากมาย

### มี Aspose.Slides สำหรับ .NET ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้งานฟรีได้จากเว็บไซต์ Aspose [ที่นี่](https://releases-aspose.com/).

### ฉันสามารถค้นหาการสนับสนุนและทรัพยากรเพิ่มเติมสำหรับ Aspose.Slides สำหรับ .NET ได้จากที่ใด
เยี่ยมชมฟอรัมสนับสนุน Aspose [ที่นี่](https://forum.aspose.com/) สำหรับคำถามหรือความช่วยเหลือใด ๆ ที่คุณอาจต้องการ

### ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถขอใบอนุญาตชั่วคราวได้จากเว็บไซต์ Aspose [ที่นี่](https://purchase-aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}