---
"description": "เรียนรู้วิธีตั้งค่าไฮเปอร์ลิงก์มาโครในงานนำเสนอของคุณด้วย Aspose.Slides สำหรับ .NET เพิ่มการโต้ตอบและดึงดูดผู้ฟังของคุณ"
"linktitle": "การจัดการไฮเปอร์ลิงก์โดยใช้แมโคร"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "วิธีการตั้งค่าคลิกไฮเปอร์ลิงก์แมโครใน Aspose.Slides สำหรับ .NET"
"url": "/th/net/hyperlink-manipulation/macro-hyperlink/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการตั้งค่าคลิกไฮเปอร์ลิงก์แมโครใน Aspose.Slides สำหรับ .NET


ในโลกของการพัฒนาซอฟต์แวร์สมัยใหม่ การสร้างงานนำเสนอแบบไดนามิกและโต้ตอบได้ถือเป็นประเด็นสำคัญ Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้คุณสามารถทำงานกับงานนำเสนอได้อย่างราบรื่น ไม่ว่าคุณจะกำลังสร้างงานนำเสนอทางธุรกิจหรือสไลด์โชว์เพื่อการศึกษา ความสามารถในการตั้งค่าการคลิกไฮเปอร์ลิงก์มาโครสามารถปรับปรุงประสบการณ์ของผู้ใช้ได้อย่างมาก ในคู่มือทีละขั้นตอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการตั้งค่าการคลิกไฮเปอร์ลิงก์มาโครโดยใช้ Aspose.Slides สำหรับ .NET 

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกในบทช่วยสอนแบบทีละขั้นตอน มีข้อกำหนดเบื้องต้นบางประการที่คุณควรมี:

1.Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio ไว้ในคอมพิวเตอร์ของคุณแล้ว เนื่องจากนี่จะเป็นสภาพแวดล้อมการพัฒนาของเรา

2.Aspose.Slides สำหรับ .NET: คุณจะต้องติดตั้งไลบรารี Aspose.Slides สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/net/).

3. ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# ถือเป็นสิ่งสำคัญที่ต้องปฏิบัติตามพร้อมกับบทช่วยสอนนี้

## นำเข้าเนมสเปซ

ในขั้นตอนแรก ให้เรานำเข้าเนมสเปซที่จำเป็นสำหรับการใช้งาน Aspose.Slides:

### ขั้นตอนที่ 1: นำเข้าเนมสเปซ

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

เราได้นำเข้า `Aspose.Slides` เนมสเปซซึ่งเป็นเนมสเปซหลักสำหรับการทำงานกับการนำเสนอและ `Aspose.Slides.Export` เนมสเปซ

## การตั้งค่าการคลิกไฮเปอร์ลิงก์มาโคร

ตอนนี้เรามาดูส่วนหลักของบทช่วยสอนนี้กันดีกว่า - การตั้งค่าการคลิกไฮเปอร์ลิงก์มาโครในงานนำเสนอของคุณ

### ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ

ขั้นแรก เราต้องเริ่มต้นการนำเสนอใหม่

```csharp
using (Presentation presentation = new Presentation())
{
    // โค้ดของคุณจะอยู่ที่นี่
}
```

ภายในคำสั่งการใช้ คุณจะสร้างวัตถุการนำเสนอใหม่และดำเนินการทั้งหมดภายในนั้น

### ขั้นตอนที่ 3: เพิ่มรูปร่างอัตโนมัติ

หากต้องการตั้งค่าการคลิกไฮเปอร์ลิงก์ของมาโคร คุณจะต้องมีวัตถุที่ผู้ใช้สามารถคลิกได้ ในตัวอย่างนี้ เราจะใช้ AutoShape เป็นองค์ประกอบที่คลิกได้

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

ที่นี่ เราสร้าง AutoShape โดยใช้ประเภท "BlankButton" ในพิกัดเฉพาะ (20, 20) และมีขนาด 80x30 คุณสามารถปรับแต่งค่าเหล่านี้ให้เหมาะกับเค้าโครงของงานนำเสนอของคุณได้

