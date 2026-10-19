# 30. Kat — çalışma notları

Bu depo, "30. Kat" zombi hayatta kalma oyununun tek ve güncel kaynağıdır.
Kullanıcı (umtiti719) hem laptoptan hem masaüstü bilgisayardan çalışıyor; bu yüzden
her şeyin doğrusu burada durur.

## Kurallar
- İşe başlamadan önce depodaki en son hâli çek (`git pull`). Eski bir kopyanın üzerinde çalışma.
- Her değişiklikten sonra commit at ve `main` dalına push et. İş bitince depoda olmayan değişiklik kalmasın.
- Commit mesajları Türkçe ve kısa olsun.
- Kullanıcı kodlamaya yeni başlıyor: açıklamaları sade Türkçeyle yap.

## Dosyalar
- `index.html` — oyunun 3B sürümü (Three.js r128 cdnjs, post-processing dosyaları jsdelivr three@0.128.0/examples/js). Tüm kod tek dosyada.
  Modeller kodla üretiliyor, dışarıdan model dosyası yok.
- `2d.html` — eski 2B (SVG) sürüm, arşiv olarak duruyor.
- `.nojekyll` — GitHub Pages için.

## Yayın
- GitHub Pages: https://umtiti719.github.io/30-kat/ (main dalı, kök klasör). Push edince kendiliğinden güncellenir.
- Claude artifact sürümü: https://claude.ai/artifact/3ckcVTfHkHF8fXVhDXp3NR
  Oyun değişince bunu da güncelle: `index.html`'den `<!doctype>`, `<html>`, `<head>`, `<body>` sarmalayıcısını
  ve `<style>html,body{margin:0}</style>` satırını çıkarıp kalan içeriği bu URL'ye yayınla.

## Oyun yapısı (kısaca)
- Durum nesnesi `s` (gün, enerji, sağlık, tokluk, su, moral, barikat, stoklar). `localStorage` anahtarı `kat30-save-v1`.
- `ACTIONS`: gündüz eylemleri. `pickEvent()`: gece olayları (2., 3., 5., 8., 11., 13., 19., 24. günler sabit olaylar).
- `build3D()` / `updateScene()` / `loop()`: 3B sahne. `SPOT3`: karakterin gittiği noktalar.
- Olay pencerelerindeki çizimler (`peepSVG`, `artFire`, `artHeli`...) SVG olarak kaldı.

## Görsel yön
- Kasvetli, salgın atmosferi: soluk renkler, sis, yanan şehir, titreyen lamba, mum ışığı, film greni ve vinyet.
- Neşeli/çizgi film renklerinden kaçın. Olay pencerelerindeki 2B SVG çizimler henüz bu tona uyarlanmadı.
