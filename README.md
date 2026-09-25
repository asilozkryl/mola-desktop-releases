# Mola masaüstü

Mola'nın Windows, macOS ve Linux kurulum paketleri ve güncellemeleri bu depoda yayımlanır. Bu depo uygulamanın kaynak deposunu veya sunucu verilerini içermez.

[Kurulum paketlerini indir](https://github.com/asilozkryl/mola-desktop-releases/releases) · [Mola indirme sayfası](https://mola.psychodry.cloud/download)

## Kurulum

| Bilgisayar                              | Paket                   |
| --------------------------------------- | ----------------------- |
| Windows x64                             | `win-x64.exe`           |
| Apple Silicon Mac (M serisi), macOS 13+ | `mac-arm64.dmg`         |
| Intel Mac, macOS 13+                    | `mac-x64.dmg`           |
| Ubuntu / Debian x64                     | `linux-amd64.deb`       |
| Diğer uyumlu Linux x64 dağıtımları      | `linux-x86_64.AppImage` |

Mac'te DMG içindeki Mola'yı Uygulamalar klasörüne taşıyın. Linux AppImage için çalıştırma izni ve FUSE 2 desteği gerekir. Windows ve DEB paketlerinde işletim sisteminin kurulum adımlarını tamamlayın.

Mola'yı açın, ekibinizin HTTPS sunucu adresini girin ve Mola hesabınızla giriş yapın. Ana sunucumuz `https://mola.psychodry.cloud`. Tarayıcı oturumu masaüstüne otomatik aktarılmaz. Google ile giriş şimdilik web tarayıcısında kullanılabilir; masaüstünde Mola e-posta adresinizi ve parolanızı kullanın.

## Güncelleme

**1.0.8 ve önceki sürümlerden geçiş:** Yeni dağıtım kanalını kullanmak için 1.0.9 veya sonraki paketi bir kez indirip mevcut uygulamanın üzerine kurun. Kullanıcı profilini silmeyin; sunucu adresiniz ve oturum bilgileriniz burada saklanır. Eski sürümün güncelleme penceresi bu yeni dağıtım kanalını bulamaz.

**1.0.9 ve sonrası:** Uygulamada yeni sürüm bilgisi göründüğünde **Güncellemeyi aç** düğmesini kullanın. **Mola → Güncellemeleri kontrol et** menüsü de aynı pencereyi açar. Paketi uygulamadan indirin; indirme ilerlemesini takip edebilir ve iptal edebilirsiniz. Dosya bütünlüğü kurulumdan önce doğrulanır.

Kurulum siz onayladığınızda başlar. Önce görüşmenizi bitirin ve gönderilmemiş mesajınızı kontrol edin. Mac ve yazılabilir AppImage kurulumları güncellenip yeniden açılır; Windows ve DEB paketlerinde sistem kurucusunu tamamlayın. Başarısız indirme mevcut uygulamayı değiştirmez.

## Paket bütünlüğü ve işletim sistemi onayı

Her sürümde yedi kurulum dosyası ve bu dosyaların SHA-256 özetlerini içeren `SHA256SUMS` bulunur. İndirdiğiniz dosyanın özetini aynı sürümün listesiyle karşılaştırabilirsiniz. Bu kontrol, yayıncı sertifikasının yerine geçmez.

Windows paketleri henüz yayıncı sertifikasıyla imzalanmamıştır. Mac paketleri ad-hoc bütünlük imzası taşır; Apple Developer ID ve noter onayı bulunmaz. İlk açılışta işletim sistemi uyarısı görülebilir. Mac'te kaynağını doğruladığınız uygulama için Apple'ın [Gizlilik ve Güvenlik yönergelerini](https://support.apple.com/tr-tr/102445) izleyin; sistem genelinde güvenlik denetimlerini kapatmayın.

Mac uygulama bütünlüğünü kontrol etmek için:

```sh
codesign --verify --deep --strict --verbose=2 /Applications/Mola.app
```

Doğrulama başarısızsa uygulamayı açmaya zorlamayın; resmi paketi yeniden indirin.
