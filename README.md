# QGIS Seçili Katmanı GeoJSON Olarak Kaydetme 🗺️

Bu proje, QGIS üzerinde seçili katmanı otomatik olarak **GeoJSON formatında dışa aktarmayı** sağlar. Python ile **PyQGIS** kullanarak dışa aktarım işlemini hızlandırır.

## 📌 Özellikler
- Seçili vektör katmanını **tek tıklama** ile `.geojson` formatında kaydeder.
- **QGIS Python Konsolunda** kolayca çalıştırılabilir.
- Kullanıcıdan ek giriş istemeden **otomatik olarak kaydetme işlemi yapar**.

## 🛠 Kullanılan Teknolojiler
- **QGIS & PyQGIS** (QGIS Python API)
- **Python 3**

## 🚀 Kullanım
### **1️⃣ QGIS Python Konsolunu Aç**
- QGIS’te **Plugins → Python Console** menüsüne tıkla.

### **2️⃣ Kodu Yapıştır ve Çalıştır**
- Aşağıdaki komutu Python Konsoluna yapıştır:

from qgis.core import QgsProject, QgsVectorFileWriter

# 1️⃣ Aktif katmanı al
layer = QgsProject.instance().mapLayersByName("Bina_Katmanı")[0]  # Katman adını değiştir

if layer:
    # 2️⃣ Çıktı dosya yolunu belirle
    output_path = "/home/kullanici/itu_bina.geojson"  # Dosya yolunu değiştir

    # 3️⃣ Katmanı GeoJSON olarak dışa aktar
    QgsVectorFileWriter.writeAsVectorFormat(layer, output_path, "UTF-8", layer.crs(), "GeoJSON")

    print(f"✅ Katman başarıyla {output_path} olarak kaydedildi!")
else:
    print("⚠️ Lütfen önce bir katman seçin!")

# 1️⃣ Aktif katmanı al
layer = QgsProject.instance().mapLayersByName("Bina_Katmanı")[0]  # Katman adını değiştir

if layer:
    # 2️⃣ Çıktı dosya yolunu belirle
    output_path = "/home/kullanici/itu_bina.geojson"  # Dosya yolunu değiştir

    # 3️⃣ Katmanı GeoJSON olarak dışa aktar
    QgsVectorFileWriter.writeAsVectorFormat(layer, output_path, "UTF-8", layer.crs(), "GeoJSON")

    print(f"✅ Katman başarıyla {output_path} olarak kaydedildi!")
else:
    print("⚠️ Lütfen önce bir katman seçin!")
```

### **3️⃣ Çıktıyı Kontrol Et**
- Belirtilen dizinde **`.geojson`** dosyasının oluştuğunu kontrol et.

## 📂 Çıktılar
- **GeoJSON formatında harita verisi**
- **Kayıt işleminin başarılı olup olmadığını gösteren konsol mesajı**

## 📌 Lisans
Bu proje **MIT Lisansı** altında paylaşılmıştır.

