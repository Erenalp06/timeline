# Timeline

Tarayıcıda çalışan, projelere ayrılmış kişisel çalışma günlüğü.

## Özellikler

- Her proje için ayrı, soldan sağa kronolojik zaman çizelgesi
- Yalnızca **bugünün tarihine** kayıt oluşturma (tarih alanı seçilemiyor)
- Geliştirme, karar, sorun, çözüm ve not kayıt türleri
- Tür filtresi, yatay kaydırma ve "Bugüne git" düğmesi
- Aynı güne ait kayıtları tek tarih altında gruplama ve günlük detay görünümü
- Başlık, açıklama, Markdown, tarih, proje ve tür üzerinden üç kapsamlı arama: tüm projeler, mevcut proje, mevcut gün
- Arama kısayolu: Ctrl+K (macOS: Cmd+K), sonuçtan ilgili gün ve kayda geçiş
- LLM gerektirmeyen, kural tabanlı Markdown biçimlendirme ve önizleme
- Kayıt türü, başlık ve açıklamasını düzenleme; son düzenleme zamanını saklama
- Kayıtları çöp kutusuna taşıma, orijinal tarihine geri yükleme veya kalıcı silme
- Verilerin tarayıcıda localStorage ile saklanması
- Bütün projeleri (çöp kutusundaki kayıtlar dahil) JSON olarak dışa aktarma ve içe aktarma
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

Yeni kayıtlar cihazın yerel tarihi ve saati ile oluşturulur. Geçmişe tarih seçimi yoktur. Mevcut kayıtların içeriği düzenlenebilir, ancak oluşturulma tarihi ve saati sabit kalır. Silinen kayıtlar önce çöp kutusuna taşınır ve geri yüklenebilir; çöp kutusundan kalıcı silme geri alınamaz. Bu, sunucusuz bir uygulamada değiştirilemez kayıtların kriptografik olarak doğrulanabildiği anlamına gelmez; bilgisayar saati veya JSON dosyası değiştirilebilir.

## Not

Bu erken sürümdür. Kayıtlar metin ve sınırlı Markdown biçimlendirmesi içerir; dosya eki, bulut senkronizasyonu ve kullanıcı hesabı yoktur.

## Çöp kutusu

Bir kayıt silindiğinde zaman çizelgesinden ve aramadan gizlenir; çöp kutusunda saklanır. Sol menüde **Çöp kutusu** üzerinden kayıt geri yüklenebilir veya ikinci onayla kalıcı silinebilir. Geri yükleme kaydın orijinal tarihini, başlığını, türünü ve içeriğini korur. JSON yedekleri çöp kutusunu da içerir; eski JSON dosyaları aynı formatla içe aktarılabilir. Çöp kutusu otomatik boşaltılmaz.
