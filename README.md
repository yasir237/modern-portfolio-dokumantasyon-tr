# Modern Portfolio Kılavuz Dokümantasyonu
Modern, modüler ve JSON tabanlı portfolyo sisteminin mimari yapısını ve içerik yönetim modelini açıklayan resmi dokümantasyon.

Eğer teknik bilginiz yoksa veya JSON dosyalarını hızlı bir şekilde düzenlemek isterseniz, bu dokümantasyondaki ilgili bölümü doğrudan **ChatGPT veya başka bir yapay zeka aracına** gönderebilirsiniz.

Örneğin:

* Yeni bir proje eklemek istiyorum
* Yeni bir hizmet kartı eklemek istiyorum
* Deneyim veya eğitim bilgisi eklemek istiyorum
* Bir alanın yapısını değiştirmek istiyorum

İlgili dokümantasyon bölümünü ve mevcut dosya içeriğini yapay zeka aracına gönderdiğinizde, size:

* Hangi dosyayı düzenlemeniz gerektiğini
* Dosyanın hangi kısmını değiştirmeniz gerektiğini
* Yeni JSON yapısının nasıl olması gerektiğini
* Güncellenmiş dosyanın son halini

hazır şekilde verecektir.

Bu sayede teknik detaylarla uğraşmadan gerekli değişiklikleri güvenli bir şekilde yapabilirsiniz.

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

### Ana Sayfa → İstatistikler

Bu görsel, Ana Sayfa’daki **İstatistikler bölümünün** hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="stats-map" src="https://github.com/user-attachments/assets/9c22e682-9a69-4367-b5e9-8a891f1940b9" />

Bu bölümde görünen bilgiler ayrı dosyalardan yönetilir. Bu sayede sayıları ve yazıları kolayca değiştirebilirsiniz.

#### ‣ Başlık ve Metinler


Bölüm başlığı ve alt metinler `messages/en.json` dosyasından gelir.

Dosyayı açtıktan sonra `"home"` → `"stats"` bölümünü bulun.

Aşağıdaki gibi bir yapı göreceksiniz:

```json
"home": {
    "stats": {
      "title": "Our Achievements",
      "subtitle": "Let the figures tell the story of our impact before you explore our work",
      "yearsLabel": "Years",
      "yearsDesc": "of Experience",
      "projectsLabel": "Projects",
      "projectsDesc": "Successfully Completed",
      "clientsLabel": "Clients",
      "clientsDesc": "Worldwide",
      "awardsLabel": "Awards",
      "awardsDesc": "& Recognition",
      "trustedBy": "Trusted by industry leaders worldwide",
      "yearsExp": "Years Exp",
      "projects": "Projects",
      "k": "K"
    }
}
```

Buradaki metinleri istediğiniz gibi değiştirebilirsiniz.

Örneğin:

```json
"title": "Our Successes"
```

Dosyayı kaydettiğinizde site otomatik olarak güncellenir.

#### ‣ Sayıları Güncellemek

Deneyim yılı, proje sayısı, müşteri sayısı ve ödül sayısı ayrı bir dosyada tutulur.

Şu dosyayı açın:

```
data/stats.ts
```

İçinde aşağıdaki yapıyı göreceksiniz:

```ts
export const statsData = {
  years: 5,
  projects: 54,
  clients: 2,
  awards: 48
};
```

Sayıları kendi bilgilerinize göre değiştirebilirsiniz.

Örneğin:

```ts
years: 8,
projects: 120
```

Kaydettiğinizde hem Ana Sayfa’daki İstatistikler bölümü hem de bu verileri kullanan diğer alanlar otomatik olarak güncellenir.

### Ana Sayfa → Hizmetler

Bu görsel, Ana Sayfa’daki **Hizmetler bölümünün** hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="services-map" src="https://github.com/user-attachments/assets/ed5fcb35-ef32-4807-b04d-ad6e47e2cf4f" />

Bu bölümde görünen bilgiler tek bir dosyadan, `messages/services/en.json` dosyasından yönetilir:

Dosya yapısı şu şekildedir:
```json
{
  "title": "My Quality Services",
  "subtitle": "I turn ideas into powerful, scalable, and beautifully crafted digital experiences — built with precision and long-term vision.",
  "items": [
    {
      "title": "Full Stack Development",
      "description": "I create complete end-to-end web solutions — from intuitive, high-performance interfaces to secure backend architectures. My focus is on clean code, scalability, and exceptional user experience across all devices.",
      "icon": "Code"
    },
    {
      "title": "UI / UX Design",
      "description": "I design elegant, functional, and user-centered interfaces. Every layout, interaction, and flow is shaped to feel natural, visually refined, and effortless, ensuring your users enjoy every moment of the experience.",
      "icon": "Palette"
    },
    {
      "title": "Algorithm Development",
      "description": "I develop custom algorithms that solve complex problems with precision and efficiency. From optimized logic structures to intelligent automation, I engineer systems that run smarter, faster, and more reliably.",
      "icon": "Cpu"
    },
    {
      "title": "Website Security & Maintenance",
      "description": "I protect and maintain websites using industry-standard security practices. With continuous monitoring, performance optimization, and regular updates, I ensure your website stays fast, stable, and fully secure.",
      "icon": "Shield"
    }
  ]
}
```

#### ‣ Ne Nereden Değişir?

* `title` → Bölüm başlığı
* `subtitle` → Üst açıklama metni
* `items` → Tüm hizmet kartları

Her kart için:

* `title` → Hizmet başlığı
* `description` → Hizmet açıklaması
* `icon` → Kullanılan ikon adı

Yeni hizmet eklemek için `items` içine yeni bir obje eklemeniz yeterlidir.
Dosyayı kaydettiğinizde site otomatik olarak güncellenir.

Yeni bir kart eklemek için `items` dizisine aşağıdaki yapıyı eklemeniz yeterlidir.

```json
{
      "title": "",
      "description": "",
      "icon": ""
    }
```

Her kart nesnesi arasına `,` (virgül) koyulmalıdır.
Ancak son nesneden sonra virgül eklenmemelidir. Aksi halde JSON dosyası hata verir.


#### ‣ İkon Seçimi

Hizmet kartlarında kullanılan ikonlar `lucide-react` kütüphanesinden gelir.

Bir ikon değiştirmek için `icon` alanına kullanmak istediğiniz ikonun adını yazmanız yeterlidir:

```json
"icon": "Code"
```

#### ‣ İkon Nasıl Seçilir?



1. İkon listesini görmek için:

