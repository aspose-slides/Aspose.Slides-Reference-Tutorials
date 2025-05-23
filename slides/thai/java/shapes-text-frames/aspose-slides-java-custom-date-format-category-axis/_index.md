---
"date": "2025-04-17"
"description": "เรียนรู้วิธีปรับแต่งรูปแบบวันที่สำหรับแกนหมวดหมู่โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงแผนภูมิของคุณด้วยการนำเสนอข้อมูลแบบกำหนดเอง ซึ่งเหมาะสำหรับรายงานประจำปีและอื่นๆ อีกมากมาย"
"title": "วิธีการตั้งค่ารูปแบบวันที่แบบกำหนดเองบนแกนหมวดหมู่ใน Aspose.Slides Java | คู่มือการสร้างภาพข้อมูล"
"url": "/th/java/shapes-text-frames/aspose-slides-java-custom-date-format-category-axis/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการตั้งค่ารูปแบบวันที่แบบกำหนดเองบนแกนหมวดหมู่ใน Aspose.Slides Java | คู่มือการสร้างภาพข้อมูล

ในโลกปัจจุบันที่ขับเคลื่อนด้วยข้อมูล การนำเสนอข้อมูลอย่างชัดเจนถือเป็นสิ่งสำคัญสำหรับการตัดสินใจที่มีประสิทธิผล เมื่อสร้างแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java การปรับแต่งรูปแบบวันที่บนแกนหมวดหมู่สามารถปรับปรุงทั้งความเข้าใจและคุณภาพการนำเสนอได้อย่างมาก คู่มือนี้จะแนะนำคุณเกี่ยวกับการตั้งค่ารูปแบบวันที่แบบกำหนดเองใน Aspose.Slides เพื่อปรับปรุงความน่าสนใจทางภาพและความชัดเจนของข้อมูลของสไลด์ของคุณ

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่า Aspose.Slides สำหรับ Java
- การนำรูปแบบวันที่แบบกำหนดเองมาใช้งานบนแกนหมวดหมู่
- การแปลงวันที่ GregorianCalendar เป็นรูปแบบวันที่อัตโนมัติของ OLE
- การประยุกต์ใช้งานจริงของฟีเจอร์เหล่านี้ในสถานการณ์โลกแห่งความเป็นจริง

มาลองดูกันว่าคุณสามารถทำสิ่งนี้ได้อย่างง่ายดายอย่างไร!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม โปรดตรวจสอบว่าคุณได้ครอบคลุมข้อกำหนดเบื้องต้นต่อไปนี้แล้ว:

### ไลบรารีและเวอร์ชันที่จำเป็น:
- **Aspose.Slides สำหรับ Java**คุณต้องใช้เวอร์ชัน 25.4 ขึ้นไป

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม:
- สภาพแวดล้อมการพัฒนาที่มีความสามารถในการรันโค้ด Java (เช่น IntelliJ IDEA, Eclipse หรือ NetBeans)
- Maven หรือ Gradle ที่ถูกกำหนดค่าในโครงการของคุณเพื่อจัดการการอ้างอิง

### ข้อกำหนดความรู้เบื้องต้น:
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- ความคุ้นเคยกับการใช้ส่วนประกอบแผนภูมิภายในงานนำเสนอ

## การตั้งค่า Aspose.Slides สำหรับ Java

หากต้องการใช้งาน Aspose.Slides สำหรับ Java ให้รวม Aspose.Slides เป็นส่วนที่ต้องพึ่งพาในโปรเจ็กต์ของคุณ ด้านล่างนี้คือคำแนะนำในการติดตั้ง:

**เมเวน:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**เกรเดิ้ล:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

