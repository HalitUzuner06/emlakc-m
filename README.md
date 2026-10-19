<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Emlakcım – Ankara mahalle bazlı fiyat tahmini</title>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,500;12..96,800&family=Figtree:wght@400;600;700&family=Fredoka:wght@600&display=swap">
<style>
:root{--sky1:#0f1733;--sky2:#2b2f6b;--sky3:#c4577a;--sun:#f6b45c;--far:#2a2f5e;--mid:#1a2049;--near:#0c1230;
--paper:#e8ebf0;--card:#fff;--txt:#162033;--mute:#5d6a7e;--line:#d6dce6;--acc:#0e8f8a;--acc2:#0b6f6b;--field:#f3f5f8;--chip:#e3e8ef;--bar:#b8c2d1;
--ok:#1f8a5b;--hi:#c2412f;--lo:#b9770e;
box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px);color-scheme:light}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--paper:#0a0f22;--card:#121a36;--txt:#e8ecf6;--mute:#94a0ba;--line:#26305a;--acc:#3dd1c9;--acc2:#3dd1c9;--field:#0c1330;--chip:#1c2650;--bar:#33407a;--ok:#5fd3a0;--hi:#ff9a88;--lo:#f2bd6a;color-scheme:dark}}
:root[data-theme="dark"]{--paper:#0a0f22;--card:#121a36;--txt:#e8ecf6;--mute:#94a0ba;--line:#26305a;--acc:#3dd1c9;--acc2:#3dd1c9;--field:#0c1330;--chip:#1c2650;--bar:#33407a;--ok:#5fd3a0;--hi:#ff9a88;--lo:#f2bd6a;color-scheme:dark}
*{box-sizing:border-box}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
body{margin:0;background:var(--paper);color:var(--txt);font:16px/1.55 Figtree,system-ui,-apple-system,"Segoe UI",sans-serif}
.hero{position:relative;overflow:hidden;color:#fff;padding:22px 20px 120px;background:linear-gradient(180deg,var(--sky1) 0%,var(--sky2) 55%,var(--sky3) 100%)}
.sun{position:absolute;right:14%;bottom:70px;width:150px;height:150px;border-radius:50%;background:radial-gradient(circle,var(--sun) 0,rgba(246,180,92,.55) 45%,transparent 70%);filter:blur(2px)}
.sky{position:absolute;left:0;right:0;bottom:-1px;width:100%;height:120px;display:block;opacity:.85}
.in{position:relative;max-width:1080px;margin:0 auto}
.top{display:flex;justify-content:space-between;align-items:center}
.brand{font-family:"Bricolage Grotesque",system-ui,sans-serif;font-weight:800;font-size:20px;letter-spacing:-.01em;display:flex;gap:9px;align-items:center}
.brand i{width:14px;height:14px;background:var(--sun);border-radius:3px 3px 3px 12px;display:block}
h1{font-family:"Bricolage Grotesque",system-ui,sans-serif;font-weight:800;font-size:clamp(30px,4.6vw,48px);line-height:1.08;margin:30px 0 12px;letter-spacing:-.025em;max-width:22ch;text-wrap:balance}
.lead{max-width:52ch;color:#dfe3f3;margin:0;font-size:17px}
.stats{display:flex;flex-wrap:wrap;gap:10px 28px;margin-top:18px;font-size:14px;color:#dfe3f3}
.stats b{display:block;font-family:"Bricolage Grotesque",sans-serif;font-size:26px;color:#fff;line-height:1.1}
main{max-width:1080px;margin:-64px auto 0;padding:0 20px 56px;display:grid;gap:22px;position:relative}
.work{display:grid;grid-template-columns:1.15fr .85fr;gap:22px;align-items:start}
@media(max-width:860px){.work{grid-template-columns:1fr}.res{position:static!important}}
.card{background:var(--card);border:1px solid var(--line);border-radius:14px;padding:24px;box-shadow:0 18px 40px -26px rgba(10,15,40,.5)}
.seg{display:grid;grid-template-columns:1fr 1fr;background:var(--chip);border-radius:10px;padding:4px;margin-bottom:10px;gap:4px}
.seg button{border:0;background:none;color:var(--mute);font:inherit;font-weight:700;padding:10px 4px;cursor:pointer;border-radius:7px}
.seg button[aria-pressed="true"]{background:var(--card);color:var(--txt);box-shadow:0 1px 3px rgba(10,15,40,.2)}
.row{display:grid;grid-template-columns:1fr 1fr;gap:14px}
@media(max-width:480px){.row{grid-template-columns:1fr}}
label{display:block;font-size:13px;color:var(--mute);margin:12px 0 5px;font-weight:600}
input,select{width:100%;font:inherit;color:var(--txt);background:var(--field);border:1px solid var(--line);border-radius:8px;padding:11px 12px}
input:focus-visible,select:focus-visible,button:focus-visible{outline:2px solid var(--acc);outline-offset:2px}
.checks{display:flex;flex-wrap:wrap;gap:8px;margin-top:16px}
.checks label{display:flex;align-items:center;gap:7px;margin:0;color:var(--txt);border:1px solid var(--line);border-radius:999px;padding:7px 14px;cursor:pointer;font-size:14px;font-weight:600}
.checks input{width:auto;accent-color:var(--acc2)}
.hint{font-size:13px;color:var(--mute);margin:18px 0 0}
.res{background:linear-gradient(160deg,#141c45,#0f1733);color:#eef1fb;border-color:#26305a;position:sticky;top:calc(env(safe-area-inset-top,0px) + 12px)}
.res .k{color:#a9b4d4;font-size:14px}
.big{font-family:"Bricolage Grotesque",sans-serif;font-weight:800;font-size:clamp(38px,7vw,54px);line-height:1.05;color:#ffd08a;margin:6px 0 4px;letter-spacing:-.02em;font-variant-numeric:tabular-nums}
.rng{color:#cdd5ee;font-size:15px}
.bar{position:relative;height:8px;border-radius:4px;background:linear-gradient(90deg,#3b4688,#3dd1c9,#3b4688);margin:30px 0 8px}
.pin{position:absolute;top:-8px;width:4px;height:24px;background:#fff;border-radius:2px;transform:translateX(-50%);transition:left .4s}
.scale{display:flex;justify-content:space-between;font-size:13px;color:#cdd5ee}
.verdict{margin-top:16px;padding:13px 15px;border-left:4px solid #3dd1c9;border-radius:0 8px 8px 0;background:rgba(255,255,255,.08);font-weight:600;font-size:15px}
.verdict.hi{border-color:#ff9a88}.verdict.lo{border-color:#f2bd6a}
dl{display:grid;grid-template-columns:auto 1fr;gap:7px 16px;margin:20px 0 0;font-size:14px;border-top:1px solid #26305a;padding-top:16px}
dt{color:#a9b4d4}dd{margin:0;text-align:right;font-weight:600}
.cmp{grid-column:1/-1}
.cmp h2{font-family:"Bricolage Grotesque",sans-serif;font-size:22px;margin:0 0 4px;letter-spacing:-.01em}
.cmp p{margin:0 0 14px;color:var(--mute);font-size:14px}
.bars{display:grid;gap:6px;max-height:380px;overflow:auto;padding-right:4px}
.more{margin-top:22px;border-top:1px solid var(--line);padding-top:6px}
.more>summary,.tb>summary{cursor:pointer;font-weight:700;padding:12px 0;list-style:none}
.more>summary::after{content:"+";float:right;color:var(--acc2);font-size:20px;line-height:1}
.more[open]>summary::after{content:"−"}
.tb>summary{color:#cdd5ee;font-size:14px;margin-top:14px;border-top:1px solid #26305a}
.info{grid-column:1/-1;display:grid;gap:28px}
.info h2{font-family:"Bricolage Grotesque",sans-serif;font-size:22px;margin:0 0 14px;letter-spacing:-.01em}
.steps{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
@media(max-width:720px){.steps{grid-template-columns:1fr}}
.steps div{border-left:3px solid var(--acc);padding-left:14px}
.steps b{display:block;margin-bottom:4px}
.steps p{margin:0;color:var(--mute);font-size:14px}
.faq details{border-bottom:1px solid var(--line)}
.faq summary{cursor:pointer;font-weight:700;padding:13px 0;list-style:none}
.faq summary::after{content:"+";float:right;color:var(--acc2);font-size:20px;line-height:1}
.faq details[open] summary::after{content:"−"}
.faq p{margin:0 0 14px;color:var(--mute);font-size:15px;max-width:70ch}
footer{background:var(--sky1);color:#cdd5ee;padding:32px 20px calc(32px + env(safe-area-inset-bottom,0px));font-size:14px}
footer .in{display:grid;gap:10px}
footer b{font-family:Fredoka,"Trebuchet MS",sans-serif;font-weight:600;font-size:20px;color:#fff}
footer p{margin:0;max-width:78ch;color:#a9b4d4}
.b{display:grid;grid-template-columns:120px 1fr 92px;gap:10px;align-items:center;border:0;background:none;color:var(--txt);font:inherit;font-size:14px;text-align:left;padding:3px 6px;border-radius:8px;cursor:pointer}
.b:hover{background:var(--field)}
.b .t{height:12px;border-radius:6px;background:var(--chip);overflow:hidden}
.b .t i{display:block;height:100%;background:var(--bar);border-radius:6px;transition:width .4s}
.b.on{background:var(--field);font-weight:700}.b.on .t i{background:var(--acc)}
.b span:last-child{text-align:right;font-variant-numeric:tabular-nums}
@media(max-width:480px){.b{grid-template-columns:92px 1fr 74px;font-size:13px}}
.note{grid-column:1/-1;font-size:13px;color:var(--mute);max-width:72ch;margin:0}
.brand svg{width:38px;height:38px;flex:none;filter:drop-shadow(0 2px 6px rgba(0,0,0,.3))}
.brand span{font-family:Fredoka,"Trebuchet MS",system-ui,sans-serif;font-weight:600;font-size:27px;letter-spacing:.01em;line-height:1}
.sec{font-family:"Bricolage Grotesque",sans-serif;font-size:16px;margin:26px 0 0;padding-top:18px;border-top:1px solid var(--line)}
.tt{font-size:13px;color:#a9b4d4;margin:22px 0 6px;font-weight:700}
.tbl{width:100%;border-collapse:collapse;font-size:13px}
.tbl td{padding:6px 8px;border-bottom:1px solid #26305a}.tbl td:last-child{text-align:right;font-variant-numeric:tabular-nums}
.tbl tr.on td{background:rgba(61,209,201,.16);font-weight:700;color:#fff}
@media(min-width:861px){.res{max-height:calc(100vh - 24px);overflow:auto}}
@media(prefers-reduced-motion:reduce){*{transition:none!important}}
</style>
</head>
<body>
<header class="hero">
  
  <svg class="sky" id="sky" viewBox="0 0 1200 210" preserveAspectRatio="xMidYMax slice" aria-hidden="true"></svg>
  <div class="in">
    <div class="top"><div class="brand"><svg viewBox="0 0 40 40" role="img" aria-label="Emlakcım logosu"><path d="M5 19.5 20 5.5l15 14V33a2.5 2.5 0 0 1-2.5 2.5h-25A2.5 2.5 0 0 1 5 33z" fill="#f6b45c"/><rect x="27.5" y="7" width="4.5" height="9" rx="1" fill="#fff"/><path d="M3.5 20 20 4.5 36.5 20" fill="none" stroke="#fff" stroke-width="2.6" stroke-linecap="round" stroke-linejoin="round"/><path d="M16 35.5V26a4 4 0 0 1 8 0v9.5z" fill="#0f1733"/><rect x="9.5" y="20.5" width="5" height="5" rx="1" fill="#0f1733"/><rect x="25.5" y="20.5" width="5" height="5" rx="1" fill="#0f1733"/></svg><span>Emlakcım</span></div></div>
    <h1>Ankara’da evinin değerini mahalle mahalle gör.</h1>
    <p class="lead">Mahalle bazlı satış ve kira tahmini. Ev sahipleri doğru fiyatı belirler, ev arayanlar istenen fiyatı kıyaslar.</p>
    <div class="stats"><div><b id="s1">0</b>mahalle</div><div><b id="s2">0</b>ilçe</div><div><b>Eylül 2026</b>güncel piyasa verisi</div></div>
  </div>
</header>

<main>
<div class="work">
<section class="card" aria-label="Ev bilgileri">
  <div class="seg" id="role" role="group" aria-label="Kimsin?">
    <button type="button" data-v="owner" aria-pressed="true">Ev sahibiyim</button>
    <button type="button" data-v="seeker" aria-pressed="false">Ev arıyorum</button>
  </div>
  <div class="seg" id="mode" role="group" aria-label="İşlem türü">
    <button type="button" data-v="sale" aria-pressed="true">Satılık</button>
    <button type="button" data-v="rent" aria-pressed="false">Kiralık</button>
  </div>
  <div class="row">
    <div><label for="city">İl</label><select id="city"></select></div>
    <div><label for="dist">İlçe</label><select id="dist"></select></div>
  </div>
  <label for="hood">Mahalle</label><select id="hood"></select>
  <div class="row">
    <div><label for="m2">Brüt metrekare</label><input id="m2" type="number" min="20" max="500" value="110" inputmode="numeric"></div>
    <div><label for="rooms">Oda sayısı</label><select id="rooms"><option>1+0</option><option>1+1</option><option>2+1</option><option selected>3+1</option><option>4+1</option><option>5+</option></select></div>
  </div>
  <div class="row">
    <div><label for="age">Bina yaşı</label><select id="age"><option value="1.1">Sıfır bina</option><option value="1.08">1–4</option><option value="1" selected>5–10</option><option value="0.96">11–15</option><option value="0.93">16–20</option><option value="0.89">21–25</option><option value="0.86">26–30</option><option value="0.78">31 ve üzeri</option></select></div>
    <div><label for="floor">Bulunduğu kat</label><select id="floor"><option value="0.8" data-n="0">Bodrum</option><option value="0.92" data-n="0">Zemin / bahçe katı</option><option value="0.96" data-n="1">Yüksek giriş</option><option value="0.98" data-n="1">1. kat</option><option value="1" data-n="2" selected>2. kat</option><option value="1" data-n="3">3. kat</option><option value="1.02" data-n="4">4. kat</option><option value="1.02" data-n="5">5. kat</option><option value="1.02" data-n="6">6. kat</option><option value="1.02" data-n="7">7. kat</option><option value="1.03" data-n="8">8–10. kat</option><option value="1.03" data-n="11">11–15. kat</option><option value="1.03" data-n="16">16 ve üzeri</option><option value="0.97" data-n="5">Çatı katı</option></select></div>
  </div>
  <div class="row">
    <div><label for="heat">Isıtma</label><select id="heat"><option value="1" selected>Kombi (doğalgaz)</option><option value="0.97">Merkezi</option><option value="1.04">Yerden ısıtma</option><option value="0.9">Klima / soba</option></select></div>
    <div id="askBox" hidden><label for="ask">İstenen fiyat (₺)</label><input id="ask" type="number" min="0" inputmode="numeric" placeholder="Örn. 6500000"></div>
  </div>
  <div class="checks">
    <label><input type="checkbox" id="elev" checked>Asansör</label>
    
    <label><input type="checkbox" id="balc" checked>Balkon</label>
    <label><input type="checkbox" id="site">Site içinde</label>
    <label id="furnL" hidden><input type="checkbox" id="furn">Eşyalı</label>
  </div>
  <details class="more"><summary>Daire ve bina detayları (cephe, banyo, özellikler)</summary>
  <div class="row">
    <div><label for="net">Net m²</label><input id="net" type="number" min="15" max="450" inputmode="numeric" placeholder="Örn. 95"></div>
    <div><label for="tot">Binadaki kat sayısı</label><input id="tot" type="number" min="1" max="60" value="6" inputmode="numeric"></div>
  </div>
  <div class="row">
    <div><label for="bath">Banyo sayısı</label><select id="bath"><option value="1">1</option><option value="2" selected>2</option><option value="3">3 ve üzeri</option></select></div>
    <div><label for="park">Otopark</label><select id="park"><option value="1">Yok</option><option value="1.02">Açık otopark</option><option value="1.04">Kapalı otopark</option></select></div>
  </div>
  <div class="row">
    <div><label for="view">Manzara</label><select id="view"><option value="1">Yok</option><option value="1.02">Şehir</option><option value="1.03">Doğa / orman</option></select></div>
    <div><label for="cond">Bakım durumu</label><select id="cond"><option value="1.05">Yenilenmiş</option><option value="1" selected>Bakımlı</option><option value="0.92">Tadilat gerekli</option></select></div>
  </div>
  <div class="row">
    <div><label for="deed">Tapu durumu</label><select id="deed"><option value="1">Kat mülkiyeti</option><option value="0.95">Kat irtifakı</option><option value="0.85">Hisseli tapu</option></select></div>
    <div><label for="use">Kullanım durumu (satış)</label><select id="use"><option value="1">Boş</option><option value="1">Mal sahibi oturuyor</option><option value="0.96">Kiracılı</option></select></div>
  </div>
  <label>Cephe</label>
  <div class="checks" id="facade">
    <label><input type="checkbox" value="K">Kuzey</label>
    <label><input type="checkbox" value="G">Güney</label>
    <label><input type="checkbox" value="D">Doğu</label>
    <label><input type="checkbox" value="B">Batı</label>
  </div>
  <label>İç özellikler</label>
  <div class="checks ft">
    <label><input type="checkbox" data-m="1.025" checked>Ebeveyn banyosu</label>
    <label><input type="checkbox" data-m="1.01">Giyinme odası</label>
    <label><input type="checkbox" data-m="1.01">Ankastre mutfak</label>
    <label><input type="checkbox" data-m="1.005">Amerikan mutfak</label>
    <label><input type="checkbox" data-m="1.02">Teras</label>
    <label><input type="checkbox" data-m="1.005">Klima</label>
    <label><input type="checkbox" data-m="1.01">Akıllı ev</label>
  </div>
  <label>Bina ve site olanakları</label>
  <div class="checks ft">
    <label><input type="checkbox" data-m="1.01">Güvenlik</label>
    <label><input type="checkbox" data-m="1.02">Yüzme havuzu</label>
    <label><input type="checkbox" data-m="1.01">Spor salonu</label>
    <label><input type="checkbox" data-m="1.005">Jeneratör</label>
    <label><input type="checkbox" data-m="1.01">Isı yalıtımı (mantolama)</label>
  </div>
  </details>
  <p class="hint">Sonuç, bilgileri değiştirdikçe anında güncellenir.</p>
</section>

<section class="card res" aria-live="polite" id="out"></section>
</div>

<section class="card cmp" id="cmp" aria-label="İlçe karşılaştırması"></section>

<section class="card info" aria-label="Nasıl hesaplıyoruz">
  <div>
    <h2>Nasıl hesaplıyoruz?</h2>
    <div class="steps">
      <div><b>Mahalle tabanı</b><p>Seçtiğin mahallenin güncel ilan bazlı m² fiyatından başlarız. Veri Eylül 2026 tarihlidir.</p></div>
      <div><b>Daireye göre düzeltme</b><p>Bina yaşı, kat, cephe, banyo, ebeveyn banyosu, tapu durumu gibi özellikler fiyatı yukarı ya da aşağı ayarlar.</p></div>
      <div><b>Makul aralık</b><p>Tahminin %8 altı ve üstünü makul aralık olarak gösteririz. Kira, bölgenin kira ile geri dönüş süresinden türetilir.</p></div>
    </div>
  </div>
  <div class="faq">
    <h2>Sık sorulan sorular</h2>
    <details><summary>Tahmin ekspertiz raporunun yerine geçer mi?</summary><p>Hayır. Emlakcım size fikir verir. Bankadan kredi çekecekseniz ya da resmi bir işlem yapacaksanız lisanslı bir değerleme uzmanına başvurun.</p></details>
    <details><summary>Fiyatlar ne kadar güncel?</summary><p>Ankara verileri Eylül 2026 tarihli ilan fiyatlarına dayanır. İlan fiyatı gerçekleşen satış fiyatı değildir, pazarlık sonunda genelde daha düşük bir tutara anlaşılır.</p></details>
    <details><summary>Mahallemi bulamıyorum, neden?</summary><p>Şimdilik Ankara’da seçili mahalleler var. Çankaya en ayrıntılı ilçemiz. Diğer ilçeleri ve mahalleleri genişletmeye devam ediyoruz.</p></details>
    <details><summary>Başka iller için de hesap yapabilir miyim?</summary><p>İstanbul, İzmir, Bursa ve Antalya örnek veriyle çalışır ve doğrulanmamıştır. Sonuç kartında bu açıkça belirtilir.</p></details>
    <details><summary>Girdiğim bilgiler kaydediliyor mu?</summary><p>Hayır. Hesaplama tarayıcınızda yapılır, girdiğiniz bilgiler bir sunucuya gönderilmez.</p></details>
  </div>
</section>

<p class="note">Ankara satış m² fiyatları Eylül 2026 ilan bazlı piyasa verisine dayanır; Çankaya mahalleleri doğrudan, diğer ilçelerde mahalle farkları ilçe ortalamasına göre ölçeklenmiştir. İlan fiyatı gerçekleşen satış fiyatı değildir ve az ilanlı mahallelerde sapma olabilir. Kira değerleri bölgenin amortisman süresinden türetilmiştir. Diğer iller örnek veridir. Karar vermeden önce ekspertiz veya tapu verisiyle doğrulayın. Cephe, kat, banyo, ebeveyn banyosu gibi özellik katsayıları kaynak veri değil, ayarlanabilir varsayımdır.</p>
</main>
<footer><div class="in"><b>Emlakcım</b><p>Ankara’da mahalle bazlı konut değer ve kira tahmini. Emlakcım’ın sunduğu bilgiler bilgilendirme amaçlıdır; resmi değerleme raporu, yatırım ya da hukuki tavsiye değildir.</p><p>© 2026 Emlakcım</p></div></footer>

<script>
// Örnek veri: [satış bin ₺/m², aylık kira ₺/m²]
const DATA={
"Ankara":{
 "Çankaya":{"Kavaklıdere":[85,420],"Gaziosmanpaşa":[80,400],"Yıldız":[82,390],"Oran":[78,360],"Ayrancı":[68,350],"Çukurambar":[72,380],"Bahçelievler":[62,340],"Çayyolu":[58,310],"Ümitköy":[55,300],"Balgat":[52,280],"Beytepe":[50,280],"Dikmen":[48,260]},
 "Yenimahalle":{"Batıkent":[40,240],"Demetevler":[38,230],"İvedik":[36,220],"Ostim":[33,210],"Şentepe":[30,190]},
 "Etimesgut":{"Eryaman":[41,245],"Elvankent":[38,225],"Bağlıca":[36,220],"Süvari":[35,215],"Erler":[33,210]},
 "Keçiören":{"Etlik":[38,220],"Ayvalı":[36,210],"Kuşcağız":[33,200],"Aktepe":[31,190],"Bağlum":[29,180]},
 "Gölbaşı":{"İncek":[65,320],"Bahçelievler":[44,245],"Karşıyaka":[40,230]},
 "Mamak":{"Abidinpaşa":[30,185],"Kutludüğün":[27,170],"Tuzluçayır":[26,165],"Mutlu":[25,160]},
 "Sincan":{"Fatih":[28,175],"Yenikent":[26,165],"Ahi Mesut":[25,160]},
 "Altındağ":{"Aydınlıkevler":[29,180],"Karapürçek":[27,165],"Siteler":[25,160]},
 "Pursaklar":{"Merkez":[32,190],"Saray":[30,180]},
 "Polatlı":{"Merkez":[18,110]}},
"İstanbul":{"Tüm il":{"Ortalama":[85,430]}},
"İzmir":{"Tüm il":{"Ortalama":[55,300]}},
"Bursa":{"Tüm il":{"Ortalama":[38,220]}},
"Antalya":{"Tüm il":{"Ortalama":[55,290]}}
};
// Güncel veri: Eylül 2026 (satılık daire, ₺/m²). Kira, bölgenin amortisman süresinden türetilir.
(function(){
  const A=DATA.Ankara;
  const P={"Yenimahalle":52.646,"Etimesgut":47.931,"Keçiören":36.546,"Gölbaşı":73.452,"Mamak":32.534,"Sincan":34.078,"Altındağ":34.264,"Pursaklar":39.426,"Polatlı":22.343};
  const Y={"Çankaya":14,"Yenimahalle":15,"Etimesgut":13,"Keçiören":13,"Gölbaşı":14,"Mamak":12,"Sincan":13,"Altındağ":13,"Pursaklar":15,"Polatlı":12};
  const rent=(s,d)=>Math.round(s*1000/(Y[d]*12));
  const C={"Oran":118,"Çayyolu":117.9,"Bahçelievler":117.8,"Ümit":113.1,"Konutkent":109.9,"Beytepe":108.1,"Mutlukent":107.9,"Ahlatlıbel":100.7,"Yukarı Dikmen":97.3,"Mebusevleri":95.5,"Dumlupınar":95.2,"Alacaatlı":95.1,"Yukarı Öveçler":93.3,"Kızılırmak":92.2,"İlkbahar":91.6,"Yukarı Bahçelievler":91.4,"Yeşilkent":90.7,"A. Taner Kışlalı":88.7,"Koru":85.9,"Çukurambar":85,"Yıldızevler":83.9,"Barbaros":83.1,"Yaşamkent":83.1,"Gaziosmanpaşa":81.8,"Emek":80.5,"Çiğdem":77.7,"Güvenevler":74.2,"Küçükesat":71.2,"Kavaklıdere":69.6,"Ayrancı":68.5,"Cevizlidere":68.4,"Maltepe":67.9,"Büyükesat":65.4,"100. Yıl":63.8,"Hilal":61.7,"Birlik":59.1,"Balgat":57.3,"Kırkkonaklar":55.1,"Aşağı Öveçler":55,"Akpınar":54.2,"Cebeci":51.7,"Öveçler":51.4,"Kızılay":47.1,"Aşıkpaşa":42.8,"Murat":42.3};
  A["Çankaya"]=Object.fromEntries(Object.entries(C).map(([n,s])=>[n,[s,rent(s,"Çankaya")]]));
  Object.keys(P).forEach(d=>{const h=A[d],v=Object.values(h).map(x=>x[0]),f=P[d]/(v.reduce((a,b)=>a+b,0)/v.length);
    Object.keys(h).forEach(n=>{const s=+(h[n][0]*f).toFixed(1);h[n]=[s,rent(s,d)]})});
})();
const $=id=>document.getElementById(id);
const st={role:"owner",mode:"sale"};
const tl=n=>Math.round(n).toLocaleString("tr-TR")+" ₺";
const opts=a=>a.map(x=>`<option>${x}</option>`).join("");
function fillCity(){$("city").innerHTML=opts(Object.keys(DATA));fillDist()}
function fillDist(){$("dist").innerHTML=opts(Object.keys(DATA[$("city").value]));fillHood()}
function fillHood(){$("hood").innerHTML=opts(Object.keys(DATA[$("city").value][$("dist").value]))}
$("city").addEventListener("change",()=>{fillDist();render()});
$("dist").addEventListener("change",()=>{fillHood();render()});
function seg(id,key){$(id).addEventListener("click",e=>{const b=e.target.closest("button");if(!b)return;$(id).querySelectorAll("button").forEach(x=>x.setAttribute("aria-pressed",x===b));st[key]=b.dataset.v;sync();render()})}
function sync(){$("askBox").hidden=st.role!=="seeker";$("furnL").hidden=st.mode!=="rent";$("ask").placeholder=st.mode==="rent"?"Örn. 28000":"Örn. 6500000"}
seg("role","role");seg("mode","mode");

// Ankara silüeti: Atakule, Kocatepe Camii ve apartman blokları
(function(){
  let s='<path fill="var(--far)" d="M0 150 Q150 105 300 140 T600 120 T900 140 T1200 115 V210 H0Z"/>';
  let x=0,i=0;const hs=[44,70,56,90,62,48,80,58,100,66];
  while(x<1200){const w=26+(i*7%22),h=hs[i%hs.length]*.8+10;s+=`<rect x="${x}" y="${190-h}" width="${w}" height="${h+20}" fill="var(--mid)"/>`;x+=w+4;i++}
  s+='<g fill="var(--near)">';
  // Atakule
  s+='<rect x="866" y="52" width="8" height="140"/><ellipse cx="870" cy="52" rx="24" ry="9"/><rect x="858" y="40" width="24" height="12" rx="4"/><rect x="869" y="18" width="2" height="22"/>';
  // Kocatepe: kubbe + dört minare
  s+='<rect x="250" y="148" width="120" height="50"/><path d="M262 148 a48 44 0 0 1 96 0z"/><rect x="309" y="96" width="2" height="12"/>';
  [236,374,226,384].forEach((m,k)=>{const h=k<2?100:84;s+=`<rect x="${m-3}" y="${190-h}" width="6" height="${h+10}"/><path d="M${m-4} ${190-h} L${m} ${190-h-18} L${m+4} ${190-h}z"/>`});
  // ön plan bloklar
  for(let b=0,bx=0;bx<1200;b++){const w=34+(b*13%30),h=26+(b*37%44);s+=`<rect x="${bx}" y="${200-h}" width="${w}" height="${h+10}"/>`;bx+=w+10}
  s+='</g><g fill="#ffd08a" opacity=".75">';
  for(let w=0;w<46;w++){s+=`<rect x="${(w*97)%1180+8}" y="${170+(w*29)%32}" width="3" height="4"/>`}
  $("sky").innerHTML=s+'</g>';
})();

let shown=0,raf;
function anim(el,to,suffix){cancelAnimationFrame(raf);const from=shown,t0=performance.now();
  const reduce=matchMedia("(prefers-reduced-motion:reduce)").matches;
  const step=t=>{const p=reduce?1:Math.min(1,(t-t0)/450),v=from+(to-from)*(1-Math.pow(1-p,3));el.textContent=tl(v)+suffix;if(p<1)raf=requestAnimationFrame(step);else shown=to};
  raf=requestAnimationFrame(step)}

function factor(m2,ageV){
  const rent=st.mode==="rent",o=$("floor").selectedOptions[0],fl=+o.dataset.n,tot=+$("tot").value||0;
  let f=ageV*+o.value*+$("heat").value*+$("park").value*+$("view").value*+$("cond").value*+$("deed").value;
  if(m2<60)f*=1.06;else if(m2>160)f*=.94;
  if(!$("elev").checked&&fl>=3)f*=.93;
  if(tot>=4&&fl===tot)f*=.98;
  if(!rent)f*=+$("use").value;
  const fc=[...document.querySelectorAll("#facade input:checked")].map(x=>x.value);
  if(fc.includes("G"))f*=1.02;else if(fc.length===1&&fc[0]==="K")f*=.98;
  if(fc.length>=3)f*=1.015;
  const ba=+$("bath").value;if(ba>=2)f*=ba>=3?1.03:1.015;
  if($("balc").checked)f*=1.02;if($("site").checked)f*=1.05;if(rent&&$("furn").checked)f*=1.12;
  document.querySelectorAll(".ft input:checked").forEach(x=>{f*=+x.dataset.m});
  return f}
function extra(){
  const m2=+$("m2").value||0,net=+$("net").value||0,tot=+$("tot").value||0,o=$("floor").selectedOptions[0];
  const nm={K:"Kuzey",G:"Güney",D:"Doğu",B:"Batı"};
  const fc=[...document.querySelectorAll("#facade input:checked")].map(x=>nm[x.value]);
  return{net:net?`${net} m² · %${Math.round(net/(m2||1)*100)}`:"Girilmedi",face:fc.join(", ")||"Belirtilmedi",kat:`${o.text}${tot?" · "+tot+" katlı":""}`,warn:net&&net>m2?"Net m² brüt m²’den büyük olamaz. Değerleri kontrol et.":""}}
function calc(){
  const d=DATA[$("city").value][$("dist").value],h=d[$("hood").value];
  const idx=st.mode==="rent"?1:0,mult=st.mode==="rent"?1:1000;
  const rate=h[idx]*mult;
  const vals=Object.values(d).map(v=>v[idx]*mult),avg=vals.reduce((a,b)=>a+b,0)/vals.length;
  const m2=Math.max(20,+$("m2").value||0);
  const mid=m2*rate*factor(m2,+$("age").value);
  const sale=h[0]*1000,rent=h[1];
  return{rate,mid,lo:mid*.92,hi:mid*1.08,m2,rooms:$("rooms").value,perM2:mid/m2,vsAvg:(rate/avg-1)*100,payback:sale/(rent*12),d,idx,mult,avg};
}
function render(){
  const r=calc(),rent=st.mode==="rent",u=rent?" /ay":"",ex=extra();
  let h=`<div class="k">${rent?"Tahmini aylık kira":"Tahmini satış değeri"} – ${$("hood").value}, ${$("dist").value}</div>
  <div class="big" id="big">${tl(shown)}${u}</div>
  <div class="rng">Makul aralık: ${tl(r.lo)} – ${tl(r.hi)}</div>`;
  const ask=+$("ask").value;
  if(st.role==="seeker"&&ask>0){
    const pos=Math.min(100,Math.max(0,(ask-r.lo*.85)/(r.hi*1.15-r.lo*.85)*100)),diff=(ask/r.mid-1)*100;
    let c="ok",m="İstenen fiyat makul aralıkta.";
    if(ask>r.hi){c="hi";m=`İstenen fiyat tahminin %${diff.toFixed(0)} üzerinde. Pazarlık payı var.`}
    else if(ask<r.lo){c="lo";m=`İstenen fiyat tahminin %${Math.abs(diff).toFixed(0)} altında. Evin durumunu ve tapusunu mutlaka kontrol et.`}
    h+=`<div class="bar" role="img" aria-label="İstenen fiyatın aralıktaki yeri"><div class="pin" style="left:${pos}%"></div></div><div class="scale"><span>${tl(r.lo)}</span><span>${tl(r.hi)}</span></div><div class="verdict ${c}">${m}</div>`;
  }else if(st.role==="owner"){
    h+=`<div class="verdict ok">İlana ${tl(r.hi)}${u} ile başla, ${tl(r.mid)}${u} civarında anlaşmayı hedefle.</div>`;
  }
  const cmp=Math.abs(r.vsAvg)<1?"ilçe ortalamasında":`ilçe ortalamasının %${Math.abs(r.vsAvg).toFixed(0)} ${r.vsAvg>0?"üzerinde":"altında"}`;
  h+=`<dl><dt>Metrekare başı</dt><dd>${tl(r.perM2)}</dd><dt>Mahalle konumu</dt><dd>${cmp}</dd><dt>Alan / oda</dt><dd>${r.m2} m² · ${r.rooms}</dd><dt>Net / brüt</dt><dd>${ex.net}</dd><dt>Kat</dt><dd>${ex.kat}</dd><dt>Cephe</dt><dd>${ex.face}</dd><dt>Kira ile geri dönüş</dt><dd>${r.payback.toFixed(1)} yıl</dd></dl>`;
  if($("city").value!=="Ankara")h+=`<div class="verdict lo">Bu il için veri örnektir, doğrulanmamıştır.</div>`;
  else if(rent)h+=`<p class="k" style="margin:14px 0 0;font-size:13px">Kira, bölgenin amortisman süresinden türetilmiş tahmindir.</p>`;
  if(ex.warn)h+=`<div class="verdict lo">${ex.warn}</div>`;
  const sh=n=>n>=1e6?(n/1e6).toFixed(2).replace(".",",")+" M ₺":Math.round(n/1e3)+" bin ₺";
  const ageV=+$("age").value,fa=(m,a)=>m*r.rate*factor(m,a),sf=rent?" (aylık)":"";
  const SZ=[[50,70],[70,90],[90,110],[110,130],[130,160],[160,200]];
  h+=`<details class="tb" open><summary>Boyuta ve yaşa göre aralıklar</summary><h3 class="tt">Boyuta göre fiyat aralığı${sf}</h3><table class="tbl"><tbody>`+SZ.map(([a,b])=>`<tr class="${r.m2>=a&&r.m2<b?"on":""}"><td>${a}–${b} m²</td><td>${sh(fa(a,ageV))} – ${sh(fa(b,ageV))}</td></tr>`).join("")+`</tbody></table>`;
  const AG=[["Sıfır bina",1.1],["1–4 yaş",1.08],["5–10 yaş",1],["11–15 yaş",.96],["16–20 yaş",.93],["21–25 yaş",.89],["26–30 yaş",.86],["31+ yaş",.78]];
  h+=`<h3 class="tt">Bina yaşına göre, ${r.m2} m²${sf}</h3><table class="tbl"><tbody>`+AG.map(([n,v])=>{const p=fa(r.m2,v);return `<tr class="${v===ageV?"on":""}"><td>${n}</td><td>${sh(p*.92)} – ${sh(p*1.08)}</td></tr>`}).join("")+`</tbody></table>`;
  h+="</details>";
  $("out").innerHTML=h;
  anim($("big"),r.mid,u);
  // İlçe karşılaştırma grafiği
  const rows=Object.entries(r.d).sort((a,b)=>b[1][r.idx]-a[1][r.idx]),mx=rows[0][1][r.idx];
  $("cmp").innerHTML=`<h2>${$("dist").value} mahalleleri</h2><p>${rent?"Aylık kira, m² başına":"Satış fiyatı, m² başına"}. Bir mahalleye dokunarak hesabı onun için güncelle.</p><div class="bars">`+
    rows.map(([n,v])=>`<button type="button" class="b${n===$("hood").value?" on":""}" data-h="${n}"><span>${n}</span><span class="t"><i style="width:${v[r.idx]/mx*100}%"></i></span><span>${tl(v[r.idx]*r.mult)}</span></button>`).join("")+`</div>`;
}
$("cmp").addEventListener("click",e=>{const b=e.target.closest("[data-h]");if(!b)return;$("hood").value=b.dataset.h;render()});
document.querySelector("main").addEventListener("input",render);
document.querySelector("main").addEventListener("change",render);

fillCity();sync();
const hoods=Object.values(DATA).reduce((a,c)=>a+Object.values(c).reduce((b,d)=>b+Object.keys(d).length,0),0);
$("s1").textContent=Object.values(DATA.Ankara).reduce((a,d)=>a+Object.keys(d).length,0);$("s2").textContent=Object.keys(DATA.Ankara).length;
render();
</script>
</body>
</html>
