---
title: การเพิ่มบทช่วยสอนกรอบรูปด้วย Aspose.Slides .NET
linktitle: การเพิ่มกรอบรูปที่มีความสูงสัมพัทธ์ใน Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีการเพิ่มกรอบรูปที่มีความสูงตามมาตราส่วนใน Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อการนำเสนอที่ราบรื่น
weight: 17
url: /th/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
Aspose.Slides สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint ในแอปพลิเคชัน .NET ของตนได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการเพิ่มกรอบรูปที่มีความสูงขนาดสัมพันธ์โดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อพัฒนาทักษะการสร้างการนำเสนอของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา C# ที่ต้องการอื่น ๆ
- เพิ่มไลบรารี Aspose.Slides สำหรับ .NET ในโครงการของคุณ
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณ ขั้นตอนนี้ช่วยให้แน่ใจว่าคุณสามารถเข้าถึงคลาสและฟังก์ชันการทำงานที่ไลบรารี Aspose.Slides มอบให้
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ ตรวจสอบให้แน่ใจว่าได้เพิ่มไลบรารี Aspose.Slides สำหรับ .NET ให้กับโปรเจ็กต์ของคุณโดยการอ้างอิง
## ขั้นตอนที่ 2: โหลดการนำเสนอและรูปภาพ
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    //โหลดรูปภาพที่จะเพิ่มในคอลเลกชันรูปภาพการนำเสนอ
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // -
}
```
ในขั้นตอนนี้ เราสร้างออบเจ็กต์การนำเสนอใหม่และโหลดรูปภาพที่เราต้องการเพิ่มลงในงานนำเสนอ
## ขั้นตอนที่ 3: เพิ่มกรอบรูปเพื่อสไลด์
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
ตอนนี้ เพิ่มกรอบรูปลงในสไลด์แรกของงานนำเสนอ ปรับพารามิเตอร์ เช่น ประเภทรูปร่าง ตำแหน่ง และขนาด ตามความต้องการของคุณ
## ขั้นตอนที่ 4: ตั้งค่าความกว้างและความสูงของสเกลสัมพันธ์
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
ตั้งค่าความสูงและความกว้างของมาตราส่วนสัมพัทธ์สำหรับกรอบรูปเพื่อให้ได้เอฟเฟกต์มาตราส่วนที่ต้องการ
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
สุดท้าย ให้บันทึกงานนำเสนอด้วยกรอบรูปที่เพิ่มเข้ามาในรูปแบบเอาต์พุตที่ระบุ
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มกรอบรูปที่มีความสูงสัมพัทธ์โดยใช้ Aspose.Slides สำหรับ .NET เรียบร้อยแล้ว ทดลองกับรูปภาพ ตำแหน่ง และขนาดต่างๆ เพื่อสร้างงานนำเสนอที่ดึงดูดสายตาซึ่งปรับให้เหมาะกับความต้องการของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
Aspose.Slides รองรับภาษา .NET เป็นหลัก แต่คุณสามารถสำรวจผลิตภัณฑ์ Aspose อื่นๆ เพื่อความเข้ากันได้กับแพลตฟอร์มที่แตกต่างกัน
### ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 อ้างถึง[เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับข้อมูลและตัวอย่างที่ครอบคลุม
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
 ใช่ คุณจะได้รับ[ทดลองฟรี](https://releases.aspose.com/) เพื่อประเมินความสามารถของห้องสมุด
### ฉันจะรับการสนับสนุน Aspose.Slides สำหรับ .NET ได้อย่างไร
 เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อขอความช่วยเหลือจากชุมชนและผู้เชี่ยวชาญของ Aspose
### ฉันจะซื้อ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 คุณสามารถซื้อ Aspose.Slides สำหรับ .NET ได้จาก[หน้าซื้อ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