<p align="center">
  <a href="https://lucide.dev/icons" target="_blank">
    <img 
      src="https://github.com/user-attachments/assets/6ce78af2-d171-4f5c-a698-80db4404bd8a"
      alt="Lucide React İkonları"
      width="900"
      style="border-radius:15px;"
    />
  </a>
</p>

<p align="center">
  <sub>
    Eğer ikon sayfasına ulaşamazsanız,
    <a href="https://lucide.dev/icons" target="_blank">
      buraya tıklayarak
    </a>
    doğrudan erişebilirsiniz.
  </sub>
</p>


3. Kullanmak istediğiniz ikonun adını kopyalayın.
   (Örneğin: `Palette`, `Shield`, `Cpu`, `Smartphone`)

4. JSON dosyasında ilgili kartın `icon` alanına yapıştırın:

```json
"icon": "Smartphone"
```

Kaydettiğinizde ikon otomatik olarak güncellenir.

İkon adını doğru şekilde öğrenmek için aşağıdaki adımları takip edin:

<br>

<p align="center">
  <img width="900" alt="İkon adını kopyalama" src="https://github.com/user-attachments/assets/1d017023-ca6e-4fab-a754-53d04df011da" style="border-radius:15px;" />
</p>

1. İstediğiniz ikonun üzerine tıklayın.
2. Detaylar sayfasına giderek kodunu görüntüleyin.
3. Açılan sayfada ikonun adını kopyalayın.
4. Kopyaladığınız ismi JSON dosyasındaki `"icon"` alanına yapıştırın.

> Not: İkon adı büyük/küçük harfe duyarlıdır. İsmi sitede göründüğü şekilde yazmanız gerekir.

### Ana Sayfa → Öne Çıkan Projeler

Bu görsel, Ana Sayfa’daki **Önce Çıkan Hizmetler** hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="featured-projectes-map" src="https://github.com/user-attachments/assets/d5e1810d-69fd-410b-918b-66fc55cf57fd" />

Bu bölümde görünen bilgiler tek bir dosyadan, `messages/projects/index/en.json` dosyasından yönetilir:

Dosya yapısı şu şekildedir:

```json
{
  "featuredProjects": {
    "title": "Featured Projects",
    "subtitle": "Showcasing innovative solutions built with modern technologies",
    "viewProject": "View Project"
  }
}
```

#### ‣ Değiştirilebilir Alanlar

* `title` → Bölüm başlığı
* `subtitle` → Üst açıklama metni
* `viewProject` → Buttonun içindeki metin

Metni değiştirdiğinizde sayfa otomatik olarak güncellenir.

Diğer proje bilgileri bu bölümden manuel olarak değiştirilmez.
Bu alanlar projelerden otomatik olarak (dinamik şekilde) çekilir.

Yeni bir projenin nasıl ekleneceğini ilerleyen bölümlerde detaylı olarak göstereceğiz.

Bir projenin “Öne Çıkan Projeler” alanında görüntülenebilmesi için, ilgili projenin JSON dosyasına aşağıdaki özelliğin eklenmesi gerekir.

```json
"isFeatured": true,
```


### Ana Sayfa → Tüm Projeler Alanı
Bu görsel, Ana Sayfa’daki **Tüm Projeler bölümünün** hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="featured-projectes-down-map" src="https://github.com/user-attachments/assets/5428db7f-3da8-42a1-a5da-52fb2ef0ffb5" />


Bu bölümde görünen:

* Başlık (Explore My Complete Portfolio)
* Açıklama metni
* “View All Projects” butonu
* Proje, Teknoloji ve Yıl istatistikleri

iki farklı dosyadan yönetilir.


#### ‣ Metinler Nereden Değişir?

Başlık, açıklama ve buton metni aşağıdaki dosyadan düzenlenir:

```
messages/projects/index/en.json
```

Dosya yapısı:

```json
"featuredProjects": {
  "allProjects": {
    "title": "Explore My Complete Portfolio",
    "description": "Discover more...",
    "button": "View All Projects",
    "stats": {
      "projects": "Projects",
      "technologies": "Technologies",
      "years": "Years"
    }
  }
}
```

#### ‣ Değiştirilebilir Alanlar

* `title` → Bölüm başlığı
* `description` → Açıklama metni
* `button` → Buton yazısı
* `stats` → Alt istatistik başlıkları

Örneğin:

```json
"title": "Tüm Projelerimi Keşfedin",
"button": "Tüm Projeleri Gör"
```


#### ‣ Sayılar Nereden Değişir?

Alt kısımda görünen:

* Proje sayısı
* Kullanılan teknoloji sayısı
* Deneyim yılı

Daha önce `İstatistikler` bölümünde anlatıldığı gibi şu dosyadan çekilir:

```
data/stats.ts
```

Dosya yapısı:

```ts
export const statsData = {
  years: 5,
  technologies: 26,
  projects: 54
};
```

Buradaki sayıları değiştirdiğinizde alan otomatik olarak güncellenir.


## Ana Sayfa → Deneyim & Eğitim
Bu görsel, Ana Sayfa’daki **Deneyim & Eğitim** bölümünün hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="experience-education-map" src="https://github.com/user-attachments/assets/09797f30-9e52-40d2-9e02-102e8ff7f0c6" />


Bu bölüm aşağıdaki dosyadan yönetilir:

```
messages/resume/en.json
```

Dosya yapısı şu şekildedir:

```json
{
  "title": "Experience & Education",
  "subtitle": "My professional journey and academic achievements",
  "tabs": {
    "experience": "My Experience",
    "education": "My Education"
  },
  "experience": [],
  "education": []
}
```



#### ‣ Başlık ve Sekmeler

* `title` → Bölüm ana başlığı
* `subtitle` → Açıklama metni
* `tabs.experience` → Deneyim sekme adı
* `tabs.education` → Eğitim sekme adı

Metni değiştirdiğinizde sayfa otomatik güncellenir.

#### ‣ Deneyim Bilgisi Nasıl Eklenir?

Deneyimler `"experience"` dizisi içinde yer alır.

Örnek yapı:

```json
{
  "year": "July 2025 - August 2025",
  "title": "Freelance Full-Stack Developer",
  "company": "AI-Powered Audio Separation Platform"
}
```

#### ‣ Deneyim Alanların Anlamı

* `year` → Çalışma tarih aralığı
* `title` → Pozisyon adı
* `company` → Şirket veya proje adı

#### ‣ Yeni Deneyim Eklemek

`experience` dizisine yeni bir obje eklemeniz yeterlidir:

```json
"experience": [
  {
    "year": "2026 - Present",
    "title": "Senior Developer",
    "company": "Tech Company"
  }
]
```

