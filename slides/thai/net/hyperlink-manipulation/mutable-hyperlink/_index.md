---
title: การสร้างไฮเปอร์ลิงก์ที่ไม่แน่นอนใน Aspose.Slides สำหรับ .NET
linktitle: การสร้างไฮเปอร์ลิงก์ที่ไม่แน่นอน
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: ปรับปรุงการนำเสนอ PowerPoint ของคุณด้วยไฮเปอร์ลิงก์ที่ไม่แน่นอนโดยใช้ Aspose.Slides สำหรับ .NET ดึงดูดผู้ชมของคุณอย่างที่ไม่เคยมีมาก่อน!
weight: 14
url: /th/net/hyperlink-manipulation/mutable-hyperlink/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


ในโลกของการพัฒนาซอฟต์แวร์สมัยใหม่ การสร้างงานนำเสนอแบบไดนามิกด้วยไฮเปอร์ลิงก์เชิงโต้ตอบถือเป็นสิ่งสำคัญในการดึงดูดผู้ชมของคุณ Aspose.Slides สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ช่วยให้คุณสามารถจัดการและปรับแต่งงานนำเสนอ PowerPoint รวมถึงการสร้างไฮเปอร์ลิงก์ที่ไม่แน่นอน ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างไฮเปอร์ลิงก์ที่ไม่แน่นอนโดยใช้ Aspose.Slides สำหรับ .NET 

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะดำดิ่งสู่โลกของไฮเปอร์ลิงก์ที่ไม่แน่นอน มีข้อกำหนดเบื้องต้นบางประการที่คุณต้องมี:

### 1. Aspose.Slides สำหรับ .NET
 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Slides สำหรับ .NET และตั้งค่าในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).

### 2. .NET Framework
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework บนเครื่องของคุณแล้ว Aspose.Slides สำหรับ .NET ต้องใช้ .NET Framework ในการทำงาน

### 3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE)
คุณจะต้องมี IDE เช่น Visual Studio เพื่อเขียนและรันโค้ด .NET

เมื่อคุณมีข้อกำหนดเบื้องต้นที่จำเป็นแล้ว เรามาต่อกันที่การสร้างไฮเปอร์ลิงก์ที่ไม่แน่นอนใน Aspose.Slides สำหรับ .NET

## การสร้างไฮเปอร์ลิงก์ที่ไม่แน่นอน

### ขั้นตอนที่ 1: การตั้งค่าโครงการของคุณ
ขั้นแรก สร้างโปรเจ็กต์ใหม่หรือเปิดโปรเจ็กต์ที่มีอยู่ใน IDE ของคุณ ตรวจสอบให้แน่ใจว่าคุณมีการอ้างอิง Aspose.Slides สำหรับ .NET อย่างถูกต้องในโครงการของคุณ

