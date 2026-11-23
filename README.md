# Timeline

Tarayıcıda çalışan, projelere ayrılmış kişisel çalışma günlüğü.

## Özellikler

- Her proje için ayrı, soldan sağa kronolojik zaman çizelgesi
- Yalnızca **bugünün tarihine** kayıt oluşturma (tarih alanı seçilemiyor)
- Geliştirme, karar, sorun, çözüm ve not kayıt türleri
- Tür filtresi, yatay kaydırma ve "Bugüne git" düğmesi
- Aynı güne ait kayıtları tek tarih altında gruplama ve günlük detay görünümü
- Tek günlük projelerde ortalanmış, geniş ekrana uyumlu kartlar
- Kayıtlar arasında **Çözüyor**, **Devamı** ve **İlgili** bağlantıları; çözülmüş sorun etiketleri
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

## Kayıt bağlantıları

Bir kayıt detayını açıp **Bağlantı ekle** butonunu kullanarak aynı projedeki başka bir kayıtla ilişki kurabilirsin. **Çözüyor** ilişkisi, çözüm kaydından sorun kaydına oluşturulur. Sorun kaydının **Çözüldü** etiketi, buna gelen bağlantıdan hesaplanır. İlişkiler tek tek kaldırılabilir; bağlantı kaldırmak kayıtları silmez. İlişkiler JSON yedeğinde kaydedilir.

`version: 1` korunmuştur. Eski yedeklerde `relations` bulunmayabilir; bu alan isteğe bağlıdır. Bağlantılar `relations: [{"type":"resolves|continues|related","targetId":"..."}]` biçiminde saklanır. Aynı proje kısıtlaması uygulanır. JSON içe aktarımı eskiden olduğu gibi mevcut verilerin tamamının yerine geçer; öncesinde yedek alın.

## Gerçek / Test çalışma alanları

Sol menüde **Gerçek** ve **Test** arasında geçiş yapılabilir. Gerçek ortam mevcut `localStorage` anahtarı olan `timeline.v1` ile devam eder; **mevcut veriler için otomatik taşıma yapılmaz**. Test ortamı `timeline.test.v1` anahtarında bağımsız tutulur. Seçilen ortam sekme bazında `sessionStorage` ile hatırlanır. Her ortamın projeleri, kayıtları, bağlantıları, çöp kutusu, içe/dışa aktarma işlemleri ayrıdır.

Test ortamındaki **Gerçek verileri teste kopyala** düğmesi, onaydan sonra gerçek verilerin bir kopyasını test alanına aktarır. Gerçek alanı değiştirmez ancak testteki eski verilerin üzerine yazar. JSON yedekleri `workspace` alanı içerir; eski sürümün `version:1` yedekleri uyumludur. İçe aktarmada kaynak ve hedef ortam gösterilir; seçili çalışma alanına yazılır. Bu ayrım sunucu tarafı çok kiracılı yapı veya kimlik doğrulama değildir ve yalnızca o tarayıcı profiline özgüdür.
