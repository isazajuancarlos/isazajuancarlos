# Xiliux — Juan Carlos Isaza

> Post-quantum security engineering, responsible disclosure, and offline-first software. Built in Rust, in Medellín, Colombia.
>
> Ingeniería de seguridad post-cuántica, divulgación responsable y software *offline-first*. Hecho en Rust, desde Medellín, Colombia.

**[🇬🇧 English](#english) · [🇪🇸 Español](#español)**

---

## English
<a name="english"></a>

I'm **Juan Carlos Isaza** — a security engineer and software developer (and a lawyer, which shapes how I think about privacy and evidence). Under the **Xiliux** name I build cryptography, security tooling, and full-stack products that run **offline, as a single binary, with no telemetry and no phone-home**.

Two things set the work apart: it's **post-quantum from the core**, and it's **measured** — every claim here is backed by a number or a public disclosure, not a slogan.

### What I do

| Area | What it means |
|---|---|
| 🔐 **Post-quantum cryptography** | Hybrid encryption and signatures for data at rest: XChaCha20-Poly1305 · Argon2id · ML-KEM (FIPS 203) · ML-DSA (FIPS 204) · SLH-DSA (FIPS 205) · VOPRF. |
| 🔎 **Security research & responsible disclosure** | IAM/SAML/OIDC, broken access control (IDOR/BOLA/BAC), and post-quantum signature verification. I find it, I report it through the official channel, I never weaponize it. |
| 🦀 **Full-stack product engineering** | Rust + `axum` + `SQLx`/SQLite on the server, `maud` + htmx on the screen. One executable, one database per instance, works offline. |
| ⚖️ **Legal-tech & compliance** | Digital forensics with a cryptographic chain of custody, and data-protection compliance (Colombia's Law 1581 / GDPR-style). Lawyer + engineer in one. |

### Open cryptography

- **[quipu](https://github.com/isazajuancarlos/quipu)** — post-quantum hybrid cryptography for data at rest. Rust core with Python/Node/Go bindings. `XChaCha20-Poly1305 · Argon2id · ML-KEM-1024 · ML-DSA-87 · VOPRF`. AGPL-3.0.
- **[guaca](https://github.com/isazajuancarlos/guaca)** — at-rest protection (encryption + signing) for applications, built on quipu.
- **[tunjo](https://github.com/isazajuancarlos/tunjo)** — cryptographic sealing of digital evidence + chain-of-custody record, with post-quantum signatures. It *attests*; it doesn't conclude.
- **[tumbaga](https://github.com/isazajuancarlos/tumbaga)** — password verification with a scheme chain and opportunistic upgrade: migrate bcrypt → Argon2id on login, nobody locked out.

### Developer & agent-security tools

- **[guecha](https://github.com/isazajuancarlos/guecha)** — **prompt-injection defense for AI coding agents**, as a Claude Code plugin. Two advisory hooks catch obfuscation (bidi / zero-width / Unicode-tag smuggling) and image-based exfiltration in tool output, and guard the agent's own config against injection persistence. Advisory, local, **MIT**. Sub-millisecond and measured; survived three rounds of adversarial review (every detector ships a paired red/green test).

Tools I sell self-serve at **[xiliux.lemonsqueezy.com](https://xiliux.lemonsqueezy.com)** — single binary, offline, no telemetry:

- **Xué** — the standalone **MCP** prompt-injection scanner (the paid, broader sibling of guecha). Catches obfuscation (bidi / zero-width / homoglyphs) and indirect injection in agent inputs.
- **Chaquén** — MCP secret scanner. Finds credentials, tokens and keys before they're committed — including secrets deleted from the tree but still alive in git history.
- **[sin-caso-rojo](https://github.com/isazajuancarlos/sin-caso-rojo)** — diff coverage gap finder. Reverts each hunk and runs your suite: tells you exactly which lines nothing would catch if they broke.

More tooling: **[zaque](https://github.com/isazajuancarlos/zaque)** (boot-chain integrity) · **[autz](https://github.com/isazajuancarlos/autz)** (broken-access-control detection) · **[tequendama](https://github.com/isazajuancarlos/tequendama)** (data ingestion) · **[guardia-supresiones](https://github.com/isazajuancarlos/guardia-supresiones)** (honest `cargo-deny` suppressions) · **[escaner-android](https://github.com/isazajuancarlos/escaner-android)** / **[escaner-windows](https://github.com/isazajuancarlos/escaner-windows)** (security-hygiene scanners) · **[bochica](https://github.com/isazajuancarlos/bochica)** (Law 1581 compliance) · **[mindala](https://github.com/isazajuancarlos/mindala)** (technical intelligence).

### Products

Full-stack products — one binary, one database per instance, offline-first:

- **[medico](https://github.com/isazajuancarlos/medico)** — health-information system for Colombian providers: clinical records, billing, and the RIPS → FEV-RIPS → MUV reporting chain (Res. 948/2026).
- **[validador-rips](https://github.com/isazajuancarlos/validador-rips)** — pre-flight validator: *"upload your RIPS and I'll tell you what MinSalud would reject."* Free at **[rips.xiliux.com](https://rips.xiliux.com)**.
- **[informes](https://github.com/isazajuancarlos/informes)** — general platform for structured reports, XBRL / iXBRL first-class.
- **[chasqui](https://github.com/isazajuancarlos/chasqui)** — automated customer attention over WhatsApp, Instagram and Messenger.
- **[bachue](https://github.com/isazajuancarlos/bachue)** — OpenID Connect identity provider.
- **[winext4](https://github.com/isazajuancarlos/winext4)** — native ext4 for Windows, no WSL / no VM (in active development).

### Security research — public disclosures

Responsible, coordinated disclosure only, always through the vendor's official security channel:

- **OpenAM** — SAML 1.x signature confusion (**CWE-347**), advisory `GHSA-j56q-q3r3-hg7f`.
- **midPoint / Evolveum** — broken access control (**CWE-862**), disclosed.
- **Ethereum Lean roadmap** — differential and adversarial verification of the validator hash-based signatures (generalized XMSS) with my harness **[Iraca](https://github.com/isazajuancarlos/iraca)**: canonicity, malleability, and the one-time-per-epoch invariant.
- Additional IDOR/BAC findings coordinated through HackerOne and Intigriti programs.

### Depth, measured

> If the code can't always be seen, the proof of depth has to stand on its own. These do.

- **9.8× faster crypto CI** (598 s → 61 s) on quipu by optimizing dependency builds — with the control that proves it wasn't the compiler.
- **Independent verification of NIST PQC** against reference implementations — ML-DSA, SLH-DSA and ML-KEM harnesses (**[Iraca-2](https://github.com/isazajuancarlos/iraca-2)** / **[3](https://github.com/isazajuancarlos/iraca-3)** / **[4](https://github.com/isazajuancarlos/iraca-4)**): tens of thousands of mutations, **zero** accepted; four-way cross-language differential (Rust ↔ pq-crystals C ↔ libcrux ↔ AWS-LC) green byte-for-byte.
- **guecha**: a prompt-injection detector that discriminates — 28 unit + 33 end-to-end paired tests, three rounds of adversarial review, sub-millisecond.

### Stack

`Rust` · `axum` · `SQLx` / `SQLite` · `maud` · `htmx` · zero-Node builds · single binary · offline-first · one database per instance.

### Writing

- **[They're not after your code](https://xiliux.com/en/blog/no-vienen-por-tu-codigo)** — why the big 2025–2026 attacks hit everything massive (npm, the AUR, the Snap Store, GitHub, WordPress), and where the truth of your software should live. More essays: **[escritos](https://github.com/isazajuancarlos/escritos)**.

### Reach me

- 🌐 Portfolio & products: **[xiliux.com](https://xiliux.com)**
- 🛒 Store: **[xiliux.lemonsqueezy.com](https://xiliux.lemonsqueezy.com)**

---

## Español
<a name="español"></a>

Soy **Juan Carlos Isaza** — ingeniero de seguridad y desarrollador de software (y abogado, lo que moldea cómo pienso la privacidad y la evidencia). Bajo el nombre **Xiliux** construyo criptografía, herramientas de seguridad y productos full-stack que corren **offline, como un solo binario, sin telemetría y sin llamar a casa**.

Dos cosas distinguen el trabajo: es **post-cuántico desde el núcleo**, y está **medido** — cada afirmación aquí se respalda con un número o una divulgación pública, no con un eslogan.

### Qué hago

| Área | Qué significa |
|---|---|
| 🔐 **Criptografía post-cuántica** | Cifrado y firmas híbridas para datos en reposo: XChaCha20-Poly1305 · Argon2id · ML-KEM (FIPS 203) · ML-DSA (FIPS 204) · SLH-DSA (FIPS 205) · VOPRF. |
| 🔎 **Investigación de seguridad y divulgación responsable** | IAM/SAML/OIDC, control de acceso roto (IDOR/BOLA/BAC) y verificación de firmas post-cuánticas. Lo encuentro, lo reporto por el canal oficial, nunca lo convierto en arma. |
| 🦀 **Ingeniería de producto full-stack** | Rust + `axum` + `SQLx`/SQLite en el servidor, `maud` + htmx en la pantalla. Un ejecutable, una base de datos por instancia, funciona offline. |
| ⚖️ **Legal-tech y cumplimiento** | Informática forense con cadena de custodia criptográfica, y cumplimiento de protección de datos (Ley 1581 de Colombia / estilo GDPR). Abogado + ingeniero en uno. |

### Criptografía abierta

- **[quipu](https://github.com/isazajuancarlos/quipu)** — criptografía post-cuántica híbrida para datos en reposo. Núcleo en Rust con *bindings* Python/Node/Go. `XChaCha20-Poly1305 · Argon2id · ML-KEM-1024 · ML-DSA-87 · VOPRF`. AGPL-3.0.
- **[guaca](https://github.com/isazajuancarlos/guaca)** — protección en reposo (cifrado + firma) para aplicaciones, sobre quipu.
- **[tunjo](https://github.com/isazajuancarlos/tunjo)** — sellado criptográfico de evidencia digital + acta de cadena de custodia, con firma post-cuántica. *Acredita*; no concluye.
- **[tumbaga](https://github.com/isazajuancarlos/tumbaga)** — verificación de contraseñas con cadena de esquemas y actualización oportunista: migra de bcrypt a Argon2id al iniciar sesión, sin dejar a nadie fuera.

### Herramientas para desarrolladores y seguridad de agentes

- **[guecha](https://github.com/isazajuancarlos/guecha)** — **defensa anti-inyección para agentes de código con IA**, como plugin de Claude Code. Dos *hooks* de aviso cazan ofuscación (bidi / ancho-cero / *smuggling* por Tags Unicode) y exfiltración por imagen en la salida de herramientas, y protegen la propia config del agente contra la persistencia de una inyección. Advisory, local, **MIT**. Sub-milisegundo y medido; sobrevivió tres rondas de revisión adversaria (cada detector trae su par de pruebas rojo/verde).

Herramientas que vendo en autoservicio en **[xiliux.lemonsqueezy.com](https://xiliux.lemonsqueezy.com)** — binario único, offline, sin telemetría:

- **Xué** — el escáner de inyección de *prompts* por **MCP** (el hermano de pago, más amplio, de guecha). Caza ofuscación (bidi / ancho-cero / homóglifos) e inyección indirecta en las entradas de un agente.
- **Chaquén** — escáner de secretos por MCP. Encuentra credenciales, tokens y llaves antes de que se suban — incluidos los secretos borrados del árbol pero vivos en la historia de git.
- **[sin-caso-rojo](https://github.com/isazajuancarlos/sin-caso-rojo)** — detector de huecos de cobertura en un diff. Revierte cada *hunk* y corre tu banco de pruebas: te dice exactamente qué líneas no vigilaría nadie si se rompieran.

Más herramientas: **[zaque](https://github.com/isazajuancarlos/zaque)** (integridad de arranque) · **[autz](https://github.com/isazajuancarlos/autz)** (detección de control de acceso roto) · **[tequendama](https://github.com/isazajuancarlos/tequendama)** (ingestión de datos) · **[guardia-supresiones](https://github.com/isazajuancarlos/guardia-supresiones)** (supresiones honestas de `cargo-deny`) · **[escaner-android](https://github.com/isazajuancarlos/escaner-android)** / **[escaner-windows](https://github.com/isazajuancarlos/escaner-windows)** (escáneres de higiene de seguridad) · **[bochica](https://github.com/isazajuancarlos/bochica)** (cumplimiento Ley 1581) · **[mindala](https://github.com/isazajuancarlos/mindala)** (inteligencia técnica).

### Productos

Productos full-stack — un binario, una base por instancia, *offline-first*:

- **[medico](https://github.com/isazajuancarlos/medico)** — sistema de información para prestadores de salud en Colombia: historia clínica, facturación y la cadena RIPS → FEV-RIPS → MUV (Res. 948/2026).
- **[validador-rips](https://github.com/isazajuancarlos/validador-rips)** — validador de pre-vuelo: *«sube tu RIPS y te digo qué rechazaría MinSalud».* Gratis en **[rips.xiliux.com](https://rips.xiliux.com)**.
- **[informes](https://github.com/isazajuancarlos/informes)** — plataforma general de informes estructurados, con XBRL / iXBRL de primera clase.
- **[chasqui](https://github.com/isazajuancarlos/chasqui)** — atención automatizada por WhatsApp, Instagram y Messenger.
- **[bachue](https://github.com/isazajuancarlos/bachue)** — proveedor de identidad OpenID Connect.
- **[winext4](https://github.com/isazajuancarlos/winext4)** — ext4 nativo para Windows, sin WSL / sin VM (en desarrollo activo).

### Investigación de seguridad — divulgaciones públicas

Solo divulgación responsable y coordinada, siempre por el canal oficial de seguridad del proveedor:

- **OpenAM** — confusión de firma SAML 1.x (**CWE-347**), aviso `GHSA-j56q-q3r3-hg7f`.
- **midPoint / Evolveum** — control de acceso roto (**CWE-862**), divulgado.
- **Lean roadmap de Ethereum** — verificación diferencial y adversarial de las firmas hash-based del validador (XMSS generalizado) con mi arnés **[Iraca](https://github.com/isazajuancarlos/iraca)**: canonicidad, *malleability* e invariante de un-uso-por-epoch.
- Hallazgos adicionales de IDOR/BAC coordinados por programas de HackerOne e Intigriti.

### Profundidad, medida

> Si el código no siempre puede verse, la prueba de profundidad tiene que sostenerse sola. Estas lo hacen.

- **CI de cripto 9,8× más rápido** (598 s → 61 s) en quipu optimizando la compilación de dependencias — con el control que prueba que no fue el compilador.
- **Verificación independiente del PQC del NIST** contra implementaciones de referencia — arneses de ML-DSA, SLH-DSA y ML-KEM (**[Iraca-2](https://github.com/isazajuancarlos/iraca-2)** / **[3](https://github.com/isazajuancarlos/iraca-3)** / **[4](https://github.com/isazajuancarlos/iraca-4)**): decenas de miles de mutaciones, **cero** aceptadas; diferencial de cuatro vías entre lenguajes (Rust ↔ C de pq-crystals ↔ libcrux ↔ AWS-LC) verde byte a byte.
- **guecha**: un detector de inyección de *prompts* que discrimina — 28 pruebas unitarias + 33 de extremo a extremo pareadas, tres rondas de revisión adversaria, sub-milisegundo.

### Stack

`Rust` · `axum` · `SQLx` / `SQLite` · `maud` · `htmx` · *builds* sin Node · binario único · *offline-first* · una base de datos por instancia.

### Escritos

- **[No vienen por tu código](https://xiliux.com/blog/no-vienen-por-tu-codigo)** — por qué los grandes ataques de 2025–2026 golpean todo lo masivo (npm, el AUR, la Snap Store, GitHub, WordPress), y dónde debe vivir la verdad de tu software. Más ensayos: **[escritos](https://github.com/isazajuancarlos/escritos)**.

### Contacto

- 🌐 Portafolio y productos: **[xiliux.com](https://xiliux.com)**
- 🛒 Tienda: **[xiliux.lemonsqueezy.com](https://xiliux.lemonsqueezy.com)**
