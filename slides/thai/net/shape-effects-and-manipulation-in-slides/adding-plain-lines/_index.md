---
title: การเพิ่มเส้นธรรมดาให้กับสไลด์การนำเสนอโดยใช้ Aspose.Slides
linktitle: การเพิ่มเส้นธรรมดาให้กับสไลด์การนำเสนอโดยใช้ Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: ปรับปรุงงานนำเสนอ PowerPoint ของคุณใน .NET โดยใช้ Aspose.Slides ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อเพิ่มเส้นธรรมดาอย่างง่ายดาย
weight: 16
url: /th/net/shape-effects-and-manipulation-in-slides/adding-plain-lines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
การสร้างงานนำเสนอ PowerPoint ที่น่าดึงดูดและดึงดูดสายตามักจะเกี่ยวข้องกับการรวมรูปทรงและองค์ประกอบต่างๆ หากคุณทำงานกับ .NET Aspose.Slides เป็นเครื่องมืออันทรงพลังที่ทำให้กระบวนการง่ายขึ้น บทช่วยสอนนี้เน้นที่การเพิ่มบรรทัดธรรมดาให้กับสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามเพื่อปรับปรุงการนำเสนอของคุณด้วยคำแนะนำที่ปฏิบัติตามง่ายนี้
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม .NET
- ติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET ที่ต้องการ
-  ติดตั้ง Aspose.Slides สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
เริ่มต้นด้วยการกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## ขั้นตอนที่ 2: สร้างอินสแตนซ์คลาส PresentationEx
 สร้างอินสแตนซ์ของ`Presentation` คลาสซึ่งเป็นตัวแทนของไฟล์ PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // รหัสของคุณสำหรับขั้นตอนต่อไปจะอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: รับสไลด์แรก
เข้าถึงสไลด์แรกของงานนำเสนอ:
```csharp
ISlide sld = pres.Slides[0];
```
## ขั้นตอนที่ 4: เพิ่มเส้นรูปร่างอัตโนมัติ
เพิ่มเส้นรูปร่างอัตโนมัติให้กับสไลด์:
```csharp
sld.Shapes.AddAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
ปรับพารามิเตอร์ (ซ้าย ด้านบน ความกว้าง ความสูง) ตามความต้องการของคุณ
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขแล้วลงในดิสก์:
```csharp
pres.Save(dataDir + "LineShape1_out.pptx", SaveFormat.Pptx);
```
นี่เป็นการสรุปคำแนะนำทีละขั้นตอนในการเพิ่มบรรทัดธรรมดาให้กับสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET
## บทสรุป
การรวมเส้นเรียบง่ายเข้ากับงานนำเสนอ PowerPoint ของคุณสามารถเพิ่มความดึงดูดสายตาได้อย่างมาก Aspose.Slides สำหรับ .NET มอบวิธีที่ตรงไปตรงมาในการบรรลุเป้าหมายนี้ ทดลองใช้รูปทรงและองค์ประกอบต่างๆ เพื่อสร้างงานนำเสนอที่น่าดึงดูด
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถปรับแต่งรูปลักษณ์ของเส้นได้หรือไม่
ตอบ: ได้ คุณสามารถปรับสี ความหนา และสไตล์ได้โดยใช้ Aspose.Slides API
### ถาม: Aspose.Slides เข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุดหรือไม่
ตอบ: แน่นอน Aspose.Slides รองรับเฟรมเวิร์ก .NET ล่าสุด
### ถาม: ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน
 ตอบ: สำรวจเอกสารประกอบ[ที่นี่](https://reference.aspose.com/slides/net/).
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
 ตอบ: เยี่ยมชม[ที่นี่](https://purchase.aspose.com/temporary-license/) สำหรับใบอนุญาตชั่วคราว
### ถาม: ประสบปัญหาใช่ไหม ฉันจะรับการสนับสนุนได้ที่ไหน?
 ตอบ: ขอความช่วยเหลือเกี่ยวกับ[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
