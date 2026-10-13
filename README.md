<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Для Айгерим</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Marck+Script&family=Nunito:wght@700&display=swap" rel="stylesheet">
<style>
:root{
  box-sizing:border-box;
  padding-top:env(safe-area-inset-top,0px);
  padding-bottom:env(safe-area-inset-bottom,0px);
  --bg1:#ffe4ef;--bg2:#ffb8d4;--bg3:#ff8dbc;--bg4:#ffd3e6;
  --ink:#7d1646;--soft:#a8416f;--halo:rgba(255,255,255,.6);
  --card:rgba(255,255,255,.82);--veil:rgba(255,125,178,.35);
  --btn1:#ff7ab0;--btn2:#ff3d8b;--glow:rgba(255,61,139,.45);
  --blob1:#ff9cc7;--blob2:#fff0f6;
}
@media (prefers-color-scheme:dark){
  :root:not([data-theme="light"]){--bg1:#3d0f2c;--bg2:#6e1b4d;--bg3:#a8286f;--bg4:#51153a;--ink:#ffe4ef;--soft:#ffb8d4;--halo:rgba(255,80,160,.4);--card:rgba(58,14,40,.86);--veil:rgba(25,4,17,.6);--blob1:#e0488f;--blob2:#7a2459}
}
:root[data-theme="dark"]{--bg1:#3d0f2c;--bg2:#6e1b4d;--bg3:#a8286f;--bg4:#51153a;--ink:#ffe4ef;--soft:#ffb8d4;--halo:rgba(255,80,160,.4);--card:rgba(58,14,40,.86);--veil:rgba(25,4,17,.6);--blob1:#e0488f;--blob2:#7a2459}

html{height:100%;scroll-padding-top:env(safe-area-inset-top,0px)}
body{
  margin:0;height:100%;display:grid;place-items:center;color:var(--ink);
  font-family:'Nunito',system-ui,sans-serif;
  background:linear-gradient(135deg,var(--bg1),var(--bg2),var(--bg3),var(--bg4));
  background-size:300% 300%;animation:drift 18s ease-in-out infinite;
}
.blob{position:fixed;width:46vmax;height:46vmax;border-radius:50%;opacity:.7;pointer-events:none;background:radial-gradient(circle,var(--blob1),transparent 65%)}
.b1{top:-18vmax;left:-14vmax}
.b2{bottom:-20vmax;right:-16vmax;background:radial-gradient(circle,var(--blob2),transparent 65%)}

main{position:relative;z-index:1;text-align:center;padding:24px;animation:rise 1.2s ease both}
h1,.card p,footer{font-family:'Marck Script','Segoe Script','Brush Script MT',cursive;font-weight:400}
h1{font-size:clamp(2.5rem,9vw,4.8rem);line-height:1.15;margin:0 auto 40px;max-width:11em;text-wrap:balance;text-shadow:0 2px 24px var(--halo)}

.btn{
  font:700 1.05rem 'Nunito',system-ui,sans-serif;color:#fff;border:0;cursor:pointer;
  padding:14px 34px;border-radius:999px;
  background:linear-gradient(135deg,var(--btn1),var(--btn2));background-size:160% 160%;background-position:0% 50%;
  box-shadow:0 10px 28px var(--glow);
  transition:transform .35s ease,box-shadow .35s ease,background-position .6s ease;
}
.btn:hover{transform:translateY(-3px) scale(1.04);background-position:100% 50%;box-shadow:0 16px 36px var(--glow)}
.btn:active{transform:scale(.97)}
.btn:focus-visible{outline:3px solid var(--ink);outline-offset:4px}
#open{font-size:1.25rem;padding:18px 48px;animation:pulse 2.6s ease-in-out infinite}

.modal{
  position:fixed;inset:0;z-index:10;display:flex;align-items:center;justify-content:center;
  padding:calc(16px + env(safe-area-inset-top,0px)) 16px calc(16px + env(safe-area-inset-bottom,0px));
  background:var(--veil);backdrop-filter:blur(10px);-webkit-backdrop-filter:blur(10px);
  opacity:0;visibility:hidden;transition:opacity .5s ease,visibility 0s linear .5s;
}
.modal.open{opacity:1;visibility:visible;transition:opacity .5s ease}
.card{
  box-sizing:border-box;width:min(100%,560px);max-height:100%;overflow:auto;
  padding:28px 24px 24px;border-radius:28px;text-align:center;
  background:var(--card);box-shadow:0 30px 80px rgba(160,20,90,.35);
  transform:translateY(24px) scale(.94);transition:transform .6s cubic-bezier(.2,.9,.3,1.2);
}
.modal.open .card{transform:none}
.card p{font-size:clamp(1.6rem,5.6vw,2.1rem);line-height:1.35;margin:0 0 20px;color:var(--ink)}
.video{position:relative;aspect-ratio:16/9;border-radius:18px;overflow:hidden;background:#3a0d24;box-shadow:0 10px 30px rgba(120,20,70,.3)}
.video iframe{display:block;width:100%;height:100%;border:0}
.snd{position:absolute;top:12px;left:50%;translate:-50% 0;padding:8px 18px;font-size:.9rem}
.alt{display:inline-block;margin:14px 0 18px;font-size:.9rem;color:var(--soft);text-underline-offset:3px}
.alt:hover{color:var(--ink)}

footer{
  position:fixed;left:0;right:0;bottom:0;text-align:center;pointer-events:none;
  padding:20px 20px calc(24px + env(safe-area-inset-bottom,0px));
  font-size:1.7rem;color:var(--ink);
  opacity:0;transform:translateY(12px);transition:opacity 1.4s ease .4s,transform 1.4s ease .4s;
}
footer.show{opacity:1;transform:none}
footer span{display:block}
.wish{font-size:clamp(1.7rem,6vw,2.3rem);line-height:1.25;max-width:18em;margin:0 auto 10px;text-wrap:balance}
.by{font-size:1.5rem;opacity:0;transition:opacity 1.2s ease 1.6s}
footer.show .by{opacity:1}

@keyframes drift{0%,100%{background-position:0% 50%}50%{background-position:100% 50%}}
@keyframes rise{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:none}}
@keyframes pulse{0%,100%{box-shadow:0 10px 28px var(--glow),0 0 0 0 var(--glow)}60%{box-shadow:0 10px 28px var(--glow),0 0 0 22px transparent}}
@media (prefers-reduced-motion:reduce){*{animation:none!important;transition-duration:.01s!important;transition-delay:0s!important}}
</style>
</head>
<body>
<div class="blob b1"></div><div class="blob b2"></div>

<main>
  <h1>Айгерим, нажми на эту кнопку</h1>
  <button class="btn" id="open" type="button">Нажми</button>
</main>

<footer id="sign"><span class="wish">Никогда не поздно начать с чистого листа</span><span class="by">От Алимжана</span></footer>

<div class="modal" id="modal" role="dialog" aria-modal="true" aria-labelledby="msg" aria-hidden="true">
  <div class="card">
    <p id="msg">Ты не Селена Гомез, а я не Чарли Пут. Тогда почему мы больше не разговариваем?</p>
    <div class="video">
      <iframe id="yt" title="Видео на YouTube" allow="autoplay; encrypted-media; picture-in-picture; fullscreen" allowfullscreen referrerpolicy="strict-origin-when-cross-origin"></iframe>
      <button class="btn snd" id="snd" type="button" hidden>Включить звук</button>
    </div>
    <a class="alt" href="https://youtu.be/3AtDnEC4zak" target="_blank" rel="noopener">Видео не загрузилось? Открыть на YouTube</a><br>
    <button class="btn" id="close" type="button">Закрыть</button>
  </div>
</div>

<script>
const $ = id => document.getElementById(id);
const modal = $('modal'), yt = $('yt'), sign = $('sign'), openBtn = $('open'), closeBtn = $('close'), snd = $('snd');
const SRC = 'https://www.youtube.com/embed/3AtDnEC4zak?rel=0&playsinline=1&enablejsapi=1'
  + (location.origin.startsWith('http') ? '&origin=' + encodeURIComponent(location.origin) : '');
let loaded = false, state = null;
const isOpen = () => modal.classList.contains('open');
const post = obj => yt.contentWindow && yt.contentWindow.postMessage(JSON.stringify(obj), '*');
const send = (func, args = []) => post({event: 'command', func, args});

function resetPlayer() {           // плеер грузится заранее, чтобы видео стартовало мгновенно
  loaded = false; state = null; snd.hidden = true;
  yt.src = SRC;
}
yt.onload = () => { loaded = true; post({event: 'listening', id: 1, channel: 'widget'}); };
window.addEventListener('message', e => {
  if (e.source !== yt.contentWindow || typeof e.data !== 'string') return;
  try {
    const d = JSON.parse(e.data);
    if (d.event === 'onStateChange') state = d.info;
    else if (d.info && typeof d.info.playerState === 'number') state = d.info.playerState;
  } catch (_) {}
});
resetPlayer();

openBtn.onclick = () => {
  modal.classList.add('open');
  modal.setAttribute('aria-hidden', 'false');
  closeBtn.focus({preventScroll: true});
  if (!loaded) { yt.src = SRC + '&autoplay=1'; return; }
  [0, 300, 900].forEach(t => setTimeout(() => isOpen() && send('playVideo'), t));
  setTimeout(() => {   // браузер не разрешил звук: запускаем без звука
    if (isOpen() && [-1, 2, 5].includes(state)) { send('mute'); send('playVideo'); snd.hidden = false; }
  }, 2200);
};
snd.onclick = () => { send('unMute'); send('playVideo'); snd.hidden = true; };

function closeModal() {
  if (!modal.classList.contains('open')) return;
  modal.classList.remove('open');
  modal.setAttribute('aria-hidden', 'true');
  resetPlayer();          // останавливает видео и звук
  sign.classList.add('show');      // подпись появляется после закрытия
  openBtn.focus({preventScroll: true});
}

closeBtn.onclick = closeModal;
modal.addEventListener('click', e => { if (e.target === modal) closeModal(); });
document.addEventListener('keydown', e => { if (e.key === 'Escape') closeModal(); });
</script>
</body>
</html>
