---
"date": "2025-04-16"
"description": "เรียนรู้วิธีการสร้างกราฟิก SmartArt แบบไดนามิกใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET เพิ่มประสิทธิภาพการนำเสนอของคุณด้วยคู่มือที่ครอบคลุมนี้"
"title": "สร้างรูปทรง SmartArt ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอน"
"url": "/th/net/smart-art-diagrams/create-smartart-shapes-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการสร้างรูปทรง SmartArt ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET: คำแนะนำทีละขั้นตอน

## การแนะนำ

ปรับปรุงการนำเสนอ PowerPoint ของคุณโดยผสานกราฟิก SmartArt แบบไดนามิกโดยใช้ C# ด้วย Aspose.Slides สำหรับ .NET คุณสามารถสร้างและจัดการรูปร่าง SmartArt ในสไลด์ของคุณได้อย่างราบรื่น คู่มือนี้จะแนะนำคุณตลอดขั้นตอนการตั้งค่าและการนำ SmartArt ไปใช้กับ Aspose.Slides สำหรับ .NET

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่าสภาพแวดล้อมของคุณด้วย Aspose.Slides สำหรับ .NET
- การสร้างรูปทรง SmartArt ภายในสไลด์ PowerPoint
- การจัดการไดเรกทอรีอย่างมีประสิทธิภาพในโค้ดของคุณ

## ข้อกำหนดเบื้องต้น (H2)

ในการใช้โซลูชันนี้อย่างประสบความสำเร็จ ให้แน่ใจว่าคุณมี:
- **ห้องสมุดที่จำเป็น**: Aspose.Slides สำหรับ .NET (แนะนำเวอร์ชัน 21.11 ขึ้นไป)
- **สภาพแวดล้อมการพัฒนา**: .NET Core หรือ .NET Framework
- **ความรู้พื้นฐาน**: ความคุ้นเคยกับ C# และการทำงานของระบบไฟล์

## การตั้งค่า Aspose.Slides สำหรับ .NET (H2)

### การติดตั้ง

เริ่มต้นด้วยการติดตั้ง Aspose.Slides โดยใช้หนึ่งในวิธีต่อไปนี้:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**คอนโซลตัวจัดการแพ็คเกจใน Visual Studio**
```powershell
Install-Package Aspose.Slides
```

**UI ตัวจัดการแพ็กเกจ NuGet**
1. เปิดตัวจัดการแพ็กเกจ NuGet
2. ค้นหา "Aspose.Slides" และติดตั้งเวอร์ชันล่าสุด

### การขอใบอนุญาต
- **ทดลองใช้งานฟรี**:ดาวน์โหลดใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อประเมินศักยภาพทั้งหมดของ Aspose.Slides
- **ซื้อ**:เพื่อใช้งานอย่างต่อเนื่อง โปรดซื้อใบอนุญาตผ่าน [ลิงค์นี้](https://purchase-aspose.com/buy).

เมื่อคุณมีไฟล์ใบอนุญาตแล้ว ให้เริ่มต้นใช้งานในแอปพลิเคชันของคุณดังนี้:
```csharp
License license = new License();
license.SetLicense("Aspose.Slides.lic");
```

## คู่มือการใช้งาน (H2)

### คุณสมบัติ: สร้างรูปทรง SmartArt (H2)

คุณลักษณะนี้ช่วยให้คุณสามารถเพิ่มกราฟิก SmartArt ที่น่าสนใจให้กับสไลด์ PowerPoint ของคุณได้โดยผ่านโปรแกรม

#### ภาพรวมของกระบวนการ (H3)
เราจะเริ่มต้นด้วยการตั้งค่าไดเร็กทอรี การสร้างวัตถุการนำเสนอ และจากนั้นการเพิ่มรูปร่าง SmartArt

#### โค้ดสาธิตการใช้งาน (H3)
1. **การจัดการไดเรกทอรี**
   ตรวจสอบให้แน่ใจว่าไดเร็กทอรีเอกสารของคุณมีอยู่หรือสร้างขึ้นใหม่หากจำเป็น:
   ```csharp
   string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // กำหนดเส้นทางไดเรกทอรีเอกสารเป้าหมาย
   bool isExists = Directory.Exists(dataDir); // ตรวจสอบว่าไดเร็กทอรีมีอยู่หรือไม่
   if (!isExists) 
       Directory.CreateDirectory(dataDir); // สร้างไดเรกทอรีหากไม่มีอยู่
   ```

2. **การสร้างงานนำเสนอใหม่**
   เริ่มต้นการนำเสนอใหม่และเข้าถึงสไลด์แรก:
   ```csharp
   using (Presentation pres = new Presentation())
   {
       ISlide slide = pres.Slides[0]; // เข้าถึงสไลด์แรก
   ```
   
3. **การเพิ่ม SmartArt ลงในสไลด์**
   เพิ่มรูปร่าง SmartArt ในพิกัดที่ระบุพร้อมขนาดและประเภทเค้าโครงที่ต้องการ:
   ```csharp
   // เพิ่มรูปร่าง SmartArt โดยใช้เค้าโครง BasicBlockList
   ISmartArt smart = slide.Shapes.AddSmartArt(0, 0, 400, 400, SmartArtLayoutType.BasicBlockList);
   ```

4. **การบันทึกการนำเสนอ**
   สุดท้ายให้บันทึกการนำเสนอของคุณไปยังไดเร็กทอรีที่ต้องการ:
   ```csharp
   pres.Save(dataDir + "SimpleSmartArt_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}