### ขั้นตอนที่ 4: ตั้งค่าการคลิกไฮเปอร์ลิงก์มาโคร

ตอนนี้มาถึงส่วนที่คุณต้องตั้งค่าการคลิกไฮเปอร์ลิงก์มาโคร คุณจะต้องระบุชื่อมาโครเป็นพารามิเตอร์

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

ในตัวอย่างนี้ เราได้ตั้งค่าการคลิกไฮเปอร์ลิงก์ของแมโครเป็น "TestMacro" เมื่อผู้ใช้คลิกที่ AutoShape ระบบจะเรียกใช้แมโครนี้

### ขั้นตอนที่ 5: ดึงข้อมูล

คุณยังสามารถดึงข้อมูลเกี่ยวกับไฮเปอร์ลิงก์ที่คุณตั้งค่าได้

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

บรรทัดโค้ดเหล่านี้ช่วยให้คุณสามารถพิมพ์ URL ภายนอกและประเภทการกระทำของไฮเปอร์ลิงก์ได้

และเสร็จเรียบร้อย! คุณได้ตั้งค่าการคลิกไฮเปอร์ลิงก์มาโครในงานนำเสนอของคุณสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ .NET

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการตั้งค่าการคลิกไฮเปอร์ลิงก์มาโครในงานนำเสนอของคุณโดยใช้ Aspose.Slides สำหรับ .NET ฟีเจอร์นี้มีประโยชน์ในการสร้างงานนำเสนอแบบโต้ตอบและไดนามิกที่ดึงดูดผู้ฟัง ด้วย Aspose.Slides สำหรับ .NET คุณจะมีเครื่องมืออันทรงพลังที่จะช่วยยกระดับการพัฒนางานนำเสนอของคุณไปอีกขั้น

ตอนนี้ถึงเวลาที่คุณจะทดลองและสร้างการนำเสนอที่น่าสนใจด้วยไฮเปอร์ลิงก์มาโครแบบกำหนดเอง อย่าลังเลที่จะสำรวจ [เอกสาร Aspose.Slides สำหรับ .NET](https://reference.aspose.com/slides/net/) เพื่อข้อมูลเชิงลึกและความเป็นไปได้เพิ่มเติม

## คำถามที่พบบ่อย (FAQs)

### ฉันสามารถใช้ Aspose.Slides สำหรับ .NET ร่วมกับภาษาการเขียนโปรแกรมอื่น ๆ ได้หรือไม่
Aspose.Slides ได้รับการออกแบบมาโดยเฉพาะสำหรับ .NET แต่ Aspose ก็มีไลบรารีที่คล้ายคลึงกันสำหรับภาษาการเขียนโปรแกรมอื่นๆ เช่น Java

### Aspose.Slides สำหรับ .NET เป็นไลบรารีฟรีหรือไม่
Aspose.Slides สำหรับ .NET เป็นไลบรารีเชิงพาณิชย์ที่มีเวอร์ชันทดลองใช้งานฟรี คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/).

### มีข้อจำกัดใด ๆ ในการใช้แมโครในงานนำเสนอที่สร้างด้วย Aspose.Slides สำหรับ .NET หรือไม่
Aspose.Slides สำหรับ .NET ช่วยให้คุณสามารถทำงานกับแมโครได้ แต่คุณควรตระหนักถึงข้อควรพิจารณาด้านความปลอดภัยและความเข้ากันได้เมื่อใช้แมโครในงานนำเสนอ

### ฉันสามารถปรับแต่งลักษณะของ AutoShape ที่ใช้สำหรับไฮเปอร์ลิงก์ได้หรือไม่
ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของ AutoShape ได้โดยการปรับคุณสมบัติ เช่น ขนาด สี และแบบอักษร

### ฉันสามารถรับความช่วยเหลือหรือการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้จากที่ใด
หากคุณพบปัญหาหรือมีคำถาม คุณสามารถขอความช่วยเหลือได้จากฟอรัมสนับสนุน Aspose [ที่นี่](https://forum-aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}