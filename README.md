<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title> Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<style>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&family=Playfair+Display:wght@400;700&display=swap');

  :root{
    --bg:#07080a; --card:#0e1114; --muted:#9ca3a8; --accent1:#7fd6c2; --accent2:#9a88f7;
    --glass: rgba(255,255,255,0.04);
  }
  *{box-sizing:border-box}
  body{margin:0; font-family:Inter,system-ui; background: linear-gradient(180deg, #060607 0%, #0b0c0f 100%); color:#e7e7e7; -webkit-font-smoothing:antialiased}
  header{min-height:72vh; display:grid; grid-template-columns: 1fr 420px; gap:36px; align-items:center; padding:60px 6%; position:relative}
  @media (max-width:900px){ header{grid-template-columns:1fr; padding:40px 6%; min-height:60vh} }

  .hero-left h1{ font-family:"Playfair Display", serif; font-size:48px; margin:0; background:linear-gradient(90deg,var(--accent1),var(--accent2)); -webkit-background-clip:text; color:transparent}
  .hero-left p{color:var(--muted); margin-top:12px; font-size:16px; max-width:60ch}
  .cta{margin-top:20px; display:flex; gap:12px; align-items:center}
  .btn{padding:12px 16px; border-radius:12px; border:1px solid rgba(255,255,255,0.05); background:rgba(255,255,255,0.02); color:#e9eef0; cursor:pointer; font-weight:600}
  .btn.primary{background:linear-gradient(90deg,var(--accent1),var(--accent2)); color:#071117;}
  .profile-card{background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent); border-radius:16px; padding:18px; border:1px solid rgba(255,255,255,0.04); height:fit-content;}

  .meta{display:flex; gap:12px; align-items:center}
  .avatar{width:80px;height:80px;border-radius:12px; background:linear-gradient(90deg,var(--accent1),var(--accent2)); display:flex;align-items:center;justify-content:center;font-weight:700;color:#051018}
  .skills{display:flex;flex-wrap:wrap;gap:8px;margin-top:12px}
  .chip{padding:8px 10px;border-radius:10px;background:rgba(255,255,255,0.03);font-size:13px;color:var(--muted)}

  .section{padding:60px 6%}
  .projects-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
  @media (max-width:980px){ .projects-grid{grid-template-columns:repeat(2,1fr)}}
  @media (max-width:600px){ .projects-grid{grid-template-columns:1fr} }

  .project{
    border-radius:14px; overflow:hidden; position:relative; cursor:pointer; min-height:180px;
    background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent); border:1px solid rgba(255,255,255,0.03);
    transition: transform .36s cubic-bezier(.2,.9,.3,1), box-shadow .36s;
    display:flex;flex-direction:column; justify-content:space-between;
  }
  .project:hover{transform:translateY(-8px); box-shadow:0 18px 50px rgba(2,4,7,0.7)}
  .project .meta{padding:16px}
  .project .thumb{height:160px; background-size:cover; background-position:center; filter:brightness(0.9)}

  
  .modal{position:fixed; inset:0; background:rgba(2,4,7,0.85); display:none; align-items:center; justify-content:center; z-index:1000}
  .modal-card{width:min(920px,95%); background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent); border-radius:12px; padding:18px; border:1px solid rgba(255,255,255,0.04)}
  .modal-close{position:absolute; right:28px; top:22px; font-size:26px; cursor:pointer; color:#dcdcdc}


  footer{padding:36px 6%; text-align:center; color:var(--muted)}

  
  .reveal{opacity:0; transform:translateY(18px); transition: all .6s cubic-bezier(.2,.9,.3,1)}
  .reveal.show{opacity:1; transform:none}
</style>
</head>
<body>

  <header>
    <div class="hero-left">
      <h1 class="reveal">Hi, I'm Aimen. I craft interfaces that feel cinematic.</h1>
      <p class="reveal" style="transition-delay:.08s">I build beautiful, high-performance frontends with a focus on typography, color and motion. Below are a selection of projects you can demo.</p>
      <div class="cta reveal" style="transition-delay:.12s">
        <button class="btn primary" id="view-projects">View Projects</button>
        <a class="btn" href="#" onclick="downloadResume()">Download Resume</a>
      </div>
    </div>

    <aside class="profile-card">
      <div class="meta">
        <div class="avatar">AS</div>
        <div>
          <div style="font-weight:700">Aimen Shahidd</div>
          <div class="small" style="color:var(--muted)">Frontend Developer • UI/UX Enthusiast</div>
        </div>
      </div>

      <div class="skills">
        <div class="chip">HTML</div><div class="chip">CSS</div><div class="chip">JavaScript</div>
        <div class="chip">React</div><div class="chip">Accessibility</div><div class="chip">Motion</div>
      </div>

      <div style="margin-top:12px;color:var(--muted);font-size:13px">Location: Pakistan · Open to Remote</div>
    </aside>
  </header>

  <section class="section projects">
    <h2 style="margin:0 0 18px 6%">Selected Projects</h2>
    <div class="projects-grid" id="projects">
   
      <article class="project" data-title="Photo Gallery" data-desc="Advanced image gallery with filters, masonry layout, lightbox & animations." data-img="https://images.unsplash.com/photo-1501785888041-af3ef285b470?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=4b8b2f1b2c8f">
        <div class="thumb" style="background-image:url('https://images.unsplash.com/photo-1501785888041-af3ef285b470?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=4b8b2f1b2c8f')"></div>
        <div class="meta"><div style="font-weight:700">Photo Gallery</div><div class="small">UX, JS, Responsive</div></div>
      </article>

      <article class="project" data-title="CarTech Landing" data-desc="High-conversion landing with product testing tone & cinematic hero." data-img="https://images.unsplash.com/photo-1502877338535-766e1452684a?q=80&w=1200&auto=format&fit=crop">
        <div class="thumb" style="background-image:url('https://images.unsplash.com/photo-1502877338535-766e1452684a?q=80&w=1200&auto=format&fit=crop')"></div>
        <div class="meta"><div style="font-weight:700">CarTech Landing</div><div class="small">Marketing, Design</div></div>
      </article>

      <article class="project" data-title="Music Player" data-desc="Custom JS music player with playlist, progress & visualizer." data-img="https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4?q=80&w=1200&auto=format&fit=crop">
        <div class="thumb" style="background-image:url('https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4?q=80&w=1200&auto=format&fit=crop')"></div>
        <div class="meta"><div style="font-weight:700">Music Player</div><div class="small">Audio, UX</div></div>
      </article>
     
      <article class="project" data-title="Portfolio UI" data-desc="Animated portfolio with dark theme & perfect typography." data-img="https://images.unsplash.com/photo-1520975698513-4b6a8b4f0bbc?q=80&w=1200&auto=format&fit=crop">
        <div class="thumb" style="background-image:url('https://images.unsplash.com/photo-1520975698513-4b6a8b4f0bbc?q=80&w=1200&auto=format&fit=crop')"></div>
        <div class="meta"><div style="font-weight:700">Portfolio UI</div><div class="small">Design, Motion</div></div>
      </article>

      <article class="project" data-title="Calculator Widget" data-desc="Accessible calculator widget with expression history." data-img="https://images.unsplash.com/photo-1498050108023-c5249f4df085?q=80&w=1200&auto=format&fit=crop">
        <div class="thumb" style="background-image:url('https://images.unsplash.com/photo-1498050108023-c5249f4df085?q=80&w=1200&auto=format&fit=crop')"></div>
        <div class="meta"><div style="font-weight:700">Calculator Widget</div><div class="small">JS, UX</div></div>
      </article>

      <article class="project" data-title="Interactive Showcase" data-desc="3D card interactions, filters and staggered reveal." data-img="https://images.unsplash.com/photo-1506634572410-7b8f58ff2d1a?q=80&w=1200&auto=format&fit=crop">
        <div class="thumb" style="background-image:url('https://images.unsplash.com/photo-1506634572410-7b8f58ff2d1a?q=80&w=1200&auto=format&fit=crop')"></div>
        <div class="meta"><div style="font-weight:700">Interactive Showcase</div><div class="small">JS, CSS</div></div>
      </article>
    </div>
  </section>

 
  <div class="modal" id="modal" aria-hidden="true">
    <div class="modal-card" role="dialog" aria-modal="true" aria-labelledby="mTitle">
      <div style="display:flex;gap:16px;align-items:center">
        <img id="mImg" src="" alt="" style="width:120px;height:80px;border-radius:8px;object-fit:cover">
        <div>
          <h3 id="mTitle" style="margin:0"></h3>
          <p id="mDesc" style="color:var(--muted);margin-top:8px"></p>
        </div>
      </div>
      <p style="margin-top:12px;color:var(--muted)">Technologies: HTML · CSS · JS. Role: Design + Implementation</p>
      <div style="margin-top:14px; display:flex; gap:10px">
        <a class="btn primary" href="#" onclick="closeModal()">Open Demo</a>
        <a class="btn" href="#" onclick="closeModal()">View Code</a>
      </div>
      <div class="modal-close" onclick="closeModal()">✕</div>
    </div>
  </div>

  <footer>© <strong>Aimen Shahidd</strong> • Crafted for CodeAlpha Internship</footer>

<script>
  
  document.querySelectorAll('.reveal').forEach((el,i)=> setTimeout(()=>el.classList.add('show'), 120*i));


  const projects = document.querySelectorAll('.project');
  const modal = document.getElementById('modal'), mTitle = document.getElementById('mTitle'),
        mDesc = document.getElementById('mDesc'), mImg = document.getElementById('mImg');

  projects.forEach(p=>{
    p.addEventListener('click', ()=>{
      mTitle.textContent = p.dataset.title;
      mDesc.textContent = p.dataset.desc;
      mImg.src = p.dataset.img;
      modal.style.display = 'flex';
      modal.setAttribute('aria-hidden','false');
    });
  });
  function closeModal(){ modal.style.display='none'; modal.setAttribute('aria-hidden','true') }
  window.addEventListener('keydown', e => { if(e.key==='Escape') closeModal() });

  
  function downloadResume(){
  
    const text = `Aimen Shahidd - Frontend Developer\n\nSkills: HTML,CSS,JS,React\n\nPortfolio: GitHub Link`;
    const blob = new Blob([text], {type:'text/plain'});
    const a = document.createElement('a');
    a.href = URL.createObjectURL(blob);
    a.download = 'Aimen-Shahidd-Resume.txt';
    a.click();
    URL.revokeObjectURL(a.href);
  }

  
  document.getElementById('view-projects').addEventListener('click', ()=> {
    document.querySelector('.projects').scrollIntoView({behavior:'smooth'});
  });
</script>
</body>
</html>