Yani birden fazla proje eklemek istendiğinde yapı bu şekilde oluşmaktadır:
```json
"experience": [
  {
    "year": "2026 - Present",
    "title": "Project 1",
    "company": "Alrawi"
  },
  {
    "year": "2024 - Present",
    "title": "Project 2",
    "company": "Alrawi"
  }
]
```

> Not: Her obje arasına virgül koyulmalıdır, ancak son objeden sonra virgül eklenmemelidir.


#### ‣ Eğitim Bilgisi Nasıl Eklenir?

Eğitim bilgileri `"education"` dizisi içinde yer alır.

Örnek yapı:

```json
{
  "year": "September 2021 - June 2025",
  "title": "Bachelor in Computer Engineering",
  "company": "Kırıkkale University, Kırıkkale"
}
```

#### ‣ Eğitim Alanların Anlamı

* `year` → Eğitim tarih aralığı
* `title` → Bölüm veya diploma adı
* `company` → Üniversite veya kurum adı

#### ‣ Yeni Eğitim Eklemek

`education` dizisine yeni bir obje ekleyin:

```json
"education": [
  {
    "year": "2026 - 2028",
    "title": "Master in Software Engineering",
    "company": "Example University"
  }
]
```

Birden fazla eğitim bilgisini eklemek için:

```json
"education": [
  {
    "year": "2026 - 2028",
    "title": "Master in Software Engineering",
    "company": "Example- 1 University"
  },
  {
    "year": "2023 - 2026",
    "title": "Bachelor in Software Engineering",
    "company": "Example- 2 University"
  }
]
```

> Not: Her obje arasına virgül koyulmalıdır, ancak son objeden sonra virgül eklenmemelidir.





### Ana Sayfa → Yetenekler (Skills & Expertise)
Bu görsel, Ana Sayfa’daki **Yetenekler** bölümünün hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="skills-map" src="https://github.com/user-attachments/assets/92571936-b8f2-4f17-b425-619f50508af0" />


Bu bölüm aşağıdaki dosyadan yönetilir:

```
messages/skills/en.json
```

Dosya yapısı şu şekildedir:

```json
{
  "title": "Skills & Expertise",
  "subtitle": "Technologies and tools I work with...",
  "categories": {
    "programmingLanguages": "Programming Languages",
    "frameworks": "Frameworks & Libraries",
    "concepts": "Concepts & Techniques",
    "databases": "Databases"
  },
  "skills": {
    "programmingLanguages": [],
    "frameworks": [],
    "concepts": [],
    "databases": []
  }
}
```


#### ‣ Başlık ve Kategori İsimlerini Değiştirmek

* `title` → Bölüm başlığı
* `subtitle` → Açıklama metni
* `categories` → Sekme isimleri

Örneğin:

```json
"title": "Yeteneklerim",
"programmingLanguages": "Programlama Dilleri"
```

Kaydettiğinizde sayfa otomatik olarak güncellenir.


#### ‣ Yetenek (Skill) Nasıl Eklenir?

Her kategori kendi dizisi içinde yer alır.

Örnek:

```json
"programmingLanguages": [
  { "name": "C#" },
  { "name": "Java" }
]
```

#### ‣ Yeni Programlama Dili Eklemek

```json
{ "name": "Python" }
```


#### ‣ Yeni Framework Eklemek

```json
"frameworks": [
  { "name": "ASP.NET MVC Core" },
  { "name": "Laravel" },
  { "name": "React" }
]
```


#### ‣ Yeni Concept Eklemek

```json
{ "name": "Clean Architecture" }
```


#### ‣ Yeni Database Eklemek

```json
{ "name": "PostgreSQL" }
```


#### ‣ Önemli Not

* Her obje arasına `,` (virgül) koyulmalıdır.
* Son elemandan sonra virgül eklenmemelidir.
* Sadece `"name"` alanını doldurmanız yeterlidir.



### Ana Sayfa → Diller 
Bu görsel, Ana Sayfa’daki **Diller** bölümünün hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="languages-map" src="https://github.com/user-attachments/assets/0359f538-bba8-4c3d-8188-1e81562e0dd1" />

Bu bölüm aşağıdaki dosyadan yönetilir:

```
messages/languages/en.json
```

Dosya yapısı şu şekildedir:

```json
{
  "title": "Languages",
  "subtitle": "Mastering languages...",
  "levels": {
    "native": "Native",
    "professional": "Professional",
    "intermediate": "Intermediate"
  },
  "languages": []
}
```


#### ‣ Başlık ve Seviye İsimlerini Değiştirmek

* `title` → Bölüm başlığı
* `subtitle` → Açıklama metni
* `levels` → Dil seviyeleri

Örneğin:

```json
"title": "Diller",
"native": "Anadil"
```

Kaydettiğinizde sayfa otomatik olarak güncellenir.

#### ‣ Yeni Dil Nasıl Eklenir?

Her dil `"languages"` dizisi içinde yer alır.

Örnek yapı:

```json
{
  "name": "Arabic",
  "nativeName": "العربية",
  "level": "native",
  "flag": "🇮🇶",
  "backward": "/assets/images/LanguagesFlags/iraq.png"
}
```

#### ‣ Alanların Anlamı

* `name` → Dilin İngilizce adı
* `nativeName` → Dilin kendi dilindeki adı
* `level` → Seviye (native, professional, intermediate)
* `flag` → Emoji bayrak
* `backward` → Arka plan bayrak görselinin yolu

#### ‣ Yeni Dil Eklemek

`languages` dizisine yeni bir obje eklemeniz yeterlidir:

```json
{
  "name": "German",
  "nativeName": "Deutsch",
  "level": "intermediate",
  "flag": "🇩🇪",
  "backward": "/assets/images/LanguagesFlags/germany.png"
}
```

#### ‣ Önemli Notlar

* `level` alanı sadece şu değerlerden biri olmalıdır:

  * `native`
  * `professional`
  * `intermediate`

* Her obje arasına virgül koyulmalıdır.

* Son elemandan sonra virgül eklenmemelidir.



### Ana Sayfa → Gönüllülük Bölümü
Bu görsel, Ana Sayfa’daki **Gönüllülük** bölümünün hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="volunteering-map" src="https://github.com/user-attachments/assets/26abe781-2dd1-4fdf-ae19-c796022610aa" />

Bu bölüm aşağıdaki dosyadan yönetilir:

```
messages/volunteering/en.json
```

Gönüllülük başlığı ve tüm etkinlik içerikleri bu dosyadan otomatik olarak çekilir.



#### ‣ Dosya Yapısı

```json
{
  "title": "Volunteering",
  "volunteering": []
}
```


