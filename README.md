<!-- ============================================================================
     GITHUB PROFILE README — "NETWORK <> CODE"
     ----------------------------------------------------------------------------
     QUICK START (baca ini dulu!):
     1. Buat repo PUBLIC dengan nama yang SAMA PERSIS dengan username GitHub kamu
        (kalau belum ada). File ini taruh di root repo itu sebagai README.md.
     2. Ganti SEMUA token di bawah ini (bisa pakai Ctrl+H / Find & Replace):
          mhdayatz  → username GitHub kamu  (paling banyak dipakai)
          Muhammad Hidayat             → nama kamu (muncul di banner)
          YOUR_LINKEDIN         → id LinkedIn kamu
          YOUR_INSTAGRAM        → username Instagram kamu
          YOUR_TELEGRAM         → username Telegram kamu
          YOUR_PORTFOLIO_URL    → URL website/portfolio kamu
          your.email@example.com→ email kamu
          project-a .. d       → nama repo project kamu (section Featured Projects)
          URL_DEMO              → link live demo project
          URL_SERTIFIKAT        → link verifikasi sertifikat
     3. (Opsional) Aktifkan animasi "snake" — panduan lengkap ada di KOMENTAR
        PALING BAWAH file ini.
     4. Cek hasilnya di github.com/mhdayatz (reload / hard-refresh
        Ctrl+F5 kalau gambar belum muncul karena cache).

     CATATAN PENTING TENTANG ANIMASI:
     GitHub meng-STRIP CSS <style>/@keyframes di dalam README, tapi MEMPERTAHANKAN
     animasi SMIL (<animate>/<animateTransform>). Makanya banner & divider di
     bawah memakai SMIL, bukan CSS. Jangan ubah teknik ini kalau tidak mau
     animasinya mati.
     ============================================================================ -->

