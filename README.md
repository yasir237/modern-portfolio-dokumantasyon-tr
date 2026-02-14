# Modern Portfolio Kılavuz Dokümantasyonu
Modern, modüler ve JSON tabanlı portfolyo sisteminin mimari yapısını ve içerik yönetim modelini açıklayan resmi dokümantasyon.

## Modern Portfolio
Modern, yüksek performanslı ve ölçeklenebilir bir geliştirici portfolyo uygulaması. Estetik tasarım, modüler mimari ve JSON tabanlı içerik yönetimini tek bir güçlü sistemde birleştirir.

<p align="center">
  <a href="https://yasiralrawi.netlify.app">
    <img src="https://img.shields.io/badge/Canlı_Demo-Modern_Portfolio-8750f7?style=for-the-badge" />
  </a>
</p>

Her bir bölümün ieriğini nereden yönetilebilir detaylıca açıklayan dokümentasyondur.

### 1. Header (Üst Menü)
Header, sitenin en üst kısmında bulunan menüdür.
Buradaki yazılar, dil seçimi ve iletişim bilgisi ayrı dosyalardan kontrol edilir.

Bu sayede kodla uğraşmadan içerikleri değiştirebilirsiniz.

<img width="1919" height="903" alt="header-map" src="https://github.com/user-attachments/assets/ae3597c6-38b9-4370-8469-5c92eeee67c3" />

#### Menü Yazılarını Değiştirmek

Menüde görünen yazılar şu dosyada bulunur:

```
messages/en.json
```

Bu dosyayı açtığınızda şöyle bir bölüm görürsünüz:

```json
{
  "header": {
    "home": "Home",
    "stats": "Stats",
    "services": "Services",
    "work": "Work",
    "projects": "Projects",
    "resume": "Resume",
    "about": "About",
    "skills": "Skills",
    "languages": "Languages",
    "volunteering": "Volunteering",
    "certificates": "Certificates",
    "contact": "Contact",
    "startAProject": "Start a Project"
  }
}
```

Tırnak içindeki yazıları istediğiniz gibi değiştirebilirsiniz.

Örneğin:

```json
"home": "My Home"
```

Aynı zamanda son satır olan `startAProject` bilgisini değiştirdiğimizde buttonun içindeki metni değişir

Örneğin:

```json
"startAProject": "Make Your Project"
```

Dosyayı kaydettikten sonra site otomatik olarak güncellenir.
Herhangi bir kod değiştirmeniz gerekmez.

Bu dosyanın adının `en` olması, İngilizce dili temsil ettiğini gösterir.

Yeni bir dil eklemek istediğinizde aynı yapıda yeni bir dosya oluşturmanız gerekir.
Örneğin Türkçe için:

```
tr.json
```

Yeni dil ekleme işlemi, ilerleyen bölümlerde adım adım açıklanacaktır.

#### Logo Değiştirmek

Logo dosya yolu şu dosyada bulunur:

```
data/techIcons.ts
```

```ts
export const SiteLogo = "/assets/images/logoLight.svg";
```

Buraya yeni logo dosyanızın yolunu yazmanız yeterlidir.



#### E-posta Adresini Değiştirmek

E-posta bilgisi şu dosyadadır:

```
data/contacts.ts
```

```ts
export const contactData = {
  email: "example@email.com"
};
```

Buraya kendi e-posta adresinizi yazabilirsiniz.