#### ‣ Yeni Gönüllülük Etkinliği Nasıl Eklenir?

Her etkinlik `"volunteering"` dizisine bir obje olarak eklenir.

Örnek yapı:

```json
{
  "role": "Guest Speaker",
  "organization": "Bahçeşehir College – Kırıkkale Campus",
  "event": "Career Journeys: How I Succeeded",
  "location": "Kırıkkale, Türkiye",
  "date": "November 2025",
  "description": "As a representative of Kırıkkale University, I shared my experiences...",
  "image": "/assets/images/Volunteering/bahcesehir-katilim-belgesi.png"
},
{
      "role": "Organizing Committee Member",
      "organization": "Kırıkkale University",
      "event": "International Symposium on History of Science",
      "location": "Kırıkkale, Turkey",
      "date": "November 2024",
      "description": "Served as a member of the organizing committee for the International Symposium on History of Science, contributing to planning, organizing, website management, and supervision to ensure the success of the academic event.",
      "image": "/assets/images/Volunteering/Committee.png"
}
```

#### ‣ Alanların Açıklaması

* `role` → Görev (Örn: Guest Speaker, Mentor, Volunteer)
* `organization` → Kurum adı
* `event` → Etkinlik adı
* `location` → Şehir ve ülke
* `date` → Tarih bilgisi
* `description` → Açıklama metni
* `image` → Sertifika veya etkinlik görsel yolu

#### ‣ Görsel Ekleme

1. Görseli şu klasöre ekleyin:

```
/assets/images/Volunteering/
```

2. Dosya adını `image` alanında belirtin:

```json
"image": "/assets/images/Volunteering/dosya-adi.png"
```


#### ‣ Önemli JSON Kuralları

* Her obje arasına `,` virgül konulmalıdır.
* Son objeden sonra virgül konulmamalıdır.
* Görsel yolu doğru yazılmalıdır.
* Dosya yapısı bozulursa sistem hata verir.






### Ana Sayfa → Sertifikalar
Bu görsel, Ana Sayfa’daki **Sertifikalar** bölümünün hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="certificates-map" src="https://github.com/user-attachments/assets/9ba47c0d-af48-417b-b564-8fad8a28a810" />

Bu bölüm aşağıdaki dosyadan yönetilir:

```
messages/certificates/en.json
```

Başlık, alt başlık, kategori isimleri ve tüm sertifikalar bu dosyadan otomatik olarak çekilir.

#### ‣ Dosya Yapısı

```json
{
  "title": "Certificates & Achievements",
  "subtitle": "Professional certifications and continuous learning journey",
  "certificatesCount": "Certificates",
  "viewCertificate": "View Certificate",
  "of": "/",
  "categories": {},
  "certificates": []
}
```

#### ‣ Başlık ve Metinleri Değiştirme

* `title` → Bölüm başlığı
* `subtitle` → Açıklama metni
* `certificatesCount` → Sertifika sayısı yazısı
* `viewCertificate` → Buton metni

Örnek:

```json
"title": "Sertifikalar",
"viewCertificate": "Sertifikayı Gör"
```

#### ‣ Kategori Yönetimi

Kategoriler `categories` objesi içinde tanımlıdır:

```json
"categories": {
  "ai": "Artificial Intelligence",
  "cybersecurity": "Cybersecurity",
  "devops": "DevOps"
}
```

Sol taraftaki anahtar (`ai`, `devops` gibi) teknik değerdir.
Sağ taraftaki metin arayüzde görünen isimdir.

Yeni kategori eklemek için:

```json
"mobile": "Mobile Development"
```

#### ‣ Yeni Sertifika Nasıl Eklenir?

Her sertifika `"certificates"` dizisine bir obje olarak eklenir.

Örnek yapı:

```json
{
  "title": "Diction, Announcing and Presentation",
  "issuer": "Republic of Türkiye – Ministry of National Education",
  "date": "2026",
  "category": "effectiveCommunication",
  "img": "/assets/images/Certificates/diksiyon.png",
  "link": "#"
}
```

#### ‣ Alanların Açıklaması

* `title` → Sertifika adı
* `issuer` → Veren kurum
* `date` → Yıl veya tarih
* `category` → Yukarıda tanımlanan kategori anahtarı
* `img` → Sertifika görsel yolu
* `link` → Sertifika bağlantısı (PDF, doğrulama linki vb.)

#### ‣ Görsel Ekleme

1. Sertifika görselini şu klasöre ekleyin:

```
/assets/images/Certificates/
```

2. Dosya yolunu `img` alanında belirtin:

```json
"img": "/assets/images/Certificates/sertifika-adi.png"
```

#### ‣ Yeni Sertifika Eklemek

`certificates` dizisine yeni bir obje eklemeniz yeterlidir:

```json
{
  "title": "Cloud Computing Fundamentals",
  "issuer": "ABC Academy",
  "date": "2025",
  "category": "cloudComputing",
  "img": "/assets/images/Certificates/cloud.png",
  "link": "https://certificate-link.com"
}
```

#### ‣ Önemli Kurallar

* `category` değeri mutlaka `categories` içinde tanımlı olmalıdır.
* Her obje arasına virgül konulmalıdır.
* Son elemandan sonra virgül konulmamalıdır.
* Görsel yolu doğru yazılmalıdır.





### Ana Sayfa → Vision

Bu görsel, Ana Sayfa’daki **Vision** bölümünün hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="vision-map" src="https://github.com/user-attachments/assets/bea35b68-ffe5-4b01-8e6e-55a422bc2f4c" />


Bu bölüm aşağıdaki dosyadan yönetilir:

```
messages/vision/en.json
```

Ana sayfada görünen büyük vurgu cümleleri (statement metinleri) bu dosyadan otomatik olarak çekilir.

#### ‣ Dosya Yapısı

```json
{
  "statements": [
    {
      "text": "I turn complex ideas into unforgettable digital experiences",
      "direction": "default"
    }
  ]
}
```

#### ‣ Statement Yapısı

Her metin `"statements"` dizisi içinde bir obje olarak tanımlanır.

Örnek:

```json
{
  "text": "I don’t just write code, I craft game-changing solutions",
  "direction": "right"
}
```

#### ‣ Alanların Açıklaması

* `text` → Ekranda görünen metin
* `direction` → Animasyon yönü

#### ‣ Direction (Animasyon Yönleri)

`direction` alanı şu değerleri alabilir:

* `"default"` → Standart giriş animasyonu
* `"right"` → Sağdan giriş animasyonu
* `"down"` → Aşağıdan giriş animasyonu

