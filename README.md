from pathlib import Path
import zipfile, textwrap

root = Path("/mnt/data/ommama-github-profile")
assets = root / "assets"
assets.mkdir(parents=True, exist_ok=True)

def svg_header(title, subtitle, accent="#8B9CFB"):
    return f'''<svg xmlns="http://www.w3.org/2000/svg" width="1200" height="150" viewBox="0 0 1200 150">
<defs><linearGradient id="g" x1="0" y1="0" x2="1" y2="1"><stop stop-color="#151A2B"/><stop offset="1" stop-color="#0B1020"/></linearGradient><linearGradient id="a"><stop stop-color="{accent}"/><stop offset="1" stop-color="#62D6C8"/></linearGradient></defs>
<rect width="1200" height="150" rx="18" fill="url(#g)"/>
<path d="M0 118 C220 58 330 170 560 95 S920 20 1200 85" fill="none" stroke="{accent}" stroke-opacity=".18" stroke-width="2"/>
<circle cx="1090" cy="28" r="110" fill="{accent}" opacity=".07"/><circle cx="1090" cy="28" r="72" fill="none" stroke="{accent}" opacity=".2"/>
<text x="54" y="76" fill="#F4F6FF" font-family="Inter,Arial,sans-serif" font-size="34" font-weight="700" letter-spacing="1">{title}</text>
<text x="56" y="108" fill="#AAB4D0" font-family="Inter,Arial,sans-serif" font-size="15" letter-spacing="2">{subtitle}</text>
<rect x="56" y="124" width="92" height="3" rx="2" fill="url(#a)"/>
</svg>'''

def write(name, content):
    (assets/name).write_text(content, encoding="utf-8")

hero = '''<svg xmlns="http://www.w3.org/2000/svg" width="1200" height="360" viewBox="0 0 1200 360">
<defs>
 <linearGradient id="bg" x1="0" y1="0" x2="1" y2="1"><stop stop-color="#0B1020"/><stop offset="1" stop-color="#171E35"/></linearGradient>
 <linearGradient id="glow"><stop stop-color="#8B9CFB"/><stop offset="1" stop-color="#62D6C8"/></linearGradient>
 <pattern id="grid" width="32" height="32" patternUnits="userSpaceOnUse"><path d="M32 0H0V32" fill="none" stroke="#91A0D8" stroke-opacity=".09"/></pattern>
</defs>
<rect width="1200" height="360" rx="22" fill="url(#bg)"/><rect width="1200" height="360" rx="22" fill="url(#grid)"/>
<circle cx="1000" cy="170" r="210" fill="#8B9CFB" opacity=".07"/><circle cx="1000" cy="170" r="145" fill="none" stroke="#8B9CFB" stroke-opacity=".25"/>
<circle cx="1000" cy="170" r="105" fill="none" stroke="#62D6C8" stroke-opacity=".35" stroke-dasharray="5 9"/>
<g transform="translate(855 82)" fill="none" stroke="url(#glow)" stroke-width="2">
 <rect x="0" y="0" width="190" height="160" rx="18" opacity=".8"/><path d="M0 42H190M28 20h8m12 0h8m12 0h8" opacity=".8"/>
 <path d="m65 82-22 18 22 18m60-36 22 18-22 18m-19-48-18 60" stroke-linecap="round" stroke-linejoin="round"/>
 <path d="M-28 185h246M-2 160v25m190-25v25" opacity=".45"/>
</g>
<text x="64" y="92" fill="#9AA9FF" font-family="Inter,Arial,sans-serif" font-size="15" letter-spacing="4">FULL STACK ENGINEER</text>
<text x="60" y="157" fill="#F5F7FF" font-family="Inter,Arial,sans-serif" font-size="52" font-weight="750">Ommama Khan</text>
<text x="64" y="202" fill="#C5CEE8" font-family="Inter,Arial,sans-serif" font-size="21">Building products, backend systems &amp; thoughtful interfaces.</text>
<g font-family="Inter,Arial,sans-serif" font-size="13" font-weight="600">
 <rect x="64" y="246" width="110" height="34" rx="17" fill="#202A46" stroke="#6478C9"/><text x="119" y="268" fill="#DDE3FF" text-anchor="middle">Next.js</text>
 <rect x="186" y="246" width="108" height="34" rx="17" fill="#202A46" stroke="#6478C9"/><text x="240" y="268" fill="#DDE3FF" text-anchor="middle">NestJS</text>
 <rect x="306" y="246" width="148" height="34" rx="17" fill="#202A46" stroke="#6478C9"/><text x="380" y="268" fill="#DDE3FF" text-anchor="middle">TypeScript</text>
 <rect x="466" y="246" width="150" height="34" rx="17" fill="#202A46" stroke="#6478C9"/><text x="541" y="268" fill="#DDE3FF" text-anchor="middle">System Design</text>
</g>
<text x="64" y="324" fill="#7F8BAA" font-family="Inter,Arial,sans-serif" font-size="12" letter-spacing="2">PRODUCT ENGINEERING · API DESIGN · CLOUD &amp; INFRASTRUCTURE</text>
</svg>'''
write("hero.svg", hero)
write("hdr-about.svg", svg_header("ABOUT & JOURNEY", "FROM COMPUTER SCIENCE TO PRODUCTION SOFTWARE"))
write("hdr-work.svg", svg_header("SELECTED ENGINEERING", "PRODUCTS · PLATFORMS · SYSTEMS", "#62D6C8"))
write("hdr-stack.svg", svg_header("TECHNOLOGY LANDSCAPE", "TOOLS I USE TO DESIGN, BUILD AND SHIP", "#A78BFA"))
write("hdr-connect.svg", svg_header("LET'S CONNECT", "OPEN TO GOOD PROBLEMS AND COLLABORATION", "#62D6C8"))

