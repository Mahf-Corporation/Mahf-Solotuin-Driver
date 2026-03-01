# Development Notes & CI 🔧

This repo now contains a minimal CI and test setup to make iterative improvements safer.

What was added:

- CMake-based **portable core** (`include/` + `src/`) so some core logic can be tested in user-mode.
- Unit tests in `tests/` using Catch2 (fetched via CMake's FetchContent).
- GitHub Actions workflow `.github/workflows/ci.yml` that builds the portable core on Windows, runs `cppcheck`, runs unit tests, and uploads artifacts.

How to build locally:

```powershell
mkdir build
cd build
cmake -G "Visual Studio 17 2022" -A x64 ..
cmake --build . --config Release
ctest -C Release
```

Suggested next steps (I can implement):
- Integrate clang-tidy and clang-format into CI (clang-tidy added; currently reports issues and uploads a report, will add baseline and stricter failure policy next).
- Expand portable core to extract more testable logic from kernel sources
- Add a driver-build job (WDK) in a separate workflow (may require self-hosted runner or secrets for signing)
- Add static analysis enforcement in PRs and fail the pipeline on regressions

Tell me which item you'd like me to pick next and I'll proceed.

## Mahf-Lambea4 Mimarisi (v4)

### Katmanlar
- **Presentation Layer**: WPF kontrol paneli, kullanıcı etkileşimini ve canlı metriği yönetir.
- **Service Layer**: Sürücü ile güvenli köprü; servis lifecycle, yeniden bağlanma ve komut yönlendirme.
- **Kernel Layer**: IOCTL tabanlı performans profili, çekirdek telemetrisi ve frekans kontrolü.
- **Deployment Layer**: Inno Setup + install script ile tek paket kurulum.

### Sözleşmeler
- Cihaz adı: `\\.\MahfLambea4CPU`
- Servis adı: `MahfLambea4CPU`
- Kontrol paneli exe: `Mahf-Lambea4-ControlPanel.exe`
- Setup exe: `Mahf-Lambea4-Setup_4.0.0.exe`

### Geliştirme prensipleri
1. Tüm adlandırmalar ürün sürümü ile uyumlu olmalı.
2. IOCTL ve veri yapıları driver/service/panel arasında tek kaynaktan yönetilmeli.
3. Kullanıcı mesajları riskli modlar için doğrulama istemeli.
4. Kurulum scriptleri idempotent olmalı (var olan servisi güvenli temizleyip yeniden kurmalı).