Yanlış değer girilirse animasyon düzgün çalışmayabilir.

#### ‣ Yeni Statement Eklemek

Yeni bir vurgu cümlesi eklemek için `statements` dizisine aynı yapıda yeni bir obje ekleyin:

```json
{
  "text": "Design is where creativity meets logic",
  "direction": "default"
}
```

#### ‣ Önemli Kurallar

* Her obje arasına virgül koyulmalıdır.
* Son elemandan sonra virgül koyulmamalıdır.
* `direction` değeri geçerli olmalıdır.





### Ana Sayfa → İletişim
Bu görsel, Ana Sayfa’daki **İletişim** bölümünün hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="contact-map" src="https://github.com/user-attachments/assets/c47d1635-8c01-4240-9abe-247564757954" />

Bu bölüm iki farklı dosyadan yönetilir:

```
messages/en.json
```

ve

```
data/contacts.ts
```

* `messages/en.json` → Metin içerikleri (başlıklar, form alanları, mesajlar)
* `data/contacts.ts` → Gerçek iletişim bilgileri ve sosyal medya linkleri

#### ‣ Metin İçerikleri (messages/en.json)

İletişim başlığı, açıklama yazısı ve form alanları buradan yönetilir.

Dosya Yapısı:

```json
"contact": {
  "title": "Let's Work Together",
  "subtitle": "Got an idea or project? Let’s collaborate and turn your vision into reality.",
  "badge": "Contact Me",
  "form": {},
  "success": {},
  "info": {},
  "social": {}
}
```

#### ‣ Başlık ve Açıklama Değiştirme

```json
"title": "Benimle İletişime Geç",
"subtitle": "Bir fikrin mi var? Birlikte hayata geçirelim."
```

#### ‣ Form Alanlarını Düzenleme

```json
"form": {
  "name": {
    "label": "Name",
    "placeholder": "John Doe"
  },
  "email": {
    "label": "Email",
    "placeholder": "john@example.com"
  },
  "subject": {
    "label": "Subject",
    "placeholder": "Project Inquiry"
  },
  "message": {
    "label": "Message",
    "placeholder": "Tell me about your project..."
  },
  "submit": "Send Message",
  "sending": "Sending..."
}
```

Buradaki tüm metinler serbestçe değiştirilebilir.

#### ‣ Başarılı Gönderim Mesajı

```json
"success": {
  "title": "Message Sent Successfully!",
  "message": "Thank you for reaching out. I'll get back to you as soon as possible."
}
```

#### ‣ Gerçek İletişim Bilgileri (data/contacts.ts)

Gerçek e-posta, telefon, konum ve sosyal medya linkleri bu dosyada yer alır.

Dosya Yapısı

```ts
export const contactData = {
  email: "example@gmail.com",
  phone: "+90 500 000 00 00",
  location: "Ankara, Türkiye",
  cvPath: "/assets/docs/cv.pdf",
  projectsPath: "/projects",
  socialLinks: []
}
```

#### ‣ E-posta / Telefon / Konum Değiştirme

```ts
email: "yourmail@gmail.com",
phone: "+90 555 555 55 55",
location: "Ankara, Türkiye",
```

#### ‣ Sosyal Medya Linkleri

Her sosyal medya hesabı `socialLinks` dizisine bir obje olarak eklenir.

```ts
{
  name: "LinkedIn",
  icon: "Linkedin",
  href: "https://www.linkedin.com/in/username"
}
```

#### ‣ Alanların Açıklaması

* `name` → Platform adı
* `icon` → Kullanılacak ikon adı
* `href` → Profil bağlantısı

Yeni bir sosyal medya eklemek için:

```ts
{
  name: "YouTube",
  icon: "Youtube",
  href: "https://youtube.com/@username"
}
```

#### ‣ Önemli Notlar

* `messages/en.json` sadece metinleri değiştirir.
* Gerçek iletişim bilgileri `data/contacts.ts` dosyasındadır.
* `icon` değeri kullanılan ikon sistemine uygun olmalıdır.
* TypeScript yapısı bozulmamalıdır (virgül ve süslü parantezlere dikkat).



### Projects Sayfası → Hero & Filtre Alanı
Bu görsel, Projeler Sayfasının hangi dosyalardan beslendiğini göstermektedir.

<img width="1919" height="903" alt="our-project-map" src="https://github.com/user-attachments/assets/8c915b07-3b69-4c88-be81-d087b036b70e" />

> Yeni bir proje nasıl eklenmesi gerektiğini ileri anlatımlarda anlatılacaktır.

Bu bölüm aşağıdaki dosyadan yönetilir:

```
messages/projects/index/en.json
```

Sayfa başlığı, açıklama metni, arama alanı yazıları ve kategori isimleri bu dosyadan otomatik olarak çekilir.

#### ‣ Hero (Başlık Alanı)

Sayfanın üst kısmındaki başlık ve açıklama metni buradan yönetilir.

Örnek Yapı

```json
"hero": {
  "badge": "Portfolio",
  "title": "Our Projects",
  "subtitle": "Explore our portfolio of innovative solutions and creative works that drive success"
}
```

#### ‣ Alanlar

* `badge` → Küçük üst etiket (örneğin: Portfolio)
* `title` → Ana başlık
* `subtitle` → Açıklama metni

#### ‣ Arama ve Filtre Metinleri

Arama alanı ve filtre yazıları `search` objesinden gelir.

Örnek Yapı

```json
"search": {
  "placeholder": "Search projects...",
  "filterButton": "Filters",
  "showingResults": "Showing",
  "project": "project",
  "projects": "projects"
}
```

#### ‣ Alanlar

* `placeholder` → Arama kutusu iç yazısı
* `filterButton` → Filtre butonu metni
* `showingResults` → Sonuç sayısı yazısı (örnek: Showing 3 projects)
* `project` / `projects` → Tekil ve çoğul metinler

#### ‣ Kategoriler (Filtre Butonları)

Üstteki kategori filtreleri `categories` objesinden gelir.

Örnek Yapı

```json
"categories": {
  "all": "All",
  "webDevelopment": "Web Development",
  "mobileApp": "Mobile App",
  "design": "Design",
  "aiMl": "AI/ML",
  "blockchain": "Blockchain"
}
```

* **Sol Taraf (Anahtar):** Teknik değer. Projelerin kategori alanı ile birebir aynı olmalıdır.

* **Sağ Taraf (Metin):** Arayüzde görünen isimdir.

#### ‣ Yeni Kategori Eklemek

Yeni bir filtre butonu eklemek için:

```json
"gameDevelopment": "Game Development"
```

