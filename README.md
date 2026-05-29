# YALI - Yet Another Linux Installer

Pisi Linux için geliştirilmiş, Qt5 arayüzlü sistem kurucu.

## Özellikler

- **Grafik kurulum** — PyQt5 ile görsel arayüz
- **Otomatik bölümleme** — Tüm disk, var olan sistemi küçült, boş alan veya manuel
- **Disk bölümleme** — ext4 desteği, GPT/MBR, LVM (isteğe bağlı)
- **EFI/UEFI desteği**
- **Çoklu dil desteği** — Türkçe, İngilizce, Almanca, Felemenkçe, İtalyanca, Fransızca, Portekizce, Lehçe, Katalanca, İsveççe, Macarca, Rusça, Hırvatça
- **Kurulum tipleri:** Normal, Temel Sistem, OEM, İlk Açılış, Kurtarma
- **Pisi paket yöneticisi** ile uyumlu
- **Canlı ortam** kurulum desteği

## Gereksinimler

- Python 2.7
- PyQt5
- Python parted (pyparted)
- Pisi paket yöneticisi
- Linux çekirdeği + udev

## Kurulum

```bash
python setup.py build
sudo python setup.py install
```

## Kullanım

Canlı bir Pisi Linux ortamında `start-yali` komutu ile başlatılır.

### Kernel parametreleri

| Parametre | Açıklama |
|---|---|
| `yali=live` | Canlı ortam kurulumu |
| `yali=system` | Temel sistem kurulumu |
| `yali=firstboot` | İlk açılış modu |
| `yali=rescue` | Sistem kurtarma |
| `yali=oem` | OEM kurulumu |
| `yali=nolvm` | LVM kullanma |
| `yali=debug` | Hata ayıklama modu |
| `yali=dryrun` | Diske yazmadan çalıştır |

## Proje Yapısı

```
yali/
├── conf/              # Yapılandırma dosyaları
├── docs/              # Dokümantasyon
├── lang/              # Dil dosyaları (.ts/.qm)
├── po/                # Çeviri dosyaları (.po)
├── yali/
│   ├── gui/           # Arayüz ekranları
│   │   └── Ui/        # Qt Designer ile oluşturulmuş UI'lar
│   ├── storage/       # Disk bölümleme motoru
│   │   ├── devices/   # Cihaz soyutlamaları
│   │   ├── formats/   # Dosya sistemi formatları
│   │   └── library/   # Yardımcı kütüphaneler
│   ├── context.py     # Global bağlam (storage, flags, consts)
│   ├── flags.py       # Bayraklar ve kernel parametreleri
│   └── constants.py   # Sabitler
├── setup.py           # Python paketleme
└── start-yali         # Başlatma betiği
```

## Lisans

GNU General Public License v2.

## Geliştirme

Hata raporları ve katkılar için GitHub Issues kullanılabilir.
