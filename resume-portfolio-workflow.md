# Resume & Portfolio Generation Workflow

## Change Log
- Time zone standard: **All change log timestamps are recorded in PST/PDT (Pacific Time).**
- 2026-06-18 03:15 PM PST/PDT: Added dual-resume strategy steps (3.5, 5.5, 13) clarifying 2-page ATS application resume vs 4-5 page comprehensive portfolio CV.
- 2026-06-17 07:24 PM PST/PDT: Added Portfolio UX Baseline and Tracker Reliability Rules (defaultApps merge behavior, Last Updated local-time handling, and `rd_tracker_meta`/`lastUpdatedMs` data key guidance).

## Trigger
User provides: JD + LinkedIn link + Career portal link

## Resume Package Strategy (CRITICAL FOR QUALITY)
**All resumes prioritize ATS keyword optimization with role-specific terminology, strong action verbs (architected, engineered, deployed, accelerated), and measurable business impact.**

### Three-Part Resume Delivery Model:
1. **Company Portal / Referral Resume (2 pages maximum)**
   - Purpose: Online application systems, recruiter submissions, ATS scanning
   - Requirements: Strict 2-page limit, high keyword density, role-specific jargon, no graphics/tables
   - Naming: `Rajesh_Dammala_<Company>_<RoleShortName>_v<N>.docx`
   - Content Strategy: Lead with quantified outcomes, embed 7-12 role-specific keywords per bullet, use acronyms (not spelled-out), prioritize recruiter/ATS relevance over narrative flow

2. **Cover Letter (1 page exactly)**
   - Purpose: Accompanies 2-page resume in formal submissions
   - Requirements: ~250 words, matching terminology to resume, addresses key role responsibilities
   - Naming: `Rajesh_Dammala_CoverLetter_<Company>_v<N>.docx`
   - Content Strategy: Conversational tone, 2-3 strongest proof points only, position as complement to resume (not repetition)

3. **Portfolio "Resume" Download (4-5 pages comprehensive CV)**
   - Purpose: Portfolio website "Resume" button → allows deeper context viewing
   - Requirements: Full skillset coverage, extensive work history, educational background, all quantified metrics
   - Naming: `Rajesh_Dammala_<Role>_Complete_CV.docx` or `.pdf`
   - Content Strategy: Can include graphics/detailed layouts, position as "full professional profile," comprehensive but focused, reference-grade document

### Quality Baseline Across All Resumes:
- Extract high-impact keywords from role-specific research (market benchmarks, company examples, salary positioning, job description analysis)
- Density target: 1.2-1.5 role-specific keywords per bullet point
- Action verb minimum: 4+ distinct strong verbs per role bullet (architected, engineered, deployed, accelerated, optimized, customized, integrated, orchestrated, designed)
- Quantified outcomes: ≥80% of bullets include measurable impact (%, time saved, cost reduction, customer impact, scope, team size)
- ATS formatting: Standard fonts (Calibri/Helvetica), 0.5in margins, clear heading hierarchy, no tables/graphics in 2-page version

### When This Model Applies:
- Use 2-page + 1-page cover letter for **all external company submissions** (career portal, recruiter referral, direct application)
- Use 4-5 page CV for **portfolio website downloads** (when someone clicks "Resume" button on portfolio site)
- For role-specific portfolios: **Always include "Download Resume" button in hero linking to the 4-5 page CV** (ensures portfolio visitors see comprehensive profile)

## MANDATORY Steps (Execute ALL in order)
**Total Steps: 15 (includes writing guidelines + sponsorship check + dual-resume strategy)**

