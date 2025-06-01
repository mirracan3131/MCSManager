
<div align="center">
  <a href="https://mcsmanager.com/" target="_blank">
    <img src="https://public-link.oss-cn-shenzhen.aliyuncs.com/mcsm_picture/logo.png" alt="MCSManagerLogo.png" width="510px" />    
  </a>

  <br />

  <h1 id="mcsmanager">
    <a href="https://mcsmanager.com/" target="_blank">MCSManager Paneli</a>
  </h1>

[![--](https://img.shields.io/badge/Support-Windows/Linux-green.svg)](https://github.com/MCSManager)
[![Durum](https://img.shields.io/badge/npm-v8.9.14-blue.svg)](https://www.npmjs.com/)
[![Durum](https://img.shields.io/badge/node-v16.20.2-blue.svg)](https://nodejs.org/en/download/)
[![Lisans](https://img.shields.io/badge/License-Apache%202.0-red.svg)](https://github.com/MCSManager)

[Resmi Web Sitesi](http://mcsmanager.com/) | [Belgeler](https://docs.mcsmanager.com/) | [Discord](https://discord.gg/BNpYMVX7Cd)

[简体中文](README_ZH.md) | [繁體中文](README_TW.md) | [Deutsch](README_DE.md) | [Português BR](README_PTBR.md) |
[日本語](README_JP.md) | [Español](README_ES.md) | [Thai](README_TH.md) | [Türkçe](README_TR.md)

</div>

<br />

## MCSManager Nedir?

**MCSManager Paneli** (MCSM), **Minecraft ve Steam oyun sunucularını yönetmek için geliştirilmiş modern, güvenli ve dağıtık bir kontrol panelidir.**

MCSManager, özellikle Minecraft topluluğunda belirli bir popülerliğe ulaşmıştır. Birden fazla sunucuyu merkezi bir panelden yönetme imkanı sunar ve çok kullanıcıya sahip, güvenilir bir izin sistemi sağlar. Sadece Minecraft değil, Terraria ve çeşitli Steam oyunlarını da desteklemektedir. Amacımız, oyun sunucusu yönetimi için canlı ve destekleyici bir topluluk oluşturmaktır.

MCSManager şu dilleri destekler: **İngilizce, Fransızca, Almanca, İtalyanca, Japonca, Portekizce, Basitleştirilmiş Çince ve Geleneksel Çince**. İleride daha fazla dil desteği eklemeyi planlıyoruz!

**Terminal**

![failed_to_load_screenshot.png](/.github/panel-image.png)

**Sunucu Listesi**

![failed_to_load_screenshot.png](/.github/panel-instances.png)

**Özelleştirilebilir Arayüz**

![failed_to_load_screenshot.png](/.github/panel-custom-layout.gif)

## Özellikler

1. Tek tıklamayla `Minecraft` Java/Bedrock sunucusu kurulumu
2. Çoğu `Steam` oyun sunucusuyla uyumlu (`Palworld`, `Squad`, `Project Zomboid`, `Terraria` vb.)
3. Özelleştirilebilir kullanıcı arayüzü
4. `Docker Hub` üzerindeki tüm imajları destekler, çoklu kullanıcı ve ticari hizmet desteği!
5. Tek bir web arayüzü ile birden fazla sunucuyu yönetin
6. Basit teknoloji yığını, yalnızca Typescript bilgisi ile tüm panel geliştirilebilir
7. Ve dahası!

## Çalışma Ortamı

MCSManager hem `Windows` hem `Linux` sistemlerini destekler. Tek gereksinim `Node.js` ve bazı **açma (decompress) kütüphaneleridir**.

Gereken minimum Node.js sürümü: [16.20.2](https://nodejs.org/en)

## Kurulum

### Windows

Windows için paketlenmiş çalıştırılabilir dosyalar mevcuttur:

Git: [https://mcsmanager.com/](https://mcsmanager.com/)

### Linux

**Tek Komutla Kurulum**

> Bu betik sistem servislerini kaydedeceği için root izni gerektirir.

```bash
sudo su -c "wget -qO- https://script.mcsmanager.com/setup.sh | bash"
```

**Kullanım**

```bash
systemctl start mcsm-{web,daemon}
systemctl stop mcsm-{web,daemon}
```

- Sadece Ubuntu/Centos/Debian/Archlinux desteklenmektedir.
- Kurulum dizini: `/opt/mcsmanager/`

**Linux Manuel Kurulum**

Kurulum betiği başarısız olursa aşağıdaki adımlarla manuel kurulum yapabilirsiniz:

```bash
mkdir /opt
cd /opt/
wget https://nodejs.org/dist/v20.11.0/node-v20.11.0-linux-x64.tar.xz
tar -xvf node-v20.11.0-linux-x64.tar.xz
ln -s /opt/node-v20.11.0-linux-x64/bin/node /usr/bin/node
ln -s /opt/node-v20.11.0-linux-x64/bin/npm /usr/bin/npm

mkdir /opt/mcsmanager/
cd /opt/mcsmanager/

wget https://github.com/MCSManager/MCSManager/releases/latest/download/mcsmanager_linux_release.tar.gz
tar -zxf mcsmanager_linux_release.tar.gz

./install.sh

# İki ayrı terminal veya screen kullanın
./start-daemon.sh
./start-web.sh
# Web erişimi için: http://localhost:23333/
```

Bu yöntem MCSManager'ı sistem servisi olarak kurmaz. Yönetim için `screen` kullanılmalıdır. Servis olarak kurmak için dökümantasyonu inceleyin.

## Geliştirme

Geliştiriciler içindir, genel kullanıcılar atlayabilir.

### Eklentiler

VS Code üzerinde şu eklentiler önerilir:

- i18n görüntü desteği (I18n Ally)
- Kod biçimlendirici (Prettier)
- Vue - Resmi
- ESLint

### macOS

```bash
git clone https://github.com/MCSManager/MCSManager.git
./install-dependents.sh
./npm-dev-macos.sh
```

### Windows

```bash
git clone https://github.com/MCSManager/MCSManager.git
./install-dependents.bat
./npm-dev-windows.bat
```

### Bağımlılıklar

[PTY](https://github.com/MCSManager/PTY) ve [Zip-Tools](https://github.com/MCSManager/Zip-Tools) projelerinden gerekli dosyaları indirip `daemon/lib` klasörüne yerleştirin.

### Üretim Sürümünü Derleme

```bash
./build.bat # Windows
./build.sh  # macOS
```

Çıktı dizini: "production-code"

## Katkı

Sorun yaşarsanız [Issue açabilirsiniz](https://github.com/MCSManager/MCSManager/issues/new/choose) ya da projeyi çatallayıp Pull Request gönderebilirsiniz.

Kod katkısı yapmadan önce stil rehberine göz atmanız önerilir: [İlgili Issue](https://github.com/MCSManager/MCSManager/issues/544)

## Tarayıcı Uyumluluğu

- `Chrome`, `Firefox` ve `Safari` desteklenmektedir.
- `Internet Explorer` desteği sona ermiştir.

## Hata Bildirme

**Issue Aç:** [Tıklayın](https://github.com/MCSManager/MCSManager/issues/new/choose)

**Güvenlik Açıkları:** [SECURITY.md](SECURITY.md)

## Uluslararasılaştırma

Aşağıdaki katkıcılara çeviri desteklerinden dolayı teşekkür ederiz:

- [KevinLu2000](https://github.com/KevinLu2000)
- [Yumao](https://github.com/yumao233)
- [JHL-HK](https://github.com/jhl-hk)
- [IceBrick](https://github.com/IceBrick01)

## Lisans

MCSManager açık kaynak kodludur ve [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0) lisansı ile lisanslanmıştır.

Telif Hakkı ©2025 MCSManager.
