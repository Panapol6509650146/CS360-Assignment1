# CS360 Assignment 1

## วัตถุประสงค์ของ Strapi

Strapi คือโปรแกรม Headless CMS ที่เป็นโอเพนซอร์ส ซึ่งนักพัฒนาสามารถนำไปใช้สร้าง API ด้วย Javascript ได้อย่างรวดเร็ว และยังเป็นบริการที่ใช้งานได้ฟรี มีความยืดหยุ่น บริหารจัดการได้ง่าย มีความปลอดภัย รวมถึงสามารถปรับขนาดให้เหมาะสมกับธุรกิจได้ และทำงานร่วมกับ framework รุ่นใหม่ส่วนใหญ่อย่างเช่น React และ Node ได้เป็นอย่างดีอีกด้วย

* องค์ประกอบของ Strapi <sub>*อ้างอิงจาก Strapi Dashboard</sub>
  * Content-Type Builder : ระบบสร้าง Content ใน Collection Type และ Single Type
  * Media Library : ระบบจัดการไฟล์สื่อ เช่น รูปภาพ วิดีโอ และเอกสาร
  * Release : ระบบจัดการการอัพเดทและปล่อย Content
  * Plugin : ระบบส่วนขยายที่เพิ่มฟังก์ชันให้กับ Strapi
  * Marketplace : ระบบที่รวบรวม Plugin และ Provider ที่สามารถติดตั้งและใช้งานกับ Strapi ได้
  * Setting : การตั้งค่าต่างๆ เช่น API Tokens หรือ Roles

* Use cases 
  * BrandiumPro เพิ่มยอดสั่งอาหารออนไลน์ของร้านอาหาร 5 เท่าด้วยการใช้ Strapi CMS ด้วยอินเทอร์เฟซที่ใช้งานง่ายและมี admin panel ที่ทำให้เขาโฟกัสในการแก้ปัญหาโดยไม่ต้องเสียเวลาและทรัพยากร
  * Societe Generale เว็บไซต์ฝึกอบรมที่สามารถใช้งานได้จริงภายในระยะเวลา 3 เดือนโดยการใช้ Strapi CMS
  * Shelt.in บริษัท IoT สัญชาติฝรั่งเศสเปลี่ยนมาใช้ Strapi เนื่องจาก API ของพวกเขามีข้อจำกัด ซึ่ง Strapi มีความยืดหยุ่นและความเร็วสูงกว่า

* อ้างอิง
  * https://morphos.is/th/blog/what-is-strapi-and-how-it-will-dominate-the-world-of-headless-cms
  * https://strapi.io/blog/brandium-pro-boosts-restaurants-online-orders-5x-using-strapi-cms
  * https://www.zenesys.com/strapi-headless-cms-guide-features-and-use-cases

## ไฟล์ .gitignore

.gitignore มีเอาไว้เพื่อระบุไฟล์หรือโฟลเดอร์ที่ Git ควรจะละเว้นและไม่อัพโหลดซึ่งสิ่งที่เรามักจะใส่ใน .gitignore เช่น

* ไฟล์ของระบบปฏิบัติการ
* ไฟล์ที่ build จาก source code
* dependencies ที่ดาวโหลดมา
* ไฟล์ config ของ IDE: Integrated development environment
* properties file หรือ config file ของ production server
* ข้อมูลที่เป็นความลับ

.gitignore สามารถสร้างโดยเปิด Terminal/Git Bash และใช้คำสั้ง

```
touch .gitignore
```

