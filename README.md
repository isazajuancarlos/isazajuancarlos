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

Tools I sell self-serve at **[xiliux.lemonsqueezy.com](https://xiliux.lemonsqueezy.com)** — single binary, offline, no telemetry:

- **Xué** — MCP prompt-injection scanner. Catches obfuscation (bidi / zero-width / homoglyphs) and indirect injection in agent inputs.
- **Chaquén** — MCP secret scanner. Finds credentials, tokens and keys before they're committed — including secrets deleted from the tree but still alive in git history.
- **sin-caso-rojo** — diff coverage gap finder. Reverts each hunk and runs your suite: tells you exactly which lines nothing would catch if they broke.

### Security research — public disclosures

Responsible, coordinated disclosure only, always through the vendor's official security channel:

- **OpenAM** — SAML 1.x signature confusion (**CWE-347**), advisory `GHSA-j56q-q3r3-hg7f`.
- **midPoint / Evolveum** — broken access control (**CWE-862**), disclosed.
- **Ethereum Lean roadmap** — differential and adversarial verification of the validator hash-based signatures (generalized XMSS) with my harness **Iraca**: canonicity, malleability, and the one-time-per-epoch invariant.
- Additional IDOR/BAC findings coordinated through HackerOne and Intigriti programs.

### Depth, measured

> If the code can't always be seen, the proof of depth has to stand on its own. These do.

- **9.8× faster crypto CI** (598 s → 61 s) on quipu by optimizing dependency builds — with the control that proves it wasn't the compiler.
- **Independent verification of NIST PQC** against reference implementations: ML-DSA, SLH-DSA and ML-KEM harnesses (Iraca-2/3/4) — tens of thousands of mutations, **zero** accepted; cross-language differential (Rust ↔ pq-crystals C) green byte-for-byte.
- A deterministic alternative to expensive AI code review (sin-caso-rojo) that reproduced a real finding on its own.

### Stack

`Rust` · `axum` · `SQLx` / `SQLite` · `maud` · `htmx` · zero-Node builds · single binary · offline-first · one database per instance.

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

Herramientas que vendo en autoservicio en **[xiliux.lemonsqueezy.com](https://xiliux.lemonsqueezy.com)** — binario único, offline, sin telemetría:

- **Xué** — escáner de inyección de *prompts* por MCP. Caza ofuscación (bidi / ancho-cero / homóglifos) e inyección indirecta en las entradas de un agente.
- **Chaquén** — escáner de secretos por MCP. Encuentra credenciales, tokens y llaves antes de que se suban — incluidos los secretos borrados del árbol pero vivos en la historia de git.
- **sin-caso-rojo** — detector de huecos de cobertura en un diff. Revierte cada *hunk* y corre tu banco de pruebas: te dice exactamente qué líneas no vigilaría nadie si se rompieran.

### Investigación de seguridad — divulgaciones públicas

Solo divulgación responsable y coordinada, siempre por el canal oficial de seguridad del proveedor:

- **OpenAM** — confusión de firma SAML 1.x (**CWE-347**), aviso `GHSA-j56q-q3r3-hg7f`.
- **midPoint / Evolveum** — control de acceso roto (**CWE-862**), divulgado.
- **Lean roadmap de Ethereum** — verificación diferencial y adversarial de las firmas hash-based del validador (XMSS generalizado) con mi arnés **Iraca**: canonicidad, *malleability* e invariante de un-uso-por-epoch.
- Hallazgos adicionales de IDOR/BAC coordinados por programas de HackerOne e Intigriti.

### Profundidad, medida

> Si el código no siempre puede verse, la prueba de profundidad tiene que sostenerse sola. Estas lo hacen.

- **CI de cripto 9,8× más rápido** (598 s → 61 s) en quipu optimizando la compilación de dependencias — con el control que prueba que no fue el compilador.
- **Verificación independiente del PQC del NIST** contra implementaciones de referencia: arneses de ML-DSA, SLH-DSA y ML-KEM (Iraca-2/3/4) — decenas de miles de mutaciones, **cero** aceptadas; diferencial entre lenguajes (Rust ↔ C de pq-crystals) verde byte a byte.
- Una alternativa determinista a la revisión de código cara con IA (sin-caso-rojo) que reprodujo un hallazgo real por sí sola.

### Stack

`Rust` · `axum` · `SQLx` / `SQLite` · `maud` · `htmx` · *builds* sin Node · binario único · *offline-first* · una base de datos por instancia.

### Contacto

- 🌐 Portafolio y productos: **[xiliux.com](https://xiliux.com)**
- 🛒 Tienda: **[xiliux.lemonsqueezy.com](https://xiliux.lemonsqueezy.com)**