about = '''<svg xmlns="http://www.w3.org/2000/svg" width="1200" height="250" viewBox="0 0 1200 250">
<rect width="1200" height="250" rx="18" fill="#101629"/><path d="M100 92H1100" stroke="#53628D" stroke-width="2"/>
<g font-family="Inter,Arial,sans-serif">
 <g fill="#8B9CFB"><circle cx="130" cy="92" r="8"/><circle cx="450" cy="92" r="8"/><circle cx="770" cy="92" r="8"/><circle cx="1070" cy="92" r="8"/></g>
 <g fill="#F1F4FF" font-size="19" font-weight="700"><text x="90" y="52">2023</text><text x="410" y="52">2024</text><text x="730" y="52">2025</text><text x="1030" y="52">2026</text></g>
 <g fill="#AAB5D0" font-size="14"><text x="90" y="132">Frontend foundations</text><text x="90" y="154">and product development</text>
 <text x="410" y="132">Full-stack engineering</text><text x="410" y="154">APIs &amp; integrations</text>
 <text x="730" y="132">BS Computer Science</text><text x="730" y="154">graduated · Jan 2025</text>
 <text x="1030" y="132">SaaS &amp; backend systems</text><text x="1030" y="154">production engineering</text></g>
 <text x="90" y="215" fill="#7E8BAE" font-size="12" letter-spacing="2">A CONTINUOUS JOURNEY OF BUILDING AND LEARNING</text>
</g></svg>'''
write("about-timeline.svg", about)

