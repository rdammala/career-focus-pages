# Resume & Portfolio Generation Workflow

## Trigger
User provides: JD + LinkedIn link + Career portal link

## MANDATORY Steps (Execute ALL in order)

### 1. Context Loading
- Load resume context from `C:\Users\v-rdammala\.copilot\resume-context.md`
- Fetch JD from career portal URL for salary/location/details
- Review existing company folder if it exists in `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\`

### 2. Create Company Folder
- Path: `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\<CompanyName>\`

### 3. Generate Job_Details.md
- Job link/URL, Company, Position, Location, Salary, Full JD, Application status tracker

### 4. Generate Resume (.docx + .pdf)
- Use Node.js with `docx` + `pdfkit` packages (installed in Resumes/2026/)
- Naming: `Rajesh_Dammala_<Company>_<RoleShortName>_v<N>.docx` / `.pdf`
- Tailor content to JD keywords and requirements
- Font: Calibri (docx) / Helvetica (pdf), 0.5in margins
- Sections: Name/Contact → Summary → Core Competencies → Selected Impact → Experience → Education → Technical Skills

### 5. Generate Cover Letter (.docx + .pdf)
- Naming: `Rajesh_Dammala_CoverLetter_<Company>_v<N>.docx` / `.pdf`
- Tailored to specific role/company, referencing JD requirements directly
- 4 paragraphs: hook + key strengths (2-3 bullet max) + passion/fit + close
- **Keep it concise and crisp** — NOT a second resume. Max ~250 words total.
- Avoid restating full experience details; instead highlight 2-3 strongest proof points
- Tone: confident, conversational, direct — not corporate-dense

### 6. Generate Portfolio Website
- Create in: `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\Repos\<RoleName>\`
- **Naming: Use the ROLE NAME (not company name)** — e.g., `Director-Technical-Support-Engineering`, `VP-SRE`, `Head-of-Support-Engineering`
  - Exception: RD-Profile is the generic one for Technical Support Director/VP/C-level
- Files: `index.html`, `style.css`, `script.js`, `README.md`
- Stack: Pure HTML/CSS/JS + Google Fonts (Inter) — no frameworks
- Theme: Dark (same variables as existing portfolios), but **vary styling slightly each time**:
  - Rotate accent colors (teal, purple, amber, emerald, rose)
  - Vary card layouts (grid vs masonry vs timeline-first)
  - Different hero designs (centered text, split-screen, full-bleed stats)
  - Alternate section ordering based on role emphasis
- Content: Generic (no company name in portfolio) — usable for multiple applications to similar roles
- Sections: Hero + About + Leadership Competencies + Experience + Impact + Initiatives + Philosophy + Education + Contact

### 7. Deploy to GitHub
- Use `gh` CLI (refresh PATH first: `$env:Path = [System.Environment]::GetEnvironmentVariable("Path","Machine") + ";" + [System.Environment]::GetEnvironmentVariable("Path","User")`)
- Create public repo: `gh repo create <RoleName> --public --source=. --push`
- Enable GitHub Pages: `gh api repos/rdammala/<RoleName>/pages -X POST -f "source[branch]=main" -f "source[path]=/"`
- Live URL: `https://rdammala.github.io/<RoleName>/`

### 8. Add Portfolio Link to Job_Details.md
- Open the company's `Job_Details.md` file
- Add a `## Portfolio` section (or inline `Portfolio:` line matching existing format) with the live GitHub Pages URL
- Place it just before the Application Status/Tracker section

### 9. Update Job Application Tracker
- File: `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\Job_Application_Tracker.html`
- Also in repo: `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\Repos\career-focus-pages\Job_Application_Tracker.html`
- Add a new entry to the `defaultApps` array in the `<script>` section with:
  - `portfolio`: The portfolio/repo name (e.g., `Senior-Manager-SRE`)
  - `role`: Exact role title from JD
  - `company`: Company name
  - `date`: Today's date (YYYY-MM-DD)
  - `link`: Portfolio GitHub Pages URL (e.g., `https://rdammala.github.io/<RoleName>/`)
  - `status`: `'Applied'`
  - `comments`: `''`
  - `id`: Next sequential number after existing entries
- After editing, copy the file to the career-focus-pages repo and push
- Live tracker: https://rdammala.github.io/career-focus-pages/Job_Application_Tracker.html