### 1. Context Loading
- Load resume context from `C:\Users\v-rdammala\.copilot\resume-context.md`
- Fetch JD from career portal URL for salary/location/details
- Review existing company folder if it exists in `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\`

### 1.5. CRITICAL: Check Visa/Sponsorship Eligibility
**⚠️ CRITICAL:** Before creating resumes, verify work authorization requirements in the JD. If they conflict with your eligibility, skip this application.

#### Keywords to Search in JD
Look for these exact terms or phrases (use Ctrl+F):
- "sponsorship", "will not sponsor", "no sponsorship"
- "H1B", "visa sponsorship", "visa willing"
- "Green Card", "GC", "Green Card required"
- "US Citizen", "USC", "citizenship required"
- "work authorization", "employment eligible"
- "TN visa", "L1", "O1", "EB-1C"
- "existing visa holder", "OPT", "STEM OPT"

#### Common Scenarios & What to Do

**Scenario 1: "No Sponsorship" or "No Visa Required"**
- What JD says: "Company will NOT sponsor visa/H1B" OR "Only US Citizens"
- ❌ If you NEED sponsorship → **SKIP this application** (proceed to next job)
- ✅ If you have Green Card/USC → **PROCEED** to Step 2
- **Action:** Ask yourself: "Do I have work authorization without sponsorship?" If NO, skip. If YES, continue.

**Scenario 2: "H1B OK" or "Visa Sponsorship Available"**
- What JD says: "Willing to sponsor H1B" OR "Visa sponsorship available"
- ✅ If you have H1B, OPT, or STEM OPT → **PROCEED** to Step 2
- ✅ If you have Green Card/USC → **PROCEED** to Step 2 (even better fit)
- ❌ If you have no work authorization → **SKIP this application**
- **Action:** Confirm your current visa status allows this role.

**Scenario 3: "Green Card Only" or "Existing Visa Holder"**
- What JD says: "Green Card holder preferred" OR "Existing visa holders only"
- ✅ If you have Green Card/USC → **PROCEED** to Step 2
- ❌ If you have H1B/OPT/no status → **SKIP this application**
- **Action:** If you don't match, move to next opportunity.

**Scenario 4: "USC/Citizenship Required"**
- What JD says: "US Citizen Only" OR "Citizenship required" (often DoD/government contracts)
- ✅ If you are USC → **PROCEED** to Step 2
- ❌ If you are not USC → **SKIP this application**
- **Action:** Only apply if you hold US citizenship.

**Scenario 5: "Not Mentioned" or "Flexible"**
- What JD says: No mention of visa/sponsorship requirements OR "Flexible for right candidate"
- ✅ **PROCEED** to Step 2 (most flexible scenario)
- **Action:** Apply with confidence; no blocker identified.

#### Decision Checklist
Before moving to Step 2, confirm:
- [ ] I found visa/sponsorship language in the JD (or confirmed it's not mentioned)
- [ ] I understand what work authorization they require (H1B OK, GC only, USC only, no sponsorship, etc.)
- [ ] My current work status matches or exceeds their requirement
- [ ] I am comfortable proceeding to resume creation
- [ ] If any doubt → **ASK** before proceeding (don't apply to jobs you're not eligible for)

#### Red Flags to Watch
- "No visa sponsorship" + you need visa = ❌ SKIP
- "US Citizens only" + you're not USC = ❌ SKIP
- "Green Card required" + you have H1B = ❌ SKIP (unless you're getting GC soon)
- "Existing visa holders only" + you're USC = ✅ PROCEED (you exceed requirement)
- "Flexible" + any status = ✅ PROCEED (apply with full confidence)

### 2. Create Company Folder
- Path: `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\<CompanyName>\`

### 3. Generate Job_Details.md
- Job link/URL, Company, Position, Location, Salary, Full JD, Application status tracker

### 3.5. Resume Writing Guidelines: Inference vs. Fabrication
**⚠️ CRITICAL:** Intelligent inference of related technologies is ENCOURAGED, but complete fabrication is NOT allowed.

#### ALLOWED: Smart Inference Across Tech Families

**Cloud Platforms (AWS ↔ Azure ↔ GCP):**
- JD says: "AWS EC2, RDS, S3, CloudWatch"
- You CAN write: "Cloud compute (AWS EC2, Azure VMs), databases (AWS RDS, Azure SQL/Cosmos), object storage (S3, Blob Storage), observability (CloudWatch, Azure Monitor)"
- Why: All three clouds use parallel service patterns; you're mapping your Azure knowledge to AWS terminology

**Container Orchestration (Kubernetes variants):**
- JD says: "Kubernetes (e.g., EKS), Docker containers"
- You CAN write: "Kubernetes (EKS, AKS, GKE), containerization (Docker, containerd), registries (ECR, Azure Container Registry)"
- Why: EKS/AKS/GKE are all Kubernetes — your AKS experience transfers

**Infrastructure as Code (IaC):**
- JD says: "Infrastructure as code tools like Terraform"
- You CAN write: "Infrastructure as code (Terraform, Bicep, ARM Templates, CloudFormation)"
- Why: All serve the same purpose; Bicep + ARM are Azure equivalents to Terraform

**Databases & Data Stores:**
- JD says: "PostgreSQL, data analytics"
- You CAN write: "Relational databases (PostgreSQL, SQL Server, Azure SQL), analytics (Kusto/ADX, Azure Data Explorer), NoSQL (Cosmos DB)"
- Why: Mapping database types and analytical tools you know

**Observability & Monitoring:**
- JD says: "CloudWatch, logging"
- You CAN write: "Observability (CloudWatch, Azure Monitor, Application Insights), structured logging (Log Analytics, KQL), distributed tracing"
- Why: All are monitoring/telemetry platforms with overlapping concepts

#### NOT ALLOWED: Complete Fabrication

**❌ False Claim Examples:**
- You've never touched Node.js → do NOT write "Node.js backend development"
- You've never used Jenkins → do NOT write "CI/CD pipeline development with Jenkins"
- You've never worked with Rust → do NOT write "Systems programming in Rust"
- You've only used Azure, never AWS → do NOT write "AWS infrastructure design" with zero AWS experience

**✅ Honest Alternatives:**
- Instead of fabricating Node.js: Focus on overlapping areas ("API design, microservices architecture, event-driven systems")
- Instead of fabricating Jenkins: Highlight actual tools ("CI/CD pipeline design using Azure DevOps/GitHub Actions")
- Instead of fabricating Rust: Emphasize systems thinking ("performance optimization, memory management, low-level integration")

#### Decision Framework
**Before adding any technology to resume/cover letter, ask:**
1. **Have I used this exact tool?** → YES: Include it explicitly
2. **Have I used a parallel/equivalent tool in the same family?** → YES: Include with mapping (e.g., "Terraform/Bicep")
3. **Have I worked with closely related concepts?** → YES: Frame around the concept, not the tool (e.g., "CI/CD design" vs. "Jenkins")
4. **None of the above?** → NO: Omit completely — do NOT fabricate

### 3.6. CRITICAL: Understand the Dual-Resume Strategy
**This is NOT a single resume. You will generate TWO different resumes for every application.**

#### Resume #1: Application Resume (2 pages strict + 1-page cover letter)
- **Purpose:** Submitted to career portals, ATS systems, recruiter submissions
- **Format:** 
  - Resume: Exactly 2 pages (no more, no less)
  - Cover Letter: Exactly 1 page (~250 words)
- **Quality Standard:** 
  - ✅ ATS-optimized (keyword-rich, role-specific terminology)
  - ✅ High keyword density (1.2-1.5 keywords per bullet)
  - ✅ Strong action verbs (architected, engineered, deployed, accelerated, optimized)
  - ✅ ≥80% of bullets include measurable impact (%, time, cost, scope, team size)
  - ✅ Clean formatting: standard fonts (Calibri/Helvetica), no graphics/tables, clear hierarchy
  - ✅ Tailored to company JD (mirror keywords, match terminology)
  - ✅ Designed for recruiter scanning in 6-8 seconds
- **Naming Convention:**
  - Resume: `Rajesh_Dammala_<Company>_<RoleShortName>_v<N>.docx` / `.pdf`
  - Cover Letter: `Rajesh_Dammala_CoverLetter_<Company>_v<N>.docx` / `.pdf`

#### Resume #2: Portfolio Download Resume (4-5 pages comprehensive CV)
- **Purpose:** Available as downloadable file via "Resume" button on portfolio website
- **Format:**
  - 4-5 pages (no strict page limit)
  - Comprehensive, reference-grade professional CV
- **Content Coverage (comprehensive):**
  - Full work history (all roles, dates, detailed impact)
  - All quantified achievements and metrics
  - Educational background (degree, certifications, relevant training)
  - Complete technical skills breakdown
  - Optional: Industry recognitions, speaking engagements, publications
  - Can include role-specific case studies or deep-dive projects
- **Quality Standard:**
  - ✅ Extensively tailored to role-specific JD and portfolio theme
  - ✅ Can include graphics, visual layout, colored accents (matches portfolio design)
  - ✅ Comprehensive but focused (no filler)
  - ✅ Reference-grade (suitable for executive-level conversation)
  - ✅ Same strong action verbs and measurable impact as 2-page version
  - ✅ Branded (matches portfolio aesthetic)
- **Naming Convention:**
  - `Rajesh_Dammala_<Role>_Complete_CV.docx` / `.pdf`
  - Example: `Rajesh_Dammala_Senior-Manager-SRE_Complete_CV.pdf`
  - Store in portfolio repo alongside index.html, style.css, script.js
- **Availability:**
  - Linked from portfolio "Resume" button (hero section)
  - Always available for download on public portfolio site
  - Used by portfolio visitors for deeper research

#### Quick Decision Matrix

| Scenario | Which Resume? |
|----------|---------------|
| Applying to company via career portal | Resume #1 (2-page) |
| Submitting to recruiter | Resume #1 (2-page) |
| ATS system scanning | Resume #1 (2-page) |
| Portfolio visitor clicks "Resume" button | Resume #2 (4-5 page CV) |
| Email follow-up with hiring manager | Resume #1 (2-page) |
| Portfolio-to-interview discussion | Resume #2 (4-5 page CV) |

**KEY CONSTRAINT:** Do NOT use 4-5 page CV for job portals. It will be rejected by ATS. Always use 2-page version for applications.

### 4. Generate Resume #1 (.docx + .pdf) — 2-Page Application Version (from Step 3.6 strategy)
- Use Node.js with `docx` + `pdfkit` packages (installed in Resumes/2026/)
- Naming: `Rajesh_Dammala_<Company>_<RoleShortName>_v<N>.docx` / `.pdf`
- Tailor content to JD keywords and requirements
- **Remember Step 3.5 Writing Guidelines:** Infer tech families smartly (AWS/Azure, Terraform/Bicep), but never fabricate experience
- **Modern Template Touches:**
  - Professional header with subtle color accent or border (light gray line, 2-3pt)
  - Name in 14-16pt bold, title/role below in 11pt italic
  - Section dividers: Clean horizontal lines or left-side accent bar
  - Subtle background for key sections (light gray 5-10% opacity)
  - Professional spacing: 0.5in top/bottom, 0.5in left/right margins
  - Font: Calibri (docx) / Helvetica (pdf), body 10-11pt, headers 12-14pt
- **Sections Layout:** Name/Title → Contact Info → Professional Summary → Core Competencies (2-3 columns) → Selected Impact (highlight box) → Experience → Education → Technical Skills
- **ATS Optimization Checklist:**
  - [ ] No graphics (except subtle header line/bar — keep minimal)
  - [ ] No tables or complex formatting
  - [ ] Standard headings (Professional Summary, Core Competencies, Experience, Education, Technical Skills)
  - [ ] Action-verb rich bullets with quantified impact
  - [ ] Keywords from JD appear 1.2-1.5x throughout resume
  - [ ] Font size 10-11pt body text (readable by ATS scanners)
  - [ ] 1.0-1.15 line spacing for compact formatting
  - [ ] Color accents subtle (light gray or single brand color, not competing with text)

### 5. Generate Cover Letter (.docx + .pdf)
- Naming: `Rajesh_Dammala_CoverLetter_<Company>_v<N>.docx` / `.pdf`
- Tailored to specific role/company, referencing JD requirements directly
- 4 paragraphs: hook + key strengths (2-3 bullet max) + passion/fit + close
- **Keep it concise and crisp** — NOT a second resume. Max ~250 words total.
- Avoid restating full experience details; instead highlight 2-3 strongest proof points
- Tone: confident, conversational, direct — not corporate-dense

### 5.5. Generate Resume #2 (.docx + .pdf) — 4-5 Page Portfolio Download Version (from Step 3.6 strategy)
**This is the "comprehensive CV" for portfolio website download — NOT for job applications.**
**Remember Step 3.5 Writing Guidelines:** Smart inference across tech families OK; fabrication NOT OK
**⚠️ CRITICAL:** Must include ATS-ready keywords while maintaining comprehensive CV format.

- **Location:** Store in portfolio repo folder: `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\Repos\<RoleName>\Rajesh_Dammala_<Role>_Complete_CV.pdf`
- **Naming:** `Rajesh_Dammala_<Role>_Complete_CV.docx` / `.pdf` (e.g., `Rajesh_Dammala_Senior-Manager-SRE_Complete_CV.pdf`)
- **Length:** 4-5 pages (comprehensive, no page restrictions)
- **Content Strategy (COMPREHENSIVE + ATS-OPTIMIZED):**
  - ✅ Full career history (all roles, dates, detailed scope and impact)
  - ✅ **ATS Keywords embedded naturally:** Use role-specific terminology 1.5-2x throughout (more densely than 2-page version)
  - ✅ All quantified achievements and metrics (no abbreviated bullets)
  - ✅ Complete technical skills with proficiency levels — **list all skill keywords from JD**
  - ✅ Educational background, certifications, continuous learning — **include all cert acronyms (AWS, CKA, PMP, etc.)**
  - ✅ Optional: Industry recognitions, speaking engagements, patents, publications
  - ✅ Role-specific case studies or deep-dive projects (2-3 examples) — **case study titles should match JD keywords**
  - ✅ Leadership philosophy or operating principles (if applicable to role) — **weave in role keywords**
- **ATS Keyword Strategy (Dual-Purpose):**
  - Extract all keywords from JD and target industry benchmarks
  - Embed keywords naturally in section headers, bullet points, and skill callouts
  - Use full terminology (not abbreviations) in first mention, then abbreviation (e.g., "Site Reliability Engineering (SRE)")
  - Repeat 1.5-2x keyword density (higher than 2-page version because this is comprehensive)
  - Example: For SRE role, include: "incident management", "on-call rotation", "deployment pipeline", "monitoring infrastructure", "observability", "service mesh", "Kubernetes", "container orchestration", etc. throughout the document
- **Design & Formatting (comprehensive + visual, NOT ATS-stripped):**
  - ✅ CAN include colored text, subtle graphics, visual hierarchy
  - ✅ Match portfolio aesthetic (same accent color, font family)
  - ✅ Professional layout (can use two-column format, accent bars, timeline view for experience)
  - ✅ Font: Same family as portfolio (e.g., Inter, Calibri, or matching theme)
  - ✅ Margins: 0.6-0.75in (slightly more generous than 2-page version)
  - ✅ Visual callout boxes for "Key Achievements", "Technical Stack", "Leadership Metrics"
- **Content Emphasis (differs by portfolio/role) + Keywords:**
  - For SRE roles: Emphasize operational metrics (MTTR, MTTF, SLA %), incident management scale, automation impact — use SRE-specific keywords throughout
  - For incident management roles: Detail escalation frameworks, crisis response examples, team leadership — use incident/escalation terminology
  - For engineering management: Highlight team scale, hiring/mentorship, strategic initiatives — use leadership/scale keywords
- **Quality Bar:**
  - Same strong action verbs as 2-page version
  - ≥90% of bullets include measurable impact
  - ≥1.5-2x keyword density (ATS-ready for parsing)
  - Reference-grade document suitable for C-level executive conversation
  - Branded to match portfolio theme
  - **Can be ATS-scanned** (keywords will be found) AND beautifully designed
- **Storage & Linking:**
  - Store alongside `index.html`, `style.css`, `script.js` in portfolio repo
  - Link from portfolio "Resume" button (hero section): `href="./Rajesh_Dammala_<Role>_Complete_CV.pdf"`
  - Ensure PDF is included in git commit and pushed to GitHub
  - Test link before marking portfolio live

### 6. Generate Portfolio Website
- Create in: `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\Repos\<RoleName>\`
- **Naming: Use the ROLE NAME (not company name)** — e.g., `Director-Technical-Support-Engineering`, `VP-SRE`, `Head-of-Support-Engineering`
  - Exception: RD-Profile is the generic one for Technical Support Director/VP/C-level
- Files: `index.html`, `style.css`, `script.js`, `README.md`, `Rajesh_Dammala_<Role>_Complete_CV.pdf` (from step 5.5)
- Stack: Pure HTML/CSS/JS + Google Fonts (Inter) — no frameworks
- Theme: Dark (same variables as existing portfolios), but **vary styling slightly each time**:
  - Rotate accent colors (teal, purple, amber, emerald, rose)
  - Vary card layouts (grid vs masonry vs timeline-first)
  - Different hero designs (centered text, split-screen, full-bleed stats)
  - Alternate section ordering based on role emphasis
- Content: Generic (no company name in portfolio) — usable for multiple applications to similar roles
- Sections: Hero + About + Leadership Competencies + Experience + Impact + Initiatives + Philosophy + Education + Contact

### 6.5. CRITICAL: GitHub Repo Naming Convention (Company + Role)
**⚠️ IMPORTANT FOR TRACKING:** GitHub repo names must include BOTH company name and role for easy tracking and deletion.

- **GitHub Repo Naming Pattern:** `<CompanyName>_<RoleName>`
- **Examples:**
  - `Snowflake_Staff-Escalation-Manager`
  - `Databricks_Senior-Manager-SRE`
  - `Google_Manager-Cloud-Support`
  - `Amazon_Technical-Lead-Deployment-Operations`
- **Why:** Makes it easy to identify which company each portfolio was for, and simplifies bulk deletion when you want to clean up old applications
- **Local folder naming:** Still use just `<RoleName>` for the local Repos folder (e.g., `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\Repos\Staff-Escalation-Manager\`)
- **But GitHub repo name:** Use `<CompanyName>_<RoleName>` (e.g., `Snowflake_Staff-Escalation-Manager`)
- **Portfolio domain:** Still `https://rdammala.github.io/<CompanyName>_<RoleName>/` (GitHub will auto-create based on repo name)

