---
"description": "เรียนรู้การเพิ่มกรอบรูปที่มีความสูงตามมาตราส่วนสัมพันธ์ใน Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อการนำเสนอที่ราบรื่น"
"linktitle": "การเพิ่มกรอบรูปด้วยความสูงตามมาตราส่วนสัมพันธ์ใน Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "บทช่วยสอนการเพิ่มกรอบรูปด้วย Aspose.Slides .NET"
"url": "/th/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# บทช่วยสอนการเพิ่มกรอบรูปด้วย Aspose.Slides .NET

## การแนะนำ
Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint ในแอปพลิเคชัน .NET ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการเพิ่มกรอบรูปที่มีความสูงตามมาตราส่วนโดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อพัฒนาทักษะการสร้างงานนำเสนอของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา C# อื่น ๆ ที่ต้องการ
- เพิ่มไลบรารี Aspose.Slides สำหรับ .NET ลงในโปรเจ็กต์ของคุณแล้ว
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณ ขั้นตอนนี้จะช่วยให้คุณสามารถเข้าถึงคลาสและฟังก์ชันต่างๆ ที่จัดเตรียมไว้โดยไลบรารี Aspose.Slides ได้
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ อย่าลืมเพิ่มไลบรารี Aspose.Slides สำหรับ .NET ลงในโปรเจ็กต์ของคุณด้วยการอ้างอิง
## ขั้นตอนที่ 2: โหลดงานนำเสนอและรูปภาพ
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // โหลดภาพที่จะเพิ่มเข้าในคอลเลคชันภาพนำเสนอ
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // -
}
```
ในขั้นตอนนี้ เราจะสร้างวัตถุการนำเสนอใหม่และโหลดรูปภาพที่เราต้องการเพิ่มลงในการนำเสนอ
## ขั้นตอนที่ 3: เพิ่มกรอบรูปลงในสไลด์
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
ตอนนี้ เพิ่มกรอบรูปลงในสไลด์แรกของการนำเสนอ ปรับพารามิเตอร์ต่างๆ เช่น ประเภทรูปร่าง ตำแหน่ง และขนาดตามความต้องการของคุณ
## ขั้นตอนที่ 4: ตั้งค่าความกว้างและความสูงตามมาตราส่วน
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
ตั้งค่าความสูงและความกว้างของมาตราส่วนสัมพันธ์ของกรอบรูปเพื่อให้ได้เอฟเฟกต์การปรับขนาดตามที่ต้องการ
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
สุดท้ายให้บันทึกการนำเสนอพร้อมกรอบรูปที่เพิ่มเข้ามาในรูปแบบผลลัพธ์ที่ระบุ
## บทสรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการเพิ่มกรอบรูปที่มีความสูงตามมาตราส่วนสัมพันธ์โดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว ทดลองใช้รูปภาพ ตำแหน่ง และมาตราส่วนต่างๆ เพื่อสร้างงานนำเสนอที่ดึงดูดสายตาซึ่งเหมาะกับความต้องการของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ .NET ร่วมกับภาษาการเขียนโปรแกรมอื่น ๆ ได้หรือไม่
Aspose.Slides รองรับภาษา .NET เป็นหลัก แต่คุณสามารถสำรวจผลิตภัณฑ์ Aspose อื่นๆ เพื่อความเข้ากันได้กับแพลตฟอร์มอื่นๆ ได้
### ฉันสามารถหาเอกสารโดยละเอียดเกี่ยวกับ Aspose.Slides สำหรับ .NET ได้จากที่ไหน
อ้างถึง [เอกสารประกอบ](https://reference.aspose.com/slides/net/) เพื่อดูข้อมูลและตัวอย่างที่ครอบคลุม
### มี Aspose.Slides สำหรับ .NET ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถรับได้ [ทดลองใช้งานฟรี](https://releases.aspose.com/) เพื่อประเมินศักยภาพของห้องสมุด
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
เยี่ยมชม [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อแสวงหาความช่วยเหลือจากชุมชนและผู้เชี่ยวชาญ Aspose
### ฉันสามารถซื้อ Aspose.Slides สำหรับ .NET ได้จากที่ใด
คุณสามารถซื้อ Aspose.Slides สำหรับ .NET ได้จาก [หน้าการซื้อ](https://purchase-aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}