### เนื้อหาใน .gitigore ที่ Strapi มีให้มามีรายละเอียดดังนี้
```
OS X:

.DS_Store: เป็นไฟล์ที่ macOS สร้างขึ้นเพื่อเก็บข้อมูลเกี่ยวกับการจัดเรียงไอคอนในโฟลเดอร์ ไม่เกี่ยวข้องกับโค้ดและมักทำให้ repository รก
.AppleDouble, ._*: ไฟล์ที่ใช้เก็บ resource fork ของไฟล์ต่าง ๆ เมื่อ macOS ต้องการให้ข้อมูลเพิ่มเติมในระบบที่ไม่รองรับ ไม่จำเป็นสำหรับโปรเจกต์
.LSOverride, Icon, .Spotlight-V100, .Trashes: เกี่ยวกับการตั้งค่าการแสดงผลไอคอนหรือการจัดการไฟล์ภายในระบบ macOS ไม่มีผลต่อการทำงานของโปรเจกต์
Linux:

*~: ไฟล์สำรองหรือไฟล์ชั่วคราวที่ถูกสร้างขึ้นโดย text editors เช่น Emacs หรือ Vim เพื่อเก็บสถานะการแก้ไขครั้งล่าสุด ไม่เกี่ยวข้องกับโค้ดจริง
Windows:

Thumbs.db, ehthumbs.db: ไฟล์ที่ Windows สร้างเพื่อแคชภาพขนาดย่อของไฟล์รูปภาพในโฟลเดอร์ ไม่เกี่ยวข้องกับการพัฒนา
Desktop.ini: ไฟล์ที่เก็บข้อมูลการตั้งค่าของโฟลเดอร์ใน Windows เช่น ไอคอนและการจัดเรียงข้อมูล ไม่เกี่ยวข้องกับโค้ด
$RECYCLE.BIN/: โฟลเดอร์รีไซเคิลของ Windows ไม่เกี่ยวข้องกับโปรเจกต์
*.cab, *.msi, *.msm, *.msp: ไฟล์แพ็คเกจที่ใช้ติดตั้งซอฟต์แวร์ใน Windows ไม่จำเป็นสำหรับโค้ดแอปพลิเคชัน
Packages:

.7z, .rar, .zip, .dmg, .iso: ไฟล์บีบอัดและอิมเมจที่มักใช้สำหรับการติดตั้งหรือสำรองข้อมูล ไม่เกี่ยวข้องกับการพัฒนาโดยตรง
.jar, .com, .dll, .exe: ไฟล์ที่คอมไพล์แล้วหรือ executable ไม่ควรเก็บใน repository เพื่อป้องกันปัญหาความเข้ากันได้ข้ามแพลตฟอร์มและขนาดไฟล์ที่ใหญ่เกินไป
.o, .so: ไฟล์ object ที่สร้างจากการคอมไพล์โค้ด มักจะเปลี่ยนแปลงบ่อยและใหญ่
.swo, .swp, .swn, .swm: ไฟล์ชั่วคราวของ text editors เช่น Vim ที่ใช้เก็บสถานะการแก้ไข
.out, .pid: ไฟล์ผลลัพธ์ของการรันโปรแกรมหรือไฟล์ที่เก็บ Process ID ซึ่งไม่จำเป็นต้องติดตาม
Logs and databases:

.tmp: ไฟล์ชั่วคราวที่โปรแกรมสร้างขึ้นเพื่อเก็บข้อมูลชั่วคราว ไม่จำเป็นต้องเก็บไว้ใน repository
.log: ไฟล์บันทึกการทำงานของโปรแกรมที่ช่วยวิเคราะห์ปัญหา แต่ไม่จำเป็นต่อการพัฒนา
.sql, .sqlite, .sqlite3: ไฟล์ฐานข้อมูลที่เก็บข้อมูลการทดสอบหรือข้อมูลที่เกิดจากการทำงานจริง ไม่จำเป็นต้องแชร์ใน repository
Misc.:

*#: ไฟล์สำรองที่บางโปรแกรมสร้างขึ้น เช่นเดียวกับไฟล์ที่ลงท้ายด้วย ~ ไม่จำเป็นต่อการพัฒนา
ssl: โฟลเดอร์ที่มักใช้เก็บใบรับรอง SSL ซึ่งอาจมีข้อมูลสำคัญหรือความลับ ไม่ควรแชร์
.idea, nbproject: ไฟล์การตั้งค่าโปรเจกต์ของ IDE เช่น IntelliJ IDEA, NetBeans ซึ่งมักจะเป็นข้อมูลเฉพาะเครื่องผู้ใช้
public/uploads/*: โฟลเดอร์ที่มักเก็บไฟล์ที่ผู้ใช้ upload ซึ่งอาจมีข้อมูลส่วนตัวหรือข้อมูลที่ไม่ควรแชร์
!public/uploads/.gitkeep: การระบุไฟล์ .gitkeep เพื่อให้ Git เก็บโฟลเดอร์ว่างโดยไม่เก็บข้อมูลภายใน
Node.js:

lib-cov, lcov.info: ไฟล์ที่เก็บข้อมูลการทดสอบความครอบคลุมของโค้ด ไม่จำเป็นต่อการพัฒนา
pids, logs, results: ไฟล์ที่สร้างขึ้นระหว่างการรันแอปพลิเคชัน Node.js เพื่อเก็บข้อมูลชั่วคราวหรือผลลัพธ์ของการทำงาน
node_modules: โฟลเดอร์ที่เก็บ dependencies ของ Node.js ขนาดใหญ่และสามารถสร้างใหม่ได้ทุกครั้งที่ติดตั้งโปรเจกต์
.node_history: ประวัติการใช้ Node.js ใน command line ที่ไม่เกี่ยวข้องกับการทำงานของโปรเจกต์
Tests:

coverage: โฟลเดอร์ที่เก็บผลลัพธ์ของการทดสอบการครอบคลุมโค้ด เป็นข้อมูลการทดสอบที่ไม่จำเป็นต้องเก็บใน repository
Strapi:

.env: ไฟล์ที่ใช้เก็บ environment variables ซึ่งมักมีข้อมูลความลับ เช่น API keys, ข้อมูลการเชื่อมต่อฐานข้อมูล ไม่ควรแชร์
license.txt, exports: ไฟล์ข้อมูลที่ไม่เกี่ยวข้องกับโค้ดหลักของโปรเจกต์
.strapi, .strapi-updater.json, .strapi-cloud.json: ไฟล์การตั้งค่าภายในของ Strapi ที่ไม่จำเป็นต้องแชร์ไปยังทีมพัฒนา
dist, build: ไฟล์ที่สร้างจากการ build โค้ดและสามารถสร้างใหม่ได้ ไม่จำเป็นต้องเก็บใน repository
```
### อ้างอิง
* https://docs.github.com/en/get-started/getting-started-with-git/ignoring-files
* https://medium.com/odds-team/gitignore-%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%AA%E0%B8%B2%E0%B8%A1%E0%B8%B2%E0%B8%A3%E0%B8%96%E0%B8%82%E0%B8%AD%E0%B8%87-git-version-control-a77d1677a9d3
* ChatGPT (รายละเอียด .gitignore)