<!-- ============================================================ -->
<!-- 1. HEADER BANNER — SVG custom tema "network topology + code"  -->
<!--    (animasi SMIL: pulse node, packet berjalan, terminal float -->
<!--     blinking cursor. Warna bisa diubah langsung di atribut)   -->
<!-- ============================================================ -->
<div align="center">
  <div style="max-width:1000px;margin:0 auto;border:1px solid rgba(110,130,170,.25);border-radius:18px;overflow:hidden;background:#0b1220">
    <svg viewBox="0 0 1000 340" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Network and Code banner" style="width:100%;height:auto;display:block">
      <defs>
        <linearGradient id="pbBg" x1="0" y1="0" x2="1" y2="1">
          <stop offset="0" stop-color="#0b1220"/>
          <stop offset="1" stop-color="#101a2e"/>
        </linearGradient>
        <linearGradient id="pbTxt" x1="0" y1="0" x2="1" y2="0">
          <stop offset="0" stop-color="#22d3ee"/>
          <stop offset="1" stop-color="#8b5cf6"/>
        </linearGradient>
        <pattern id="pbGrid" width="42" height="42" patternUnits="userSpaceOnUse">
          <path d="M42 0H0V42" fill="none" stroke="#223352" stroke-width="1" opacity="0.35"/>
        </pattern>
      </defs>
      <rect width="1000" height="340" fill="url(#pbBg)"/>
      <rect width="1000" height="340" fill="url(#pbGrid)"/>

      <!-- ==== jaringan mesh (node topology) ==== -->
      <g stroke="#2c3e5e" stroke-width="1.5" opacity="0.9">
        <line x1="90" y1="252" x2="205" y2="196"/>
        <line x1="205" y1="196" x2="330" y2="236"/>
        <line x1="330" y1="236" x2="268" y2="300"/>
        <line x1="205" y1="196" x2="425" y2="186"/>
        <line x1="425" y1="186" x2="535" y2="244"/>
        <line x1="535" y1="244" x2="610" y2="196"/>
        <line x1="330" y1="236" x2="425" y2="186"/>
        <line x1="268" y1="300" x2="535" y2="244"/>
      </g>

      <!-- node statis -->
      <g fill="#22d3ee">
        <circle cx="90" cy="252" r="6"/>
        <circle cx="205" cy="196" r="8"/>
        <circle cx="330" cy="236" r="6"/>
        <circle cx="425" cy="186" r="7"/>
        <circle cx="610" cy="196" r="6"/>
      </g>
      <g fill="#8b5cf6">
        <circle cx="268" cy="300" r="5"/>
        <circle cx="535" cy="244" r="5"/>
      </g>

      <!-- ring pulse di node utama -->
      <circle cx="205" cy="196" r="8" fill="none" stroke="#22d3ee" stroke-width="2">
        <animate attributeName="r" values="8;22" dur="2s" repeatCount="indefinite"/>
        <animate attributeName="opacity" values="0.8;0" dur="2s" repeatCount="indefinite"/>
      </circle>
      <circle cx="425" cy="186" r="7" fill="none" stroke="#8b5cf6" stroke-width="2">
        <animate attributeName="r" values="7;20" dur="2.4s" begin="0.6s" repeatCount="indefinite"/>
        <animate attributeName="opacity" values="0.8;0" dur="2.4s" begin="0.6s" repeatCount="indefinite"/>
      </circle>

      <!-- titik satelit berkedip -->
      <circle cx="90" cy="252" r="3" fill="#fbbf24">
        <animate attributeName="opacity" values="1;0.15;1" dur="2.2s" begin="0.4s" repeatCount="indefinite"/>
      </circle>
      <circle cx="268" cy="300" r="3" fill="#fbbf24">
        <animate attributeName="opacity" values="1;0.15;1" dur="2.2s" begin="1.1s" repeatCount="indefinite"/>
      </circle>
      <circle cx="610" cy="196" r="3" fill="#fbbf24">
        <animate attributeName="opacity" values="1;0.15;1" dur="2.2s" begin="1.8s" repeatCount="indefinite"/>
      </circle>

      <!-- packet berjalan di jalur jaringan -->
      <circle cx="90" cy="252" r="4" fill="#fbbf24">
        <animate attributeName="cx" values="90;205;330" dur="4.5s" repeatCount="indefinite"/>
        <animate attributeName="cy" values="252;196;236" dur="4.5s" repeatCount="indefinite"/>
      </circle>
      <circle cx="425" cy="186" r="4" fill="#f472b6">
        <animate attributeName="cx" values="425;535;610" dur="3.8s" begin="1s" repeatCount="indefinite"/>
        <animate attributeName="cy" values="186;244;196" dur="3.8s" begin="1s" repeatCount="indefinite"/>
      </circle>

      <!-- ==== terminal window (melayang halus) ==== -->
      <g>
        <animateTransform attributeName="transform" type="translate" values="0 0;0 -7;0 0" dur="7s" repeatCount="indefinite"/>
        <rect x="630" y="82" width="300" height="178" rx="14" fill="#0d1526" stroke="#2c3e5e" stroke-width="1.5"/>
        <circle cx="656" cy="108" r="5" fill="#f87171"/>
        <circle cx="676" cy="108" r="5" fill="#fbbf24"/>
        <circle cx="696" cy="108" r="5" fill="#34d399"/>
        <text x="800" y="113" text-anchor="middle" font-size="11" font-family="'Fira Code',Consolas,monospace" fill="#64748b" letter-spacing="1">terminal — /home/engineer</text>
        <text x="650" y="146" font-size="13" font-family="'Fira Code',Consolas,monospace" fill="#94a3b8"><tspan fill="#fbbf24">$ </tspan>ping 8.8.8.8</text>
        <text x="650" y="166" font-size="12" font-family="'Fira Code',Consolas,monospace" fill="#64748b">64 bytes from 8.8.8.8: ttl=118 time=4.2 ms</text>
        <text x="650" y="190" font-size="13" font-family="'Fira Code',Consolas,monospace" fill="#94a3b8"><tspan fill="#fbbf24">$ </tspan>npm run deploy</text>
        <text x="650" y="210" font-size="12" font-family="'Fira Code',Consolas,monospace" fill="#22d3ee">deployed → production</text>
        <text x="650" y="234" font-size="13" font-family="'Fira Code',Consolas,monospace" fill="#94a3b8"><tspan fill="#fbbf24">$ </tspan>whoami</text>
        <text x="650" y="252" font-size="12" font-family="'Fira Code',Consolas,monospace" fill="#a78bfa">network · software engineer</text>
        <rect x="716" y="241" width="8" height="13" fill="#22d3ee">
          <animate attributeName="opacity" values="1;0;1" dur="1.1s" repeatCount="indefinite"/>
        </rect>
      </g>

      <!-- ==== teks utama ==== -->
      <text x="48" y="58" font-size="12" letter-spacing="4" font-family="'Fira Code',Consolas,monospace" fill="#f59e0b">// NETWORK &lt;=&gt; CODE</text>
      <text x="46" y="120" font-size="44" font-weight="700" font-family="'Segoe UI',Verdana,sans-serif" fill="url(#pbTxt)">Hi, I'm Muhammad Hidayat</text>
      <text x="48" y="154" font-size="17" font-family="'Segoe UI',Verdana,sans-serif" fill="#e2e8f0">Network Engineer · Full-Stack Developer</text>
      <text x="48" y="180" font-size="13.5" font-family="'Fira Code',Consolas,monospace" fill="#8b9bb4">connecting packets &amp; pixels — from fiber optics to full-stack code</text>
    </svg>
  </div>
</div>

<!-- ============================================================ -->
<!-- 2. ANIMATED TYPING TEXT (readme-typing-svg, dual theme)       -->
<!--    Ganti isi `lines=` kalau mau; pisahkan baris dengan `;`   -->
<!-- ============================================================ -->
<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=23&duration=2600&pause=700&color=22D3EE&center=true&vCenter=true&width=920&height=44&lines=Network%20Engineer%20%26%20Software%20Engineer;MikroTik%20%C2%B7%20Cisco%20%C2%B7%20Fiber%20Optic;React%20%C2%B7%20Laravel%20%C2%B7%20Node.js%20%C2%B7%20TypeScript;Linux%20Server%20%26%20Infrastructure;Building%20with%20AI%20Coding%20Agents"/>
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=23&duration=2600&pause=700&color=0E7490&center=true&vCenter=true&width=920&height=44&lines=Network%20Engineer%20%26%20Software%20Engineer;MikroTik%20%C2%B7%20Cisco%20%C2%B7%20Fiber%20Optic;React%20%C2%B7%20Laravel%20%C2%B7%20Node.js%20%C2%B7%20TypeScript;Linux%20Server%20%26%20Infrastructure;Building%20with%20AI%20Coding%20Agents" alt="Typing animation of my roles" style="width:100%;max-width:920px;height:auto"/>
  </picture>
  <br/>
  <b>Connecting packets and pixels</b> — from fiber optic splicing to full-stack code.
