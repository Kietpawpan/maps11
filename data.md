ระบบนี้มีการเชื่อมโยงกับไฟล์ ฐานข้อมูล และ API ต่างๆ แบ่งออกเป็น 5 กลุ่มหลัก ดังนี้

1. ไฟล์ภายในโปรเจกต์หรือไฟล์ที่จัดเก็บไว้บน GitHub
ไฟล์ Manifest: manifest3.json (สำหรับตั้งค่า Web App)
รูปภาพไอคอนแอป: [https://kietpawpan.github.io/hotspot/img/EPO11App.png](https://kietpawpan.github.io/hotspot/img/EPO11App.png)
ไฟล์ขอบเขตพื้นที่ (GeoJSON): [https://raw.githubusercontent.com/Kietpawpan/maps11/refs/heads/main/MAPS11_boundary_highres-Overpass200k.json](https://raw.githubusercontent.com/Kietpawpan/maps11/refs/heads/main/MAPS11_boundary_highres-Overpass200k.json) (ใช้สำหรับตีกรอบพื้นที่ 4 จังหวัด)
2. ฐานข้อมูลและ Web API (สำหรับดึงข้อมูลแสดงผล)
Google Apps Script (จุดความร้อน NASA): [https://script.google.com/macros/s/AKfycbyJfWRJFtBwsIZecPHZYJda69wXoWdmp1fINaU8-qagZdI7sc8TvB5FzKpGqosbxaUf/exec](https://script.google.com/macros/s/AKfycbyJfWRJFtBwsIZecPHZYJda69wXoWdmp1fINaU8-qagZdI7sc8TvB5FzKpGqosbxaUf/exec)
Google Apps Script (สถานที่กำจัดขยะ): [https://script.google.com/macros/s/AKfycbwWI0NvtyToeNBq5Y0Yu6VCKiJh27JDSDBZTJ0IbQ1mGsErkJfFdzYdkiVAw72GGWKZ/exec](https://script.google.com/macros/s/AKfycbwWI0NvtyToeNBq5Y0Yu6VCKiJh27JDSDBZTJ0IbQ1mGsErkJfFdzYdkiVAw72GGWKZ/exec)
Longdo Map API: [https://api.longdo.com/map/services/address](https://api.longdo.com/map/services/address) (ใช้สำหรับแปลงพิกัดละติจูดและลองจิจูดเป็นชื่อ ตำบล อำเภอ จังหวัด โดยใช้ API Key bce812933744d2530d26f0fabb0017cf)
Open-Meteo API: [https://api.open-meteo.com/v1/forecast](https://api.open-meteo.com/v1/forecast) (ใช้สำหรับดึงข้อมูลทิศทางลมและความเร็วลมแบบเรียลไทม์ ณ จุดเกิดเหตุ)
3. เซิร์ฟเวอร์แผนที่ฐาน (Map Tile Servers)
OpenStreetMap: https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png
Esri World Imagery: [https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/](https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/){z}/{y}/{x}
Google Maps Hybrid: https://{s}[.google.com/vt/lyrs=y&x=](https://.google.com/vt/lyrs=y&x=){x}&y={y}&z={z}
4. ไลบรารีภายนอก (CDN Links สำหรับ CSS และ JavaScript)
Leaflet (1.9.4): สำหรับสร้างและแสดงผลแผนที่อินเทอร์แอคทีฟ
Leaflet MarkerCluster (1.4.1): สำหรับจัดกลุ่มหมุดบนแผนที่เมื่อมีจำนวนมาก
Turf.js (6.5.0): สำหรับคำนวณทางภูมิศาสตร์ (เช่น วัดระยะทางจากบ่อขยะถึงจุดความร้อนเพื่อสร้างพื้นที่รัศมีแจ้งเตือน)
SheetJS / xlsx (0.18.5): สำหรับสร้างและส่งออกไฟล์ Excel เมื่อผู้ใช้กดดาวน์โหลดข้อมูล
PapaParse (5.3.2): ไลบรารีเสริมสำหรับจัดการโครงสร้างข้อมูลข้อความ
CryptoJS (4.1.1): สำหรับเข้ารหัส (SHA3) และตรวจสอบความถูกต้องของรหัสผ่านก่อนดาวน์โหลดไฟล์
jQuery (3.7.1): สำหรับช่วยจัดการการทำงานของ JavaScript บางส่วน
5. ลิงก์บริการเชื่อมโยงภายนอก
Google Maps URL: มีการสร้างลิงก์อัตโนมัติภายในโค้ดเพื่อส่งผู้ใช้ไปยัง Google Maps (เช่น [https://www.google.com/maps/dir/](https://www.google.com/maps/dir/)... หรือ [https://www.google.com/maps/search/](https://www.google.com/maps/search/)...) สำหรับใช้นำทางไปยังจุดเกิดเหตุหรือสถานที่กำจัดขยะ