### 10. Embed Portfolio Link in Resume & Cover Letter
- **Why**: Many application portals don't have a "Portfolio URL" field — embedding it in the documents ensures recruiters always see it.
- **Resume (.docx + .pdf)**: Add a clickable hyperlink **below the contact info line** (centered, same font), formatted as:
  `Rajesh Dammala — <Role Title>` → hyperlinked to the portfolio GitHub Pages URL
  - Example: "Rajesh Dammala — Senior Manager, Site Reliability Engineering" → `https://rdammala.github.io/Senior-Manager-SRE/`
  - In the docx generation script: add a centered paragraph with hyperlink after the contact line
  - In the pdf generation script: use pdfkit `.text('Rajesh Dammala — <Role>', { link: portfolioUrl, underline: true, align: 'center' })`
- **Cover Letter (.docx + .pdf)**: Add the same clickable hyperlink as the **signature line** at the very end (after "Best regards,"):
  `Rajesh Dammala — <Role Title>` → hyperlinked to the portfolio GitHub Pages URL
  - In the docx generation script: make the closing name line a hyperlink to the portfolio
  - In the pdf generation script: use pdfkit `.text(...)` with `{ link: portfolioUrl }` on the signature line
- **Manual Steps (user does these after generation)**:
  1. Review Word documents for content accuracy
  2. Rename resume from `Rajesh_Dammala_<Company>_<Role>.docx` → `Rajesh_Dammala.docx` (or preferred name)
  3. Rename cover letter from `Rajesh_Dammala_CoverLetter_<Company>.docx` → `Rajesh_Dammala_CoverLetter.docx`
  4. Change file sensitivity from "Confidential-Internal" to "Public" (so recipients can open)
  5. These are intentional quality-gate checkpoints — do NOT automate them

## Job Application Tracker Details
- **3 tabs**: Applications, Networking Contacts, Portfolio Guide
- **Applications**: Table with portfolio, role, company, date, link, status, comments; search/filter/sort
- **Contacts**: Card grid with name, company, email, multi-phone (Call/WhatsApp/Other labels), LinkedIn, source, resume shared, comments, voice note + auto-transcript
- **Portfolio Guide**: All 9 portfolios with role fit descriptions and clickable links
- **Resume Shared dropdown** includes all 9 portfolios with role hints + General Resume
- **Data**: localStorage (`rd_job_tracker`, `rd_contacts`, `tracker_theme`); export/import as JSON
- **Voice notes**: MediaRecorder API + Web Speech API for auto-transcription; editable transcript saved to contact
- **GitHub repo**: `career-focus-pages` (master branch)

## Key References
- Resume context: `C:\Users\v-rdammala\.copilot\resume-context.md`
- Existing portfolios for styling reference: `https://rdammala.github.io/rajesh-dammala-portfolio/`
- Resumes base: `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\`
- npm packages already installed in Resumes/2026/ (docx, pdfkit)
- GitHub account: rdammala (authenticated via gh CLI with keyring)

## Style Variation Ideas (rotate per portfolio)
1. Blue/Teal gradient (used for RD-Profile) — dark navy bg
2. Purple/Violet gradient (used for Senior-Incident-Manager) — charcoal bg
3. Amber/Gold gradient (used for Staff-Escalation-Manager) — deep slate bg, split hero, masonry expertise, philosophy section
4. Emerald/Mint gradient (used for Technical-Lead-Deployment-Operations) — dark forest bg, full-bleed stats bar hero, timeline-first experience, operating principles section
5. Rose/Coral gradient (used for Manager-Cloud-Support) — midnight bg, centered about, 2x2 philosophy grid, 4-pillar row
6. Cyan/Electric Blue gradient (used for Senior-Manager-SRE) — deep space bg, metric cards hero, split about with signal cards, engineering approach section
7. Lime/Chartreuse gradient (used for Application-SRE-Manager) — dark charcoal bg, badge hero, timeline experience, numbered principles section
8. Indigo/Deep Blue gradient (used for Senior-IT-Systems-Operations-Manager) — dark slate bg, split hero with floating metrics, stacked exp cards, progress bar impact section
9. Magenta/Fuchsia gradient (used for TPM-Infrastructure) — dark obsidian bg, asymmetric split hero with floating stats panel, impact-featured card, numbered philosophy cards ✅
10. Next color TBD