## ขั้นตอนในการติดตั้งทั้งหมด
### Strapi

ระบบปฏิบัติการที่ใช้ : Window

ดาวน์โหลด npm และ nodejs ได้ที่ https://nodejs.org/en/download/prebuilt-installer

```
1.เลือกเวอร์ชั่น v20.17.0(LTS)*
2.เลือกระบบปฏิบัติการที่ใช้
3.เลือกสถาปัตยกรรมที่ใช้
4.กดปุ่มดาวน์โหลด
5.ติดตั้งลงบน PC
```

<sub>*LTS (Long Time Support) เป็น version ที่มีเสถียรภาพที่สุดที่ถูกปล่อยออกมา</sub>

หลังจากดาวน์โหลดสามารถตรวจสอบเวอร์ชั่นเพื่อให้มั่นใจว่า package ถูกติดตั้งไว้แล้วโดยใช้คำสั่ง
git bash
```
node -v #ตรวจสอบเวอร์ชั่น Node.js
npm -v #ตรวจสอบเวอร์ชั่น Node Package Manager
```

ติดตั้ง Yarn สำหรับติดตั้ง Strapi
```
npm install -g yarn
```
หลังจากดาวน์โหลดสามารถตรวจสอบเวอร์ชั่นเพื่อให้มั่นใจว่า package ถูกติดตั้งไว้แล้วโดยใช้คำสั่ง
```
yarn -v #ตรวจสอบเวอร์ชั่น Yarn
```

หลังจากติดตั้ง Yarn แล้วเราจะใช้สร้าง Strapi project โดยใช้คำสั่ง

```
yarn create strapi-app ..ชื่อ project..
->quickstart
->skip
```
หลังจากสร้าง Strapi project แล้ว project จะรันโดยอัตโนมัติและสามารถรันด้วนตนเองได้โดยใช้คำสั่ง

```
cd ..ชื่อ project.. #ถ้ายังไม่อยู่ใน directory project
yarn develop #รัน project 
```

### push code ขึ้น GitHub
สร้าง repository ได้ที่ https://github.com/ และตั้งชื่อ repository ตามต้องการเช่น ..my-repo..

ดาวน์โหลด Git Bash ได้ที https://git-scm.com/download/win
```
1.เลือกระบบปฏิบัติการที่ใช้
2.เลือกสถาปัตยกรรมที่ใช้
3.กดปุ่มดาวน์โหลด standalone
4.ติดตั้งลงบน PC
```
หลังจากดาวน์โหลดสามารถตรวจสอบเวอร์ชั่นเพื่อให้มั่นใจว่า package ถูกติดตั้งไว้แล้วโดยใช้คำสั่ง
```
git -v #ตรวจสอบเวอร์ชั่น Git
```
ในการ push code ขึ้น GitHub มีขั้นตอนการรันคำสั่งดังนี้
```
#setup เบื้องต้น
cd ..ชื่อ project.. #ถ้ายังไม่อยู่ใน directory project
git init #บอก Git ว่าเราจะทำงานในโฟลเดอร์นี้
git config --global user.name "..ชื่อ.." #ตั้ง username ถ้ายังไม่ได้ตั้ง
git config --global user.email ..email.. #ตั้ง email ถ้ายังไม่ได้ตั้ง
git remote add ..ชื่อ remote.. ..remote-repository-URL(เช่น git@github.com:yourname/..my-repo...git).. #ตั้งค่าให้ repository ในเครื่องเชื่อมต่อกับ repository บน GitHub ที่ remote-repository-URL
git branch -M main #สร้าง branch สำหรับเก็บโค้ด ในที่นี้คือ main

git add . #add ทุกอย่างใน directory
git commit -m "..ข้อความ.." #บันทึกการเปลี่ยนแปลงใน local repository
git push -u ..ชื่อ remote.. main #บันทึกการเปลี่ยนแปลงใน remote repository
```