</div>

<!-- divider: network node path -->
<svg viewBox="0 0 1000 26" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Section divider" style="width:100%;height:26px;display:block">
  <line x1="0" y1="13" x2="462" y2="13" stroke="#0ea5e9" stroke-width="2" stroke-linecap="round" opacity="0.7"/>
  <line x1="538" y1="13" x2="1000" y2="13" stroke="#8b5cf6" stroke-width="2" stroke-linecap="round" opacity="0.7"/>
  <circle cx="500" cy="13" r="6" fill="#f59e0b">
    <animate attributeName="opacity" values="1;0.3;1" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="500" cy="13" r="12" fill="none" stroke="#f59e0b" stroke-width="1.5">
    <animate attributeName="r" values="6;14" dur="2s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.9;0" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="0" cy="13" r="3" fill="#0ea5e9">
    <animate attributeName="cx" values="0;462" dur="5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="1;1;0" keyTimes="0;0.85;1" dur="5s" repeatCount="indefinite"/>
  </circle>
  <circle cx="1000" cy="13" r="3" fill="#8b5cf6">
    <animate attributeName="cx" values="1000;538" dur="5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="1;1;0" keyTimes="0;0.85;1" dur="5s" repeatCount="indefinite"/>
  </circle>
</svg>

<!-- ============================================================ -->
<!-- 3. ABOUT ME — persona dual identity                           -->
<!-- ============================================================ -->
## ▸ About Me

<sub>Network engineer by training, software engineer by obsession — full-stack by choice.</sub>

Hi! I'm **Muhammad Hidayat** — an IT generalist with a dual identity. On one side, I'm a **network & infrastructure engineer**: MikroTik and Cisco routing, fiber optic installation and termination (splicing + OTDR verification), Linux server administration, and hands-on troubleshooting of whatever breaks. On the other side, I'm a **full-stack software engineer**: designing and shipping web applications with modern frameworks — and increasingly building them with AI coding agents in my daily workflow.

<!-- Edit baris [CODE] di bawah sesuai stack kamu yang sebenarnya -->
```
[NETWORK]  MikroTik RouterOS · Cisco IOS · Fiber Optic (SPL & OTDR) · VLAN/VPN/MPLS · Linux · Troubleshooting
[CODE]     React · Next.js · TypeScript · Node.js · Laravel · PHP · MySQL · Tailwind
[HARDWARE] PC assembly & maintenance · OS deployment · Drivers & peripherals · On-site IT support
```

<!-- divider: code brackets -->
<svg viewBox="0 0 1000 26" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Section divider" style="width:100%;height:26px;display:block">
  <line x1="0" y1="13" x2="430" y2="13" stroke="#0ea5e9" stroke-width="2" opacity="0.5" stroke-linecap="round"/>
  <line x1="570" y1="13" x2="1000" y2="13" stroke="#8b5cf6" stroke-width="2" opacity="0.5" stroke-linecap="round"/>
  <text x="500" y="19" text-anchor="middle" font-size="16" font-family="'Fira Code',Consolas,monospace" font-weight="700" fill="#f59e0b">&lt;/&gt;
    <animate attributeName="opacity" values="1;0.4;1" dur="3s" repeatCount="indefinite"/>
  </text>
  <circle cx="430" cy="13" r="2.5" fill="#0ea5e9">
    <animate attributeName="opacity" values="1;0.3;1" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="570" cy="13" r="2.5" fill="#8b5cf6">
    <animate attributeName="opacity" values="0.3;1;0.3" dur="2s" repeatCount="indefinite"/>
  </circle>
</svg>

<!-- ============================================================ -->
<!-- 4. TECH STACK — 2 grup besar                                 -->
<!-- ============================================================ -->
## ▸ Tech Stack

### Group 1 — Infrastructure & Networking

<!-- ikon: skillicons.dev (theme=dark utk dark mode, theme=light utk light mode) -->
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://skillicons.dev/icons?i=linux,ubuntu,debian,windows,docker,kubernetes,nginx,bash,powershell,ansible,prometheus,grafana,raspberrypi&perline=13&theme=dark"/>
  <img src="https://skillicons.dev/icons?i=linux,ubuntu,debian,windows,docker,kubernetes,nginx,bash,powershell,ansible,prometheus,grafana,raspberrypi&perline=13&theme=light" alt="Infrastructure and networking tools" style="max-width:100%;height:auto"/>
</picture>

<!-- badge teks untuk hal yang tidak punya ikon (MikroTik, Cisco, fiber, dll) -->
<div align="center">
  <img src="https://img.shields.io/badge/-MikroTik%20RouterOS-0EA5E9?style=flat-square&labelColor=0F172A" alt="MikroTik RouterOS"/>
  <img src="https://img.shields.io/badge/-Cisco%20IOS-3B82F6?style=flat-square&labelColor=0F172A" alt="Cisco IOS"/>
  <img src="https://img.shields.io/badge/-Fiber%20Optic%20%C2%B7%20SPL%20%26%20OTDR-059669?style=flat-square&labelColor=0F172A" alt="Fiber Optic splicing and OTDR"/>
  <img src="https://img.shields.io/badge/-VLAN%20%C2%B7%20VPN%20%C2%B7%20MPLS-94A3B8?style=flat-square&labelColor=0F172A" alt="VLAN VPN MPLS"/>
  <img src="https://img.shields.io/badge/-Linux%20Server-84CC16?style=flat-square&labelColor=0F172A" alt="Linux Server"/>
  <img src="https://img.shields.io/badge/-Network%20Troubleshooting-EF4444?style=flat-square&labelColor=0F172A" alt="Network Troubleshooting"/>