### 7. Deploy to GitHub
- Use `gh` CLI (refresh PATH first: `$env:Path = [System.Environment]::GetEnvironmentVariable("Path","Machine") + ";" + [System.Environment]::GetEnvironmentVariable("Path","User")`)
- Create public repo with COMPANY + ROLE naming: `gh repo create <CompanyName>_<RoleName> --public --source=. --push`
  - Example: `gh repo create Snowflake_Staff-Escalation-Manager --public --source=. --push`
- Enable GitHub Pages: `gh api repos/rdammala/<CompanyName>_<RoleName>/pages -X POST -f "source[branch]=main" -f "source[path]=/"`
  - Example: `gh api repos/rdammala/Snowflake_Staff-Escalation-Manager/pages -X POST -f "source[branch]=main" -f "source[path]=/"`
- Live URL: `https://rdammala.github.io/<CompanyName>_<RoleName>/`
  - Example: `https://rdammala.github.io/Snowflake_Staff-Escalation-Manager/`

### 8. Add Portfolio Link to Job_Details.md
- Open the company's `Job_Details.md` file
- Add a `## Portfolio` section (or inline `Portfolio:` line matching existing format) with the live GitHub Pages URL
- **Use the company+role GitHub URL:** `https://rdammala.github.io/<CompanyName>_<RoleName>/`
  - Example: `https://rdammala.github.io/Snowflake_Staff-Escalation-Manager/`
