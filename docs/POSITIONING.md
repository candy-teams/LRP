# LRP — Lesstupid Resource Planning

## Konumlandırma

LRP, iş süreçlerini anlamak, iyileştirmek ve uygulamak için geliştirilen yapay zekâ destekli bir yaklaşım ve ortak çekirdek projesidir.

**Bir süreci dokümante et, mevcut sistemde iyileştir veya LRP Core üzerinde inşa et.**

## Üç Uygulama Yolu

| Yol | Ne yapılır? | Çıktı |
|---|---|---|
| Blueprint | Adımlar, roller, iş kuralları, veriler, kontroller ve istisnalar tanımlanır. | LRP Core kurulmadan da kullanılabilen süreç tasarımı. |
| Mevcut sistemde iyileştirme | SAP, Oracle veya kullanılan sistemde uygun konfigürasyon ve geliştirmeler yapılır. | Mevcut yatırım üzerinde test edilmiş iyileştirme. |
| LRP Core üzerinde inşa | Ortak nesne, ilişki, olay ve süreç bileşenleri üzerinde uygulama geliştirilir. | Bağımsız veya mevcut sistemlerle entegre uygulama. |

Bu yollar zorunlu aşamalar değildir. Aynı kurumda birlikte kullanılabilir. Blueprint nihai çıktı olabilir; her süreç LRP'ye taşınmak zorunda değildir.

## Örnek: Fatura Onayı

- Blueprint: Onay limitlerini, sorumluları, gerekli belgeleri ve istisnaları tanımla.
- Mevcut sistem: Onay akışını müşterinin ERP'sinde düzenle ve test et.
- LRP Core: Onay ve istisna yönetimini LRP üzerinde kur; muhasebeleştirmeyi SAP'de sürdür.

Uygulama yolu süreç bazında seçilir. Süreç yönetimi ile finansal kaydın sahipliği ayrı tanımlanır.

## SAP ve Diğer Sistemlerle Bağlantı

[SAP ADT MCP](https://github.com/ilkerkaanipcioglu/sap-adt-mcp), SAP'nin sunduğu servisler ve verilen yetkiler kapsamında kaynak kodu, bağımlılık ve geliştirme analizi için değerlendirilen bağlantı katmanıdır.

Günlük iş işlemleri için müşterinin sağlayacağı RFC/BAPI erişimi veya uygun iş API'leri kullanılması planlanır. ADT geliştirme erişimi, genel amaçlı işlem entegrasyonunun yerine geçmez. SAP sürümü, erişilebilir servisler, yetkiler ve veri kapsamı müşteri bazında doğrulanmalıdır. Oracle ve diğer sistemler kendi adaptörlerini gerektirir; bu metin hazır connector desteği ilan etmez.

## Yapay Zekâ ve Yerel Kurulum

AI; doküman/kod analizi, süreç tasarımı, değişiklik ve test önerileri, sınıflandırma ve istisna açıklaması için kullanılabilir. İşlem yetkileri, finansal kontroller ve onay zorunlulukları deterministik kurallarla yönetilmelidir.

Kurum içinde çalışan modeller bir kurulum seçeneğidir. Model ve donanım, veri politikası ve iş yüküne göre seçilir. Tamamen yerel kurulumda model dışındaki bileşenlerin telemetri ve dış servis bağlantıları da doğrulanır.

## Geçiş Seçildiğinde

Sağlayıcı değişimi gereken süreçlerde shadow, partial, primary ve full_cutover yaklaşımı uygulanabilir. Geçiş kapsamı, yetkili kayıt sistemi, mutabakat, kabul kriterleri ve geri dönüş koşulları tanımlanır. Sağlayıcıyı değiştirmek tek başına veri mutabakatı veya geri dönüş garantisi sağlamaz.

## Geliştirme Durumu ve İletişim

LRP geliştirme aşamasındadır. Bu belge ürün yaklaşımını tanımlar; tüm entegrasyonların, AI akışlarının veya üretim kontrollerinin tamamlandığını iddia etmez. [README](../README.md) uygulama durumunu, [VISION](../VISION.md) uzun vadeli hedefleri açıklar.

Müşteri ve partner iletişiminde:
- Mevcut sistemi anlamak ve ölçülebilir süreç faydası sağlamak önceliklidir.
- SAP, Oracle veya başka bir sistem üzerinde iyileştirme geçerli bir sonuçtur.
- Performans, tasarruf ve üretime hazır olma iddiaları gerçek ölçümle desteklenir.
- SAP partnerları ve danışmanlık ekipleri blueprint, mevcut sistem geliştirmesi veya LRP Core uygulaması teslimatına katılabilir.