### อ้างอิง
https://docs.strapi.io/dev-docs/installation/cli

## ขั้นตอนการ Deploy
ขั้นตอนการ launch instance 
```
1.ตั้งชื่อ instance
2.เลือก OS : Ubuntu Server 24.04 LTS (HVM), SSD Volume Type
3.เลือก Instance : type t2.small
4.เลือก keypair
5.สร้าง security group 
  -Type: SSH, Protocol: TCP, Port Range 22, Source: 0.0.0.0/0 (ถ้ามีแล้วไม่ต้องเพิ่ม)
  -Type: SSH, Protocol: TCP, Port Range 22, Source: ::/0
  -Type: HTTP, Protocol: TCP, Port Range 80, Source: 0.0.0.0/0, ::/0
  -Type: HTTPS, Protocol: TCP, Port Range 443, Source: 0.0.0.0/0, ::/0
  -Type: Custom TCP Rule, Protocol: TCP, Port Range 1337, Source: 0.0.0.0/0
6.Configure storage : 1x 8 GiB gp2 Root volume
7.Launch instance
*ขั้นตอนนี้จะได้ key.pem มา
```
หลังจากสร้างแล้วต้องเชื่อมต่อ instace นี้กับเครื่องของเราโดยทำตามขั้นตอนดั้งนี้
```
1.เข้าไปยัง console home ของ aws
2.click EC2
3.click instane ใน Resources
4.click ขวาที่ intance ที่สร้างไว้
5.click connect
6.copy code ตรง example โดยแก้ไข directory key.pem ในโค้ดให้ตรงกับ directory key.pem ในเครื่องเรา
```

หลังจากเชื่อมต่อ instance หับเครื่องได้แล้วจำเป็นต้องอัพเดท apt และติดตั้ง package ที่จำเป็น
```
sudo apt update #อัพเดท apt
sudo apt install npm #ติดตั้ง Node Package Manager
sudo npm install yarn -g #ติดตั้ง Yarn
sudo apt install git #ติดตั้ง Git
sudo npm install pm2 -g #ติดตั้ง สำหรับจัดการ process
```
หลังจากดาวน์โหลดสามารถตรวจสอบเวอร์ชั่นเพื่อให้มั่นใจว่า package ถูกติดตั้งไว้แล้วโดยใช้คำสั่ง
```
npm -v #ตรวจสอบเวอร์ชั่น Node Package Manager
node -v #ตรวจสอบเวอร์ชั่น Node.js
yarn -v #ตรวจสอบเวอร์ชั่น Yarn
git -v #ตรวจสอบเวอร์ชั่น Git
pm2 -v #ตรวจสอบเวอร์ชั่น pm2
```
สร้าง directory สำหรับรัน project ด้วยคำสั่ง
```
mkdir ..ชื่อ directory.. #สร้าง directory
cd ..ชื่อ directory.. #เข้าไปยัง directory
```

clone project จาก GitHub มาลง EC2
```
git clone ..remote-repository-URL.. #clone project จาก remote-repository-URL
cd ..ชื่อ directory project.. #เข้าไปยัง directory ของ project 
yarn install #ติดตั้งแพ็กเกจและ dependencies ต่าง ๆ ในโปรเจกต์
```

setup .env ของเว็บไซต์ โดย copy template จาก .env.example
```
cp .env.example .env #สร้าง .env โดย copy .env.example
nano .env #แก้ไข HOST, PORT, Key, Token ต่างๆใน .env
```

build project โดยใช้คำสั่ง
```
NODE_ENV=production yarn build
```
สร้างไฟล์สำหรับรัน project
```
cd ..
pm2 init #สร้าง ecosystem.config.js สำหรับรัน project
sudo nano ecosystem.config.js #แก้ไขไฟล์สำหรับรัน project

#แก้ไขในไฟล์ ecosystem.config.js ตามโต้ดด้านล่าง

module.exports = {
  apps: [
    {
      name: 'strapi-deploy',
      cwd: '/home/ubuntu/strapi/CS360-Assignment1',
      script: 'yarn',
      args: 'start',
      env: {
        APP_KEYS: process.env.API_KEYS,
        API_TOKEN_SALT: process.env.API_TOKEN_SALT,
        ADMIN_JWT_SECRET: process.env.ADMIN_JWT_SECRET,
        JWT_SECRET: process.env.JWT_SECRET,
        NODE_ENV: 'production',
      },
    },
  ],
};


```

รัน project โดยใช้คำสั่ง
```
pm2 start ecosystem.config.js
```

### อ้างอิง
https://docs.strapi.io/dev-docs/deployment
https://docs.strapi.io/dev-docs/deployment/amazon-aws