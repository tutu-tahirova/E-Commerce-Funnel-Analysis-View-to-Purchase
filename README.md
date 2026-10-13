# E-Commerce Funnel Analysis — View to Purchase (Yanvar–Fevral 2020)

##  1. Metodologiya və Məlumatların Hazırlanması
Bu təhlil 2020-ci ilin **Yanvar** (~2.6 milyon sətir) və **Fevral** (~1.7 milyon sətir) aylarına aid kosmetika onlayn mağazasının hadisə səviyyəsində (event-level) e-ticarət məlumatlarından istifadə edərək istifadəçi davranışını və konversiya dinamikasını qiymətləndirir (ümumi ~4.3 milyon qeyd birləşdirilib).

### Funnel (Huni) Tərifi:
Məlumatların dürüstlüyünü təmin etmək və eyni istifadəçinin təkrar hərəkətlərinin nəticəni təhrif etməsinin qarşısını almaq üçün bütün huni göstəriciləri **Unikal İstifadəçilər (`user_id`)** əsasında hesablanmışdır:

### Məlumatların Təmizlənməsi və Outlier (Kənar Hədlər) Analizi:
- **Çatışmayan Dəyərlər:** Kateqoriya kodu olmayan sətirlər `'unknown'` olaraq təsnif edilmişdir.
- **Qiymət Outlier-ləri:** Alış qiymətlərindəki ekstremal anomaliyaları (lüks mallar və ya səhv daxiletmələr) aşkar etmək və təcrid etmək üçün yuxarı həddən ($Q3 + 1.5 \times IQR$) yuxarıda olan qiymətlərə IQR metodu tətbiq edilmişdir.

---

## 📊 2. Əsas Xülasə Metrikləri
- **Event Paylanması:** Baxışlar əsas qarşılıqlı əlaqələrin böyük əksəriyyətini təşkil edir (~85.1%), ardınca səbətə əlavələr (~8.7%) və alışlar (~6.2%).
- **Aylıq Artım:** Ümumi konversiya dərəcəsi Yanvar ayı ilə müqayisədə Fevral ayında **0.8 faiz bəndi (percentage points - pp)** artıb.
- **Ən Yüksək Konversiya Verən Kateqoriya:** **Accessories (Aksesuarlar)** kateqoriyası ən yüksək ümumi konversiya dərəcəsinə (~12.1%) malikdir.
- **Brend Konsentrasiyası:** Top 5 brend ümumi tamamlanmış alışların təqribən **34%-ni** təşkil edir.

---

1. İnsanlar məhsula baxır, amma səbətə atmaqdan qaçırlar (View-to-Cart problemi)
Analizə baxanda dərhal gözə çarpan ilk şey odur ki, sayta girənlər məhsullara baxır (view), amma iş səbətə atmağa (cart) gələndə təxminən 90%-i saytdan çıxıb gedir. Yəni böyük bir kütləni itirik. Buradakı əsas problem odur ki, məhsul səhifələrimiz (PDP) istifadəçini inandıra bilmir, ya da nəsə çatışmır. Məhsul şəkilləri daha keyfiyyətli olmalı, qiymət və ölçü məlumatları gözə dərhal çarpmalıdır. Mobil versiyada isə "Səbətə at" düyməsini istifadəçinin gözünün önündə, həmişə sabit saxlamaq lazımdır ki, adam məhsulu almaq istəyəndə düyməni axtarmasın.

2. Səbətə nəsə atıldımı, işin demək olar ki, 70%-i bitib
Bütün bu prosesin ən müsbət tərəfi odur ki, istifadəçi çətinliyi keçib məhsulu səbətə atdısa, artıq onun 71.4%-i gəlib alışı tamamlayır. Yəni səbətə məhsul atan adamda real almaq niyyəti var. Onda sual yaranır: bəs niyə hamı almaqla bitirmir? Deməli, səbəti tərk edənləri (cart abandoners) geri qaytarmaq üçün əlimizdə alət olmalıdır. Məsələn, kimsə səbətə məhsul atıb çıxıb gedirsə, ona dərhal "pulsuz çatdırılma" və ya qısa müddətli endirim xatırlatması edən pop-uplar çıxara bilərik. Eyni zamanda, 1-2 saat ərzində ona səbətində qalan məhsulu xatırladan qısa bir e-poçt və ya bildiriş atmaqla çox ciddi şəkildə əlavə satış qazana bilərik.

3. Aksesuarlar gözlədiyimizdən daha yaxşı satılır, bundan istifadə etməliyik
Kateqoriyalara baxanda gördüm ki, aksesuarlar (~12.1%) digər əsas məhsullara nisbətən qat-qat yaxşı konversiya verir. Çünki adam bahalı bir kosmetika alanda çox düşünür, amma ucuz və ya risksiz bir aksesuarı seçmək onun üçün daha asandır. Biz bu tendensiyadan mütləq yapışmalıyıq. Məsələn, əsas məhsul səbətə atılanda və ya ödəniş səhifəsində həmin an istifadəçiyə uyğun aksesuarları çarpaz satış (cross-sell) kimi təklif etməliyik. "Görünüşünüzü bu kiçik aksesuarla tamamlayın" tipli yanaşma ümumi səbət dəyərimizi (AOV) rahatlıqla yuxarı qaldırar.

4. Çox baxılan, amma heç alınmayan "ölü" məhsulları təmizləməliyik
Məlumatlarda maraqlı bir detal da çıxdı: elə məhsullar var ki, minlərlə adam girib baxıb, amma alanların sayı demək olar ki, sıfırdır. Bu cür məhsullar sadəcə serverdə yer tutmur, həm də bizim marketinq büdcəmizi və trafisimizi boşa xərcləyir. Gərək bu məhsulları bir-bir yoxlayaq: görək qiyməti baha qoyulub, yoxsa stoku qurtarıb, yaxud da haqqında yazılanlar o qədər zəifdir ki, adam şübhələnib qaçır? Əgər bu məhsulları düzəltmək mümkün deyilsə, reklam xərclərini onlara yönəltməyi dayandırıb, diqqəti həqiqətən satan məhsullara verməliyik.

5. Gəlirimizin üçdə birini bir neçə brend təmin edir – diqqətli olmalıyıq
Baxdım ki, ümumi alışların təxminən 34%-i (3-də 1-dən çoxu) yalnız top 5 brendin payına düşür. Bu əla хəbərdir, çünki həmin brendlər bizə əsas pulu qazandırır. Amma eyni zamanda böyük bir riskdir — əgər o brendlərdən biri ilə nəsə problem yaşansa, bütün dövriyyəmiz silkələnəcək. Ona görə də bu top 5 brendlə əlaqələrimizi möhkəmlətməliyik (məsələn, onlardan xüsusi endirimlər, eksklüziv məhsul gətirmək hüququ və ya birgə reklam büdcəsi almaq olar). Eyni zamanda, çalışmalıyıq ki, saytdakı digər az tanınan və ya yerli brendləri də irəli çəkək ki, riskimiz tək bir yerdə cəmləşməsin.