stack = '''<svg xmlns="http://www.w3.org/2000/svg" width="1200" height="390" viewBox="0 0 1200 390">
<rect width="1200" height="390" rx="18" fill="#101629"/>
<g font-family="Inter,Arial,sans-serif">
 <g transform="translate(70 65)">
  <path d="M0 65 190 0 380 65 190 130Z" fill="#222D4D" stroke="#7588D8"/><path d="M0 65v120l190 65V130Z" fill="#18213A" stroke="#7588D8"/><path d="M380 65v120l-190 65V130Z" fill="#202B49" stroke="#7588D8"/>
  <text x="190" y="56" text-anchor="middle" fill="#F0F3FF" font-size="20" font-weight="700">FRONTEND</text><text x="190" y="91" text-anchor="middle" fill="#B9C5E8" font-size="14">React · Next.js · TypeScript</text>
  <path d="M430 65 620 0 810 65 620 130Z" fill="#26334E" stroke="#62D6C8"/><path d="M430 65v120l190 65V130Z" fill="#192A3B" stroke="#62D6C8"/><path d="M810 65v120l-190 65V130Z" fill="#1E3542" stroke="#62D6C8"/>
  <text x="620" y="56" text-anchor="middle" fill="#F0F3FF" font-size="20" font-weight="700">BACKEND</text><text x="620" y="91" text-anchor="middle" fill="#B9DCD8" font-size="14">NestJS · Node.js · REST · Queues</text>
  <path d="M860 65 1050 0 1240 65 1050 130Z" fill="#2C2B4B" stroke="#A78BFA"/><path d="M860 65v120l190 65V130Z" fill="#211F3A" stroke="#A78BFA"/><path d="M1240 65v120l-190 65V130Z" fill="#292644" stroke="#A78BFA"/>
  <text x="1050" y="56" text-anchor="middle" fill="#F0F3FF" font-size="20" font-weight="700">PLATFORM</text><text x="1050" y="91" text-anchor="middle" fill="#D0C4F5" font-size="14">Docker · Linux · Nginx · Cloud</text>
 </g>
 <text x="70" y="350" fill="#8996B8" font-size="13" letter-spacing="2">DATA: POSTGRESQL · MONGODB · PRISMA  /  OBSERVABILITY: OPENTELEMETRY · LOGGING</text>
</g></svg>'''
write("stack-isometric.svg", stack)

# Simple reusable project-card artwork
cards = {
"project-cmm.svg": ("CAPTUREMYMEETING", "Meeting capture · transcription · AI workflows", "#62D6C8", "01"),
"project-saas.svg": ("SAAS PLATFORMS", "Multi-tenant portals · APIs · integrations", "#8B9CFB", "02"),
"project-ar.svg": ("3D & AR PIPELINES", "3D assets · USDZ / glTF · mobile experiences", "#A78BFA", "03"),
"project-automation.svg": ("AUTOMATION SYSTEMS", "Document processing · data extraction · tooling", "#E6B86A", "04"),
}
for fn, (t, sub, color, num) in cards.items():
    write(fn, f'''<svg xmlns="http://www.w3.org/2000/svg" width="600" height="260" viewBox="0 0 600 260">
<defs><linearGradient id="b"><stop stop-color="#11182B"/><stop offset="1" stop-color="#1B2540"/></linearGradient></defs>
<rect width="600" height="260" rx="18" fill="url(#b)" stroke="{color}" stroke-opacity=".45"/>
<circle cx="510" cy="68" r="92" fill="{color}" opacity=".08"/><circle cx="510" cy="68" r="58" fill="none" stroke="{color}" opacity=".3"/>
<path d="M410 175h125m-100-25 25-25 25 25 25-25" fill="none" stroke="{color}" stroke-width="2" opacity=".6"/>
<text x="38" y="55" fill="{color}" font-family="Arial,sans-serif" font-size="13" letter-spacing="3">ENGINEERING / {num}</text>
<text x="38" y="126" fill="#F3F5FF" font-family="Arial,sans-serif" font-size="28" font-weight="700">{t}</text>
<text x="38" y="163" fill="#AEB9D5" font-family="Arial,sans-serif" font-size="16">{sub}</text>
<rect x="38" y="196" width="64" height="3" rx="2" fill="{color}"/>
</svg>''')

