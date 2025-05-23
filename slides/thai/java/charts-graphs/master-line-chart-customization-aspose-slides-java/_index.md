---
"date": "2025-04-17"
"description": "เรียนรู้วิธีการสร้างและปรับแต่งแผนภูมิเส้นใน Java โดยใช้ Aspose.Slides คู่มือนี้ครอบคลุมถึงองค์ประกอบ เครื่องหมาย ป้ายกำกับ และรูปแบบของแผนภูมิสำหรับการนำเสนอแบบมืออาชีพ"
"title": "การปรับแต่งแผนภูมิเส้นหลักใน Java ด้วย Aspose.Slides"
"url": "/th/java/charts-graphs/master-line-chart-customization-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เรียนรู้การปรับแต่งแผนภูมิเส้นใน Java ด้วย Aspose.Slides

## การแนะนำ

การสร้างงานนำเสนอระดับมืออาชีพที่ผสมผสานความชัดเจนของข้อมูลเข้ากับความน่าสนใจทางภาพอาจเป็นเรื่องท้าทาย โดยเฉพาะอย่างยิ่งเมื่อต้องปรับแต่งแผนภูมิเส้นในแอปพลิเคชัน Java คู่มือนี้จะช่วยให้คุณเชี่ยวชาญการใช้ "Aspose.Slides for Java" เพื่อสร้างและปรับแต่งแผนภูมิเส้นได้อย่างง่ายดาย คุณจะได้เรียนรู้วิธีปรับปรุงองค์ประกอบแผนภูมิ เช่น ชื่อเรื่อง คำอธิบาย แกน เครื่องหมาย ป้ายกำกับ สี สไตล์ และอื่นๆ

**สิ่งที่คุณจะได้เรียนรู้:**
- สร้างแผนภูมิเส้นโดยใช้ Aspose.Slides สำหรับ Java
- ปรับแต่งองค์ประกอบแผนภูมิ เช่น ชื่อ คำอธิบาย และแกน
- ปรับเครื่องหมายชุด ป้าย สีเส้น และสไตล์
- บันทึกการนำเสนอของคุณพร้อมการแก้ไขทั้งหมด

ก่อนที่จะเริ่มดำเนินการ เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกอย่างพร้อมสำหรับการเริ่มต้นเสียก่อน

## ข้อกำหนดเบื้องต้น

หากต้องการติดตาม โปรดแน่ใจว่าคุณมี:

- **ห้องสมุดที่จำเป็น:** คุณต้องมี Aspose.Slides สำหรับ Java เราขอแนะนำให้ใช้เวอร์ชัน 25.4
- **การตั้งค่าสภาพแวดล้อม:** สภาพแวดล้อม Java ของคุณควรได้รับการกำหนดค่าอย่างถูกต้องด้วย JDK16 หรือใหม่กว่า
- **ข้อกำหนดความรู้เบื้องต้น:** ความคุ้นเคยกับการเขียนโปรแกรม Java และแนวคิดการทำแผนภูมิขั้นพื้นฐานจะเป็นประโยชน์

## การตั้งค่า Aspose.Slides สำหรับ Java

เริ่มต้นด้วยการรวม Aspose.Slides เข้ากับโปรเจ็กต์ของคุณ ต่อไปนี้คือวิธีการดำเนินการโดยใช้เครื่องมือสร้างต่างๆ:

