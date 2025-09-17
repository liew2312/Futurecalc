
# futurecalculate – PWA/APK

ชุดไฟล์นี้คือเวอร์ชัน PWA ของ **futurecalculate** ที่สามารถติดตั้งเป็นแอพมือถือได้  
ต้องการไฟล์ **APK** มี 2 วิธีที่เร็วที่สุด:

## วิธี A) ผ่านเว็บ (ง่ายสุด) – PWABuilder
1) ดีพลอยเว็บนี้ขึ้น GitHub Pages (หรือโฮสต์ static) เพื่อให้ได้ URL สาธารณะ
2) เข้า https://www.pwabuilder.com (บนคอม)
3) วาง URL เว็บไซต์ของคุณ → กด *Start*
4) ไปที่แท็บ **Android** → กด **Generate** เพื่อดาวน์โหลดไฟล์ **APK/AAB**
5) เปลี่ยนชื่อแอพ/แพ็กเกจในขั้นตอน Generate ให้เป็น `futurecalculate` ตามต้องการ

> วิธีนี้ใช้เวลาไม่กี่นาที และได้ไฟล์ APK พร้อมติดตั้งทันที

## วิธี B) สร้าง APK เองบนเครื่อง (Capacitor)
1) ติดตั้ง Node.js และ Android Studio
2) สร้างโปรเจกต์ Capacitor และคัดลอกไฟล์เว็บไปที่ `dist/`:
```bash
npm i -g @capacitor/cli
mkdir futurecalculate-cap && cd $_
npm init -y
npx cap init "futurecalculate" "com.futurecalculate.app" --web-dir=dist
mkdir dist
# คัดลอกไฟล์ index.html, manifest.webmanifest, service-worker.js, โฟลเดอร์ icons ไปที่ dist/
```
3) เพิ่มแพลตฟอร์ม Android และเปิดใน Android Studio
```bash
npx cap add android
npx cap sync
npx cap open android
```
4) ใน Android Studio: **Build → Build Bundle(s)/APK(s) → Build APK(s)**  
   จะได้ไฟล์ `app-debug.apk` เพื่อติดตั้งทดสอบ หรือทำ **Generate Signed Bundle / APK** เพื่อแจกจริง

## เปลี่ยนชื่อแอพบนไอคอน
- ชื่อที่เห็นใต้ไอคอนมาจาก `short_name` ใน `manifest.webmanifest` (ตั้งไว้เป็น `futurecalculate` แล้ว)

## โครงสร้างไฟล์
```
.
├─ index.html
├─ manifest.webmanifest  # name/short_name: futurecalculate
├─ service-worker.js
└─ icons/
   ├─ icon-192.png
   ├─ icon-512.png
   ├─ icon-maskable-192.png
   └─ icon-maskable-512.png
```
