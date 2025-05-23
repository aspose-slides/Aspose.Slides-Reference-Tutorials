---
"date": "2025-04-15"
"description": "เรียนรู้วิธีการทำให้แน่ใจว่าการแสดงผลแบบอักษรมีความสม่ำเสมอเมื่อแปลงงานนำเสนอเป็น HTML โดยใช้ Aspose.Slides สำหรับ .NET โดยการฝังแบบอักษรโดยตรง"
"title": "วิธีเชื่อมโยงแบบอักษรใน HTML โดยใช้ Aspose.Slides สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอน"
"url": "/th/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีเชื่อมโยงแบบอักษรใน HTML โดยใช้ Aspose.Slides สำหรับ .NET

## การแนะนำ

การแปลงงานนำเสนอเป็น HTML ในขณะที่รักษาการแสดงผลแบบอักษรให้สม่ำเสมอในทุกแพลตฟอร์มอาจเป็นเรื่องท้าทาย **Aspose.Slides สำหรับ .NET** นำเสนอโซลูชันที่ราบรื่นโดยให้คุณเชื่อมโยงแบบอักษรทั้งหมดที่ใช้ในการนำเสนอโดยตรงภายในเอาท์พุต HTML ผ่านไฟล์แบบอักษรที่ฝังไว้

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการใช้การเชื่อมโยงแบบอักษรโดยใช้ Aspose.Slides สำหรับ .NET และตรวจสอบความสอดคล้องของการออกแบบในแพลตฟอร์มต่างๆ 

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่าสภาพแวดล้อมของคุณด้วย Aspose.Slides สำหรับ .NET
- การเชื่อมโยงแบบอักษรในการแปลง HTML
- เขียนตัวควบคุมแบบกำหนดเองสำหรับการฝังฟอนต์
- การประยุกต์ใช้งานจริงและการพิจารณาประสิทธิภาพ

มาดูรายละเอียดขั้นตอนที่จำเป็นในการบรรลุเป้าหมายนี้กัน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

### ไลบรารีและการอ้างอิงที่จำเป็น
- **Aspose.Slides สำหรับ .NET** ไลบรารี: ส่วนประกอบหลักสำหรับการใช้งานของเรา

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- สภาพแวดล้อมการพัฒนาที่มีการติดตั้ง .NET Framework หรือ .NET Core

### ข้อกำหนดเบื้องต้นของความรู้
- ความเข้าใจพื้นฐานในการเขียนโปรแกรม C#
- ความคุ้นเคยกับ HTML และ CSS โดยเฉพาะอย่างยิ่ง `@font-face` กฎ.

## การตั้งค่า Aspose.Slides สำหรับ .NET

หากต้องการใช้ Aspose.Slides ในโปรเจ็กต์ .NET คุณจำเป็นต้องติดตั้งไลบรารี ซึ่งมีวิธีการต่างๆ ดังต่อไปนี้:

### การใช้ .NET CLI
```bash
dotnet add package Aspose.Slides
```

### การใช้คอนโซลตัวจัดการแพ็คเกจ
```powershell
Install-Package Aspose.Slides
```

### ผ่าน UI ของตัวจัดการแพ็คเกจ NuGet
- เปิดโปรเจ็กต์ของคุณใน Visual Studio
- ไปที่ "ตัวจัดการแพ็กเกจ NuGet"
- ค้นหา "Aspose.Slides" และติดตั้งเวอร์ชันล่าสุด

### ขั้นตอนการรับใบอนุญาต
คุณสามารถรับใบอนุญาตทดลองใช้งานฟรีเพื่อทดสอบฟีเจอร์ทั้งหมดโดยไม่มีข้อจำกัดได้โดยทำตามขั้นตอนเหล่านี้:
1. **ทดลองใช้งานฟรี**: ดาวน์โหลดใบอนุญาตชั่วคราว [ที่นี่](https://releases-aspose.com/slides/net/).
2. **ใบอนุญาตชั่วคราว**:สมัครขอขยายเวลาการเข้าใช้งาน [ที่นี่](https://purchase-aspose.com/temporary-license/).
3. **ซื้อ**:เพื่อการใช้งานเต็มรูปแบบ โปรดซื้อใบอนุญาต [ที่นี่](https://purchase-aspose.com/buy).

### การเริ่มต้นและการตั้งค่าเบื้องต้น
```csharp
// สร้างอินสแตนซ์ของคลาสใบอนุญาต
easpose.slides.License license = new aspose.slides.License();

// ใช้ใบอนุญาตจากเส้นทางไฟล์
license.SetLicense("Aspose.Slides.lic");
```

## คู่มือการใช้งาน

ตอนนี้เรามาทำการเชื่อมโยงแบบอักษรในการแปลง HTML โดยใช้ **Aspose.Slides สำหรับ .NET**-

### ภาพรวมคุณลักษณะ: การเชื่อมโยงแบบอักษรในการแปลง HTML
คุณสมบัตินี้ช่วยให้แน่ใจว่าแบบอักษรทั้งหมดที่ใช้ในการนำเสนอจะเชื่อมโยงโดยตรงภายในไฟล์ HTML ที่ได้โดยการฝังไฟล์แบบอักษร วิธีการนี้มอบโซลูชันที่มีประสิทธิภาพสำหรับการรักษาความสอดคล้องของการออกแบบในเบราว์เซอร์และแพลตฟอร์มที่แตกต่างกัน

#### ขั้นตอนที่ 1: สร้างตัวควบคุมแบบกำหนดเอง
สร้างคลาสตัวควบคุมแบบกำหนดเอง `LinkAllFontsHtmlController` ซึ่งสืบทอดมาจาก `EmbedAllFontsHtmlController`-
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // ตั้งค่าไดเรกทอรีที่จะเก็บไฟล์ฟอนต์
    }
}
```
#### ขั้นตอนที่ 2: นำวิธีการเขียนแบบอักษรมาใช้
การ `WriteFont` วิธีการเขียนข้อมูลแบบอักษรลงในไฟล์และสร้างโค้ด HTML ที่สอดคล้องกันสำหรับการฝัง:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // กำหนดชื่อแบบอักษรที่จะใช้ โดยเลือกใช้แบบอักษรอื่น ๆ ที่สามารถทดแทนได้หากมี
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // สร้างเส้นทางไฟล์สำหรับไฟล์ฟอนต์ .woff
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // เขียนข้อมูลแบบอักษรไปยังเส้นทางไฟล์ที่ระบุ
    File.WriteAllBytes(path, fontData);

    // สร้างบล็อกสไตล์ HTML โดยฝังแบบอักษรโดยใช้กฎ @font-face
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}