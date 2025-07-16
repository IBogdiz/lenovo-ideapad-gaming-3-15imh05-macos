# 💻 EFI Hackintosh pentru Lenovo IdeaPad Gaming 3 15IMH05 (i5-10300H)

Acesta este EFI-ul meu pentru Hackintosh, făcut și testat pe **macOS Monterey 12.7.6**, special pentru Lenovo IdeaPad Gaming 3 15IMH05. Funcționează decent, dar mai sunt lucruri care trebuie rezolvate.

---

## 🧱 Specificații hardware

| Componentă     | Informații                                                                 |
|----------------|----------------------------------------------------------------------------|
| **CPU**        | Intel Core i5-10300H (UHD Graphics 630)                                    |
| **RAM**        | 32 GB DDR4                                                                 |
| **Stocare**    | SSD M.2 NVMe + SSD SATA 128GB (macOS instalat aici)                        |
| **Grafică**    | Intel UHD Graphics 630 (fără accelerare grafică)                           |
| **Placă video**| NVIDIA GTX 1650 (dezactivată complet în macOS)                             |
| **Display**    | 15.6" FHD 1920x1080 IPS 60Hz                                                |
| **Wi-Fi/BT**   | Intel AX201 – **nu funcționează** în macOS                                 |
| **Trackpad**   | I2C HID – funcționează cu VoodooI2C + VoodooI2CHID                         |

---

## ✅ Compatibilitate macOS Monterey 12.7.6

| Status | Componentă              | Detalii                                                                 |
|--------|--------------------------|-------------------------------------------------------------------------|
| ❌     | **Wi-Fi**               | AX201 nu e suportat – nu funcționează                                   |
| ❌     | **Bluetooth**           | Nu funcționează (e parte din AX201)                                     |
| ⚠️     | **Grafică**            | Fără accelerare (VRAM 1044MB, dock negru, lag)                          |
| ⚠️     | **Audio**              | Funcționează cu AppleALC, dar parțial                                   |
| ❌     | **USB**                | NU sunt mapate – trebuie configurat cu USBMap                           |
| ✅     | **Tastatură + Fn**     | Merge perfect, inclusiv iluminarea cu tasta Fn                          |
| ✅     | **Trackpad + Gesturi** | Funcționează cu VoodooI2C + VoodooI2CHID (gesturi de bază)              |
| ✅     | **Microfon**           | Funcțional                                                              |
| ✅     | **Webcam**             | Funcțional                                                              |
| ⚠️     | **Sleep**              | Instabil – se recomandă dezactivare                                     |

---

## 📦 Ce include EFI-ul

- OpenCore (versiune stabilă compatibilă cu Monterey)
- Config.plist configurat pentru MacBookPro16,1
- SSDT-uri: EC, PLUG, dezactivare dGPU (GTX 1650)
- Kext-uri:
  - Lilu
  - WhateverGreen
  - AppleALC
  - VirtualSMC
- Nu conține nimic pentru Wi-Fi/BT (nu are rost fără Broadcom)

---

## 🔧 Ce mai ai de făcut

- 🧩 Mapează USB-urile (cu Hackintool sau USBMap)
- 🛜 Schimbă placa AX201 cu una **Broadcom compatibilă** (ex: BCM94360NG) pentru Wi-Fi/Bluetooth
- 🎨 Activează accelerarea grafică (momentan lipsește)
- 🎧 Testează și alte `layout-id` pentru un sunet mai stabil
- 💤 Dezactivează sleep-ul dacă ai probleme

---

## ⚙️ Setări BIOS recomandate

- Secure Boot → dezactivat  
- Fast Boot → dezactivat  
- VMD → dezactivat  
- AHCI → activat  
- CFG Lock → dezactivat (sau patch dacă nu se poate)

---

## 📜 Alte informații

- EFI-ul a fost testat pe macOS **Monterey 12.7.6**
- Ar putea merge și pe Ventura sau Sonoma, dar necesită modificări

---

## 🙌 Disclaimer & contribuții

Acest EFI e oferit gratuit pentru uz personal. Nu îl vinde și nu-l redistribui ca fiind al tău.  
Dacă ai același laptop și reușești să-l îmbunătățești, deschide un pull request sau trimite un mesaj!
