# Izleme-AlarmBotu-HAQQ

PANIC, SimplyVC tarafından tasarlanmış Cosmos düğümleri için hafif ancak güçlü bir açık kaynaklı izleme ve uyarı çözümüdür. Cosmos SDK kullanılarak oluşturulan tüm zincirlerle uyumludur. Araç, önemli uyarılar için telefon aramaları ve uyarı cihazınız üzerinde daha fazla kontrol için Telegram komutları gibi harika ve kullanışlı özellikler hariç tutulmadan, kullanıcı dostu olması düşünülerek oluşturulmuştur.

# PANIC Kurulum Rehberi

PANIC'i kurmak ve çalıştırmak için hazırsanız, başlayalım. PANIC'i kurabilmek için öncelikle bir linux işletim sistemine ve kuruluma başlamadan önce ön gereksinimlerin kurulmasına ihtiyacımız var.

Öncelikle Git'in kurulu olup olmadığını kontrol edelim. Terminaliniz çıktı olarak bir Git sürümünü verirse, bu Git'in sisteminizde kurulu olduğu anlamına gelir.
```
git --version
```
Eğer git kurulu değilse aşağıdaki komut ile kuralım.
```
sudo apt install git
```
# Docker ve Docker-Compose Kurulumu

Docker, uygulamalarınızı hızla derlemenize, test etmenize ve dağıtmanıza imkan tanıyan bir yazılım platformudur. Docker, yazılımları kitaplıklar, sistem araçları, kod ve çalışma zamanı dahil olmak üzere yazılımların çalışması için gerekli her şeyi içeren container adlı standartlaştırılmış birimler halinde paketler. Şimdi kuruluma geçelim.

Yine önceki gibi aşağıdaki komutlar yardımıyla sistemimizde docker kurulu olup olmadığını kontrol edelim.

```
docker --version
docker-compose --version
```

Kurulu değilse aşağıdaki komutları kullanarak kuralım.

```
curl -sSL https://get.docker.com/ | sh
sudo apt install docker-compose -y
```
# PANIC Reposunu Sistemimize Klonlama

Aşağıdaki komut ile PANIC reposunu sistemimize klonlayalım ve klasörün içine girelim.

```
git clone https://github.com/SimplyVC/panic
cd panic
```
# Parametreleri Düzenleme

Aşağıdaki komut ile nano kullanarak .env dosyasına giriş yapalım.

```
sudo nano .env 
```
Ardından aşağıdaki parametreleri bulup düzenleyelim.

* INSTALLER_USERNAME: kullanıcıadı

* INSTALLER_PASSWORD: şifre

* UI_ACCESS_IP: Panic'in kurulu olduğu host ip si.

Düzenleme bittikten sonra "Ctrl + x" tuşlarına basıp ardından "Y" tuşu ile dosyayı modifiye ettiğimizi onaylayalım ve "Enter" ile kaydedip çıkalım.

# PANIC'i Başlatma

Aşağıdaki komut ile docker imajı yaratarak PANIC'i başlatalım.

```
``bash docker-compose up -d --build
```
Eğer işlem sırasında bir sorun yaşarsanız aşağıdaki komutlar ile Docker imajını silip, problemi çözdükten sonra tekrar deneyebilirsiniz.

```
```bash
docker-compose kill
docker system prune -a --volumes
docker-compose up -d --build
```

# Telegram Botu Yaratma ve Bildirimleri Aktif Etme

Öncelikle Telegram hesabımıza @BotFather 'ı ekleyeceğiz.

BotFather, yeni bot hesapları oluşturmak ve mevcut botlarınızı yönetmek için kullanabileceğiniz bir bot yazılımıdır.

Botfather'ı telegrama ekledikten sonra kendi botumuzu yaratmak için "Start" a basıyoruz. Ardından aşağıdaki adımları takip ediyoruz.

- "/newbot" komutu ile bot adı ve kullanıcı adı gibi bilgileri tanımlıyoruz.
- Bot bize yarattığımız bota ulaşmak için bir link ve API Token kodu verecek. Kodu bir yere kaydediyoruz.
- Bize verilen t.me/<kullanıcıadı> linkini kullanarak botumuza erişiyoruz ve "Start" butonuna basıyoruz.
- 