### ขั้นตอนที่ 2: นำเข้าเนมสเปซ
ในไฟล์โค้ดของคุณ ให้นำเข้าเนมสเปซที่จำเป็นสำหรับการทำงานกับ Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Shape;
```

### ขั้นตอนที่ 3: สร้างงานนำเสนอใหม่
หากต้องการสร้างงานนำเสนอ PowerPoint ใหม่ ให้ใช้รหัสต่อไปนี้:

```csharp
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation())
{
    // รหัสของคุณสำหรับการสร้างและจัดการงานนำเสนออยู่ที่นี่
    presentation.Save(dataDir + "presentation-out.pptx", SaveFormat.Pptx);
}
```

### ขั้นตอนที่ 4: การเพิ่มรูปร่างไฮเปอร์ลิงก์
ตอนนี้ มาเพิ่มรูปร่างให้กับงานนำเสนอของคุณด้วยไฮเปอร์ลิงก์ ในตัวอย่างนี้ เราจะสร้างรูปทรงสี่เหลี่ยมผืนผ้าพร้อมไฮเปอร์ลิงก์ไปยังเว็บไซต์ Aspose:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

ในขั้นตอนนี้ เราได้เพิ่มรูปร่างสี่เหลี่ยมพร้อมข้อความ "Aspose: File Format APIs" และไฮเปอร์ลิงก์ที่คลิกได้ คุณสามารถปรับแต่งรูปร่าง ข้อความ และไฮเปอร์ลิงก์ได้ตามความต้องการของคุณ

### ขั้นตอนที่ 5: บันทึกการนำเสนอ
สุดท้าย บันทึกงานนำเสนอของคุณลงในไฟล์โดยใช้โค้ดต่อไปนี้:

```csharp
presentation.Save(dataDir + "presentation-out.pptx", SaveFormat.Pptx);
```

การนำเสนอไฮเปอร์ลิงก์ที่ไม่แน่นอนของคุณพร้อมแล้ว!

## บทสรุป

Aspose.Slides สำหรับ .NET ทำให้การสร้างไฮเปอร์ลิงก์ที่ไม่แน่นอนในงานนำเสนอ PowerPoint เป็นเรื่องง่าย ด้วยขั้นตอนง่ายๆ ที่อธิบายไว้ในคู่มือนี้ คุณสามารถสร้างงานนำเสนอเชิงโต้ตอบแบบไดนามิกที่ดึงดูดผู้ชมของคุณได้ ไม่ว่าคุณจะเป็นนักพัฒนาที่ทำงานเกี่ยวกับการนำเสนอขององค์กรหรือสื่อการเรียนรู้ Aspose.Slides ช่วยให้คุณสามารถเพิ่มไฮเปอร์ลิงก์และปรับปรุงเนื้อหาของคุณได้อย่างง่ายดาย

 สำหรับข้อมูลเชิงลึกและเอกสารประกอบเพิ่มเติม โปรดดูที่[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/).

## คำถามที่พบบ่อย

### 1. Aspose.Slides สำหรับ .NET รองรับ .NET Framework เวอร์ชันใดบ้าง
Aspose.Slides สำหรับ .NET รองรับ .NET Framework หลายเวอร์ชัน รวมถึง 2.0, 3.5, 4.x และอื่นๆ

### 2. ฉันสามารถสร้างไฮเปอร์ลิงก์ไปยังเว็บไซต์ภายนอกในงานนำเสนอ PowerPoint ของฉันโดยใช้ Aspose.Slides สำหรับ .NET ได้หรือไม่
ได้ คุณสามารถสร้างไฮเปอร์ลิงก์ไปยังเว็บไซต์ภายนอกได้ตามที่แสดงในคู่มือนี้ Aspose.Slides สำหรับ .NET ช่วยให้คุณสามารถเชื่อมโยงไปยังหน้าเว็บ ไฟล์ หรือทรัพยากรอื่นๆ

### 3. มีตัวเลือกสิทธิ์การใช้งานสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
 ใช่ Aspose เสนอตัวเลือกสิทธิ์การใช้งานสำหรับกรณีการใช้งานที่แตกต่างกัน คุณสามารถสำรวจและซื้อใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy) หรือได้รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).

### 4. ฉันสามารถปรับแต่งลักษณะที่ปรากฏของไฮเปอร์ลิงก์ในงานนำเสนอของฉันได้หรือไม่
อย่างแน่นอน. Aspose.Slides สำหรับ .NET มีตัวเลือกมากมายสำหรับการปรับแต่งลักษณะที่ปรากฏของไฮเปอร์ลิงก์ รวมถึงข้อความ สี และสไตล์

### 5. Aspose.Slides สำหรับ .NET เหมาะสำหรับการสร้างเนื้อหาอีเลิร์นนิงแบบโต้ตอบหรือไม่
ใช่ Aspose.Slides สำหรับ .NET เป็นเครื่องมืออเนกประสงค์ที่สามารถใช้เพื่อสร้างเนื้อหาอีเลิร์นนิงเชิงโต้ตอบ รวมถึงไฮเปอร์ลิงก์ แบบทดสอบ และองค์ประกอบมัลติมีเดีย
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