⚠️ Dikkat:
Bu kategoriye ait projelerin `category` değeri de `"gameDevelopment"` olmalıdır.

#### ‣ Önemli Kurallar

* JSON yapısı bozulmamalıdır.
* Her satır arasında virgül olmalıdır.
* Son elemandan sonra virgül olmamalıdır.
* Kategori anahtarları proje dosyaları ile eşleşmelidir.


### Yeni Proje Nasıl Eklenir?

Yeni bir proje eklemek için aşağıdaki adımları takip edin.



#### ‣ 1️⃣ Doğru Klasöre Git

Proje detayları şu klasörde yer alır:

```
messages/projects/details
```

Bu klasörün içinde dil klasörleri bulunur (örneğin `en`, `tr` gibi).

‣  Eklemek istediğiniz projenin dili hangi klasördeyse, o klasöre yeni bir JSON dosyası oluşturmanız gerekir.

Örneğin:

```
messages/projects/details/en/
```

#### ‣ 2️⃣ Dosya İsmini Doğru Oluştur

Dosya ismi şu formatta olmalıdır:

```
index-projectname.json
```

Kurallar:

* Önce proje sırası (index) yazılır
* Ardından `-` konur
* Proje adı boşluksuz yazılır
* Küçük harf kullanılması önerilir

#### ‣ Örnek:

```
12-nobadwords.json
13-portfolioai.json
14-mobilebankingapp.json
```

⚠️ Dikkat:

* Proje adında boşluk olmamalıdır.
* Her proje benzersiz bir index numarasına sahip olmalıdır.

#### ‣ 3️⃣ JSON İçeriğini Ekleyin

Dosyayı oluşturduktan sonra aşağıdaki temel yapıyı kopyalayıp düzenleyebilirsiniz:

```json
{
  "id": 13,
  "title": "Project Title",
  "subtitle": "Project Subtitle",
  "isFeatured": false,
  "description": "Project Description",
  "longDescription": "Project Long Description",
  "category": "Project Category",
  "tags": ["tag1", "tag2"],
  "image": "image link",
  "techLogos": ["techLogo1", "techLogo2"],
  "date": "2026-02",
  "duration": "4 months",
  "teamSize": 1,
  "role": "Your Role",
  "demoLink": null,
  "githubLink": null
}
```

Mevcut logo isimlerini görmek için şu dosyaya bakabilirsiniz:
```
data/techIcons.ts
```

#### ‣ Önemli Alanlar

‣ id

* Benzersiz olmalıdır.
* Dosya index numarası ile eşleşmesi önerilir.

‣ isFeatured

* `true` → Ana sayfada öne çıkan projelerde görünür.
* `false` → Sadece projeler sayfasında görünür.

‣ category

Bu değer, şu dosyadaki kategori anahtarlarından biri olmalıdır:

```
messages/projects/index/en.json
```

Örneğin:

```json
"category": "aiMl"
```

#### ‣ technologies

Bu alan projede kullanılan teknolojileri detaylı şekilde göstermek için kullanılır.

```json
"technologies": [
  {
    "name": "Django & Python",
    "description": "Backend API with machine learning integration"
  }
]
```

‣ Ne işe yarar?

* Projede kullanılan ana teknolojileri listeler
* Her teknoloji için kısa bir açıklama gösterir
* Proje detay sayfasında ayrı bir bölüm olarak görünür

‣ Kurallar

* `name` → Teknolojinin adı
* `description` → O teknolojinin projedeki rolü
* En az 1 tane olabilir
* Sıralama, sayfadaki görünüm sırasını belirler

#### ‣ contentBlocks

Bu alan proje detay sayfasının ana içeriğini oluşturur.
Yani sayfadaki metinler, görseller ve kod örnekleri buradan yönetilir.

Her blok farklı bir içerik türünü temsil eder.

‣ **type: 0 → Metin Bloğu**

Uzun açıklamalar için kullanılır.

```json
{
  "type": 0,
  "heading": "Project Overview",
  "subheading": "Building a Safer Digital Environment",
  "content": "Uzun açıklama metni..."
}
```

**Alanlar**

* `heading` → Bölüm başlığı
* `subheading` → Alt başlık
* `content` → Uzun açıklama metni
  (Satır atlamak için `\n\n` kullanılır)

‣ **type: 1 → Tek Görsel Bloğu**

Bir adet büyük görsel göstermek için kullanılır.

```json
{
  "type": 1,
  "heading": "Platform Hero Section",
  "imageUrl": "https://...",
  "caption": "Görsel açıklaması"
}
```

**Alanlar**

* `imageUrl` → Görsel linki
* `caption` → Görsel alt açıklaması

‣ **type: 3 → Çoklu Görsel Bloğu**

Birden fazla görseli grid şeklinde göstermek için kullanılır.

```json
{
  "type": 3,
  "heading": "Examples",
  "images": [
    {
      "url": "https://...",
      "alt": "Image alt text",
      "caption": "Image caption 1"
    },
    {
      "url": "https://...",
      "alt": "Image alt text",
      "caption": "Image caption 2"
    }
  ]
}
```

**Alanlar**

* `url` → Görsel linki
* `alt` → SEO ve erişilebilirlik için alternatif metin
* `caption` → Açıklama

‣ **type: 4 → Kod Örneği Bloğu**

API veya kullanım örnekleri göstermek için kullanılır.

```json
{
  "type": 4,
  "heading": "Usage Example",
  "codeBlocks": [
    {
      "language": "javascript",
      "label": "Node.js",
      "code": "console.log('Hello');"
    },
    {
      "language": "C#",
      "label": "CSharp",
      "code": "Console.WriteLine(\"Hello\");"
    }
  ],
  "defaultTab": 0
}
```

**Alanlar**

* `language` → Kod dili (syntax highlight için)
* `label` → Sekme başlığı
* `code` → Kod içeriği
* `defaultTab` → Varsayılan açık sekme indexi

#### ‣ challenges

Projede karşılaşılan teknik zorlukları listeler.

```json
"challenges": [
  "Gerçek zamanlı performans sağlamak",
  "Çok dilli model eğitimi"
]
```

* Liste formatındadır
* Her madde ayrı bir satırdır

#### ‣ solutions

Challenges bölümüne karşılık gelen çözümleri içerir.

```json
"solutions": [
  "GPU destekli inference sistemi kuruldu",
  "Custom transformer modeller eğitildi"
]
```

#### ‣ results

Projeye ait ölçülebilir sonuçları gösterir.

```json
"results": [
  {
    "metric": "Accuracy",
    "value": "92.3%",
    "description": "Detection accuracy"
  },
  {
    "metric": "Speed",
    "value": "250ms",
    "description": "Average API response time"
  }
]
```

