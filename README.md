<div align="center">

![GitHub repo size](https://img.shields.io/github/repo-size/itu-helper/data?style=flat-square)
![GitHub](https://img.shields.io/github/license/itu-helper/data?style=flat-square)

# **ITU Helper**

</div>
    
<div align="left">
    <img src="https://raw.githubusercontent.com/itu-helper/home/main/images/logo.png" align="right"
     alt="ITU Helper Logo" width="180" height="180">
</div>
<div align="center">

_İTÜ'lüler için İTÜ'lülerden_

_ITU Helper_ İstanbul Teknik Üniversitesi öğrencilerine yardım etmek amacıyla ön şart görselleştirme, ders planı oluşturma ve resmi İTÜ sitelerini birleştirme gibi hizmetler sağlayan bir açık kaynaklı websitesidir.

_ITU Helper_'a [_bu adresten_](https://itu-helper.github.io/home/) ulaşabilirsiniz.

</div>
<br>
<br>
<br>

# **itu-helper/data**

## **Ne İşe Yarar?**

[`itu-helper/data-updater`](https://github.com/itu-helper/data-updater) _repo_'sunun scraplediği verileri saklamak için kullanılır. Saklanan verilerin kullanımı için ise [`itu-helper/sdk`](https://github.com/itu-helper/sdk) _repo_'sundan yararlanabilirsiniz.

## **Veri Format'ları**

> [!TIP]
>Veri formatlarını incelemeden önce, [verilerin isimlendirilmesine](https://github.com/itu-helper/data-updater?tab=readme-ov-file#verilerin-i%CC%87simlendirilmesi) bakmanız tavsiye edilir.

### **lessons.psv**

[Bu](https://obs.itu.edu.tr/public/DersProgram) sayfada bulunan tablo üzerinden toplanan, **lisans** ders (_Lesson_) verilerini tutar.

```text
CRN|Ders Kodu|Öğretim Yöntemi|Öğretim Üyesi|Bina|Gün|Saat|Derslik|Kontenjan|Yazılan|Dersi Alabilen Programlar
```

### **courses.psv**

[Bu](https://www.sis.itu.edu.tr/TR/ogrenci/lisans/ders-bilgileri/ders-bilgileri.php) sayfada bulunan sorgulama sistemi üzerinden toplanan, ders (_Course_) verilerini tutar.

```text
Ders Kodu|Ders Adı|Dil|Kredi|AKTS|Önşart|Sınıf Kısıtı|Açıklama
```

### **course_plans.txt**

[Bu](https://obs.itu.edu.tr/public/DersPlan/) sayfada bulunan sorgulama sistemi üzerinden toplanan, ders planı (_Course Plan_) verilerini tutar.

```text
# Fakülte Adı
## Bölüm Adı
### İterasyon Adı
Dönem1Ders1=Dönem1Ders2=Dönem1Ders3=Dönem1Ders4
Dönem2Ders1=Dönem2Ders2=Dönem2Ders3=Dönem2Ders4
...
Dönem8Ders1=Dönem8Ders2=Dönem8Ders3=Dönem8Ders4
```

Burdaki ders isimlerinde, `courses.psv` ve `lessons.psv` dosyalarındaki `Ders Kodu` kısımdaki veri kullanılır. Eğer ders seçmeli iste, aşağıdaki formatta saklanır

```text
[SeçmeliDersAdı*(AlınabilecekDers1|AlınabilecekDers2|AlınabilecekDers3)]
```

> [!NOTE]
> Veri bulunamayan dönemler yerine boş satır bulunmaktadır.

### **building_codes.psv**

[Bu](https://www.sis.itu.edu.tr/TR/obs-hakkinda/bina-kodlari.php) sayfada bulunan tablo üzerinden toplanan, bina verilerini tutar.

```text
Bina Kodu|Bina Adı|Yerleşke
```

### **programme_codes.psv**

[Bu](https://www.sis.itu.edu.tr/TR/obs-hakkinda/lisans-program-kodlari.php) sayfada bulunan tablo üzerinden toplanan, program verilerini tutar.

```text
Program Kodu|Program Adı|Fakülte Adı| Fakülte Kodu
```
