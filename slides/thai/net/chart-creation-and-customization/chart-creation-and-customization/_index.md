---
title: การสร้างแผนภูมิและการปรับแต่งใน Aspose.Slides
linktitle: การสร้างแผนภูมิและการปรับแต่งใน Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างและปรับแต่งแผนภูมิใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอนสำหรับการสร้างงานนำเสนอแบบไดนามิก
weight: 10
url: /th/net/chart-creation-and-customization/chart-creation-and-customization/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## การแนะนำ

ในโลกของการนำเสนอข้อมูล อุปกรณ์แสดงผลมีบทบาทสำคัญในการถ่ายทอดข้อมูลอย่างมีประสิทธิภาพ การนำเสนอ PowerPoint ถูกนำมาใช้กันอย่างแพร่หลายเพื่อจุดประสงค์นี้ และ Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้คุณสามารถสร้างและปรับแต่งสไลด์โดยทางโปรแกรมได้ ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีสร้างแผนภูมิและปรับแต่งแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกในการสร้างและปรับแต่งแผนภูมิ คุณจะต้องมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[หน้าดาวน์โหลด](https://releases.aspose.com/slides/net/).

2. ไฟล์การนำเสนอ: เตรียมไฟล์งานนำเสนอ PowerPoint ที่คุณต้องการเพิ่มและปรับแต่งแผนภูมิ

ตอนนี้ เรามาแบ่งกระบวนการออกเป็นหลายขั้นตอนสำหรับบทช่วยสอนที่ครอบคลุม

## ขั้นตอนที่ 1: เพิ่มสไลด์เค้าโครงในการนำเสนอ

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
        //สถานการณ์เมื่องานนำเสนอไม่มีเค้าโครงบางประเภท
        // -

        // เพิ่มสไลด์เปล่าพร้อมเพิ่มสไลด์เลย์เอาต์
        p.Slides.InsertEmptySlide(0, layoutSlide);

        // บันทึกการนำเสนอ
        p.Save(FileName, SaveFormat.Pptx);
    }
}
```

ในขั้นตอนนี้ เราจะสร้างงานนำเสนอใหม่ ค้นหาสไลด์เค้าโครงที่เหมาะสม และเพิ่มสไลด์เปล่าโดยใช้ Aspose.Slides

## ขั้นตอนที่ 2: รับตัวอย่างตัวยึดฐาน

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

ขั้นตอนนี้เกี่ยวข้องกับการเปิดงานนำเสนอที่มีอยู่และการแยกพื้นที่ที่สำรองไว้ ซึ่งจะทำให้คุณสามารถทำงานกับพื้นที่ที่สำรองไว้ในสไลด์ของคุณได้

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

ในขั้นตอนสุดท้ายนี้ เราจัดการส่วนหัวและส่วนท้ายในสไลด์โดยการสลับการมองเห็น ตั้งค่าข้อความ และปรับแต่งตัวยึดตำแหน่งวันที่-เวลา

ตอนนี้เราได้แบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนแล้ว คุณสามารถใช้ Aspose.Slides สำหรับ .NET เพื่อสร้าง ปรับแต่ง และจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรมได้ ไลบรารีอันทรงพลังนี้มีความสามารถที่หลากหลาย ช่วยให้คุณสร้างสรรค์การนำเสนอที่น่าสนใจและให้ข้อมูลได้อย่างง่ายดาย

## บทสรุป

การสร้างและปรับแต่งแผนภูมิใน Aspose.Slides สำหรับ .NET เปิดโลกแห่งความเป็นไปได้สำหรับการนำเสนอแบบไดนามิกและขับเคลื่อนด้วยข้อมูล ด้วยคำแนะนำทีละขั้นตอนเหล่านี้ คุณจะสามารถควบคุมศักยภาพสูงสุดของไลบรารีนี้เพื่อปรับปรุงงานนำเสนอ PowerPoint ของคุณและถ่ายทอดข้อมูลได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### Aspose.Slides สำหรับ .NET รองรับ .NET เวอร์ชันใดบ้าง
Aspose.Slides สำหรับ .NET รองรับ .NET เวอร์ชันที่หลากหลาย รวมถึง .NET Framework และ .NET Core ตรวจสอบเอกสารประกอบเพื่อดูรายละเอียดเฉพาะ

### ฉันสามารถสร้างแผนภูมิที่ซับซ้อนโดยใช้ Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถสร้างแผนภูมิได้หลายประเภท รวมถึงแผนภูมิแท่ง แผนภูมิวงกลม และแผนภูมิเส้น พร้อมตัวเลือกการปรับแต่งที่หลากหลาย

### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จากเว็บไซต์ Aspose[ที่นี่](https://releases.aspose.com/).

### ฉันจะค้นหาการสนับสนุนและทรัพยากรเพิ่มเติมสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 เยี่ยมชมฟอรั่มสนับสนุน Aspose[ที่นี่](https://forum.aspose.com/) สำหรับคำถามหรือความช่วยเหลือใด ๆ ที่คุณอาจต้องการ

### ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จากเว็บไซต์ Aspose[ที่นี่](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