**Alanlar**

* `metric` → Ölçüm adı
* `value` → Sonuç değeri
* `description` → Açıklama

Bu alan özellikle kurumsal ve profesyonel projeler için önerilir.

#### ‣ testimonial

Müşteri veya kullanıcı yorumu göstermek için kullanılır.

```json
"testimonial": {
  "text": "Proje hayatımızı değiştirdi...",
  "author": "Ahmed Al-Rashid",
  "position": "Community Manager"
}
```

**Alanlar**

* `text` → Yorum metni
* `author` → Yorumu yapan kişi
* `position` → Kişinin pozisyonu


#### ‣ Görseller

* Görselleri uygun klasöre ekleyin.
* `image` alanına doğru yolu yazın.
* Content block görselleri için URL veya local path kullanılabilir.



#### ‣ Önemli Kurallar ve Notlar

* JSON yapısı kesinlikle bozulmamalıdır.
* Son satırdan sonra virgül konulmamalıdır.
* `category` değeri filtre sistemine uygun olmalıdır.
* Dosya ismi boşluk içermemelidir.
* Index numarası tekrar etmemelidir.
* `type` değerleri sistem tarafından okunur, değiştirilmemelidir.
* Tüm alanlar zorunlu değildir; ancak profesyonel ve zengin bir proje sayfası için detaylı alanların doldurulması önerilir.



## Yeni Bir Dil Nasıl Eklenir?

Sisteme yeni bir dil eklemek için aşağıdaki adımları eksiksiz şekilde uygulamanız gerekir.

#### ‣ 1️⃣ Dili Sisteme Tanımlayın

Öncelikle dili sistem seviyesinde tanımlamanız gerekir.

Aşağıdaki dosyayı açın:

```
data/systemLanguages.ts
```

Mevcut yapı:

```ts
export const systemLanguages = [
  { code: 'en', name: 'English', locale: 'en-US' },
] as const;
```

Örneğin Arapça eklemek istiyorsanız, `systemLanguages` dizisine şu satırı ekleyin:

```ts
{ code: 'ar', name: 'العربية', locale: 'ar-SA' }
```

Son hali şöyle olur:

```ts
export const systemLanguages = [
  { code: 'en', name: 'English', locale: 'en-US' },
  { code: 'ar', name: 'العربية', locale: 'ar-SA' }
] as const;
```

#### ‣ 2️⃣ Gerekli Dil Dosyalarını Oluşturun

Yeni dil için `messages` klasörü içinde ilgili JSON dosyalarını oluşturmanız gerekir.

Aşağıdaki dosyalar oluşturulmalıdır:

```
messages/ar.json
messages/certificates/ar.json
messages/languages/ar.json
messages/projects/index/ar.json
messages/services/ar.json
messages/skills/ar.json
messages/vision/ar.json
messages/volunteering/ar.json
```

#### ‣ 3️⃣ Proje Detayları İçin Dil Klasörü Oluşturun

Proje detayları için ayrı bir klasör gerekir.

Şu klasöre gidin:

```
messages/projects/details
```

Burada İngilizce için genelde şu yapı vardır:

```
messages/projects/details/en/
```

Yeni dil için:

```
messages/projects/details/ar/
```

klasörünü oluşturun.

#### ‣ Projelerin Çevirisini Ekleyin

Eğer sistemde İngilizce projeler mevcutsa (`details/en` klasöründe), aynı dosyaların Arapça versiyonlarını oluşturmanız gerekir.

Örnek:

```
messages/projects/details/en/12-nobadwords.json
```

Bunun Arapça versiyonu:

```
messages/projects/details/ar/12-nobadwords.json
```

İçeriği aynı yapı korunarak, sadece metinler Arapça olacak şekilde düzenlenir.

#### ‣ Önemli Kurallar

* `code` değeri klasör ismi ile aynı olmalıdır.
* Tüm mesaj dosyaları oluşturulmalıdır.
* Proje detay klasörü oluşturulmadan dil aktif çalışmaz.
* JSON yapısı değiştirilmemelidir.
* Eksik dosya bırakılmamalıdır.


#### ‣ messages/[dil kodu].json klasörün içindeki yapı:
```json
{
  "header": {
    "home": "",
    "stats": "",
    "services": "",
    "work": "",
    "projects": "",
    "resume": "",
    "about": "",
    "skills": "",
    "languages": "",
    "volunteering": "",
    "certificates": "",
    "contact": "",
    "startAProject": ""
  },
  "home": {
    "hero": {
      "greeting": "",
      "name": "",
      "titleLine1": "",
      "titleLine2": "",
      "description": "",
      "downloadCV": "",
      "viewWork": "",
      "follow": ""
    },
    "stats": {
      "title": "",
      "subtitle": "",
      "yearsLabel": "",
      "yearsDesc": "",
      "projectsLabel": "",
      "projectsDesc": "",
      "clientsLabel": "",
      "clientsDesc": "",
      "awardsLabel": "",
      "awardsDesc": "",
      "trustedBy": "",
      "yearsExp": "",
      "projects": "",
      "k": ""
    }
  },
  "contact": {
    "title": "",
    "subtitle": "",
    "badge": "",
    "form": {
      "name": {
        "label": "",
        "placeholder": ""
      },
      "email": {
        "label": "",
        "placeholder": ""
      },
      "subject": {
        "label": "",
        "placeholder": ""
      },
      "message": {
        "label": "",
        "placeholder": ""
      },
      "submit": "",
      "sending": ""
    },
    "success": {
      "title": "",
      "message": ""
    },
    "info": {
      "email": {
        "title": ""
      },
      "phone": {
        "title": ""
      },
      "location": {
        "title": ""
      }
    },
    "social": {
      "title": ""
    }
  },
  "loading": {
    "text": ""
  },
  "backToProjects": "",
  "technologiesUsed": "",
  "projectLink": "",
  "liveDemo": "",
  "sourceCode": "",
  "challenges": "",
  "solutions": "",
  "duration": "",
  "teamSize": "",
  "resultsImpact": "",
  "videoNotSupported": "",
  "client": "",
  "technologies": "",
  "date": ""
}
```


#### ‣ messages/certificates/[dil kodu].json klasörün içindeki yapı:
```json
{
  "title": "",
  "subtitle": "",
  "certificatesCount": "",
  "viewCertificate": "",
  "of": "",
  "categories": {
    "ai": "",
    "dataScience": "",
    "cybersecurity": "",
    "php": "",
    "cloudComputing": "",
    "programming": "",
    "devops": "",
    "softSkills": "",
    "network": "",
    "effectiveCommunication": "",
    "trainingTrainers": ""
  },
  "certificates": [
    {
      "title": "",
      "issuer": "",
      "date": "",
      "category": "",
      "img": "",
      "link": ""
    },
    {
      "title": "",
      "issuer": "",
      "date": "",
      "category": "",
      "img": "",
      "link": ""
    }
  ]
}
```


