# Taipei Trip 2026

Single-page PWA แผนทริปไทเป **14–17 เมษายน 2026**

## Features

- **Interactive Map** — Leaflet.js + CartoDB dark/light tiles พร้อม custom markers ต่อวัน
- **Day-by-day itinerary** — 4 วัน แยกสีแต่ละวัน คลิก 📍 โฟกัสบน map ได้เลย
- **Drag-to-reorder** — จัดลำดับสถานที่ในแต่ละวันด้วยการลาก
- **Search** — ค้นหาสถานที่ข้ามทุกวัน
- **Dark / Light mode** — toggle ได้ บันทึก preference ไว้
- **Print / Save as PDF** — export แผนทั้ง 4 วันสวยงาม
- **Offline fallback** — ถ้า fetch JSON ไม่ได้ ใช้ hardcoded data แทน

## File Structure

```
taipei-trip-2026/
├── index.html          ← main app (vanilla JS, Leaflet, SortableJS)
├── README.md
└── data/
    └── itinerary.json  ← แก้ข้อมูลทริปที่นี่โดยไม่ต้องแตะ HTML
```

## Itinerary

| Day | Date | Theme |
|-----|------|-------|
| 1 | 14 Apr Tue | ✈️ มาถึง + Ximending |
| 2 | 15 Apr Wed | 🪙 วัดเงิน + Bitan + วิว 101 |
| 3 | 16 Apr Thu | 🙏 วัด 3 แห่ง + Museum + 101 + Shilin |
| 4 | 17 Apr Fri | 🛍️ ของฝาก + บินกลับ |

## แก้ข้อมูลทริป

เปิด `data/itinerary.json` แล้วแก้ได้เลย โครงสร้างแต่ละ place:

```json
{
  "id":   "d1p1",
  "time": "18:00",
  "icon": "🛬",
  "name": "Taoyuan Airport T2",
  "lat":  25.0797,
  "lng":  121.2325,
  "note": "Terminal 2 · Arrivals"
}
```

> ถ้าสถานที่ไม่มิ coordinates (เช่น transit) ให้ใส่ `"lat": null, "lng": null`

## Tech Stack

- Vanilla JS (no framework)
- [Leaflet.js](https://leafletjs.com/) 1.9.4 — interactive map
- [SortableJS](https://sortablejs.github.io/Sortable/) 1.15.2 — drag-to-reorder
- CartoDB basemap tiles (dark + light)
- CSS custom properties for theming