### เมเวน
เพิ่มการอ้างอิงนี้ในของคุณ `pom.xml`-
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### แกรเดิล
รวมไว้ในของคุณ `build.gradle`-
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
หรือดาวน์โหลดเวอร์ชันล่าสุดได้จาก [Aspose.Slides สำหรับการเปิดตัว Java](https://releases-aspose.com/slides/java/).

#### การขอใบอนุญาต
- **ทดลองใช้งานฟรี:** เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติต่างๆ
- **ใบอนุญาตชั่วคราว:** รับใบอนุญาตชั่วคราวเพื่อการเข้าถึงแบบเต็มรูปแบบโดยไม่มีข้อจำกัด
- **ซื้อ:** พิจารณาซื้อใบอนุญาตเพื่อใช้งานอย่างต่อเนื่อง

เริ่มการใช้งานสภาพแวดล้อมของคุณโดยตั้งค่า Aspose.Slides เพื่อให้แน่ใจว่าไลบรารีได้รับการกำหนดค่าอย่างถูกต้องในโครงการของคุณ

## คู่มือการใช้งาน

มาแบ่งกระบวนการสร้างและปรับแต่งแผนภูมิเส้นด้วย Aspose.Slides สำหรับ Java ออกเป็นฟีเจอร์ที่แตกต่างกัน

### การสร้างและกำหนดค่าแผนภูมิเส้น

#### ภาพรวม
เริ่มต้นด้วยการเพิ่มสไลด์ใหม่ลงในงานนำเสนอของคุณและแทรกแผนภูมิเส้นพร้อมเครื่องหมาย

```java
import com.aspose.slides.*;

// เริ่มต้นการนำเสนอคลาส
class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            // เข้าถึงสไลด์แรก
            ISlide slide = pres.getSlides().get_Item(0);
            
            // เพิ่มแผนภูมิเส้นพร้อมเครื่องหมาย
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

โค้ดนี้จะเริ่มต้นการนำเสนอและเพิ่มแผนภูมิเส้นลงในสไลด์แรก พารามิเตอร์จะระบุประเภทแผนภูมิและตำแหน่งบนสไลด์

### ซ่อนชื่อแผนภูมิ

#### ภาพรวม
บางครั้ง การลบชื่อแผนภูมิออกอาจทำให้ภาพดูสะอาดขึ้น

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // ซ่อนชื่อแผนภูมิ
            chart.getTitleFormat().setVisible(false);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

สไนปเป็ตนี้จะซ่อนชื่อแผนภูมิโดยตั้งค่าการมองเห็นเป็นเท็จ

### ซ่อนแกนค่าและหมวดหมู่

#### ภาพรวม
หากต้องการการออกแบบที่เรียบง่าย คุณอาจต้องการซ่อนทั้งสองแกน

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // ซ่อนแกนแนวตั้งและแนวนอน
            chart.getAxes().getVerticalAxis().setVisible(false);
            chart.getAxes().getHorizontalAxis().setVisible(false);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

โค้ดนี้จะตั้งค่าการมองเห็นของทั้งสองแกนเป็นเท็จ

### ซ่อนคำอธิบายแผนภูมิ

#### ภาพรวม
ลบคำอธิบายเพื่อเน้นที่ข้อมูลโดยตรง

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // ซ่อนตำนาน
            chart.setHasLegend(false);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

สไนปเป็ตนี้ซ่อนคำอธิบายแผนภูมิ

### ซ่อนเส้นกริดหลักบนแกนแนวนอน

#### ภาพรวม
ลบเส้นกริดหลักออกเพื่อให้ดูสะอาดขึ้น

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // ตั้งค่าเส้นกริดหลักเป็น 'ไม่เติม'
            chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat()
                .getLine().getFillFormat().setFillType(FillType.NoFill);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

โค้ดนี้จะซ่อนเส้นกริดหลักโดยตั้งค่าประเภทการเติมเป็น `NoFill`-

### ลบซีรีส์ทั้งหมดออกจากแผนภูมิ

#### ภาพรวม
ล้างชุดข้อมูลทั้งหมดเพื่อเริ่มต้นใหม่

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // ลบซีรีส์ทั้งหมดออกจากแผนภูมิ
            for (int i = chart.getChartData().getSeries().size() - 1; i >= 0; i--) {
                chart.getChartData().getSeries().removeAt(i);
            }
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

สไนปเป็ตนี้จะลบซีรีส์ที่มีอยู่ทั้งหมดออกจากแผนภูมิ

### กำหนดค่าเครื่องหมายและป้ายกำกับชุด

#### ภาพรวม
ปรับแต่งเครื่องหมายและป้ายข้อมูลเพื่อให้แสดงข้อมูลได้ดีขึ้น

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // กำหนดค่าเครื่องหมายและป้ายกำกับสำหรับซีรีส์แรก
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "A1", "Sample Series"), chart.getType());
            series.getMarkerStyleType() = MarkerStyleType.Circle;
            for (int i = 0; i < series.getDataPoints().size(); i++) {
                IDataLabel lbl = series.getDataPoints().get_Item(i).getDataPointLevels().get(0).getLabel();
                lbl.getDataLabelFormat().setShowValue(true);
            }
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

โค้ดนี้กำหนดค่าเครื่องหมายและป้ายกำกับให้กับชุดข้อมูลในแผนภูมิ

### บันทึกการนำเสนอของคุณ

หลังจากปรับแต่งทั้งหมดแล้ว ให้บันทึกการนำเสนอของคุณเพื่อเก็บรักษาการเปลี่ยนแปลง

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // ปรับแต่งแผนภูมิ...

            // บันทึกการนำเสนอ
            pres.save("CustomizedLineChart.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

รหัสนี้จะบันทึกการนำเสนอที่คุณปรับแต่งเป็นไฟล์ PPTX

## บทสรุป

หากทำตามคำแนะนำนี้ คุณจะสามารถใช้ Aspose.Slides สำหรับ Java เพื่อสร้างและปรับแต่งแผนภูมิเส้นในงานนำเสนอของคุณได้อย่างมีประสิทธิภาพ ทดลองใช้องค์ประกอบและรูปแบบแผนภูมิต่างๆ เพื่อเพิ่มความสวยงามให้กับข้อมูลของคุณ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}