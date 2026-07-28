<div align="center">

# 🇹🇷 Unitree Teleoperasyon (XR) Türkçe Rehber

**Unitree Robotics Türkiye Resmi Distribütörü · [Robotlar.org](https://www.robotlar.org)**

👉 **Tam Türkçe rehber: [robotlar.org/unitree/g1-teleoperasyon](https://www.robotlar.org/unitree/g1-teleoperasyon)**

</div>

---

## 🤖 Bu Proje Nedir?

Unitree **xr_teleoperate**, G1 insansı robotu bir **XR cihazıyla** (Apple Vision Pro, Meta Quest) uzaktan yönetmek için kullanılır. Operatörün baş, kol ve el hareketleri robota gerçek zamanlı aktarılır; kamera görüntüsü XR gözlüğe döner. **unitree_lerobot** ise bu oturumları **LeRobot formatında** kaydederek uçtan uca taklit öğrenimi (imitation learning / VLA) için veri seti üretir.

Bu depo, Unitree'nin Türkiye resmi distribütörü **Robotlar.org** tarafından hazırlanan Türkçe kurulum ve veri-toplama içeriğidir.

## 📋 Ön Gereksinimler

- Unitree **G1** robot (+ opsiyonel Inspire / Dex el)
- XR cihazı: Apple Vision Pro **veya** Meta Quest 3
- Robotla aynı ağda Linux PC (Ethernet)
- Python 3.10, conda önerilir

## ⚙️ Kurulum

```bash
git clone https://github.com/unitreerobotics/xr_teleoperate.git
cd xr_teleoperate

conda create -n tv python=3.10 -y
conda activate tv
pip install -r requirements.txt
```

XR akışı (image streaming) için robot ile gözlük arasında **WebRTC/gRPC** bağlantısı ve sertifika gerekir; detaylı adımlar için robotlar.org rehberine bakın.

## 🚀 Hızlı Başlangıç

```bash
# Robot tarafında image server'ı başlat, sonra PC'de:
conda activate tv
python teleop/teleop_hand.py        # el + kol teleoperasyonu

# Veri kaydı (LeRobot formatı) ile:
python teleop/teleop_hand.py --record
```

Kaydedilen bölümler (episodes) `unitree_lerobot` ile LeRobot veri setine dönüştürülüp ACT / Diffusion Policy / VLA eğitiminde kullanılır.

## 🛠 Sık Karşılaşılan Sorunlar

- **Gözlükte görüntü yok:** image server robot tarafında çalışıyor mu, sertifika/HTTPS ayarı doğru mu kontrol et.
- **El hareketleri robota geçmiyor:** el retarget yapılandırması (Inspire/Dex) ile robot el tipi eşleşmeli.
- **Gecikme yüksek:** Ethernet kullan, WiFi'de teleoperasyon titrer.

## 📚 Türkçe Rehberler

- **[G1 Teleoperasyon Kurulum & Kullanım Rehberi →](https://www.robotlar.org/unitree/g1-teleoperasyon)**
- [Unitree SDK Rehberi →](https://www.robotlar.org/unitree/sdk-rehberi)
- [RL Gym & Pekiştirmeli Öğrenme →](https://www.robotlar.org/unitree/rl-gym)
- [Tüm Unitree Açık Kaynak Rehberleri →](https://www.robotlar.org/unitree/acik-kaynak)

## 🤖 İlgili Robotlar

- [Unitree G1 (İnsansı / AI Avatar)](https://www.robotlar.org/tr/insansi-robotlar/unitree-g1)
- [Unitree H2 (Tam Boy İnsansı)](https://www.robotlar.org/tr/insansi-robotlar/unitree-h2)
- [Tüm İnsansı Robotlar →](https://www.robotlar.org/tr/insansi-robotlar)

## 🔗 İlgili Unitree Türkçe Depoları

[SDK2](https://github.com/Unitree-Turkiye/unitree-sdk2-turkce) ·
[Teleoperasyon](https://github.com/Unitree-Turkiye/unitree-teleoperasyon-turkce) ·
[RL Gym](https://github.com/Unitree-Turkiye/unitree-rl-gym-turkce) ·
[MuJoCo](https://github.com/Unitree-Turkiye/unitree-mujoco-turkce) ·
[ROS2](https://github.com/Unitree-Turkiye/unitree-ros2-turkce) ·
[VLA](https://github.com/Unitree-Turkiye/unitree-vla-turkce) ·
[🏠 Unitree Türkiye](https://github.com/Unitree-Turkiye)

---

> ℹ️ **Unitree Türkiye** — Unitree Robotics'in Türkiye resmi satış & teknik distribütörü. Robot tedariki, kurulum, eğitim ve Türkçe geliştirici desteği: **[robotlar.org](https://www.robotlar.org/tr/unitree-turkiye-partneri)** · 📧 info@robotlar.org

© 2026 **www.robotlar.org** — *Türkiye'de robotik iş gücü Robotlar.org'dan başlar.*
