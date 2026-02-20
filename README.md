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





## Ana Sayfa → Yetenekler (Skills & Expertise)
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