- Place it just before the Application Status/Tracker section

### 9. Update Job Application Tracker
- File: `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\Job_Application_Tracker.html`
- Also in repo: `C:\Users\v-rdammala\OneDrive - Microsoft\Desktop\Personal\Resumes\2026\Repos\career-focus-pages\Job_Application_Tracker.html`
- Add a new entry to the `defaultApps` array in the `<script>` section with:
  - `portfolio`: The portfolio/repo name using company+role (e.g., `Snowflake_Staff-Escalation-Manager`)
  - `role`: Exact role title from JD
  - `company`: Company name
  - `date`: Today's date (YYYY-MM-DD)
  - `link`: Portfolio GitHub Pages URL with company+role (e.g., `https://rdammala.github.io/Snowflake_Staff-Escalation-Manager/`)
  - `status`: `'Applied'`
  - `comments`: `''`
  - `id`: Next sequential number after existing entries
- After editing, copy the file to the career-focus-pages repo and push
- Live tracker: https://rdammala.github.io/career-focus-pages/Job_Application_Tracker.html

### 10. Embed Portfolio Link in Resume #1 & Cover Letter (Application Versions)
- **Why**: Many application portals don't have a "Portfolio URL" field — embedding it in the documents ensures recruiters always see it.
- **IMPORTANT:** This applies to Resume #1 (2-page application version), NOT the 4-5 page portfolio CV.
- **Resume #1 (.docx + .pdf)**: Add a clickable hyperlink **below the contact info line** (centered, same font), formatted as:
  `Rajesh Dammala — <Role Title>` → hyperlinked to the portfolio GitHub Pages URL
  - Example: "Rajesh Dammala — Senior Manager, Site Reliability Engineering" → `https://rdammala.github.io/Snowflake_Staff-Escalation-Manager/`
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

