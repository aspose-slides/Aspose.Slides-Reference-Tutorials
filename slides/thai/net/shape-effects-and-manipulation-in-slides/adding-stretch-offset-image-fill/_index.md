---
"description": "เรียนรู้วิธีปรับปรุงการนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนเพื่อเพิ่มการชดเชยการยืดสำหรับการเติมรูปภาพ"
"linktitle": "การเพิ่มออฟเซ็ตการยืดสำหรับการเติมรูปภาพในสไลด์"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การเพิ่มออฟเซ็ตการยืดสำหรับการเติมรูปภาพในงานนำเสนอ PowerPoint"
"url": "/th/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การเพิ่มออฟเซ็ตการยืดสำหรับการเติมรูปภาพในงานนำเสนอ PowerPoint

## การแนะนำ
ในโลกแห่งการนำเสนอที่เปลี่ยนแปลงตลอดเวลา ภาพมีบทบาทสำคัญในการดึงดูดความสนใจของผู้ชม Aspose.Slides สำหรับ .NET ช่วยให้ผู้พัฒนาสามารถปรับปรุงการนำเสนอ PowerPoint ของตนได้ด้วยชุดฟีเจอร์ที่มีประสิทธิภาพ หนึ่งในฟีเจอร์ดังกล่าวก็คือความสามารถในการเพิ่มออฟเซ็ตการยืดภาพเพื่อให้เติมภาพได้ ซึ่งช่วยให้สร้างสไลด์ที่สร้างสรรค์และดึงดูดสายตาได้
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ โปรดแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Aspose.Slides สำหรับไลบรารี .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก [เอกสาร Aspose.Slides สำหรับ .NET](https://reference-aspose.com/slides/net/).
2. สภาพแวดล้อมการพัฒนา: ให้แน่ใจว่าคุณมีการตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ทำงานอยู่
ตอนนี้เรามาเริ่มต้นด้วยคำแนะนำทีละขั้นตอนกันเลย
## นำเข้าเนมสเปซ
ประการแรก นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชัน Aspose.Slides ภายในแอปพลิเคชัน .NET ของคุณ
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโครงการ .NET ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ ตรวจสอบให้แน่ใจว่า Aspose.Slides สำหรับ .NET มีการอ้างอิงอย่างถูกต้อง
## ขั้นตอนที่ 2: เริ่มต้นคลาสการนำเสนอ
สร้างตัวอย่าง `Presentation` คลาสที่จะแสดงไฟล์ PowerPoint
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // รหัสของคุณอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: รับสไลด์แรก
ดึงสไลด์แรกจากการนำเสนอเพื่อใช้งาน
```csharp
ISlide sld = pres.Slides[0];
```
## ขั้นตอนที่ 4: สร้างอินสแตนซ์คลาส ImageEx
สร้างอินสแตนซ์ของ `ImageEx` คลาสสำหรับจัดการรูปภาพที่คุณต้องการเพิ่มลงในสไลด์
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## ขั้นตอนที่ 5: เพิ่มกรอบรูป
การใช้ประโยชน์จาก `AddPictureFrame` วิธีการเพิ่มกรอบรูปลงในสไลด์ ระบุขนาดและตำแหน่งของกรอบ
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขแล้วลงในดิสก์
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
เสร็จเรียบร้อย! คุณได้เพิ่มค่าออฟเซ็ตยืดสำหรับการเติมภาพในสไลด์โดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว
## บทสรุป
การปรับปรุงการนำเสนอ PowerPoint ของคุณเป็นเรื่องง่ายกว่าที่เคยด้วย Aspose.Slides สำหรับ .NET เมื่อทำตามบทช่วยสอนนี้ คุณจะเรียนรู้วิธีการรวมออฟเซ็ตยืดสำหรับการเติมรูปภาพ ซึ่งจะช่วยเพิ่มระดับความคิดสร้างสรรค์ให้กับสไลด์ของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ .NET ในแอพพลิเคชันเว็บของฉันได้หรือไม่
ใช่ Aspose.Slides สำหรับ .NET เหมาะสำหรับทั้งแอพพลิเคชันเดสก์ท็อปและเว็บ
### มี Aspose.Slides สำหรับ .NET ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases-aspose.com/).
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
เยี่ยมชม [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อการสนับสนุนชุมชน
### ฉันสามารถหาเอกสารประกอบฉบับสมบูรณ์สำหรับ Aspose.Slides สำหรับ .NET ได้จากที่ไหน
อ้างถึง [เอกสารประกอบ](https://reference.aspose.com/slides/net/) เพื่อดูข้อมูลโดยละเอียด
### ฉันสามารถซื้อ Aspose.Slides สำหรับ .NET ได้หรือไม่?
ใช่ครับ คุณสามารถซื้อผลิตภัณฑ์ได้ [ที่นี่](https://purchase-aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}