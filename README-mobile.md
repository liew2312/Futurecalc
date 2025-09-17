
# futurecalculate – PWA (Initial Margin Mode)

เวอร์ชันนี้ปรับส่วน PnL ให้กรอก **Initial Margin (USDT)** โดยตรง แทน **Quantity/Position**  
สูตรคำนวณ: `position = IM × Leverage`, `qty = position / entry`

## ติดตั้งเป็นแอพ (Android/iOS)
- Android (Chrome): เมนู ⋮ → Add to Home screen
- iOS (Safari): Share → Add to Home Screen

## หมายเหตุ
- ถ้าแก้ไขไฟล์ ควรเปลี่ยน CACHE_NAME ใน `service-worker.js` (เช่น `-v2`) เพื่ออัปเดตแคช
