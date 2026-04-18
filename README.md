# Process Access Checker

Windows sistemleri üzerinde çalışan süreçleri tarayan ve belirli erişim yetkilerini kontrol eden Rust tabanlı bir sistem aracıdır.

## Özellikler
- Sistem süreçlerinin anlık görüntüsünü (snapshot) alır.
- Verilen süreç adına göre PID (Process ID) tespiti yapar.
- Belirlenen sürece okuma (PROCESS_VM_READ) ve bilgi sorgulama (PROCESS_QUERY_INFORMATION) yetkileriyle erişim testi yapar.

## Teknik Detaylar
- WinAPI (`windows-sys`) doğrudan kullanılmıştır.
- Bellek yönetimi ve süreç erişimleri güvenli olmayan (unsafe) bloklar üzerinden kontrol edilir.
- Toolhelp32 kütüphanesi ile süreç iterasyonu gerçekleştirilir.

```bash
cargo run
