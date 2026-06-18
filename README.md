# MGWR WebGIS 3D — Phân tích nhiệt độ bề mặt

🌐 **Live Demo:** [https://yourusername.github.io/mgwr-3d-dashboard/](https://yourusername.github.io/mgwr-3d-dashboard/)

## Tổng quan

Dashboard 3D trực quan hóa kết quả phân tích **MGWR (Multi-scale Geographically Weighted Regression)** cho nghiên cứu nhiệt độ bề mặt (LST) với 750 điểm dữ liệu tại khu vực nghiên cứu.

### Tính năng

- 🌍 **CesiumJS 3D Globe** — Hiển thị cột 3D extruded trên globe
- 🎨 **6 chế độ màu**: LST, β NDVI, β NDBI, β DistW, NDVI, Significant
- 📏 **4 chế độ chiều cao**: LST, NDVI, Residual, Flat
- 🔍 **Bộ lọc**: LST range, NDVI range, significance
- 📊 **Biểu đồ histogram** phân phối β NDVI
- ℹ️ **Click/hover** để xem chi tiết từng điểm
- 📱 **Responsive** — hỗ trợ mobile/tablet

### Thống kê mô hình

| Metric | Giá trị |
|--------|---------|
| Adj. R² | 0.802 |
| AICc | 976 |
| Moran's I | −0.026 (ns) |
| Số điểm | 750 |

## Kiến trúc

```
gh-pages/
├── index.html          ← Dashboard chính (CesiumJS 3D)
├── data.js             ← 750 điểm dữ liệu MGWR (embedded, ~200KB)
├── .nojekyll           ← GitHub Pages config
└── README.md
```

**Không cần backend** — tất cả dữ liệu được embed trong `data.js`.


## Công nghệ

- **[CesiumJS](https://cesium.com/cesiumjs/)** v1.113 — 3D globe rendering
- **[Chart.js](https://www.chartjs.org/)** v4.4.1 — Histogram
- **[OpenStreetMap](https://www.openstreetmap.org/)** — Imagery (no API key needed)
- **Font Awesome** v6.4.0 — Icons

## Dữ liệu

750 điểm MGWR với các biến:

| Biến | Mô tả |
|------|-------|
| LST | Land Surface Temperature (°C) |
| NDVI | Normalized Difference Vegetation Index |
| NDBI | Normalized Difference Built-up Index |
| Dist_Water | Khoảng cách đến nguồn nước (m) |
| β NDVI/NDBI/DistW | Hệ số hồi quy cục bộ |
| t-stat | Giá trị t-statistic |
| sig | Ý nghĩa thống kê (p < 0.05) |
| Residual | Phần dư mô hình |

## License

MIT
