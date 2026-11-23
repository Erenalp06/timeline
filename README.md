# Timeline

Tarayıcıda çalışan, projelere ayrılmış kişisel çalışma günlüğü.

## Özellikler

- Her proje için ayrı, soldan sağa kronolojik zaman çizelgesi
- Yalnızca **bugünün tarihine** kayıt oluşturma (tarih alanı seçilemiyor)
- Geliştirme, karar, sorun, çözüm ve not kayıt türleri
- Tür filtresi, yatay kaydırma ve "Bugüne git" düğmesi
- Verilerin tarayıcıda localStorage ile saklanması
- Bütün projeleri JSON olarak dışa aktarma ve içe aktarma
- Tamamen statik, frameworksüz HTML/CSS/JavaScript; sunucu ve veritabanı gerektirmez

## GitHub Pages

Repository → **Settings → Pages → Build and deployment → Deploy from a branch** → **main** ve **/(root)** → **Save**.

Pages etkinleşince adres: https://erenalp06.github.io/timeline/

## Yerel çalıştırma

`index.html` dosyasını tarayıcıda açman yeterli.

## Verilerin saklanması

Veriler yalnızca kullanılan tarayıcı profilinin localStorage alanında saklanır; GitHub'a veya uzak sunucuya aktarılmaz. Farklı cihaz ya da tarayıcıda veriler otomatik eşitlenmez. Tarayıcı verileri silinirse kayıtlar kaybolabilir. Düzenli olarak **JSON dışa aktar** ile yedek al.

**İçe aktarma mevcut bütün kayıtların üzerine yazar;** uygulama işlemden önce onay ister. Önce dışa aktarma önerilir.

## Tarih kuralı

Yeni kayıtlar cihazın yerel tarihi ve saati ile oluşturulur. Geçmişe tarih seçimi ve mevcut kaydı düzenleme özellikleri bilerek eklenmedi. Bu, sunucusuz bir uygulamada değiştirilemez kayıtların kriptografik olarak doğrulanabildiği anlamına gelmez; bilgisayar saati veya JSON dosyası değiştirilebilir.

## Not

Bu ilk sürümdür. Kayıtlar salt metindir; dosya eki, bulut senkronizasyonu ve kullanıcı hesabı yoktur.
