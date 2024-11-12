
Basic Web Server Firewall Yapılandırma Süreci Raporum:


1. Sistem Güncellemesi Yapıldı:

"sudo apt update" komutu kullanılarak sistem güncellendi ve gerekli paket listeleri başarıyla indirildi. Güncelleme sırasında herhangi bir hata alınmadı.

2. Apache2 Kurulumu ve Servis Kontrolü Adımları:

"sudo apt install apache2 -y" komutuyla Apache2 paketi yüklendi ve mevcut bir sürüm varsa güncellendi.

"sudo systemctl start apache2" komutuyla Apache2 servisi başlatıldı ve 
"sudo systemctl enable apache2" komutuyla sistem başlangıcında otomatik olarak çalıştırıldı.

"sudo systemctl status apache2" komutuyla servisin başarılı şekilde çalıştığı doğrulandı. 

Çıktıda "active (running)" ifadesi görüldü, herhangi bir hata ile karşılaşılmadı.

3. UFW Güvenlik Duvarı Yapılandırması:

"sudo apt install ufw -y" komutuyla UFW paketi yüklendi ve sudo ufw enable komutuyla güvenlik duvarı etkinleştirildi.

Web trafiği ve özel izinler için belirli portlar açıldı:

"sudo ufw allow 80/tcp" ile HTTP trafiğine izin verildi.
"sudo ufw allow from 1.1.1.1 to any port 3306" ile belirli bir IP adresinden MySQL trafiğine izin verildi.

IMAP ve IMAPS için "sudo ufw allow 143/tcp" ve "sudo ufw allow 993/tcp" komutları çalıştırılarak ilgili portlar açıldı.

"sudo ufw status verbose" komutuyla güvenlik duvarının aktif olduğu ve belirli kuralların başarıyla uygulandığı doğrulandı.

4. Sonuç:

Yapılandırma sürecinde herhangi bir hata ile karşılaşılmadı. Apache2 servisi ve UFW güvenlik duvarı beklendiği gibi çalışmaktadır. Bu süreçte, başarılı sonuçlar alındı ve tüm hizmetler doğru şekilde yapılandırıldı.


Zehra Nur Kolsuz-2320191014