### 11. Portfolio UX Baseline (MANDATORY)
- Every role-based portfolio must include a **Download Resume** button in the hero section linking to the **4-5 page comprehensive CV** (Resume #2 from step 5.5): `Rajesh_Dammala_<Role>_Complete_CV.pdf`
  - Button label: "Download My Resume" or "View Full Resume"
  - File path: `./Rajesh_Dammala_<Role>_Complete_CV.pdf` (relative link in same repo)
  - This is the PORTFOLIO version (4-5 pages, comprehensive), NOT the 2-page application version
- Every role-based portfolio must include a **Dark/Light mode toggle** with localStorage persistence.
- Every role-based portfolio must use the **RD tab icon** (`favicon.svg`) instead of default globe favicon.
- **GitHub repo name displays correctly** as `<CompanyName>_<RoleName>` in your GitHub account for easy tracking
- After publishing to GitHub Pages, verify these 4 items live on the public URL:
  - [ ] Resume button downloads the 4-5 page PDF successfully
  - [ ] Dark/Light toggle works and persists on page reload
  - [ ] Favicon displays correctly (RD icon in browser tab)
  - [ ] GitHub repo name (e.g., Snowflake_Staff-Escalation-Manager) visible in your repos list

### 12. Tracker Reliability Rules (MANDATORY)
- Keep `defaultApps` syntactically valid; do not leave trailing/standalone commas that break array parsing.
- `loadApps()` must **merge missing `defaultApps` entries into existing localStorage data** so new applications appear for returning users.
- Tracker header must show **Last Updated** badge using local system time (not UTC-only display).
- Last-updated metadata key: `rd_tracker_meta` with `lastUpdatedMs` (epoch ms).
- If `rd_tracker_meta` is missing, seed it from the newest available app/contact date on init.

### 13. Dual-Resume Delivery Verification (FINAL CHECKLIST)
Before marking an application complete, verify:

**Resume #1 (2-Page Application Version):**
- [ ] Exactly 2 pages (not 1, not 3+)
- [ ] Modern template touches applied (header accent, subtle color, professional spacing)
- [ ] ATS-optimized (minimal graphics — only subtle header line/bar allowed)
- [ ] High keyword density (1.2-1.5 keywords per bullet matching JD)
- [ ] ≥80% of bullets include quantified impact
- [ ] Strong action verbs used consistently
- [ ] Professional section dividers and visual hierarchy maintained
- [ ] Files generated: `Rajesh_Dammala_<Company>_<RoleShortName>_v<N>.docx` and `.pdf`
- [ ] Portfolio hyperlink embedded below contact info
- [ ] Sensitivity set to "Public"

**Cover Letter (1-Page Application Version):**
- [ ] Exactly 1 page (~250 words)
- [ ] Addresses specific role requirements (mirrored from JD)
- [ ] Includes 2-3 strongest proof points (not full resume repetition)
- [ ] Tone: confident, conversational, direct
- [ ] Files generated: `Rajesh_Dammala_CoverLetter_<Company>_v<N>.docx` and `.pdf`
- [ ] Portfolio hyperlink embedded in signature line
- [ ] Sensitivity set to "Public"

**Resume #2 (4-5 Page Portfolio Version):**
- [ ] 4-5 pages (comprehensive, no page restrictions)
- [ ] **ATS keyword optimization applied** (1.5-2x keyword density throughout)
- [ ] All JD keywords embedded naturally in content and skill sections
- [ ] Stored in portfolio repo: `Rajesh_Dammala_<Role>_Complete_CV.pdf`
- [ ] Full career history with detailed scope and impact
- [ ] All quantified metrics included
- [ ] Complete technical skills with all relevant keywords listed
- [ ] Reference-grade quality (suitable for executive-level discussion)
- [ ] Visual design matches portfolio aesthetic (colors, fonts, layout)
- [ ] **Dual-purpose:** Both ATS-scannable AND beautifully designed
- [ ] PDF file included in portfolio repo git commit

**Portfolio Website:**
- [ ] "Download Resume" button in hero section
- [ ] Button links correctly to: `./Rajesh_Dammala_<Role>_Complete_CV.pdf`
- [ ] Clicking button downloads the 4-5 page PDF (test before going live)
- [ ] Dark/Light mode toggle functional
- [ ] RD favicon displays correctly
- [ ] Portfolio repo pushed to GitHub with company+role naming
- [ ] GitHub repo name: `<CompanyName>_<RoleName>` (e.g., `Snowflake_Staff-Escalation-Manager`)
- [ ] GitHub Pages live and accessible: `https://rdammala.github.io/<CompanyName>_<RoleName>/`

**Job Application Tracker:**
- [ ] Entry added to `defaultApps` array with all fields
- [ ] Portfolio repo name uses company+role format (e.g., `Snowflake_Staff-Escalation-Manager`)
- [ ] Portfolio link uses company+role format: `https://rdammala.github.io/<CompanyName>_<RoleName>/`
- [ ] tracker file synced to career-focus-pages repo
- [ ] Changes pushed to master branch
- [ ] Tracker updated successfully: https://rdammala.github.io/career-focus-pages/Job_Application_Tracker.html
- [ ] Repo naming makes it easy to identify and bulk-delete old applications later

**Final Quality Gate:**
- [ ] All files follow naming conventions (no typos)
- [ ] Application (Resume #1 + Cover Letter) submitted to career portal
- [ ] Portfolio URL accessible and functioning
- [ ] Noted follow-up date: 5 business days from submission

## Job Application Tracker Details
- **3 tabs**: Applications, Networking Contacts, Portfolio Guide
- **Applications**: Table with portfolio, role, company, date, link, status, comments; search/filter/sort
- **Contacts**: Card grid with name, company, email, multi-phone (Call/WhatsApp/Other labels), LinkedIn, source, resume shared, comments, voice note + auto-transcript
- **Portfolio Guide**: All 9 portfolios with role fit descriptions and clickable links
- **Resume Shared dropdown** includes all 9 portfolios with role hints + General Resume
- **Data**: localStorage (`rd_job_tracker`, `rd_contacts`, `tracker_theme`, `rd_tracker_meta` with `lastUpdatedMs`); export/import as JSON
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
