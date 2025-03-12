# Basic Web Server Firewall

## Genel Bakış
Bu repository, Ubuntu sistemlerinde UFW (Uncomplicated Firewall) kullanarak temel web sunucusu güvenlik duvarı yapılandırmasını içerir. Yapılandırma, Apache2 web sunucusu kurulumunu ve güvenli web trafiği yönetimi için özel güvenlik duvarı kurallarını kapsamaktadır.

## Gereksinimler
- Ubuntu Sunucu (önerilen: en son LTS sürümü)
- Root veya sudo yetkileri
- Terminal erişimi

## Kurulum Adımları

### 1. Sistem Güncellemesi
Öncelikle sistem paket listesini güncelleyin:
```bash
sudo apt update
```

### 2. Apache2 Kurulumu ve Yapılandırması
Apache2 web sunucusunu kurun ve yapılandırın:
```bash
# Apache2 Kurulumu
sudo apt install apache2 -y

# Apache2 servisini başlatma
sudo systemctl start apache2

# Sistem başlangıcında Apache2'yi etkinleştirme
sudo systemctl enable apache2

# Apache2 durumunu kontrol etme
sudo systemctl status apache2
```

### 3. UFW Güvenlik Duvarı Yapılandırması
UFW güvenlik duvarını kurun ve yapılandırın:
```bash
# UFW Kurulumu
sudo apt install ufw -y

# UFW'yi etkinleştirme
sudo ufw enable

# Güvenlik duvarı kurallarını yapılandırma
sudo ufw allow 80/tcp          # HTTP trafiğine izin ver
sudo ufw allow from 1.1.1.1 to any port 3306  # Belirli IP'den MySQL'e izin ver
sudo ufw allow 143/tcp         # IMAP'a izin ver
sudo ufw allow 993/tcp         # IMAPS'e izin ver

# UFW durumunu kontrol etme
sudo ufw status verbose
```

## Güvenlik Duvarı Kuralları Özeti
- Port 80 (HTTP): Web trafiği için açık
- Port 3306 (MySQL): Belirli IP (1.1.1.1) ile sınırlı
- Port 143 (IMAP): E-posta servisleri için açık
- Port 993 (IMAPS): Güvenli e-posta servisleri için açık

## Doğrulama
Yapılandırmayı doğrulamak için:
1. Apache2 servis durumunu kontrol edin
2. UFW'nin aktif olduğunu ve kuralların doğru ayarlandığını doğrulayın
3. Port 80 üzerinden web erişimini test edin
4. E-posta servisi erişilebilirliğini onaylayın

## Sorun Giderme
Sorunlarla karşılaşırsanız:
1. `systemctl status apache2` komutu ile Apache2 servis durumunu kontrol edin
2. `sudo ufw status verbose` ile UFW kurallarını gözden geçirin
3. Hata mesajları için `/var/log/syslog` sistem günlüklerini kontrol edin

## Yazar
Zehra Kolsuz

## Not
Bu yapılandırma temel güvenlik önlemlerini sağlar. Özel ihtiyaçlarınıza bağlı olarak ek güvenlik yapılandırmaları gerekebilir.
