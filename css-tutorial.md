# ใบงานการทดลอง: พื้นฐานการจัดการรูปแบบเว็บไซต์ด้วย CSS
[](#การทดลองที่-1-ทำความรู้จักกับ-css)
## การทดลองที่ 1: ทำความรู้จักกับ CSS

### 1.1 วิธีการใช้งาน CSS
CSS สามารถใช้งานได้ 3 วิธี:

1. **Inline CSS**:
```html
<p style="color: blue; font-size: 16px;">ข้อความสีน้ำเงิน</p>
```

2. **Internal CSS**:
```html
<head>
    <style>
        p {
            color: blue;
            font-size: 16px;
        }
    </style>
</head>
```

3. **External CSS**:
```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

### ตัวอย่างการใช้งาน: การสร้างปุ่มสไตล์ต่างๆ

```html
<!-- ไฟล์ index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>ตัวอย่างปุ่ม CSS</title>
    <!-- Internal CSS -->
    <style>
        .btn-primary {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
    <!-- External CSS -->
    <link rel="stylesheet" href="css/buttons.css">
</head>
<body>
    <!-- Inline CSS -->
    <button style="background-color: #dc3545; color: white; padding: 10px 20px;">ปุ่มแบบ Inline</button>
    
    <!-- Internal CSS -->
    <button class="btn-primary">ปุ่มแบบ Internal</button>
    
    <!-- External CSS -->
    <button class="btn-success">ปุ่มแบบ External</button>
</body>
</html>
```

```css
/* สร้างไฟล์ buttons.css ในโฟลเดอร์ css */
.btn-success {
    background-color: #28a745;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
```
[](#การทดลองที่-2-selectors-ใน-CSS)
## การทดลองที่ 2: Selectors ใน CSS
CSS Selector คือวิธีการระบุหรือเลือกองค์ประกอบ (elements) ที่เราต้องการจัดรูปแบบใน HTML โดยมีประเภทหลัก ๆ ดังนี้:

1. **Element Selector** - เลือกโดยใช้ชื่อ element
```css
p { color: red; }  /* เลือกทุก <p> elements */
h1 { color: blue; }  /* เลือกทุก <h1> elements */
```

2. **Class Selector** - เลือกโดยใช้ชื่อ class (ขึ้นต้นด้วย .)
```css
.menu { color: green; }  /* เลือก elements ที่มี class="menu" */
.highlight { background: yellow; }
```

3. **ID Selector** - เลือกโดยใช้ ID (ขึ้นต้นด้วย #)
```css
#header { background: black; }  /* เลือก element ที่มี id="header" */
#logo { width: 100px; }
```

4. **Descendant Selector** - เลือก elements ที่เป็นลูกหลาน
```css
div p { color: blue; }  /* เลือก <p> ที่อยู่ภายใน <div> */
```

5. **Child Selector** - เลือก elements ที่เป็นลูกโดยตรง (>)
```css
div > p { color: red; }  /* เลือก <p> ที่เป็นลูกโดยตรงของ <div> */
```

6. **Pseudo-class** - เลือกสถานะพิเศษ
```css
a:hover { color: red; }  /* เมื่อเมาส์ชี้ */
input:focus { border: blue; }  /* เมื่อได้รับการโฟกัส */
```

7. **Multiple Selector** - เลือกหลายอย่างพร้อมกัน
```css
h1, h2, h3 { color: purple; }
```

8. **Universal Selector** - เลือกทุก elements (*)
```css
* { margin: 0; padding: 0; }
```

9. **Attribute Selector** - เลือกตาม attribute
```css
input[type="text"] { border: 1px solid gray; }
```

10. **Adjacent Sibling Selector** - เลือกธาตุที่อยู่ถัดไป (+)
```css
h1 + p { margin-top: 20px; }
```

ความสำคัญของ Selector:
- ช่วยให้เราสามารถกำหนดสไตล์ให้กับ elements ที่ต้องการได้อย่างเฉพาะเจาะจง
- ช่วยในการจัดการและบำรุงรักษาโค้ด CSS
- ทำให้สามารถสร้างรูปแบบที่ซับซ้อนได้
- ช่วยลดการเขียนโค้ดซ้ำซ้อน
  
### 2.1 ประเภทของ Selectors
```css
/* Element Selector */
p {
    color: blue;
}

/* Class Selector */
.highlight {
    background-color: yellow;
}

/* ID Selector */
#header {
    font-size: 24px;
}

/* Descendant Selector */
div p {
    margin: 10px;
}

/* Child Selector */
div > p {
    padding: 5px;
}
```

### ตัวอย่างการใช้งาน: การสร้างเมนูนำทาง

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        /* การใช้ Element Selector */
        nav {
            background-color: #333;
            padding: 15px;
        }

        /* การใช้ Descendant Selector */
        nav ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
        }

        /* การใช้ Child Selector */
        nav > ul > li {
            margin: 0 10px;
        }

        /* การใช้ Class Selector */
        .menu-item {
            color: white;
            text-decoration: none;
            padding: 5px 10px;
        }

        /* การใช้ Pseudo-class */
        .menu-item:hover {
            background-color: #555;
            border-radius: 3px;
        }

        /* การใช้ ID Selector */
        #active {
            background-color: #007bff;
            border-radius: 3px;
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item" id="active">หน้าแรก</a></li>
            <li><a href="#" class="menu-item">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</body>
</html>
```
### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. แก้ไขให้เมนูถูกเลือกที่ สินค้า
3. เปลี่ยนสีพื้นหลังของเมนู

### ผลการทดลอง
```html
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>เมนูนำทาง</title>
    <link rel="stylesheet" href="styles.css"> <!-- ลิงก์ไปยังไฟล์ CSS ภายนอก -->
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item" id="active"a>สินค้า</a></li> <!-- เปลี่ยน active มาที่สินค้า -->
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</body>
</html>


```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1920" alt="ภาพถ่ายหน้าจอ 2568-02-23 เวลา 01 47 55" src="https://github.com/user-attachments/assets/b302e431-53bb-409d-b2b4-94cd0a7bc969" />

[](#การทดลองที่-3-การจัดการสีและพื้นหลัง)
## การทดลองที่ 3: การจัดการสีและพื้นหลัง

### 3.1 การกำหนดสีและพื้นหลัง
```css
/* สีพื้นฐาน */
color: red;
color: #FF0000;
color: rgb(255, 0, 0);
color: rgba(255, 0, 0, 0.5);

/* พื้นหลัง */
background-color: #f0f0f0;
background-image: url('image.jpg');
background-size: cover;
```

### ตัวอย่างการใช้งาน: การสร้างการ์ดสินค้า

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .product-card {
            width: 300px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            background-color: white;
        }

        .product-image {
            width: 100%;
            height: 200px;
            background-image: url('product.jpg');
            background-size: cover;
            background-position: center;
        }

        .product-info {
            padding: 15px;
        }

        .product-title {
            color: #333;
            font-size: 18px;
            margin-bottom: 10px;
        }

        .product-price {
            color: #007bff;
            font-size: 24px;
            font-weight: bold;
        }

        .product-description {
            color: #666;
            font-size: 14px;
            line-height: 1.5;
        }

        .product-button {
            display: block;
            background: linear-gradient(to right, #007bff, #0056b3);
            color: white;
            text-align: center;
            padding: 10px;
            text-decoration: none;
            margin-top: 15px;
            border-radius: 4px;
        }

        .product-button:hover {
            background: linear-gradient(to right, #0056b3, #003980);
        }
    </style>
</head>
<body>
    <div class="product-card">
        <div class="product-image"></div>
        <div class="product-info">
            <h2 class="product-title">สินค้าตัวอย่าง</h2>
            <p class="product-price">฿1,999</p>
            <p class="product-description">
                รายละเอียดสินค้าตัวอย่าง ที่มีความน่าสนใจและน่าใช้งาน
            </p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. แก้ไขให้แสดงรูปสินค้า โดยให้รูปสินค้าเก็บอยู่ในโฟลเดอร์ images
3. เพิ่มเติมให้มี card แสดงข้อมูลสินค้า 4 รูป

### ผลการทดลอง
```html
</style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item" id="active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>

    <h1>แกลเลอรีสินค้า</h1>
    <div class="gallery">
        <div class="card">
            <img src="images/PANDORA1.jpg" alt="necklace">
            <div class="card-content">
                <h3>necklace</h3>
                <p>สร้อยคอรูปหัวใจสีทองประดับด้วยเพชร</p>
                <a href="images/PANDORA1.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA2.jpg" alt="bracelet">
            <div class="card-content">
                <h3>bracelet</h3>
                <p>สร้อยข้อมือสีเงินรูปหัวใจ</p>
                <a href="images/PANDORA2.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA3.jpg" alt="earring">
            <div class="card-content">
                <h3>earring</h3>
                <p>ต่างหูรูปหัวใจสีเงินประดับด้วยเพชร</p>
                <a href="images/PANDORA3.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA4.jpg" alt="ring">
            <div class="card-content">
                <h3>ring</h3>
                <p>แหวนสีเงินประดับด้วยเพชร</p>
                <a href="images/PANDORA4.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>
    </div>

    <a href="#" class="back-to-top">กลับไปข้างบน</a>
</body>
</html>

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![image](https://github.com/user-attachments/assets/0c67d534-57a7-4c9d-b297-a284d1b911a7)

[](#การทดลองที่-4-การจัดการขนาดและระยะห่าง)
## การทดลองที่ 4: การจัดการขนาดและระยะห่าง

### 4.1 หน่วยวัดและ Box Model
```css
/* หน่วยวัด */
width: 100px;
width: 50%;
font-size: 1.2rem;
height: 100vh;

/* Box Model */
padding: 10px;
margin: 15px;
border: 1px solid black;
```

### ตัวอย่างการใช้งาน: การสร้างส่วนแสดงสถิติ

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .stats-container {
            display: flex;
            justify-content: space-around;
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1rem;
        }

        .stat-box {
            flex: 1;
            margin: 0 15px;
            padding: 2rem;
            text-align: center;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: #007bff;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 1rem;
            color: #666;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .stats-container {
                flex-direction: column;
            }

            .stat-box {
                margin: 1rem 0;
            }
        }
    </style>
</head>
<body>
    <div class="stats-container">
        <div class="stat-box">
            <div class="stat-number">1,234</div>
            <div class="stat-label">ผู้ใช้งาน</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">5.6K</div>
            <div class="stat-label">ยอดขาย</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">98%</div>
            <div class="stat-label">ความพึงพอใจ</div>
        </div>
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่ง ขนาดต่าง ๆ ของ Box model, ขนาดและฟอนต์ตัวหนังสือ, สี


### ผลการทดลอง
```html
</style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item" id="active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>

    <h1>แกลเลอรีสินค้า</h1>
    <div class="gallery">
        <div class="card">
            <img src="images/PANDORA1.jpg" alt="necklace">
            <div class="card-content">
                <h3>necklace</h3>
                <p>สร้อยคอรูปหัวใจสีทองประดับด้วยเพชร</p>
                <a href="images/PANDORA1.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA2.jpg" alt="bracelet">
            <div class="card-content">
                <h3>bracelet</h3>
                <p>สร้อยข้อมือสีเงินรูปหัวใจ</p>
                <a href="images/PANDORA2.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA3.jpg" alt="earring">
            <div class="card-content">
                <h3>earring</h3>
                <p>ต่างหูรูปหัวใจสีเงินประดับด้วยเพชร</p>
                <a href="images/PANDORA3.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA4.jpg" alt="ring">
            <div class="card-content">
                <h3>ring</h3>
                <p>แหวนสีเงินประดับด้วยเพชร</p>
                <a href="images/PANDORA4.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>
    </div>

    <a href="#" class="back-to-top">กลับไปข้างบน</a>
</body>
</html>  
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item" id="active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>

    <h1>แกลเลอรีสินค้า</h1>
    <div class="gallery">
        <div class="card">
            <img src="images/PANDORA1.jpg" alt="necklace">
            <div class="card-content">
                <h3>necklace</h3>
                <p>สร้อยคอรูปหัวใจสีทองประดับด้วยเพชร</p>
                <a href="images/PANDORA1.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA2.jpg" alt="bracelet">
            <div class="card-content">
                <h3>bracelet</h3>
                <p>สร้อยข้อมือสีเงินรูปหัวใจ</p>
                <a href="images/PANDORA2.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA3.jpg" alt="earring">
            <div class="card-content">
                <h3>earring</h3>
                <p>ต่างหูรูปหัวใจสีเงินประดับด้วยเพชร</p>
                <a href="images/PANDORA3.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA4.jpg" alt="ring">
            <div class="card-content">
                <h3>ring</h3>
                <p>แหวนสีเงินประดับด้วยเพชร</p>
                <a href="images/PANDORA4.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>
    </div>

    <a href="#" class="back-to-top">กลับไปข้างบน</a>
</body>
</html>


```
```css
@import url('https://fonts.google.com/specimen/Cormorant+Garamond?query=Cormorant+Garamond');
/* รีเซ็ตค่าพื้นฐาน */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: 'Cormorant Garamond', sans-serif; /* ใช้ฟอนต์ Cormorant Garamond */
}

/* ตั้งค่าพื้นฐาน */
body {
    background-color: #f4f4f4;
    color: #333;
    font-size: 18px;
    line-height: 1.6;
    padding: 20px;
}
        /* สไตล์เมนูนำทาง */
        nav {
            background-color: #333;
            padding: 15px;
            display: flex;
        }
        nav ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
        }
        nav ul li {
            margin: 0 10px;
        }
        .menu-item {
            color: white;
            text-decoration: none;
            padding: 5px 10px;
        }
        .menu-item:hover, #active {
            background-color: #f47ef4;
            border-radius: 3px;
        }

        /* สไตล์แกลเลอรีสินค้า */
        .gallery {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin: 20px;
        }
        .card {
            border: 1px solid #ddd;
            padding: 15px;
            width: 250px;
            text-align: center;
            border-radius: 5px;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .card img {
            max-width: 100%;
            height: 200px; /* กำหนดความสูงเท่ากัน */
            object-fit: cover;
        }
        .card-content {
            flex-grow: 1;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .btn {
            display: block;
            margin-top: auto;
            padding: 8px;
            background-color: #e573e5;
            color: white;
            text-decoration: none;
            border-radius: 3px;
        }
        .btn:hover {
            background-color: #c35ac3;
        }
        .back-to-top {
            display: block;
            margin-top: 20px;
            text-align: center;
            color: #ee82ee;
            text-decoration: none;
            font-weight: bold;
        }
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![image](https://github.com/user-attachments/assets/568105da-c090-426a-868e-fcbb4db1e345)
[](#การทดลองที่-5-การจัดการข้อความและฟอนต์)
## การทดลองที่ 5: การจัดการข้อความและฟอนต์

### 5.1 การจัดการข้อความและฟอนต์
```css
/* การจัดการข้อความ */
text-align: center;
text-decoration: none;
text-transform: uppercase;
line-height: 1.5;

/* การจัดการฟอนต์ */
font-family: 'Arial', sans-serif;
font-size: 16px;
font-weight: bold;
```

### ตัวอย่างการใช้งาน: การสร้างบทความบล็อก

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .blog-post {
            max-width: 800px;
            margin: 2rem auto;
            padding: 0 1rem;
            font-family: 'Sarabun', sans-serif;
        }

        .post-header {
            text-align: center;
            margin-bottom: 2rem;
        }

        .post-title {
            font-size: 2.5rem;
            color: #333;
            margin-bottom: 0.5rem;
            line-height: 1.2;
        }

        .post-meta {
            color: #666;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .post-content {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #444;
        }

        .post-content p {
            margin-bottom: 1.5rem;
        }

        .post-content h2 {
            font-size: 1.8rem;
            color: #333;
            margin: 2rem 0 1rem;
        }

        blockquote {
            font-style: italic;
            border-left: 4px solid #007bff;
            margin: 1.5rem 0;
            padding-left: 1rem;
            color: #555;
        }

        @media (max-width: 768px) {
            .post-title {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <article class="blog-post">
        <header class="post-header">
            <h1 class="post-title">วิธีการเขียนบทความที่น่าสนใจ</h1>
            <div class="post-meta">โพสต์เมื่อ 1 มกราคม 2025 | โดย ผู้เขียน</div>
        </header>
        
        <div class="post-content">
            <p>เนื้อหาบทความที่ดีควรมีความน่าสนใจและเป็นประโยชน์ต่อผู้อ่าน การเขียนบทความให้น่าอ่านนั้นมีหลักการสำคัญหลายประการ</p>

            <h2>1. การเลือกหัวข้อที่น่าสนใจ</h2>
            <p>หัวข้อที่ดีควรตรงกับความสนใจของกลุ่มเป้าหมาย และมีประโยชน์ต่อผู้อ่าน</p>

            <blockquote>
                "การเขียนที่ดีไม่ได้เกิดจากพรสวรรค์เพียงอย่างเดียว แต่เกิดจากการฝึกฝนอย่างสม่ำเสมอ"
            </blockquote>

            <h2>2. การจัดโครงสร้างเนื้อหา</h2>
            <p>เนื้อหาที่ดีควรมีการจัดลำดับที่เป็นระบบ เข้าใจง่าย และมีความต่อเนื่อง</p>
        </div>
    </article>
</body>
</html>
```
### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่งรูปแบบ สีและขนาด font

### ผลการทดลอง
```html
</style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item" id="active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>

    <h1>แกลเลอรีสินค้า</h1>
    <div class="gallery">
        <div class="card">
            <img src="images/PANDORA1.jpg" alt="necklace">
            <div class="card-content">
                <h3>necklace</h3>
                <p>สร้อยคอรูปหัวใจสีทองประดับด้วยเพชร</p>
                <a href="images/PANDORA1.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA2.jpg" alt="bracelet">
            <div class="card-content">
                <h3>bracelet</h3>
                <p>สร้อยข้อมือสีเงินรูปหัวใจ</p>
                <a href="images/PANDORA2.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA3.jpg" alt="earring">
            <div class="card-content">
                <h3>earring</h3>
                <p>ต่างหูรูปหัวใจสีเงินประดับด้วยเพชร</p>
                <a href="images/PANDORA3.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA4.jpg" alt="ring">
            <div class="card-content">
                <h3>ring</h3>
                <p>แหวนสีเงินประดับด้วยเพชร</p>
                <a href="images/PANDORA4.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>
    </div>

    <a href="#" class="back-to-top">กลับไปข้างบน</a>
</body>
</html>  

```
```css
 @import url('https://fonts.google.com/specimen/Cormorant+Garamond?query=Cormorant+Garamond');
/* รีเซ็ตค่าพื้นฐาน */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: 'Cormorant Garamond', sans-serif; /* ใช้ฟอนต์ Cormorant Garamond */
}

/* ตั้งค่าพื้นฐาน */
body {
    background-color: #fff9f9;
    color: #333;
    font-size: 18px;
    line-height: 1.6;
    padding: 20px;
}
        /* สไตล์เมนูนำทาง */
        nav {
            background-color: #333;
            padding: 15px;
            display: flex;
        }
        nav ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
        }
        nav ul li {
            margin: 0 15px;
        }
        .menu-item {
            color: white;
            text-decoration: none;
            padding: 5px 10px;
            border-radius: 6px;
            font-size: 18px;
            font-weight: 600;
            transition: background 0.3s ease, color 0.3s ease;
        }
        .menu-item:hover, #active {
            background-color: #f47ef4;
            border-radius: 3px;
        }
        h1 {
             text-align: center;
            font-size: 36px;
            font-weight: bold;
             color: #2c3e50;
             margin-top: 20px;
}

        /* สไตล์แกลเลอรีสินค้า */
        .gallery {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin: 20px;
        }
        .card {
            border: 1px solid #ffffff;
            padding: 15px;
            width: 250px;
            text-align: center;
            border-radius: 5px;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .card img {
            max-width: 100%;
            height: 200px; /* กำหนดความสูงเท่ากัน */
            object-fit: cover;
         /* ข้อความภายในการ์ด */
.card-content {
    padding: 20px;
}

.card-content h3 {
    font-size: 22px;
    font-weight: bold;
    color: #2c3e50;
    margin-bottom: 12px;
}

.card-content p {
    font-size: 17px;
    color: #7f8c8d;
    margin-bottom: 15px;
}

/* ปุ่ม "ดูรายละเอียด" */
.card-content a.btn {
    display: inline-block;
    background: #ad0783;
    color: white;
    padding: 12px 20px;
    border-radius: 6px;
    text-decoration: none;
    font-weight: bold;
    font-size: 18px;
    transition: background 0.3s ease, transform 0.2s ease;
}

.card-content a.btn:hover {
    background: #731abc;
  /* ข้อความภายในการ์ด */
.card-content {
    padding: 20px;
}

.card-content h3 {
    font-size: 22px;
    font-weight: bold;
    color: #2c3e50;
    margin-bottom: 12px;
}

.card-content p {
    font-size: 17px;
    color: #7f8c8d;
    margin-bottom: 15px;
}

/* ปุ่ม "ดูรายละเอียด" */
.card-content a.btn {
    display: inline-block;
    background: #ad0783;
    color: white;
    padding: 12px 20px;
    border-radius: 6px;
    text-decoration: none;
    font-weight: bold;
    font-size: 18px;
    transition: background 0.3s ease, transform 0.2s ease;
}

.back-to-top:hover {
    text-decoration: underline;
}
}

}

.back-to-top:hover {
    text-decoration: underline;
}   
        
        .card-content {
            flex-grow: 1;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .btn {
            display: block;
            margin-top: auto;
            padding: 8px;
            background-color: #e573e5;
            color: white;
            text-decoration: none;
            border-radius: 3px;
        }
        .btn:hover {
            background-color: #c35ac3;
            /* ข้อความภายในการ์ด */
.card-content {
    padding: 20px;
}

.card-content h3 {
    font-size: 22px;
    font-weight: bold;
    color: #2c3e50;
    margin-bottom: 12px;
}

.card-content p {
    font-size: 17px;
    color: #d8d8d8;
    margin-bottom: 15px;
}

/* ปุ่ม "ดูรายละเอียด" */
.card-content a.btn {
    display: inline-block;
    background: #ff9ae6;
    color: white;
    padding: 12px 20px;
    border-radius: 6px;
    text-decoration: none;
    font-weight: bold;
    font-size: 18px;
    transition: background 0.3s ease, transform 0.2s ease;
}

}

.back-to-top:hover {
    text-decoration: underline;
    transform: translateY(-3px);
}
        
        .back-to-top {
            display: block;
            margin-top: 20px;
            text-align: center;
            color: #ee82ee;
            text-decoration: none;
            font-weight: bold;
        }
</style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item" id="active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>

    <h1>แกลเลอรีสินค้า</h1>
    <div class="gallery">
        <div class="card">
            <img src="images/PANDORA1.jpg" alt="necklace">
            <div class="card-content">
                <h3>necklace</h3>
                <p>สร้อยคอรูปหัวใจสีทองประดับด้วยเพชร</p>
                <a href="images/PANDORA1.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA2.jpg" alt="bracelet">
            <div class="card-content">
                <h3>bracelet</h3>
                <p>สร้อยข้อมือสีเงินรูปหัวใจ</p>

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![image](https://github.com/user-attachments/assets/f20087fa-117b-44b4-ad88-f42023ac9379)
[](#การทดลองที่-6-Layout-และการจัดวางอิลิเมนต์)
## การทดลองที่ 6: Layout และการจัดวางอิลิเมนต์

### 6.1 การจัดวางด้วย Flexbox และ Grid

```css
/* Flexbox */
.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* Grid */
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

### ตัวอย่างการใช้งาน: การสร้างหน้าแสดงสินค้าแบบ Grid

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .product-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .product-card:hover {
            transform: translateY(-5px);
        }

        .product-image {
            width: 100%;
            height: 200px;
            background-color: #f5f5f5;
            background-size: cover;
            background-position: center;
        }

        .product-details {
            padding: 15px;
        }

        .product-title {
            font-size: 1.1rem;
            margin: 0 0 10px 0;
            color: #333;
        }

        .product-price {
            font-size: 1.2rem;
            color: #007bff;
            font-weight: bold;
        }

        .product-action {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 15px;
        }

        .add-to-cart {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
        }

        .add-to-cart:hover {
            background-color: #0056b3;
        }

        @media (max-width: 768px) {
            .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="product-grid">
        <!-- สินค้าชิ้นที่ 1 -->
        <div class="product-card">
            <div class="product-image" style="background-image: url('product1.jpg')"></div>
            <div class="product-details">
                <h3 class="product-title">สินค้าตัวอย่างที่ 1</h3>
                <div class="product-price">฿1,299</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <!-- สินค้าชิ้นที่ 2 -->
        <div class="product-card">
            <div class="product-image" style="background-image: url('product2.jpg')"></div>
            <div class="product-details">
                <h3 class="product-title">สินค้าตัวอย่างที่ 2</h3>
                <div class="product-price">฿1,499</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <!-- เพิ่มสินค้าอื่นๆ ตามต้องการ -->
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่งขนาดแสดงผลสินค้าให้เล็กลง
3. เพ่ิมรูปภาพของสินค้า


### ผลการทดลอง
```html
</style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item" id="active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>

    <h1>แกลเลอรีสินค้า</h1>
    <div class="gallery">
        <div class="card">
            <img src="images/PANDORA1.jpg" alt="necklace">
            <div class="card-content">
                <h3>necklace</h3>
                <p>สร้อยคอรูปหัวใจสีทองประดับด้วยเพชร</p>
                <a href="images/PANDORA1.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA2.jpg" alt="bracelet">
            <div class="card-content">
                <h3>bracelet</h3>
                <p>สร้อยข้อมือสีเงินมีจี้รูปหัวใจ</p>
                <a href="images/PANDORA2.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA3.jpg" alt="earring">
            <div class="card-content">
                <h3>earring</h3>
                <p>ต่างหูรูปหัวใจสีเงินประดับด้วยเพชร</p>
                <a href="images/PANDORA3.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA4.jpg" alt="ring">
            <div class="card-content">
                <h3>ring</h3>
                <p>แหวนสีเงินประดับด้วยเพชร</p>
                <a href="images/PANDORA4.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/pandora5.jpg" alt="bracelet">
            <div class="card-content">
                <h3>bracelet</h3>
                <p>สร้อยข้อมือสีเงินจี้ประดับรูปผีเสื้อ</p>
                <a href="images/pandora5.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA6.jpg" alt="necklace">
            <div class="card-content">
                <h3>necklace</h3>
                <p>สร้อยคอสีเงินประดับด้วยจี้แหวน</p>
                <a href="images/PANDORA6.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>
    </div>    

    <a href="#" class="back-to-top">กลับไปข้างบน</a>
</body>
</html>

```
```css
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;600&display=swap');

        /* รีเซ็ตค่าพื้นฐาน */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Cormorant Garamond', sans-serif;
        }

        /* ตั้งค่าพื้นฐาน */
        body {
            background-color: #fff9f9;
            color: #333;
            font-size: 18px;
            line-height: 1.6;
            padding: 20px;
        }

        /* สไตล์เมนูนำทาง */
        nav {
            background-color: #333;
            padding: 15px;
            display: flex;
            justify-content: center;
        }

        nav ul {
            list-style: none;
            display: flex;
            padding: 0;
        }

        nav ul li {
            margin: 0 15px;
        }

        .menu-item {
            color: white;
            text-decoration: none;
            padding: 8px 15px;
            border-radius: 6px;
            font-size: 18px;
            font-weight: 600;
            transition: background 0.3s ease;
        }

        .menu-item:hover, #active {
            background-color: #f47ef4;
            border-radius: 3px;
        }

        h1 {
            text-align: center;
            font-size: 36px;
            font-weight: bold;
            color: #2c3e50;
            margin-top: 20px;
        }

        /* สไตล์แกลเลอรีสินค้า */
        .gallery {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin: 20px;
        }

        .card {
            border: 1px solid #ffffff;
            padding: 15px;
            width: 250px;
            text-align: center;
            border-radius: 5px;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
            display: flex;
            flex-direction: column;
            
        }

        .card img {
            max-width: 100%;
            height: 200px; /* กำหนดความสูงเท่ากัน */
            object-fit: cover;
            border-radius: 8px;
        }

        .card-content {
            padding: 20px;
            display: flex;
            flex-direction: column;
            
}
        

        .card-content h3 {
            font-size: 22px;
            font-weight: bold;
            color: #2c3e50;
            margin-bottom: 12px;
        }

        .card-content p {
            font-size: 17px;
            color: #7f8c8d;
            margin-bottom: 15px;
        }

        /* ปุ่ม "ดูรายละเอียด" */
        .card-content a.btn {
            display: inline-block;
            background: #ff9ae6;
            color: white;
            padding: 12px 20px;
            border-radius: 6px;
            text-decoration: none;
            font-weight: bold;
            font-size: 18px;
            transition: background 0.3s ease, transform 0.2s ease;
            margin-top: auto; /* ทำให้ปุ่มอยู่ที่ด้านล่างสุด */
            text-align: center; /* จัดปุ่มให้กึ่งกลาง */
        }

        .card-content a.btn:hover {
            background: #f47ef4;
            transform: translateY(-3px);
        }

        /* ปุ่มกลับไปข้างบน */
        .back-to-top {
            display: block;
            text-align: center;
            margin-top: 20px;
            color: #ee82ee;
            text-decoration: none;
            font-weight: bold;
        }

        .back-to-top:hover {
            text-decoration: underline;
        }

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1920" alt="ภาพถ่ายหน้าจอ 2568-02-23 เวลา 20 48 51" src="https://github.com/user-attachments/assets/be3111f5-d503-4a3c-9577-be4c0f860692" />

### ตัวอย่างการใช้งาน: การสร้างเลย์เอาต์ Modern Dashboard

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .dashboard {
            display: grid;
            grid-template-areas: 
                "sidebar header"
                "sidebar main";
            grid-template-columns: 250px 1fr;
            grid-template-rows: auto 1fr;
            min-height: 100vh;
        }

        .header {
            grid-area: header;
            background: white;
            padding: 1rem;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .sidebar {
            grid-area: sidebar;
            background: #2c3e50;
            color: white;
            padding: 1rem;
        }

        .main-content {
            grid-area: main;
            padding: 1rem;
            background: #f5f7fa;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .stat-card {
            background: white;
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .chart-container {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 1rem;
        }

        .chart {
            background: white;
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        @media (max-width: 768px) {
            .dashboard {
                grid-template-areas: 
                    "header"
                    "main";
                grid-template-columns: 1fr;
            }

            .sidebar {
                display: none;
            }

            .chart-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="dashboard">
        <header class="header">
            <h1>แดชบอร์ด</h1>
            <nav>
                <button>โปรไฟล์</button>
                <button>ออกจากระบบ</button>
            </nav>
        </header>

        <aside class="sidebar">
            <nav>
                <ul>
                    <li>หน้าแรก</li>
                    <li>รายงาน</li>
                    <li>การตั้งค่า</li>
                </ul>
            </nav>
        </aside>

        <main class="main-content">
            <div class="stats-grid">
                <div class="stat-card">
                    <h3>ยอดขายรวม</h3>
                    <p>฿150,000</p>
                </div>
                <div class="stat-card">
                    <h3>จำนวนออเดอร์</h3>
                    <p>1,234</p>
                </div>
                <div class="stat-card">
                    <h3>ลูกค้าใหม่</h3>
                    <p>45</p>
                </div>
            </div>

            <div class="chart-container">
                <div class="chart">
                    <h3>กราฟแสดงยอดขาย</h3>
                    <!-- เพิ่มกราฟตามต้องการ -->
                </div>
                <div class="chart">
                    <h3>สัดส่วนสินค้าขายดี</h3>
                    <!-- เพิ่มกราฟตามต้องการ -->
                </div>
            </div>
        </main>
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่งการแสดงผลต่าง ๆ ให้สวยงาม



### ผลการทดลอง
```html
</style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item" id="active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>

    <h1>แกลเลอรีสินค้า</h1>
    <div class="gallery">
        <div class="card">
            <img src="images/PANDORA1.jpg" alt="necklace">
            <div class="card-content">
                <h3>necklace</h3>
                <p>สร้อยคอรูปหัวใจสีทองประดับด้วยเพชร</p>
                <a href="images/PANDORA1.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA2.jpg" alt="bracelet">
            <div class="card-content">
                <h3>bracelet</h3>
                <p>สร้อยข้อมือสีเงินมีจี้รูปหัวใจ</p>
                <a href="images/PANDORA2.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA3.jpg" alt="earring">
            <div class="card-content">
                <h3>earring</h3>
                <p>ต่างหูรูปหัวใจสีเงินประดับด้วยเพชร</p>
                <a href="images/PANDORA3.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA4.jpg" alt="ring">
            <div class="card-content">
                <h3>ring</h3>
                <p>แหวนสีเงินประดับด้วยเพชร</p>
                <a href="images/PANDORA4.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/pandora5.jpg" alt="bracelet">
            <div class="card-content">
                <h3>bracelet</h3>
                <p>สร้อยข้อมือสีเงินจี้ประดับรูปผีเสื้อ</p>
                <a href="images/pandora5.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>

        <div class="card">
            <img src="images/PANDORA6.jpg" alt="necklace">
            <div class="card-content">
                <h3>necklace</h3>
                <p>สร้อยคอสีเงินประดับด้วยจี้แหวน</p>
                <a href="images/PANDORA6.jpg" class="btn">ดูรายละเอียด</a>
            </div>
        </div>
    </div>    

    <a href="#" class="back-to-top">กลับไปข้างบน</a>
</body>
</html>


```
```css
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;600&display=swap');

        /* รีเซ็ตค่าพื้นฐาน */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Cormorant Garamond', sans-serif;
        }

        /* ตั้งค่าพื้นฐาน */
        body {
            background-color: #f4f4f9;
            color: #333;
            font-size: 18px;
            line-height: 1.6;
            padding: 20px;
            font-family: 'Cormorant Garamond', sans-serif;
        }

        /* สไตล์เมนูนำทาง */
        nav {
            background-color: #333;
            padding: 20px 0;
            display: flex;
            justify-content: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        nav ul {
            list-style: none;
            display: flex;
            padding: 0;
        }

        nav ul li {
            margin: 0 20px;
        }

        .menu-item {
            color: white;
            text-decoration: none;
            padding: 10px 20px;
            border-radius: 30px;
            font-size: 20px;
            font-weight: 600;
        }

        .menu-item:hover, #active {
            background-color: #f47ef4;
        }

        h1 {
            text-align: center;
            font-size: 40px;
            font-weight: bold;
            color: #2c3e50;
            margin-top: 30px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        /* สไตล์แกลเลอรีสินค้า */
        .gallery {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 40px;
        }

        .card {
            border: 1px solid #fff;
            padding: 20px;
            width: 280px;
            text-align: center;
            border-radius: 10px;
            background-color: white;
            display: flex;
            flex-direction: column;
        }

        .card img {
            max-width: 100%;
            height: 220px; /* กำหนดความสูงเท่ากัน */
            object-fit: cover;
            border-radius: 8px;
        }

        .card-content {
            padding: 20px;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .card-content h3 {
            font-size: 24px;
            font-weight: 600;
            color: #2c3e50;
            margin-bottom: 15px;
        }

        .card-content p {
            font-size: 18px;
            color: #7f8c8d;
            margin-bottom: 20px;
            line-height: 1.4;
        }

        /* ปุ่ม "ดูรายละเอียด" */
        .card-content a.btn {
            display: inline-block;
            background: #ff9ae6;
            color: white;
            padding: 14px 25px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 18px;
            margin-top: auto;
        }

        .card-content a.btn:hover {
            background: #f47ef4;
        }

        /* ปุ่มกลับไปข้างบน */
        .back-to-top {
            display: block;
            text-align: center;
            margin-top: 30px;
            color: #ee82ee;
            text-decoration: none;
            font-weight: bold;
            font-size: 20px;
        }

        .back-to-top:hover {
            text-decoration: underline;
        }

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![image](https://github.com/user-attachments/assets/b2f690da-91f6-4fe7-8d63-7fa5bb3674a1)
