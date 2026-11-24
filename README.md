# Instance Segmentation Indoor

Proyek ini membandingkan model segmentasi instance pada dataset **Panoptic Indoor Segmentation v5** dan 40 foto indoor pribadi. Model dilatih dan dievaluasi menggunakan notebook Kaggle.

## Model

- YOLO11n-seg dengan pretrained weights
- YOLO11n-seg tanpa pretrained weights
- YOLO11s-seg
- Mask R-CNN ResNet-50 FPN

YOLO merupakan model one-stage, sedangkan Mask R-CNN merupakan model two-stage.

## Struktur repositori

```text
instance-segmentation-indoor/
├── evidence/
│   └── screenshots
├── notebooks/
│   ├── evaluation/
│   │   ├── evaluate_panoptic_test.ipynb
│   │   └── evaluate_personal_test.ipynb
│   ├── resnet50-fpn.ipynb
│   ├── yolov11n-no-pretrained.ipynb
│   ├── yolov11n.ipynb
│   └── yolov11s.ipynb
├── reports/
│   ├── laporan_instance_segmentation.docx
│   └── logbook_instance_segmentation.docx
├── results/
│   ├── maskrcnn/
│   ├── yolov11n/
│   ├── yolov11n-no-pretrained/
│   └── yolov11s/
└── README.md
```

## Evaluasi

Performa diukur menggunakan **mask mAP50** dan **mask mAP50–95** pada test set Panoptic Indoor serta test set foto pribadi. Hasil kedua dataset dianalisis untuk melihat perbedaan performa pada domain yang berbeda.

Untuk NRP dengan digit terakhir 5, variabel eksperimen yang ditetapkan adalah **penggunaan pretrained weights**. Perbandingan YOLO11n dengan dan tanpa pretrained weights digunakan untuk mempelajari variabel tersebut.

> Evaluasi Mask R-CNN pada test foto pribadi perlu diulang setelah pemetaan kelas diperbaiki. Jangan gunakan metrik lamanya sebagai hasil final.

## Menjalankan notebook

Notebook dijalankan di Kaggle. Tambahkan dataset dan checkpoint model yang dibutuhkan melalui **Add Input**, lalu jalankan sel notebook dari atas ke bawah. Periksa kembali path input sebelum menjalankan evaluasi.

Jangan menaruh API key, token, atau kredensial di notebook maupun repositori.

## Data dan checkpoint

Dataset foto pribadi, anotasi, dan checkpoint model tidak disertakan di repositori. Tambahkan melalui Kaggle Input saat menjalankan notebook. Simpan metrik dan log yang diperlukan di folder `results/`.

## Bukti dan laporan

Folder `evidence/` memuat screenshot proses yang relevan. Folder `reports/` memuat laporan tugas dan logbook.