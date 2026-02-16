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

### Header (Üst Menü)
Header, sitenin en üst kısmında bulunan menüdür.
Buradaki yazılar, dil seçimi ve iletişim bilgisi ayrı dosyalardan kontrol edilir.

Bu sayede kodla uğraşmadan içerikleri değiştirebilirsiniz.

<img width="1919" height="903" alt="header-map" src="https://github.com/user-attachments/assets/ae3597c6-38b9-4370-8469-5c92eeee67c3" />

#### ‣ Menü Yazılarını Değiştirmek

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

#### ‣ Logo Değiştirmek

Logo dosya yolu şu dosyada bulunur:

```
data/techIcons.ts
```

```ts
export const SiteLogo = "/assets/images/logoLight.svg";
```

Buraya yeni logo dosyanızın yolunu yazmanız yeterlidir.



#### ‣ E-posta Adresini Değiştirmek

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

---
### Ana Sayfa → Hero

Bu görsel, sitenin en üst bölümünün (Hero alanı) hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="hero-map" src="https://github.com/user-attachments/assets/dc682336-cc6f-45dd-9584-c07483292a17" />

Hero alanında gördüğünüz tüm içerikler (yazılar, butonlar, fotoğraf, sosyal medya linkleri ve istatistikler) farklı dosyalardan yönetilir.

Bu sayede içerikleri değiştirmek için kod bilmenize gerek yoktur.

#### ‣ Yazılar
Hero alanındaki tüm metinler `messages/en.json` dosyasından gelir.

Bu dosyayı açtıktan sonra `"home"` bölümünü bulun. İçinde aşağıdaki yapıyı göreceksiniz:

```json
"home": {
    "hero": {
      "greeting": "Hello, I'm",
      "name": "Yasir",
      "titleLine1": "Full-Stack",
      "titleLine2": "Web Developer",
      "description": "I transform complex user experience challenges into clear, cohesive solutions, developing strong and reliable foundations that deliver real impact and tangible results",
      "downloadCV": "Download CV",
      "viewWork": "View Work",
      "follow": "FOLLOW"
    },
}
```
Buradaki tırnak içindeki metinleri istediğiniz gibi değiştirebilirsiniz.

Örneğin:

```json
"name": "Ahmet"
```

Dosyayı kaydettikten sonra site otomatik olarak güncellenir.
Ekstra bir işlem yapmanız gerekmez.

#### ‣ İletişim Bilgileri
İletişim bilgileri ayrı bir dosyada tutulur. Bunun sebebi, buradaki bilgilerin hem Hero alanında hem de İletişim bölümünde kullanılmasıdır.


Güncellemek için `data/contacts.ts` dosyasını açın:

İçinde aşağıdaki gibi bir yapı göreceksiniz:

```ts

export const contactData: ContactData = {
  email: "yasir7alrawi23@gmail.com",
  phone: "",
  location: "",
  cvPath: "/assets/docs/cv.pdf",
  projectsPath: "/projects",
  socialLinks: [
    {
      name: "Instagram",
      icon: "Instagram",
      href: ""
    },
    {
      name: "LinkedIn",
      icon: "Linkedin",
      href: ""
    },
    {
      name: "Twitter",
      icon: "Twitter",
      href: ""
    },
    {
      name: "GitHub",
      icon: "Github",
      href: ""
    }
  ]
};

```

Sosyal medya linklerini güncellemek için href kısmına kendi profil bağlantınızı yazmanız yeterlidir.



Örneğin:
```ts
href: "https://instagram.com/kullaniciadiniz"
```
Böylece kullanıcı Hero alanındaki Instagram ikonuna tıkladığında sizin profilinize yönlendirilir.


#### ‣ Profil Fotoğrafı
Profil fotoğrafı `data/personal.ts` dosyadan güncellenir,

```ts
export const personalData = {
  photo: "/assets/images/my-photo.png"
};
```
Buraya kendi fotoğrafınızın dosya yolunu yazmanız yeterlidir.

#### ‣ İstatistik Bilgileri
Deneyim yılı, proje sayısı gibi bilgiler hem Hero alanında hem de İstatistikler bölümünde kullanılır.

Bilgileri güncellemek için `data\stats.ts` dosyasını açarak aşağıdaki gibi değerleri güncelleyebilir:

```ts
export const statsData = {
  years: 5,
  projects: 54,
  clients: 2,
  awards: 48
};
```
Sayıları değiştirdiğinizde site otomatik olarak güncellenir.




