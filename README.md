# TDA CodeBoost

**Sürüm:** 1.0.0  
**Geliştirici:** TDA  
**Amaç:** More efficient AI-assisted software development.

TDA CodeBoost, Claude'un kod üretme, hata ayıklama, inceleme ve optimizasyon işlerinde yalnızca ilgili bağlamı kullanmasına; mevcut proje yapısına uymasına; değişiklikleri doğrulayıp test durumunu dürüstçe bildirmesine yardımcı olan ortak bir Agent Skill'dir. Claude Chat ve Claude Code için tasarlanmıştır. Harici API, ücretli servis veya ek bağımlılık gerektirmez.

Skill, çalışma yöntemlerini iyileştirmeyi hedefler; Claude kullanım limitlerini artırdığını veya belirli miktarda/yüzdede token tasarrufu sağladığını iddia etmez. Doğruluk ve güvenlik önceliklidir.

## İçerik

```text
tda-codeboost/
├── SKILL.md
├── README.md
├── CHANGELOG.md
├── references/
│   ├── context-management.md
│   ├── coding-standards.md
│   ├── quality-control.md
│   └── usage-examples.md
└── tests/
    └── validation-checklist.md
```

`SKILL.md` kısa ana akışı ve referans seçimini içerir. Ayrıntılı dosyalar yalnızca ilgili görevde açılmalıdır. Lisans tercihi belirtilmediği için LICENSE dosyası eklenmemiştir.

## Claude Chat'e yükleme

1. Claude'da **Settings → Capabilities** bölümünde **Code execution and file creation** (arayüz güncellemesine göre **Create and edit files**) özelliğinin etkin olduğundan emin olun.
2. **Customize → Skills** sayfasını açın.
3. **+ → Create skill → Upload a skill** seçin.
4. Bu proje için hazırlanmış `tda-codeboost-claude.zip` paketini yükleyin ve Skills listesinden etkinleştirin.

Menü adları Claude arayüzü veya plan/kurum ayarlarına göre değişebilir. Kurum hesabında seçenek görünmüyorsa yöneticinin Skills veya kullanıcı yüklemelerini etkinleştirmesi gerekebilir.

## Claude Code'a kurulum

### Kişisel kurulum (Linux/macOS)

Proje klasörünün bulunduğu dizinden çalıştırın:

```sh
mkdir -p "$HOME/.claude/skills"
cp -R ./tda-codeboost "$HOME/.claude/skills/tda-codeboost"
```

### Kişisel kurulum (Windows PowerShell)

Proje klasörünün bulunduğu dizinden çalıştırın:

```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\skills" | Out-Null
Copy-Item -Recurse -Path ".\tda-codeboost" -Destination "$HOME\.claude\skills\"
```

Her iki örnekte de kurulum hedefinde `tda-codeboost/SKILL.md` bulunmalıdır. Güncelleme yaparken hedefteki eski klasörü önce yedekleyip/yerine koyun; iç içe `tda-codeboost/tda-codeboost` klasörü oluşturmayın.

Bir depoda ekipçe kullanmak için klasörü depo kökündeki `.claude/skills/tda-codeboost/` yoluna koyup değişiklikleri depoya ekleyin. Claude Code becerileri proje veya kullanıcı düzeyinde yükleyebilir; kullanılabilir araçlar ve erişim, o oturumun izinlerine bağlıdır. Skill'i otomatik ya da doğrudan çağırarak sınayın; ör. `/tda-codeboost`.

## GitHub'a yükleme

Bu klasör bağımsız bir depo olarak GitHub'a yüklenmeye hazırdır. GitHub'da yeni bir depo oluşturup içeriği kök dizine yükleyin veya yerelde `git init`, `git add`, `git commit` ve depoya bağlı `git push` adımlarını uygulayın. Burada herhangi bir uzak depo oluşturulmamış ya da yayın yapılmamıştır.

## Doğrulama

Manuel karşılaştırmalı değerlendirme senaryoları ve puanlama yöntemi [`tests/validation-checklist.md`](tests/validation-checklist.md) içindedir. Claude Chat veya Claude Code oturumunda gerçek senaryolar yürütülmeden performans/test başarısı sonucu varsaymayın. Kurulum biçimi ve önkoşullar için aşağıdaki resmi belgeler esas alınmıştır:

- [Claude'da Skills kullanımı ve ZIP yükleme](https://support.claude.com/en/articles/12512180-use-skills-in-claude)
- [Claude Code Skills belgeleri](https://code.claude.com/docs/en/skills)
- [Agent Skills biçim belirtimi](https://agentskills.io/specification)
