---
title: วิธีการตั้งค่า Macro Hyperlink คลิกใน Aspose.Slides สำหรับ .NET
linktitle: การจัดการไฮเปอร์ลิงก์โดยใช้มาโคร
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่าไฮเปอร์ลิงก์มาโครในงานนำเสนอของคุณด้วย Aspose.Slides สำหรับ .NET ปรับปรุงการโต้ตอบและดึงดูดผู้ชมของคุณ
weight: 13
url: /th/net/hyperlink-manipulation/macro-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการตั้งค่า Macro Hyperlink คลิกใน Aspose.Slides สำหรับ .NET


ในโลกของการพัฒนาซอฟต์แวร์สมัยใหม่ การสร้างงานนำเสนอเชิงโต้ตอบและแบบไดนามิกถือเป็นส่วนสำคัญ Aspose.Slides สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณทำงานกับงานนำเสนอได้อย่างราบรื่น ไม่ว่าคุณกำลังสร้างการนำเสนอทางธุรกิจหรือสไลด์โชว์เพื่อการศึกษา ความสามารถในการตั้งค่าการคลิกไฮเปอร์ลิงก์มาโครสามารถปรับปรุงประสบการณ์ผู้ใช้ได้อย่างมาก ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการตั้งค่าการคลิกไฮเปอร์ลิงก์มาโครโดยใช้ Aspose.Slides สำหรับ .NET 

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอนทีละขั้นตอน มีข้อกำหนดเบื้องต้นบางประการที่คุณควรมี:

1.Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนคอมพิวเตอร์ของคุณแล้ว เนื่องจากนี่จะเป็นสภาพแวดล้อมการพัฒนาของเรา

 2.Aspose.Slides สำหรับ .NET: คุณจะต้องติดตั้งไลบรารี Aspose.Slides สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/net/).

3. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# เป็นสิ่งสำคัญที่ต้องปฏิบัติตามพร้อมกับบทช่วยสอนนี้

## นำเข้าเนมสเปซ

ในขั้นตอนแรก เรามานำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Slides:

### ขั้นตอนที่ 1: นำเข้าเนมสเปซ

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 เราได้นำเข้า`Aspose.Slides` เนมสเปซซึ่งเป็นเนมสเปซหลักสำหรับการทำงานกับการนำเสนอ และ`Aspose.Slides.Export` เนมสเปซ

## การตั้งค่ามาโคร ไฮเปอร์ลิงก์ คลิก

ตอนนี้ มาดูส่วนหลักของบทช่วยสอนนี้กัน - การตั้งค่าการคลิกไฮเปอร์ลิงก์มาโครในงานนำเสนอของคุณ

### ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ

ขั้นแรก เราต้องเริ่มต้นการนำเสนอใหม่

```csharp
using (Presentation presentation = new Presentation())
{
    // รหัสของคุณจะไปที่นี่
}
```

ภายในคำสั่งการใช้นี้ คุณจะสร้างออบเจ็กต์การนำเสนอใหม่และดำเนินการทั้งหมดภายในนั้น

### ขั้นตอนที่ 3: เพิ่มรูปร่างอัตโนมัติ

ถ้าจะตั้งค่าการคลิก Macro Hyperlink คุณจะต้องมีวัตถุที่ผู้ใช้สามารถคลิกได้ ในตัวอย่างนี้ เราจะใช้รูปร่างอัตโนมัติเป็นองค์ประกอบที่สามารถคลิกได้

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

ที่นี่ เราสร้างรูปร่างอัตโนมัติด้วยประเภท "BlankButton" ที่พิกัดเฉพาะ (20, 20) และมีขนาด 80x30 คุณสามารถปรับแต่งค่าเหล่านี้ให้เหมาะกับเค้าโครงงานนำเสนอของคุณได้

### ขั้นตอนที่ 4: ตั้งค่าการคลิกมาโครไฮเปอร์ลิงก์

ตอนนี้มาถึงส่วนที่คุณตั้งค่าการคลิกไฮเปอร์ลิงก์มาโคร คุณจะต้องระบุชื่อมาโครเป็นพารามิเตอร์

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

ในตัวอย่างนี้ เราได้ตั้งค่าการคลิกไฮเปอร์ลิงก์มาโครเป็น "TestMacro" เมื่อผู้ใช้คลิกที่รูปร่างอัตโนมัติ มันจะทริกเกอร์มาโครนี้

### ขั้นตอนที่ 5: ดึงข้อมูล

คุณยังสามารถดึงข้อมูลเกี่ยวกับไฮเปอร์ลิงก์ที่คุณตั้งไว้ได้

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

บรรทัดโค้ดเหล่านี้ช่วยให้คุณสามารถพิมพ์ URL ภายนอกและประเภทการทำงานของไฮเปอร์ลิงก์ได้

แค่นั้นแหละ! คุณได้ตั้งค่าการคลิกไฮเปอร์ลิงก์มาโครในงานนำเสนอของคุณโดยใช้ Aspose.Slides สำหรับ .NET เรียบร้อยแล้ว

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าการคลิกไฮเปอร์ลิงก์มาโครในงานนำเสนอของคุณโดยใช้ Aspose.Slides สำหรับ .NET นี่อาจเป็นคุณสมบัติที่มีคุณค่าในการสร้างการนำเสนอเชิงโต้ตอบและไดนามิกที่ดึงดูดผู้ชมของคุณ ด้วย Aspose.Slides สำหรับ .NET คุณจะมีเครื่องมืออันทรงพลังเพื่อยกระดับการพัฒนาการนำเสนอของคุณไปอีกระดับ

 ตอนนี้ถึงเวลาที่คุณจะต้องทดลองและสร้างงานนำเสนอที่น่าสนใจด้วยไฮเปอร์ลิงก์มาโครแบบกำหนดเอง รู้สึกอิสระที่จะสำรวจ[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/) เพื่อข้อมูลเชิงลึกและความเป็นไปได้เพิ่มเติม

## คำถามที่พบบ่อย (คำถามที่พบบ่อย)

### ฉันสามารถใช้ Aspose.Slides สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
Aspose.Slides ได้รับการออกแบบมาเพื่อ .NET เป็นหลัก แต่ Aspose มีไลบรารีที่คล้ายกันสำหรับภาษาการเขียนโปรแกรมอื่นๆ เช่น Java

### Aspose.Slides สำหรับ .NET เป็นห้องสมุดฟรีหรือไม่
Aspose.Slides สำหรับ .NET เป็นไลบรารีเชิงพาณิชย์ที่มีเวอร์ชันทดลองใช้ฟรี คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/).

### มีข้อจำกัดในการใช้มาโครในการนำเสนอที่สร้างด้วย Aspose.Slides สำหรับ .NET หรือไม่
Aspose.Slides สำหรับ .NET ช่วยให้คุณสามารถทำงานกับมาโครได้ แต่คุณควรคำนึงถึงความปลอดภัยและความเข้ากันได้เมื่อใช้มาโครในการนำเสนอ

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของรูปร่างอัตโนมัติที่ใช้สำหรับไฮเปอร์ลิงก์ได้หรือไม่
ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของรูปร่างอัตโนมัติได้โดยการปรับคุณสมบัติ เช่น ขนาด สี และแบบอักษร

### ฉันจะขอความช่วยเหลือหรือสนับสนุน Aspose.Slides สำหรับ .NET ได้ที่ไหน
 หากคุณพบปัญหาหรือมีคำถาม คุณสามารถขอความช่วยเหลือได้ที่ฟอรัมสนับสนุน Aspose[ที่นี่](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