readme = '''<div align="center">

<img src="assets/hero.svg" alt="Ommama Khan — Full Stack Engineer" width="100%"/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ommama-khan/)
[![GitHub](https://img.shields.io/badge/GitHub-ommamakhan-181717?style=flat&logo=github)](https://github.com/ommamakhan)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:ommama.khan@gmail.com)

</div>

---

<img src="assets/hdr-about.svg" width="100%" alt="About and journey"/>

I'm a **Full Stack Engineer** focused on building reliable web products, backend services, and practical software systems. I work across the application stack — from user-facing interfaces and API design to integrations, data processing, deployment, and production troubleshooting.

My day-to-day engineering interests include **Next.js, NestJS, TypeScript, SaaS architecture, background processing, and production infrastructure**. I enjoy taking a feature from an initial idea through implementation and into a maintainable production system.

<img src="assets/about-timeline.svg" width="100%" alt="Career and education timeline"/>

🎓 **BS Computer Science** · National University of Modern Languages (NUML), Rawalpindi  
Graduated **January 2025**

---

<img src="assets/hdr-work.svg" width="100%" alt="Selected engineering work"/>

<table>
<tr>
<td width="50%"><img src="assets/project-cmm.svg" width="100%" alt="CaptureMyMeeting project"/></td>
<td width="50%">

**CaptureMyMeeting — Meeting intelligence platform**

Working across meeting capture, transcription pipelines, AI-generated summaries, playback, integrations, and asynchronous processing. Engineering areas include NestJS, Next.js, queues, object storage, and third-party service integrations.

</td>
</tr>
<tr>
<td width="50%"><img src="assets/project-saas.svg" width="100%" alt="SaaS platforms"/></td>
<td width="50%">

**SaaS & portal-based platforms**

Building full-stack business applications with structured APIs, authentication, role-based access, database-backed workflows, and responsive interfaces.

</td>
</tr>
<tr>
<td width="50%"><img src="assets/project-ar.svg" width="100%" alt="3D and AR pipelines"/></td>
<td width="50%">

**3D, AR & mobile experiences**

Exploring interactive 3D experiences and asset pipelines, including Blender-based processing and delivery formats such as USDZ and glTF, alongside mobile application work.

</td>
</tr>
<tr>
<td width="50%"><img src="assets/project-automation.svg" width="100%" alt="Automation systems"/></td>
<td width="50%">

**Data & workflow automation**

Building document-centric and data-driven workflows, file processing, integrations, and automation services that reduce repetitive operational work.

</td>
</tr>
</table>

---

<img src="assets/hdr-stack.svg" width="100%" alt="Technology landscape"/>
<img src="assets/stack-isometric.svg" width="100%" alt="Architecture stack"/>

| Area | Technologies |
|---|---|
| **Frontend** | React, Next.js, TypeScript, JavaScript, Tailwind CSS, shadcn/ui, Redux Toolkit, Zustand |
| **Backend** | Node.js, NestJS, Express.js, REST APIs, WebSockets, JWT, Server-Sent Events |
| **Data** | PostgreSQL, MongoDB, Prisma, Redis, data processing |
| **AI & Integrations** | OpenAI APIs, transcription services, third-party APIs, Python integrations |
| **Infrastructure** | Docker, Linux, Nginx, VPS deployments, PM2, object storage |
| **Observability** | OpenTelemetry, distributed tracing, structured logging, monitoring |

---

### What I'm exploring

- React Native and cross-platform mobile development
- Event-driven systems, queues, and resilient background jobs
- Advanced system design and distributed application patterns
- Practical AI integration in production software

---

<img src="assets/hdr-connect.svg" width="100%" alt="Connect"/>

<div align="center">

**Building useful software, one system at a time.**

[GitHub](https://github.com/ommamakhan) · [LinkedIn](https://www.linkedin.com/in/ommama-khan/) · [Email](mailto:ommama.khan@gmail.com)

</div>
'''
(root / "README.md").write_text(readme, encoding="utf-8")
(root / "ASSET-NOTES.md").write_text(
"""# Profile assets

All artwork in `assets/` is editable SVG source. The README uses relative paths, so keep the `assets` folder beside `README.md` in the `ommamakhan/ommamakhan` repository.

Before publishing:
- Confirm the project descriptions are safe to disclose publicly.
- Add repository/demo links to project cards only for projects you want to make public.
- Remove any project that is confidential or not representative of your work.
- GitHub profile README supports HTML image tags and relative repository asset paths.
""", encoding="utf-8")

zip_path = Path("/mnt/data/ommama-github-profile-pack.zip")
with zipfile.ZipFile(zip_path, "w", zipfile.ZIP_DEFLATED) as z:
    for p in root.rglob("*"):
        if p.is_file():
            z.write(p, p.relative_to(root.parent))
print(f"Created {zip_path} with {sum(1 for p in root.rglob('*') if p.is_file())} files.")
