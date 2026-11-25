# TDA CodeBoost

**Sürüm:** 1.0.0  
**Geliştirici:** TDA  
**Amaç:** More efficient AI-assisted software development.

TDA CodeBoost, Claude'un kod yazma, hata ayıklama, inceleme ve optimizasyon görevlerinde ilgili bağlamı kullanmasına, mevcut proje yapısına uymasına ve test sonuçlarını doğru raporlamasına yardımcı olan bir Agent Skill'dir. Claude Chat ve Claude Code için hazırlanmıştır. Harici API, ücretli servis veya ek bağımlılık gerektirmez.

Skill çalışma yöntemlerini iyileştirmeyi hedefler; kullanım limitlerini artırdığı veya belirli oranda token tasarrufu sağladığı iddiasında bulunmaz. Doğruluk ve güvenlik önceliklidir.

## Depo yapısı

Bu GitHub deposunda Skill dosyaları doğrudan depo kökünde bulunur:

```text
.
├── SKILL.md
├── README.md
├── CHANGELOG.md
├── LICENSE
├── references/
│   ├── context-management.md
│   ├── coding-standards.md
│   ├── quality-control.md
│   └── usage-examples.md
└── tests/
    └── validation-checklist.md
```

`SKILL.md` ana iş akışını ve başvuru dosyalarının hangi durumlarda okunacağını belirtir. Ayrıntılı belgeleri yalnızca görev gerektiriyorsa yükleyin.

## Claude Chat'e yükleme

1. Claude'da Skills özelliğini açın. Hesapta isteniyorsa **Code execution and file creation** özelliğini etkinleştirin.
2. Claude'da **Customize → Skills → Add/Create skill → Upload a skill** yoluyla beceri ZIP'ini yükleyin. Menü adları hesap veya arayüz sürümüne göre değişebilir.
3. Skill'i listeden etkinleştirin ve örnek görevlerle deneyin.

Yükleme arşivinin içinde tek bir `tda-codeboost/` klasörü ve onun içinde `SKILL.md` bulunmalıdır. GitHub'a ait sıradan kaynak ZIP'ini doğrudan yüklemek yerine aşağıdaki komutla Claude için doğru klasör yapısında ZIP üretin. Komutu, `SKILL.md` dosyasının bulunduğu depo kökünde, MIT lisansı ve diğer güncellemeler commit edildikten sonra çalıştırın:

```sh
git archive --format=zip --prefix=tda-codeboost/ HEAD -o tda-codeboost-claude.zip
```

Bu komut, Git tarafından izlenen güncel dosyaları `tda-codeboost/` klasörü altında paketler; `.git` geçmişini eklemez.

## Claude Code'a kurulum

Komutları, `SKILL.md` dosyasının bulunduğu depo kökünden çalıştırın. Bu deponun dosyaları kökte olduğundan, `tda-codeboost/` adlı iç klasör varsaymayın.

### Kişisel kurulum: Linux veya macOS

```sh
mkdir -p "$HOME/.claude/skills/tda-codeboost"
cp SKILL.md README.md CHANGELOG.md LICENSE "$HOME/.claude/skills/tda-codeboost/"
cp -R references tests "$HOME/.claude/skills/tda-codeboost/"
```

### Kişisel kurulum: Windows PowerShell

```powershell
$dest = Join-Path $HOME ".claude\skills\tda-codeboost"
New-Item -ItemType Directory -Force $dest | Out-Null
Copy-Item -Path "SKILL.md","README.md","CHANGELOG.md","LICENSE" -Destination $dest -Force
Copy-Item -Path "references","tests" -Destination $dest -Recurse -Force
```

Kurulum sonunda `~/.claude/skills/tda-codeboost/SKILL.md` (Windows'ta `$HOME\.claude\skills\tda-codeboost\SKILL.md`) bulunmalıdır. Claude Code'u yeniden açın veya becerileri yenileyin; `/tda-codeboost` komutuyla doğrudan deneyin.

### Proje düzeyinde kurulum

Ekipçe tek bir depoda kullanmak için bu dosyaları hedef projenin `.claude/skills/tda-codeboost/` klasörüne kopyalayın. Bu CodeBoost deposunu ayrı bir proje olarak klonlamışsanız, CodeBoost'un kendi GitHub depo kökünü değil hedef uygulamanın depo kökünü kullanın.

## Lisans

Bu proje kök dizindeki `LICENSE` dosyasında yer alan MIT Lisansı ile paylaşılır. MIT lisansı kullanma, değiştirme ve dağıtma izni verir; yeniden dağıtımda telif ve lisans bildirimini korumak gerekir.

## Doğrulama

`tests/validation-checklist.md` Claude Chat ve Claude Code'da elle karşılaştırmalı sınama için sekiz senaryo ve puanlama ölçütü içerir. Dosya biçimi ve paket yapısı kontrol edilmiştir; gerçek Claude oturumlarında sekiz senaryo çalıştırılmadan canlı davranış veya performans sonucu varsaymayın.

## Resmi kaynaklar

- [Claude'da Skills kullanımı](https://support.claude.com/en/articles/12512180-use-skills-in-claude)
- [Claude Code Skills belgeleri](https://code.claude.com/docs/en/skills)
- [Agent Skills biçim belirtimi](https://agentskills.io/specification)