#### ‣ messages/languages/[dil kodu].json klasörün içindeki yapı:
```json
{
  "title": "",
  "subtitle": "",
  "levels": {
    "native": "",
    "professional": "",
    "intermediate": ""
  },
  "languages": [
    {
      "name": "",
      "nativeName": "",
      "level": "",
      "flag": "",
      "backward": ""
    },
    {
      "name": "",
      "nativeName": "",
      "level": "",
      "flag": "",
      "backward": ""
    },
    {
      "name": "",
      "nativeName": "",
      "level": "",
      "flag": "",
      "backward": ""
    }
  ]
}
```

#### ‣ messages/projects/details/[dil kodu]/[index-projcetname].json klasörün içindeki yapı:

```json
{
  "id": 0,
  "title": "",
  "subtitle": "",
  "isFeatured": false,
  "description": "",
  "longDescription": "",
  "category": "",
  "tags": [
    "",
    "",
    ""
  ],
  "image": "",
  "techLogos": [
    "",
    "",
    ""
  ],
  "date": "",
  "duration": "",
  "teamSize": 0,
  "role": "",
  "demoLink": "",
  "githubLink": null,
  "technologies": [
    {
      "name": "",
      "description": ""
    },
    {
      "name": "",
      "description": ""
    },
    {
      "name": "",
      "description": ""
    }
  ],
  "contentBlocks": [
    {
      "type": 0,
      "heading": "",
      "subheading": "",
      "content": ""
    },
    {
      "type": 1,
      "heading": "",
      "imageUrl": "",
      "caption": ""
    },
    {
      "type": 2,
      "heading": "",
      "videoUrl": "",
      "posterUrl": "",
      "caption": ""
    },
    {
      "type": 3,
      "heading": "",
      "images": [
        {
          "url": "",
          "alt": "",
          "caption": ""
        },
        {
          "url": "",
          "alt": "",
          "caption": ""
        },
        {
          "url": "",
          "alt": "",
          "caption": ""
        }
      ]
    },
    {
      "type": 4,
      "heading": "",
      "codeBlocks": [
        {
          "language": "",
          "label": "",
          "code": ""
        },
        {
          "language": "",
          "label": "",
          "code": ""
        },
        {
          "language": "",
          "label": "",
          "code": ""
        }
      ],
      "defaultTab": 0
    }
  ],
  "challenges": [
    "",
    "",
    ""
  ],
  "solutions": [
    "",
    "",
    ""
  ],
  "results": [
    {
      "metric": "",
      "value": "",
      "description": ""
    },
    {
      "metric": "",
      "value": "",
      "description": ""
    },
    {
      "metric": "",
      "value": "",
      "description": ""
    }
  ],
  "testimonial": {
    "text": "",
    "author": "",
    "position": ""
  }
}
```


#### ‣ messages/projects/index/[dil kodu].json klasörün içindeki yapı:

```json
{
  "hero": {
    "badge": "",
    "title": "",
    "subtitle": ""
  },
  "search": {
    "placeholder": "",
    "filterButton": "",
    "showingResults": "",
    "project": "",
    "projects": ""
  },
  "categories": {
    "all": "",
    "webDevelopment": "",
    "mobileApp": "",
    "design": "",
    "aiMl": "",
    "blockchain": ""
  },
  "projectCard": {
    "technologiesUsed": ""
  },
  "noResults": {
    "title": "",
    "description": "",
    "clearButton": ""
  },
  "featuredProjects": {
    "title": "",
    "subtitle": "",
    "viewProject": "",
    "allProjects": {
      "title": "",
      "description": "",
      "button": "",
      "stats": {
        "projects": "",
        "technologies": "",
        "years": ""
      }
    }
  }
}
```

#### ‣ messages/resume/[dil kodu].json klasörün içindeki yapı:
```json
{
  "title": "",
  "subtitle": "",
  "tabs": {
    "experience": "",
    "education": ""
  },
  "experience": [
    {
      "year": "",
      "title": "",
      "company": ""
    },
    {
      "year": "",
      "title": "",
      "company": ""
    },
    {
      "year": "",
      "title": "",
      "company": ""
    }
  ],
  "education": [
    {
      "year": "",
      "title": "",
      "company": ""
    },
    {
      "year": "",
      "title": "",
      "company": ""
    },
    {
      "year": "",
      "title": "",
      "company": ""
    }
  ]
}
```

#### ‣ messages/services/[dil kodu].json klasörün içindeki yapı:
```json
{
  "title": "",
  "subtitle": "",
  "items": [
    {
      "title": "",
      "description": "",
      "icon": ""
    },
    {
      "title": "",
      "description": "",
      "icon": ""
    },
    {
      "title": "",
      "description": "",
      "icon": ""
    }
  ]
}
```

#### ‣ messages/skills/[dil kodu].json klasörün içindeki yapı:
```json
{
  "title": "",
  "subtitle": "",
  "categories": {
    "programmingLanguages": "",
    "frameworks": "",
    "concepts": "",
    "databases": ""
  },
  "skills": {
    "programmingLanguages": [
      { "name": "" },
      { "name": "" }
    ],
    "frameworks": [
      { "name": "" },
      { "name": "" }
    ],
    "concepts": [
      { "name": "" },
      { "name": "" }
    ],
    "databases": [
      { "name": "" },
      { "name": "" }
    ]
  }
}
```

#### ‣ messages/vision/[dil kodu].json klasörün içindeki yapı:
```json
{
  "statements": [
    {
      "text": "",
      "direction": ""
    },
    {
      "text": "",
      "direction": ""
    },
    {
      "text": "",
      "direction": ""
    }
  ]
}
```

#### ‣ messages/volunteering/[dil kodu].json klasörün içindeki yapı:
```json
{
  "title": "",
  "volunteering": [
    {
      "role": "",
      "organization": "",
      "event": "",
      "location": "",
      "date": "",
      "description": "",
      "image": ""
    },
    {
      "role": "",
      "organization": "",
      "event": "",
      "location": "",
      "date": "",
      "description": "",
      "image": ""
    },
    {
      "role": "",
      "organization": "",
      "event": "",
      "location": "",
      "date": "",
      "description": "",
      "image": ""
    }
  ]
}
```