</div>

### Group 2 — Software Development

<!-- EDIT: sesuaikan daftar ikon dengan stack kamu. Daftar ikon valid:
     skillicons.dev/icons?i=... → react,nextjs,ts,js,php,laravel,nodejs,express,html,
     css,tailwind,mysql,postgres,mongodb,redis,git,github,vscode,postman,python,figma,dll -->
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://skillicons.dev/icons?i=react,nextjs,ts,js,php,laravel,nodejs,html,css,tailwind,mysql,postgres,mongodb,redis,git,github,vscode,postman,python,figma&perline=16&theme=dark"/>
  <img src="https://skillicons.dev/icons?i=react,nextjs,ts,js,php,laravel,nodejs,html,css,tailwind,mysql,postgres,mongodb,redis,git,github,vscode,postman,python,figma&perline=16&theme=light" alt="Software development tools" style="max-width:100%;height:auto"/>
</picture>

<div align="center">
  <img src="https://img.shields.io/badge/-React%20%26%20Next.js-61DAFB?style=flat-square&labelColor=0F172A" alt="React and Next.js"/>
  <img src="https://img.shields.io/badge/-Laravel%20%26%20PHP-FF2D20?style=flat-square&labelColor=0F172A" alt="Laravel and PHP"/>
  <img src="https://img.shields.io/badge/-Node.js%20%26%20TypeScript-3178C6?style=flat-square&labelColor=0F172A" alt="Node.js and TypeScript"/>
  <img src="https://img.shields.io/badge/-MySQL%20%C2%B7%20PostgreSQL-4479A1?style=flat-square&labelColor=0F172A" alt="MySQL and PostgreSQL"/>
  <img src="https://img.shields.io/badge/-Tailwind%20CSS-06B6D4?style=flat-square&labelColor=0F172A" alt="Tailwind CSS"/>
  <img src="https://img.shields.io/badge/-REST%20API%20%C2%B7%20JWT-10B981?style=flat-square&labelColor=0F172A" alt="REST API and JWT"/>
  <img src="https://img.shields.io/badge/-Git%20%C2%B7%20Docker-2496ED?style=flat-square&labelColor=0F172A" alt="Git and Docker"/>
  <img src="https://img.shields.io/badge/-AI%20Coding%20Agents-8B5CF6?style=flat-square&labelColor=0F172A" alt="AI Coding Agents"/>
</div>

<!-- divider: network node path -->
<svg viewBox="0 0 1000 26" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Section divider" style="width:100%;height:26px;display:block">
  <line x1="0" y1="13" x2="462" y2="13" stroke="#0ea5e9" stroke-width="2" stroke-linecap="round" opacity="0.7"/>
  <line x1="538" y1="13" x2="1000" y2="13" stroke="#8b5cf6" stroke-width="2" stroke-linecap="round" opacity="0.7"/>
  <circle cx="500" cy="13" r="6" fill="#f59e0b">
    <animate attributeName="opacity" values="1;0.3;1" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="500" cy="13" r="12" fill="none" stroke="#f59e0b" stroke-width="1.5">
    <animate attributeName="r" values="6;14" dur="2s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.9;0" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="0" cy="13" r="3" fill="#0ea5e9">
    <animate attributeName="cx" values="0;462" dur="5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="1;1;0" keyTimes="0;0.85;1" dur="5s" repeatCount="indefinite"/>
  </circle>
  <circle cx="1000" cy="13" r="3" fill="#8b5cf6">
    <animate attributeName="cx" values="1000;538" dur="5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="1;1;0" keyTimes="0;0.85;1" dur="5s" repeatCount="indefinite"/>
  </circle>
</svg>

<!-- ============================================================ -->
<!-- 5. CURRENTLY WORKING ON / EXPLORING (update manual berkala)   -->
<!-- ============================================================ -->
## ▸ Currently Working On