อีกทางเลือกหนึ่งคุณสามารถทำได้ [ดาวน์โหลดเวอร์ชันล่าสุด](https://releases.aspose.com/slides/java/) โดยตรงจากเว็บไซต์อย่างเป็นทางการของ Aspose

### การได้มาซึ่งใบอนุญาต:
- **ทดลองใช้งานฟรี**:เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติต่างๆ
- **ใบอนุญาตชั่วคราว**:ขอใบอนุญาตชั่วคราวเพื่อการทดสอบขยายเวลา
- **ซื้อ**:หากต้องการใช้ในระยะยาว โปรดพิจารณาซื้อการสมัครสมาชิก เยี่ยมชม [การซื้อ Aspose](https://purchase.aspose.com/buy) สำหรับรายละเอียดเพิ่มเติม

### การเริ่มต้นขั้นพื้นฐาน:

นี่คือวิธีการเริ่มต้น Aspose.Slides ในโครงการของคุณ:
```java
import com.aspose.slides.Presentation;
// สร้างอินสแตนซ์ของวัตถุการนำเสนอที่แสดงไฟล์การนำเสนอ
Presentation pres = new Presentation();
```

ตอนนี้เรามาดูแก่นของคู่มือนี้กันดีกว่า

## คู่มือการใช้งาน

### การตั้งค่ารูปแบบวันที่สำหรับแกนหมวดหมู่

ฟีเจอร์นี้ช่วยให้คุณปรับแต่งวิธีแสดงวันที่บนแกนหมวดหมู่ของแผนภูมิได้ ด้านล่างนี้เป็นคำแนะนำโดยละเอียด:

#### 1. สร้างการนำเสนอและแผนภูมิใหม่
เริ่มต้นด้วยการสร้างอินสแตนซ์ของ `Presentation` และเพิ่มแผนภูมิพื้นที่ใหม่
```java
import com.aspose.slides.*;
import java.text.ParseException;
import java.util.GregorianCalendar;

public class DateFormatFeature {
    public static void main(String[] args) throws ParseException {
        // การเริ่มต้นการนำเสนอ
        Presentation pres = new Presentation();
        
        try {
            // เพิ่มแผนภูมิพื้นที่ลงในสไลด์แรกที่ตำแหน่งและขนาดที่ระบุ
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);

            // เข้าถึงสมุดงานข้อมูลแผนภูมิสำหรับการจัดการข้อมูลแผนภูมิ
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0); // ล้างข้อมูลที่มีอยู่ทั้งหมดในแผนภูมิ

            // ลบหมวดหมู่และซีรีส์ที่มีอยู่ก่อนหน้านี้ทั้งหมด
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();

            // เพิ่มวันที่ลงในแกนหมวดหมู่โดยใช้วันที่อัตโนมัติ OLE ที่แปลงแล้ว
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

            // สร้างซีรีส์ใหม่และเพิ่มจุดข้อมูลลงไป
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));

            // ตั้งค่าประเภทแกนหมวดหมู่เป็นวันที่และกำหนดค่ารูปแบบตัวเลข
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false); 
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy"); // จัดรูปแบบวันที่เป็นปีเท่านั้น

            // บันทึกการนำเสนอไปยังไดเร็กทอรีที่ระบุ
            pres.save("YOUR_OUTPUT_DIRECTORY/test.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // วันที่ฐานสำหรับการแปลง OLE อัตโนมัติ
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60)); // แปลงเป็นวันที่อัตโนมัติ OLE
        return String.valueOf(oaDate);
    }
}
```

#### 2. การแปลงวันที่ GregorianCalendar เป็นรูปแบบวันที่อัตโนมัติของ OLE

Aspose.Slides ต้องใช้วันที่ในรูปแบบ OLE Automation ซึ่งเป็นรูปแบบวันที่มาตรฐานของ Excel ต่อไปนี้เป็นวิธีแปลง Java ของคุณ `GregorianCalendar` วันที่:
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;
import java.util.concurrent.TimeUnit;

public class OADateConversionFeature {
    public static void main(String[] args) throws ParseException {
        GregorianCalendar date = new GregorianCalendar(2021, 0, 15); // วันที่ 15 มกราคม 2564
        String oaDate = convertToOADate(date);
        System.out.println("OLE Automation Date: " + oaDate); 
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // วันที่ฐานของ Excel สำหรับ OLE Automation
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
    }
}
```

### เคล็ดลับการแก้ไขปัญหา:
- ให้แน่ใจว่าวันที่ฐานสำหรับการแปลง (`30 Dec 1899`) ได้รับการวิเคราะห์อย่างถูกต้อง
- ตรวจสอบว่าสภาพแวดล้อม Java ของคุณรองรับไลบรารีและคลาสที่จำเป็น
- หากปัญหาเกิดขึ้น ให้ตรวจสอบการอัปเดตหรือแพตช์ใดๆ ที่พร้อมใช้งานสำหรับ Aspose.Slides

### การประยุกต์ใช้งานจริง

การกำหนดรูปแบบวันที่เองอาจมีประโยชน์อย่างยิ่งในสถานการณ์เช่น:
- **รายงานประจำปี:** แสดงแนวโน้มข้อมูลรายปีได้อย่างชัดเจน
- **แผนภูมิทางการเงิน:** นำเสนองวดการเงินได้อย่างถูกต้อง
- **กำหนดเวลาโครงการ:** การเน้นกรอบเวลาหรือจุดสำคัญที่เฉพาะเจาะจง

หากทำตามคู่มือนี้ คุณจะสามารถปรับปรุงการนำเสนอของคุณด้วยรูปแบบวันที่ที่แม่นยำและน่าสนใจด้วย Aspose.Slides สำหรับ Java

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}