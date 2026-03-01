# Mahf-Lambea4 CPU Platform v4.0.0
## Kurulum, Mimari ve Kullanım Kılavuzu

Mahf-Lambea4; kernel sürücüsü, Windows servisi, kontrol paneli ve installer bileşenlerinden oluşan yeni nesil bir CPU yönetim platformudur.

## 🚀 Öne Çıkan Geliştirmeler
- **Yeni ürün adı**: Mahf-Lambea4
- **Katmanlı mimari**: Driver Core + Service Orchestrator + Control Panel + Installer
- **Tek protokol yaklaşımı**: IOCTL, servis adı, cihaz adı ve exe isimleri uyumlu hale getirildi
- **Dağıtım standardı**: Kurulum/servis/shortcut akışı yeni isimlerle güncellendi

## 🧱 Bileşenler
1. **Kernel Driver (`mahf_core.c/.h`)**
   - CPU algılama, çekirdek durumu, performans profili uygulama.
2. **Service (`mahf_service.c`)**
   - Driver bağlantısı, servis ömrü yönetimi, komut iletimi.
3. **Control Panel (`mainwindow.xaml.cs`)**
   - Canlı izleme, profil seçimi, kullanıcı etkileşimi.
4. **Installer (`setup.iss`, `install.bat`)**
   - Driver ve uygulama dağıtımı, servis oluşturma, kayıt girdileri.

## 📦 Yeni Çıktı Dosyaları
- `Mahf-Lambea4-Setup_4.0.0.exe`
- `Mahf-Lambea4-ControlPanel.exe`
- `Mahf-Lambea4-Service.exe`

## 🛠️ Hızlı Kurulum
1. `Mahf-Lambea4-Setup_4.0.0.exe` çalıştırın (Yönetici).
2. Kurulum tamamlandıktan sonra sistemi yeniden başlatın.
3. Başlat menüsünden **Mahf-Lambea4 CPU Control Panel** açın.

## 🔐 Minimum Gereksinimler
- Windows 10 21H2+ / Windows 11
- x64 mimari
- Administrator yetkisi

## 🧭 Mimari Doküman
Detaylı sistem tasarımı için `DEVELOPMENT.md` içindeki yeni Mahf-Lambea4 mimari bölümüne bakın.