- Developing **dayattt-project** — my first project, terus dikembangkan ([repository](https://github.com/mhdayatz/dayattt-project))
- Building **catatanpribadi** — a personal notes app written in TypeScript ([repository](https://github.com/mhdayatz/catatanpribadi))
- Automating network operations — router config management & monitoring with bash/Python scripts, assisted by AI coding agents
- [Tambahkan item lain di sini — section ini memang untuk kamu update manual]

## ▸ Currently Exploring

- Kubernetes & container orchestration (Docker → K8s)
- Cloud platforms: AWS / GCP / Alibaba Cloud
- Observability & monitoring: Prometheus + Grafana stack
- AI coding agents & LLM-assisted engineering workflows

<!-- divider: code brackets -->
<svg viewBox="0 0 1000 26" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Section divider" style="width:100%;height:26px;display:block">
  <line x1="0" y1="13" x2="430" y2="13" stroke="#0ea5e9" stroke-width="2" opacity="0.5" stroke-linecap="round"/>
  <line x1="570" y1="13" x2="1000" y2="13" stroke="#8b5cf6" stroke-width="2" opacity="0.5" stroke-linecap="round"/>
  <text x="500" y="19" text-anchor="middle" font-size="16" font-family="'Fira Code',Consolas,monospace" font-weight="700" fill="#f59e0b">&lt;/&gt;
    <animate attributeName="opacity" values="1;0.4;1" dur="3s" repeatCount="indefinite"/>
  </text>
  <circle cx="430" cy="13" r="2.5" fill="#0ea5e9">
    <animate attributeName="opacity" values="1;0.3;1" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="570" cy="13" r="2.5" fill="#8b5cf6">
    <animate attributeName="opacity" values="0.3;1;0.3" dur="2s" repeatCount="indefinite"/>
  </circle>
</svg>

<!-- ============================================================ -->
<!-- 6. FEATURED PROJECTS — kartu custom (bukan pinned default)    -->
<!--    Ganti: nama repo, deskripsi, badge stack, link repo/demo   -->
<!-- ============================================================ -->
## ▸ Featured Projects

<div align="center">
<table style="border-collapse:separate;border-spacing:14px">
  <tr>
    <td style="border:1px solid rgba(110,130,170,.3);border-radius:14px;padding:16px 20px;width:50%;background:rgba(120,140,180,.05);vertical-align:top">
      <a href="https://github.com/mhdayatz/dayattt-project"><b>dayattt-project</b></a><br/>
      <sub>My first project — dimulai dari nol dan terus dikembangkan.</sub><br/><br/>
      <a href="https://github.com/mhdayatz/dayattt-project"><img src="https://img.shields.io/github/stars/mhdayatz/dayattt-project?style=flat-square&label=stars&color=8B5CF6&logo=star&logoColor=8B5CF6" alt="Stars"/></a>
      <img src="https://img.shields.io/badge/-First%20Project-8B5CF6?style=flat-square&labelColor=0F172A" alt="First Project"/><br/>
      <sub><a href="https://github.com/mhdayatz/dayattt-project">Repository</a></sub>
    </td>
    <td style="border:1px solid rgba(110,130,170,.3);border-radius:14px;padding:16px 20px;width:50%;background:rgba(120,140,180,.05);vertical-align:top">
      <a href="https://github.com/mhdayatz/catatanpribadi"><b>catatanpribadi</b></a><br/>
      <sub>Personal notes app — written in TypeScript.</sub><br/><br/>
      <a href="https://github.com/mhdayatz/catatanpribadi"><img src="https://img.shields.io/github/stars/mhdayatz/catatanpribadi?style=flat-square&label=stars&color=8B5CF6&logo=star&logoColor=8B5CF6" alt="Stars"/></a>
      <img src="https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&labelColor=0F172A" alt="TypeScript"/><br/>
      <sub><a href="https://github.com/mhdayatz/catatanpribadi">Repository</a></sub>
    </td>
  </tr>
  <tr>
    <td style="border:1px solid rgba(110,130,170,.3);border-radius:14px;padding:16px 20px;width:50%;background:rgba(120,140,180,.05);vertical-align:top">
      <a href="https://github.com/mhdayatz/tes"><b>tes</b></a><br/>
      <sub>Small experiment / test repository.</sub><br/><br/>
      <a href="https://github.com/mhdayatz/tes"><img src="https://img.shields.io/github/stars/mhdayatz/tes?style=flat-square&label=stars&color=8B5CF6&logo=star&logoColor=8B5CF6" alt="Stars"/></a>
      <img src="https://img.shields.io/badge/-Experiment-10B981?style=flat-square&labelColor=0F172A" alt="Experiment"/><br/>
      <sub><a href="https://github.com/mhdayatz/tes">Repository</a></sub>
    </td>
    <td style="border:1px solid rgba(110,130,170,.3);border-radius:14px;padding:16px 20px;width:50%;background:rgba(120,140,180,.05);vertical-align:top">
      <a href="https://github.com/mhdayatz?tab=repositories"><b>And many more…</b></a><br/>
      <sub>Explore all my public repositories on GitHub.</sub><br/><br/>
      <a href="https://github.com/mhdayatz?tab=repositories"><img src="https://img.shields.io/badge/-View%20All%20Repos-0EA5E9?style=flat-square&labelColor=0F172A" alt="View all repos"/></a><br/>
      <sub><a href="https://github.com/mhdayatz?tab=repositories">All repositories</a></sub>
    </td>
  </tr>
</table>
</div>

<!-- divider: network node path -->
<svg viewBox="0 0 1000 26" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Section divider" style="width:100%;height:26px;display:block">
  <line x1="0" y1="13" x2="462" y2="13" stroke="#0ea5e9" stroke-width="2" stroke-linecap="round" opacity="0.7"/>
  <line x1="538" y1="13" x2="1000" y2="13" stroke="#8b5cf6" stroke-width="2" stroke-linecap="round" opacity="0.7"/>
  <circle cx="500" cy="13" r="6" fill="#f59e0b">
    <animate attributeName="opacity" values="1;0.3;1" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="500" cy="13" r="12" fill="none" stroke="#f59e0b" stroke-width="1.5">
    <animate attributeName="r" values="6;14" dur="2s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.9;0" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="0" cy="13" r="3" fill="#0ea5e9">
    <animate attributeName="cx" values="0;462" dur="5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="1;1;0" keyTimes="0;0.85;1" dur="5s" repeatCount="indefinite"/>
  </circle>
  <circle cx="1000" cy="13" r="3" fill="#8b5cf6">
    <animate attributeName="cx" values="1000;538" dur="5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="1;1;0" keyTimes="0;0.85;1" dur="5s" repeatCount="indefinite"/>
  </circle>
</svg>

<!-- ============================================================ -->
<!-- 7. GITHUB STATS & STREAK (tema warna custom, dual theme)      -->
<!--    Warna tema: bg_color / title_color / icon_color / text_    -->
<!--    color / ring / fire — panduan lengkap di komentar bawah    -->
<!-- ============================================================ -->
## ▸ GitHub Stats

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com/?user=mhdayatz&hide_border=true&background=0B1220&ring=22D3EE&fire=FBBF24&currStreakNum=E2E8F0&sideNums=8B9BB4&currStreakLabel=8B5CF6&sideLabels=5B6B80&dates=445069&stroke=22D3EE"/>
    <img src="https://streak-stats.demolab.com/?user=mhdayatz&hide_border=true&background=FFFFFF&ring=0284C7&fire=D97706&currStreakNum=0F172A&sideNums=334155&currStreakLabel=6D28D9&sideLabels=64748B&dates=94A3B8&stroke=0284C7" alt="GitHub streak stats" style="width:100%;max-width:560px;height:auto"/>
  </picture>
  <br/><br/>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=mhdayatz&show_icons=true&count_private=true&include_all_commits=true&hide_border=true&bg_color=0B1220&title_color=22D3EE&icon_color=8B5CF6&text_color=8B9BB4"/>
    <img src="https://github-readme-stats.vercel.app/api?username=mhdayatz&show_icons=true&count_private=true&include_all_commits=true&hide_border=true&bg_color=FFFFFF&title_color=0284C7&icon_color=6D28D9&text_color=334155" alt="GitHub stats" style="width:46%;min-width:300px;height:auto;margin:4px"/>
  </picture>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=mhdayatz&layout=compact&langs_count=8&hide_border=true&bg_color=0B1220&title_color=22D3EE&text_color=8B9BB4"/>
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=mhdayatz&layout=compact&langs_count=8&hide_border=true&bg_color=FFFFFF&title_color=0284C7&text_color=334155" alt="Top languages" style="width:46%;min-width:300px;height:auto;margin:4px"/>
  </picture>
</div>

## ▸ Contribution Activity

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=mhdayatz&bg_color=0B1220&color=8B9BB4&line=22D3EE&point=8B5CF6&area=true&hide_border=true&radius=10"/>
    <img src="https://github-readme-activity-graph.vercel.app/graph?username=mhdayatz&bg_color=FFFFFF&color=334155&line=0284C7&point=6D28D9&area=true&hide_border=true&radius=10" alt="Contribution activity graph" style="width:100%;height:auto"/>
  </picture>
  <br/><br/>

  <!-- ============ SNAKE (dinonaktifkan sementara) ============
       Aktifkan setelah setup GitHub Action "snake.yml" (panduan di
       komentar paling bawah). Caranya: hapus dua baris komentar yang
       membungkus blok picture ini (buka & tutup komentar HTML). -->
  <!--
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/mhdayatz/mhdayatz/output/snake-dark.svg"/>
    <img src="https://raw.githubusercontent.com/mhdayatz/mhdayatz/output/snake.svg" alt="Contribution snake animation" style="width:100%;height:auto"/>
  </picture>
  <br/>
  <sub>Contribution snake — regenerated daily by GitHub Actions</sub>
  -->
</div>

<!-- divider: code brackets -->
<svg viewBox="0 0 1000 26" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Section divider" style="width:100%;height:26px;display:block">
  <line x1="0" y1="13" x2="430" y2="13" stroke="#0ea5e9" stroke-width="2" opacity="0.5" stroke-linecap="round"/>
  <line x1="570" y1="13" x2="1000" y2="13" stroke="#8b5cf6" stroke-width="2" opacity="0.5" stroke-linecap="round"/>
  <text x="500" y="19" text-anchor="middle" font-size="16" font-family="'Fira Code',Consolas,monospace" font-weight="700" fill="#f59e0b">&lt;/&gt;
    <animate attributeName="opacity" values="1;0.4;1" dur="3s" repeatCount="indefinite"/>
  </text>
  <circle cx="430" cy="13" r="2.5" fill="#0ea5e9">
    <animate attributeName="opacity" values="1;0.3;1" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="570" cy="13" r="2.5" fill="#8b5cf6">
    <animate attributeName="opacity" values="0.3;1;0.3" dur="2s" repeatCount="indefinite"/>
  </circle>
</svg>

<!-- ============================================================ -->
<!-- 8. CERTIFICATIONS (dinonaktifkan sementara)                   -->
<!--    Aktifkan saat kamu punya sertifikat asli: hapus dua baris  -->
<!--    komentar (pembuka & penutup) di bawah, lalu isi tabelnya.  -->
<!-- ============================================================ -->
<!--
## ▸ Certifications

| Certification | Issuer | Year |
| :--- | :--- | :--- |
| **MTCNA** — MikroTik Certified Network Associate · [Verify](URL_SERTIFIKAT) | MikroTik | 2025 |
| **CCNA** — Cisco Certified Network Associate | Cisco | _in progress_ |
-->

<!-- ============================================================ -->
<!-- 9. CONNECT WITH ME                                          -->
<!--    Ganti semua placeholder link dengan akun kamu            -->
<!-- ============================================================ -->
## ▸ Connect With Me

<div align="center">
  <a href="https://www.linkedin.com/in/YOUR_LINKEDIN"><img src="https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="https://www.instagram.com/YOUR_INSTAGRAM"><img src="https://img.shields.io/badge/-Instagram-E4405F?style=flat-square&logo=instagram&logoColor=white" alt="Instagram"/></a>
  <a href="mailto:your.email@example.com"><img src="https://img.shields.io/badge/-Email-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Email"/></a>
  <a href="https://t.me/YOUR_TELEGRAM"><img src="https://img.shields.io/badge/-Telegram-26A5E4?style=flat-square&logo=telegram&logoColor=white" alt="Telegram"/></a>
  <a href="https://YOUR_PORTFOLIO_URL"><img src="https://img.shields.io/badge/-Portfolio-8B5CF6?style=flat-square&logo=globe&logoColor=white" alt="Portfolio"/></a>
  <a href="https://github.com/mhdayatz"><img src="https://img.shields.io/badge/-GitHub-181717?style=flat-square&logo=github&logoColor=white" alt="GitHub"/></a>
</div>

<!-- divider: network node path -->
<svg viewBox="0 0 1000 26" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Section divider" style="width:100%;height:26px;display:block">
  <line x1="0" y1="13" x2="462" y2="13" stroke="#0ea5e9" stroke-width="2" stroke-linecap="round" opacity="0.7"/>
  <line x1="538" y1="13" x2="1000" y2="13" stroke="#8b5cf6" stroke-width="2" stroke-linecap="round" opacity="0.7"/>
  <circle cx="500" cy="13" r="6" fill="#f59e0b">
    <animate attributeName="opacity" values="1;0.3;1" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="500" cy="13" r="12" fill="none" stroke="#f59e0b" stroke-width="1.5">
    <animate attributeName="r" values="6;14" dur="2s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.9;0" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="0" cy="13" r="3" fill="#0ea5e9">
    <animate attributeName="cx" values="0;462" dur="5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="1;1;0" keyTimes="0;0.85;1" dur="5s" repeatCount="indefinite"/>
  </circle>
  <circle cx="1000" cy="13" r="3" fill="#8b5cf6">
    <animate attributeName="cx" values="1000;538" dur="5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="1;1;0" keyTimes="0;0.85;1" dur="5s" repeatCount="indefinite"/>
  </circle>
</svg>

<!-- ============================================================ -->
<!-- 10. FOOTER — quote + visitor counter animasi                  -->
<!-- ============================================================ -->
<div align="center">
  <i>"Every network is a graph — every app is a network. I build and debug both."</i>
  <br/><br/>
  <img src="https://komarev.com/ghpvc/?username=mhdayatz&style=flat-square&color=0EA5E9&label=profile%20views" alt="Profile visitor counter"/>
  <br/><br/>
  <sub>Thanks for stopping by — let's build something connected.</sub>
</div>



<!-- ============================================================================
     ============================================================================
     PANDUAN KUSTOMISASI (komentar ini TIDAK tampil di GitHub, silakan baca)
     ============================================================================
     ============================================================================

----------------------------------------------------------------------------
A. YANG WAJIB DIGANTI (find & replace)
----------------------------------------------------------------------------
   - mhdayatz  → username kamu. Muncul di ~15 URL (stats, streak,
     graph, snake, badges, dll). Sekali ganti semua langsung beres.
   - Muhammad Hidayat             → di banner SVG bagian <text ...>Hi, I'm Muhammad Hidayat</text>
   - YOUR_LINKEDIN, YOUR_INSTAGRAM, YOUR_TELEGRAM, YOUR_PORTFOLIO_URL,
     your.email@example.com → link sosial di section Connect With Me.
   - project-a/b/c/d       → nama repo project kamu (Featured Projects).
   - URL_DEMO, URL_SERTIFIKAT → link demo & verifikasi sertifikat.
   - Stack di `[CODE]` dan ikon skillicons Group 2 → sesuaikan dengan stack asli.

----------------------------------------------------------------------------
B. CARA GANTI WARNA TEMA (github-readme-stats & kawan-kawan)
----------------------------------------------------------------------------
   Semua layanan stats memakai parameter warna hex (tanpa tanda #). Cari
   parameter-nya di URL lalu ubah nilainya, contoh:

   1. github-readme-stats (kartu API & Top Languages):
        bg_color=0B1220     → warna latar kartu
        title_color=22D3EE  → warna judul
        icon_color=8B5CF6   → warna ikon (API card)
        text_color=8B9BB4   → warna teks isi
        border_color=...    → warna border (aktif kalau hide_border tidak dipakai)
      Catatan: tiap layanan di-<picture> dual-theme, jadi URL dark & light
      masing-masing punya set warna sendiri. Warna dark ada di srcset,
      warna light ada di img src.

   2. Streak (streak-stats.demolab.com):
        background=...      → latar
        ring=...            → warna cincin/garis
        fire=...            → warna api
        currStreakNum=...   → angka streak aktif
        currStreakLabel=... → label streak aktif
        sideNums=...        → angka sisi (total, longest)
        sideLabels=...      → label sisi
        dates=...           → tanggal
        stroke=...          → garis bawah

   3. Activity Graph (github-readme-activity-graph.vercel.app):
        bg_color=...  color=... (teks)  line=... (garis chart)
        point=... (titik)  area=true (isi area dengan gradien)
        radius=10 → sudut membulat

   4. Typing (readme-typing-svg.demolab.com):
        color=...     → warna teks ketikan
        font=...      → font (Fira+Code, JetBrains+Mono, dll)
        size=...      → ukuran huruf
        duration=...  → kecepatan mengetik (ms)
        pause=...     → jeda antar baris (ms)
        lines=...     → isi teks, pisahkan antar baris dengan `;`,
                        spasi pakai %20, & pakai %26, · pakai %C2%B7

   5. Skill icons (skillicons.dev):
        theme=dark | theme=light → versi ikon untuk masing-masing mode
        perline=13               → jumlah ikon per baris

----------------------------------------------------------------------------
C. TRICK DUAL THEME (<picture> + prefers-color-scheme)
----------------------------------------------------------------------------
   Blok <picture> dipakai agar gambar punya 2 versi:
     - <source media="(prefers-color-scheme: dark)"> = versi dark
     - <img src="..."> = fallback versi light
   Browser otomatis memilih sesuai tema GitHub yang sedang dipakai user.
   Ini berlaku untuk: typing, stats, streak, graph, skill icons, snake.
   Mau menambah gambar baru? Ikuti pola yang sama.

----------------------------------------------------------------------------
D. SETUP ANIMASI SNAKE (butuh GitHub Action, sekali setup)
----------------------------------------------------------------------------
   Langkah:
   1. Di repo profile kamu, buat folder `.github/workflows/` lalu file
      `snake.yml` dengan isi:

        name: Generate Snake
        on:
          schedule:
            - cron: "0 0 * * *"
          workflow_dispatch:
        jobs:
          build:
            runs-on: ubuntu-latest
            steps:
              - uses: actions/checkout@v4
              - uses: Platane/snk@v3
                with:
                  github_user_name: mhdayatz
                  outputs: |
                    dist/snake.svg
                    dist/snake-dark.svg?palette=github-dark
              - uses: crazy-max/ghaction-github-pages@v4
                with:
                  target_branch: output
                  build_dir: dist
                env:
                  GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

   2. Commit & push. Buka tab Actions → pilih workflow "Generate Snake"
      → Run workflow (jalankan sekali agar langsung muncul).
   3. Setelah selesai, branch `output` otomatis dibuat berisi snake.svg &
      snake-dark.svg → URL raw-nya sudah dipakai di section Contribution
      Activity di atas.
   4. Blok <picture> snake di README otomatis aktif. Snake di-generate ulang
      tiap hari pukul 00:00 UTC.
   (Kalau tidak mau pakai snake, hapus blok <picture> snake di atas.)

----------------------------------------------------------------------------
E. KENAPA ANIMASI BANNER & DIVIDER MEMAKAI SMIL (bukan CSS)?
----------------------------------------------------------------------------
   GitHub MEMBUANG elemen <style> dan @keyframes CSS dari README, tapi
   MENYIMPAN animasi SMIL (<animate>, <animateTransform>). Karena itu semua
   animasi SVG inline di file ini memakai SMIL — dijamin jalan di
   github.com (browser desktop, termasuk Chrome/Edge/Firefox/Safari).
   Mau mengubah animasi? Cukup edit atribut di elemen <animate>:
     - attributeName="cx"   → properti yang dianimasikan (r, opacity, cx, cy)
     - values="90;205;330"  → urutan nilai
     - dur="4.5s"           → durasi satu siklus
     - begin="1s"           → tunda mulai (untuk efek bergantian)
     - repeatCount="indefinite" → loop terus-menerus
   Warna banner & divider juga tinggal diganti nilai hex-nya (#22d3ee = cyan,
   #8b5cf6 = violet, #f59e0b = amber — tema konsisten di seluruh README).

   CATATAN: banner sengaja dibuat gelap agar terlihat premium di kedua tema
   GitHub (kartu gelap di tema terang itu normal & disengaja). Kalau ingin
   banner adaptif, buat 2 file SVG terpisah di folder assets/ lalu ganti
   bloknya dengan pola <picture> seperti section lain.

----------------------------------------------------------------------------
F. TROUBLESHOOTING
----------------------------------------------------------------------------
   - Gambar rusak/broken setelah ganti username? Pastikan SEMUA
     mhdayatz sudah diganti, lalu hard-refresh (Ctrl+F5) atau
     tambahkan `&v=2` di akhir URL (mem-bypass cache GitHub).
   - Kartu stats kosong? Repo publik kamu harus ada isinya dulu (stats
     service butuh data repo publik). Cek juga `count_private` kalau repo
     kamu banyak yang private (sudah disetel aktif di file ini).
   - Ikon skillicons tidak muncul? Pastikan ID ikon valid (daftar resmi:
     https://skillicons.dev). Catatan: skillicons TIDAK punya ikon MikroTik
     & Cisco, makanya keduanya diganti badge teks di Group 1.
   - Animasi tidak bergerak? Pastikan kamu melihat di browser (bukan
     aplikasi mobile GitHub), dan OS kamu tidak mengaktifkan
     "reduce motion" (animasi tetap ada di GitHub, tapi cek juga OS-level).
   - Typing SVG kosong? Layaniannya kadang lambat — refresh beberapa detik
     lagi; kalau tetap kosong cek demo: https://readme-typing-svg.demolab.com/demo

----------------------------------------------------------------------------
G. IDE DEVELOP LANJUTAN (opsional)
----------------------------------------------------------------------------
   - Tambahkan badge "Open to work" atau "Open to collab" di bawah header
     memakai shields.io dengan pola badge yang sudah ada.
   - Ganti quote footer sesuai selera — ini bagian paling gampang
     dikustomisasi biar "terasa milik kamu".
   - Section Certifications & Currently Working On memang dirancang untuk
     di-update manual setiap beberapa minggu — itu membuat profile terlihat
     hidup.
     ============================================================================ -->
