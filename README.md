# Hi, I'm Mark Kinuthia

**Full-stack developer in Kenya.** I build web apps end to end, from the database schema and API to the UI, the tests and the CI pipeline. I'm especially interested in AI that runs offline on ordinary hardware, so patient and business data never has to leave the machine.

Right now I'm building an **offline clinical consultation assistant**: local speech recognition with Whisper, a quantized medical LLM and an encrypted local database, all on a desktop with no internet connection.

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?logo=php&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?logo=django&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?logo=nextdotjs&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-FF2D20?logo=laravel&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?logo=githubactions&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-844FBA?logo=terraform&logoColor=white)

---

## Featured projects

### [socialNET Intelligence](https://github.com/kinuthia-mark/Social-intelligence)

Brand monitoring dashboard: mentions, sentiment, crisis alerts, PDF reports and a data assistant. **Next.js 16 + TypeScript** frontend, **Django REST Framework** API.

<a href="https://github.com/kinuthia-mark/Social-intelligence"><img src="https://raw.githubusercontent.com/kinuthia-mark/Social-intelligence/main/docs/screenshots/dashboard.png" alt="socialNET dashboard" width="100%"></a>

- Wrote a sentiment and risk engine from scratch: handles negation, intensifiers, emoji and shouting, finds risk terms such as "recall" or "lawsuit", and agrees with 7 of 8 hand-labelled posts
- JWTs never reach page scripts: Next.js route handlers keep them in httpOnly cookies, with refresh-token rotation and blacklisting
- 30 API tests, type check, production build and a full Docker Compose run in CI

---

### [eQueue](https://github.com/kinuthia-mark/Equeue-project)

Digital queue for government service offices. Applicants join from their phone, see how many people are ahead and how long they have left, and get an email when they are called. A TV board in the waiting room shows who is being served. **Laravel 12**.

<a href="https://github.com/kinuthia-mark/Equeue-project"><img src="https://raw.githubusercontent.com/kinuthia-mark/Equeue-project/main/docs/screenshots/board.png" alt="eQueue waiting-room display board" width="100%"></a>

- Wait estimates learned per service from real `called_at` / `completed_at` history
- Race-safe: queue numbers and "call next" run in locked database transactions, so two officers can never call the same person
- 25 feature tests on PHP 8.2 and 8.3, Pint style check, and a Docker image started and checked in CI

---

### [DevSecOps Security Gate](https://github.com/kinuthia-mark/Devsec-gate)

CI/CD gate that blocks builds only on vulnerabilities that can actually be exploited, with severity-based fix deadlines. **Open Policy Agent (Rego), Python, Terraform, GitHub Actions**.

```
Trivy scan ─► normalize-trivy.py (+ CISA Known Exploited list) ─► OPA policy ─► pass / block + Jira ticket
```

- Gates the real container image on every push, not just sample data
- 14 Rego policy tests and 12 pytest tests; Terraform checked with TFLint and Checkov
- Found and fixed bugs in my own earlier version: SLA breaches never reached the report, and false positives still blocked builds

---

### [Nyumbani Website Rebuild](https://github.com/kinuthia-mark/Nyumbani-website-rebuild)

Website and content admin for a children's home in Kenya. **PHP 8 + MariaDB**.

<a href="https://github.com/kinuthia-mark/Nyumbani-website-rebuild"><img src="https://raw.githubusercontent.com/kinuthia-mark/Nyumbani-website-rebuild/main/docs/screenshots/blog.png" alt="Nyumbani blog page" width="100%"></a>

- Hashed passwords, prepared statements, safe uploads, CSRF tokens on every admin form, and no state change ever triggered by a plain link
- A Playwright browser test drives the whole admin against a real database in CI, including forged requests that must be refused
- Runs with one `docker compose up`

---

### More

| Project | What it is | Built with |
|---|---|---|
| [Medical-Pro](https://github.com/kinuthia-mark/MedicalProV1) | Desktop app that turns a doctor-patient transcript into a SOAP note, with copy and save. 30 headless unit tests and a screenshot rendered in CI | Godot 4, GDScript, Gemini API |
| [Comfort Executive Suites](https://github.com/kinuthia-mark/comfort-website) | Live website for a hotel in Ongata Rongai ([view site](https://kinuthia-mark.github.io/comfort-website/)). Validated HTML, lazy-loaded photos, CI with link checks and an image size limit | HTML, CSS |
| [Offline Clinical Consultation Assistant](https://github.com/kinuthia-mark/Offline-Desktop-Based-Medical-Professional-Clinical-Consultation-Assistant-) | Records a consultation, transcribes it and drafts clinical notes, fully offline (in progress) | Python, Whisper, local LLM, SQLCipher |

---

## What I work with

| Area | Tools |
|---|---|
| Languages | Python, TypeScript / JavaScript, PHP, SQL, C#, Java, GDScript |
| Backend | Django REST Framework, Laravel, Node.js |
| Frontend | Next.js, React, Tailwind CSS, Bootstrap, TanStack Query |
| Data | MySQL / MariaDB, SQLite, SQLCipher, Firebase |
| AI | Whisper, local LLMs (GGUF quantization, Ollama), Gemini API, lexicon-based NLP |
| Testing | PHPUnit, pytest, Django test runner, Playwright, OPA test |
| DevOps and security | Docker, GitHub Actions, Terraform, Open Policy Agent, Checkov, TFLint, Trivy |

## How I build

- **Tests and CI from the start.** Every project here runs its checks on each push, and the Docker setups are started and exercised in CI, not just built.
- **Security by default.** Secrets in environment variables, CSRF on every form, prepared statements, unguessable links, least-privilege database users.
- **READMEs that explain the system**, with architecture diagrams, data models and screenshots, not just install steps.
