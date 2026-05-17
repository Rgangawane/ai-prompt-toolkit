[rohit_prompt_toolkit_index.html](https://github.com/user-attachments/files/27893128/rohit_prompt_toolkit_index.html)
# ai-prompt-toolkit
better AI-assisted documentation
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AI Prompt Toolkit for Technical Writers | Rohit Gangawane</title>
  <style>
    :root {
      --bg: #0f172a;
      --panel: #162033;
      --panel-2: #1d2a3f;
      --text: #e5edf8;
      --muted: #9fb1c8;
      --accent: #2dd4bf;
      --accent-2: #60a5fa;
      --border: #30425c;
      --chip: #24324b;
      --shadow: 0 20px 45px rgba(0,0,0,.28);
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.6;
    }

    .app {
      display: grid;
      grid-template-columns: 270px 1fr;
      min-height: 100vh;
    }

    aside {
      background: #111c2f;
      border-right: 1px solid var(--border);
      padding: 22px 20px;
      position: sticky;
      top: 0;
      height: 100vh;
      overflow-y: auto;
    }

    .brand {
      font-size: 19px;
      font-weight: 800;
      margin-bottom: 28px;
      color: #f8fafc;
    }

    .label {
      color: #71829c;
      font-size: 11px;
      letter-spacing: .12em;
      text-transform: uppercase;
      margin: 18px 0 10px;
      font-weight: 800;
    }

    .nav-item {
      border: 0;
      width: 100%;
      background: transparent;
      color: #cbd5e1;
      text-align: left;
      padding: 10px 12px;
      border-radius: 10px;
      cursor: pointer;
      font-weight: 650;
      margin: 2px 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
      transition: .2s;
    }

    .nav-item:hover,
    .nav-item.active {
      background: #1d4ed8;
      color: white;
    }

    .count {
      background: rgba(255,255,255,.12);
      padding: 2px 8px;
      border-radius: 999px;
      font-size: 12px;
    }

    main {
      padding: 24px 42px 60px;
      max-width: 1180px;
      width: 100%;
    }

    header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 18px;
      margin-bottom: 28px;
      position: sticky;
      top: 0;
      background: rgba(15,23,42,.92);
      backdrop-filter: blur(12px);
      z-index: 5;
      padding: 10px 0;
    }

    .title-row {
      display: flex;
      align-items: center;
      gap: 14px;
      flex-wrap: wrap;
    }

    h1 {
      font-size: 22px;
      margin: 0;
      letter-spacing: -.02em;
    }

    .meta {
      color: var(--muted);
      font-size: 14px;
      font-weight: 700;
    }

    .meta strong {
      color: var(--accent);
    }

    .tabs {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
      margin: 10px 0;
    }

    .tab {
      background: var(--chip);
      color: #cbd5e1;
      border: 1px solid var(--border);
      border-radius: 7px;
      padding: 7px 12px;
      font-weight: 700;
      font-size: 13px;
      cursor: pointer;
    }

    .tab.active {
      background: var(--accent);
      color: #042f2e;
      border-color: var(--accent);
    }

    .search {
      min-width: 280px;
      flex: 1;
      max-width: 360px;
      position: relative;
    }

    .search input {
      width: 100%;
      border: 1px solid var(--border);
      background: #111827;
      color: var(--text);
      padding: 12px 14px;
      border-radius: 10px;
      outline: none;
      font-size: 15px;
    }

    .how-to,
    .intro {
      border: 1px solid var(--border);
      background: var(--panel);
      border-radius: 12px;
      box-shadow: var(--shadow);
      margin-bottom: 28px;
    }

    .how-to {
      padding: 18px 22px;
    }

    .how-to h2,
    .intro h2,
    .category h2 {
      margin: 0 0 12px;
      font-size: 17px;
      letter-spacing: .03em;
    }

    .steps {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 14px;
    }

    .step {
      display: grid;
      grid-template-columns: 28px 1fr;
      gap: 8px;
      font-weight: 650;
      color: #dbeafe;
    }

    .step span {
      color: var(--accent);
      font-weight: 900;
    }

    .intro {
      border-left: 4px solid var(--accent);
      padding: 20px 22px;
      color: #dbeafe;
      font-size: 16px;
    }

    .toolbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin: 22px 0 18px;
      color: var(--muted);
      font-weight: 700;
    }

    .btn {
      border: 1px solid var(--border);
      background: var(--panel-2);
      color: var(--text);
      border-radius: 8px;
      padding: 8px 13px;
      cursor: pointer;
      font-weight: 750;
      transition: .2s;
    }

    .btn:hover {
      border-color: var(--accent);
      transform: translateY(-1px);
    }

    .category {
      margin: 26px 0 44px;
    }

    .category-title {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 16px;
      padding-bottom: 10px;
      border-bottom: 1px solid var(--border);
    }

    .category-title h2 {
      margin: 0;
      font-size: 18px;
      text-transform: uppercase;
    }

    .badge {
      margin-left: auto;
      background: var(--chip);
      color: var(--muted);
      border-radius: 999px;
      padding: 4px 10px;
      font-size: 12px;
      font-weight: 800;
    }

    .prompt-card {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: 14px;
      margin-bottom: 16px;
      overflow: hidden;
      box-shadow: 0 14px 30px rgba(0,0,0,.18);
    }

    .prompt-head {
      padding: 18px 20px;
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 18px;
      cursor: pointer;
    }

    .prompt-title {
      margin: 0 0 4px;
      font-size: 17px;
      color: #f8fafc;
    }

    .prompt-desc {
      margin: 0;
      color: var(--muted);
      font-size: 14px;
    }

    .copy-btn {
      background: #042f2e;
      border: 1px solid #0f766e;
      color: var(--accent);
      padding: 8px 12px;
      border-radius: 8px;
      cursor: pointer;
      font-weight: 850;
      white-space: nowrap;
    }

    .prompt-body {
      display: none;
      border-top: 1px solid var(--border);
      padding: 18px 20px 20px;
      background: #0b1220;
    }

    .prompt-card.open .prompt-body {
      display: block;
    }

    pre {
      margin: 0;
      white-space: pre-wrap;
      word-break: break-word;
      font-family: "Cascadia Code", "Fira Code", Consolas, monospace;
      color: #d1fae5;
      font-size: 13.5px;
      line-height: 1.65;
    }

    .empty {
      display: none;
      background: var(--panel);
      border: 1px dashed var(--border);
      padding: 28px;
      border-radius: 12px;
      color: var(--muted);
      text-align: center;
      font-weight: 700;
    }

    footer {
      border-top: 1px solid var(--border);
      padding-top: 24px;
      color: var(--muted);
      font-size: 14px;
    }

    a {
      color: var(--accent);
    }

    @media (max-width: 900px) {
      .app {
        grid-template-columns: 1fr;
      }

      aside {
        position: static;
        height: auto;
      }

      main {
        padding: 22px;
      }

      header {
        position: static;
        display: block;
      }

      .search {
        max-width: 100%;
        margin-top: 14px;
      }

      .steps {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <div class="app">
    <aside>
      <div class="brand">Prompt Toolkit for Technical Writers</div>

      <div class="label">Categories</div>
      <div id="categoryNav"></div>

      <div class="label">Filter</div>
      <button class="nav-item active" data-filter="All">All prompts <span class="count" id="allCount">0</span></button>
      <button class="nav-item" data-filter="Drafting">Drafting</button>
      <button class="nav-item" data-filter="Review">Review & QA</button>
      <button class="nav-item" data-filter="API">API Docs</button>
      <button class="nav-item" data-filter="SOP">SOPs</button>
    </aside>

    <main>
      <header>
        <div>
          <div class="title-row">
            <h1>AI Prompt Toolkit for Technical Writers</h1>
            <div class="meta"><strong id="totalCount">0</strong> Prompts • <strong id="categoryCount">0</strong> Categories</div>
          </div>
          <div class="tabs">
            <button class="tab active" data-tool="All">All</button>
            <button class="tab" data-tool="ChatGPT">ChatGPT</button>
            <button class="tab" data-tool="Claude">Claude</button>
            <button class="tab" data-tool="Gemini">Gemini</button>
            <button class="tab" data-tool="Copilot">Copilot</button>
          </div>
        </div>
        <div class="search">
          <input id="searchInput" type="search" placeholder="Search prompts..." />
        </div>
      </header>

      <section class="how-to">
        <h2>&lt;-- HOW TO USE --&gt;</h2>
        <div class="steps">
          <div class="step"><span>1.</span><div>Find a prompt and click to expand it.</div></div>
          <div class="step"><span>2.</span><div>Click <strong>Copy Prompt</strong> to copy clean text.</div></div>
          <div class="step"><span>3.</span><div>Replace every <strong>[PLACEHOLDER]</strong> with your information.</div></div>
          <div class="step"><span>4.</span><div>Paste into any AI platform and improve the output.</div></div>
        </div>
      </section>

      <section class="intro">
        <p>
          This library contains ready-to-use AI prompts built for technical writers.
          The prompts are customized for API documentation, SOPs, user manuals, release notes,
          knowledge base articles, resume tailoring, and documentation quality reviews.
        </p>
        <p>
          <strong>Pro Tip:</strong> For complex tasks, add your past document sample and ask the AI
          to follow the same structure, tone, and quality standard.
        </p>
      </section>

      <div class="toolbar">
        <div>Showing <span id="showingCount">0</span> of <span id="showingTotal">0</span> prompts</div>
        <button class="btn" id="expandAll">Expand All</button>
      </div>

      <div id="prompts"></div>
      <div class="empty" id="emptyState">No prompts found. Try another search or filter.</div>

      <footer>
        <p>
          Created and customized by <strong>Rohit Gangawane</strong> for technical writing workflows.
          Inspired by Sneha Pandey’s public AI Prompt Library:
          <a href="https://snehap16.github.io/awesome-tech-writing/ai-prompt-library.html" target="_blank" rel="noopener">View source inspiration</a>.
        </p>
        <p>This is a customized version and is not a word-for-word copy of the original library.</p>
      </footer>
    </main>
  </div>

  <script>
    const prompts = [
      {
        category: "Drafting & Content Creation",
        tags: ["Drafting", "ChatGPT", "Claude", "Gemini"],
        title: "First Draft Documentation Prompt",
        desc: "Create a structured first draft for any documentation requirement.",
        text: `Act as a senior technical writer.

Create a first draft for the following documentation requirement.

Product/Feature: [NAME]
Documentation Type: [User Guide / SOP / API Guide / Release Note / Admin Manual]
Audience: [End User / Developer / Operations Team / Admin / Client]
Context: [Explain the feature, process, or API]
Source Inputs: [Paste raw notes, Jira ticket, SME notes, screenshots, or API details]

Write the output with:
- Overview
- Purpose
- Scope
- Prerequisites
- Step-by-step procedure or workflow
- Expected result
- Troubleshooting or common issues
- Notes and limitations

Style Requirements:
- Use simple language
- Use active voice
- Follow MSTP and Simplified Technical English where possible
- Use numbered steps for procedures
- Do not add unsupported information`
      },
      {
        category: "API Documentation",
        tags: ["API", "ChatGPT", "Claude", "Gemini", "Copilot"],
        title: "API Documentation Prompt",
        desc: "Document REST APIs with endpoint details, request, response, and errors.",
        text: `Act as an API documentation specialist.

Document the following REST API endpoint.

API Name: [NAME]
Base URL: [BASE URL]
Endpoint: [METHOD + PATH]
Authentication: [Bearer Token / API Key / OAuth / Other]
Audience: [Developers / Integration Partners / Internal Engineering Team]

Input Details:
- Endpoint purpose: [DESCRIBE]
- Headers: [LIST]
- Path parameters: [LIST]
- Query parameters: [LIST]
- Request body: [PASTE JSON OR SCHEMA]
- Success response: [PASTE JSON]
- Error responses: [PASTE ERROR JSON]
- Validation rules: [LIST]

Create documentation with:
1. Overview
2. Endpoint details
3. Authentication requirements
4. Request headers
5. Request parameters table
6. Request body schema
7. Sample request
8. Sample response
9. Error codes and resolutions
10. Notes, constraints, and edge cases

Also include:
- Postman-ready sample
- cURL example
- Field-level validation table`
      },
      {
        category: "SOPs & Process Documentation",
        tags: ["SOP", "Drafting", "ChatGPT", "Claude"],
        title: "SOP Creation Prompt",
        desc: "Convert raw process notes into a complete SOP.",
        text: `Act as a process documentation writer.

Create a Standard Operating Procedure for the process below.

Process Name: [NAME]
Department/Team: [TEAM]
Users/Roles Involved: [Maker / Checker / Admin / Operations / Client]
System/Application: [NAME]
Trigger: [When does the process start?]
End Result: [What confirms completion?]
Raw Process Notes: [PASTE NOTES]

Write the SOP with:
- Purpose
- Scope
- Roles and responsibilities
- Pre-conditions
- Step-by-step procedure
- System validations
- Exception handling
- Approval workflow
- Output or report generated
- Audit or compliance notes

Rules:
- Use clear, short steps
- Mention button names, field names, and status names exactly as shown in the system
- Add examples where required
- Do not use unnecessary technical jargon`
      },
      {
        category: "SOPs & Process Documentation",
        tags: ["SOP", "Drafting", "ChatGPT"],
        title: "Screenshot-Based Procedure Prompt",
        desc: "Write stepwise UI procedures from screenshots.",
        text: `Act as a technical writer creating UI-based procedure documentation.

Review the provided screenshot notes and write a stepwise procedure.

Screen Name: [SCREEN NAME]
Module: [MODULE NAME]
User Role: [ROLE]
Objective: [WHAT USER WANTS TO COMPLETE]
Screenshot Details: [Describe fields, buttons, dropdowns, tabs, and messages]

Write the procedure in this format:

Step 1: Navigate to [Menu > Submenu].
Step 2: Click [Button Name].
Step 3: In the [Field Name] field, enter/select [Example Value].
Step 4: Click Submit.
Step 5: Verify that [Expected Result].

Rules:
- Use exact UI labels
- Add examples where useful
- Keep each step short
- Avoid technical jargon
- Add notes only when required`
      },
      {
        category: "Review & Quality Assurance",
        tags: ["Review", "ChatGPT", "Claude", "Gemini"],
        title: "Simplify Technical Content Prompt",
        desc: "Rewrite complex content in simple, user-friendly language.",
        text: `Act as a plain-language technical editor.

Rewrite the following technical content for [TARGET AUDIENCE].

Original Content:
[PASTE CONTENT]

Rewrite it using:
- Simple words
- Short sentences
- Active voice
- Clear headings
- No unnecessary jargon
- No change in meaning

After rewriting, provide:
1. Improved version
2. List of difficult terms simplified
3. Any information that still needs confirmation`
      },
      {
        category: "Release Notes",
        tags: ["Drafting", "Review", "ChatGPT", "Claude"],
        title: "Release Notes Prompt",
        desc: "Create user-focused release notes from raw change lists.",
        text: `Act as a release documentation writer.

Create release notes for the following product update.

Product: [PRODUCT NAME]
Version: [VERSION]
Release Date: [DATE]
Audience: [Users / Admins / Developers / Clients]

Raw Changes:
- New features: [LIST]
- Enhancements: [LIST]
- Bug fixes: [LIST]
- Known issues: [LIST]
- Breaking changes: [LIST]

Write release notes with:
- Summary
- New Features
- Improvements
- Fixed Issues
- Known Issues
- Impact on Users
- Upgrade or action required

Use user-focused language. Explain why each change matters.`
      },
      {
        category: "Review & Quality Assurance",
        tags: ["Review", "ChatGPT", "Claude"],
        title: "Documentation Review Prompt",
        desc: "Review content for structure, accuracy, clarity, and completeness.",
        text: `Act as a senior documentation reviewer.

Review the document below for quality, clarity, and completeness.

Document Type: [TYPE]
Audience: [AUDIENCE]
Style Guide: [MSTP / STE / Company Style / Other]

Document:
[PASTE DOCUMENT]

Review against:
- Accuracy
- Completeness
- Structure
- Readability
- Terminology consistency
- UI label consistency
- Grammar and tone
- Missing prerequisites or steps
- Missing examples or error cases

Provide output as:
1. Overall score out of 100
2. Strengths
3. Issues found
4. Suggested corrections
5. Priority fixes
6. Final publishing recommendation`
      },
      {
        category: "Review & Quality Assurance",
        tags: ["Review", "ChatGPT", "Claude", "Gemini"],
        title: "MSTP and STE Compliance Prompt",
        desc: "Check documentation against MSTP and Simplified Technical English.",
        text: `Act as a technical editor familiar with Microsoft Manual of Style and Simplified Technical English.

Review the content below.

Content:
[PASTE CONTENT]

Check for:
- Long sentences
- Passive voice
- Ambiguous pronouns
- Unclear steps
- Jargon-heavy wording
- Inconsistent capitalization
- Incorrect UI references
- Weak verbs
- Unnecessary words

Return a table with:
Original Text | Issue | Suggested Rewrite | Rule/Reason

Then provide a clean rewritten version.`
      },
      {
        category: "Format & Convert",
        tags: ["Drafting", "ChatGPT", "Claude", "Gemini"],
        title: "Convert Raw Notes to Documentation Prompt",
        desc: "Turn messy notes into a polished document.",
        text: `Act as a technical writer.

Convert the following unstructured notes into a polished document.

Raw Notes:
[PASTE NOTES]

Target Format: [SOP / User Guide / API Guide / FAQ / Knowledge Base Article]
Audience: [AUDIENCE]

Output must include:
- Title
- Overview
- Organized headings
- Numbered procedures where required
- Tables for fields, roles, or validations
- Notes and warnings where required
- Open questions for missing details

Rules:
- Do not remove important details
- Do not invent missing information
- Highlight unclear points for SME confirmation`
      },
      {
        category: "Video, Audio & Transcripts",
        tags: ["Drafting", "ChatGPT", "Claude"],
        title: "Meeting Transcript to Documentation Prompt",
        desc: "Extract requirements, decisions, steps, and action items from transcripts.",
        text: `Act as a documentation analyst.

Convert the following meeting transcript into usable documentation inputs.

Transcript:
[PASTE TRANSCRIPT]

Extract:
1. Key decisions
2. Requirements
3. Process steps
4. Roles and responsibilities
5. Open questions
6. Risks or dependencies
7. Draft documentation section
8. Action items

Remove filler words and repeated statements. Keep the meaning accurate.`
      },
      {
        category: "API Documentation",
        tags: ["API", "Review", "ChatGPT", "Claude"],
        title: "Error Message Documentation Prompt",
        desc: "Create a practical error reference for products or APIs.",
        text: `Act as a developer documentation writer.

Create an error reference for the following product or API.

Product/API: [NAME]
Audience: [Developers / Operations / End Users]

Error List:
[PASTE ERROR CODES OR MESSAGES]

For each error, provide:
- Error code/message
- What it means
- When it occurs
- Possible cause
- How to resolve
- Example scenario
- Suggested user-facing message

Use a table format. Keep explanations practical and easy to troubleshoot.`
      },
      {
        category: "Sample Product Documentation",
        tags: ["Drafting", "ChatGPT", "Claude", "Gemini"],
        title: "FAQ Creation Prompt",
        desc: "Create real user-focused FAQs for products or processes.",
        text: `Act as a documentation writer creating FAQs for users.

Create FAQs for the following product or process.

Product/Process: [NAME]
Audience: [AUDIENCE]
Context: [DESCRIBE]
Known User Questions: [LIST IF AVAILABLE]

Generate:
- 10 to 15 practical FAQs
- Short, direct answers
- Examples where helpful
- Links/placeholders for related documents
- Notes for questions that need SME confirmation

Avoid marketing language. Focus on real user doubts.`
      },
      {
        category: "Strategy & Planning",
        tags: ["Drafting", "ChatGPT", "Claude"],
        title: "Documentation Plan Prompt",
        desc: "Plan documentation scope, schedule, dependencies, and review cycles.",
        text: `Act as a documentation project planner.

Create a documentation plan for the following product or feature.

Product/Feature: [NAME]
Release Date: [DATE]
Audience Groups: [LIST]
Available Inputs: [Jira / PRD / API Spec / Screenshots / SME Notes]
Documentation Outputs Needed: [LIST]

Create a plan with:
- Documentation scope
- Required documents
- Information required from SMEs
- Drafting schedule
- Review cycle
- Dependencies
- Risks
- Publishing checklist
- Maintenance plan`
      },
      {
        category: "Career Documentation",
        tags: ["Drafting", "Review", "ChatGPT"],
        title: "Resume Tailoring Prompt for Technical Writer Roles",
        desc: "Tailor resume content for ATS and technical writing roles.",
        text: `Act as an ATS resume strategist for technical writing roles.

Tailor my resume for the job description below.

Current Resume:
[PASTE RESUME]

Job Description:
[PASTE JD]

Target Role: [ROLE NAME]
Target Industry: [INDUSTRY]

Update:
- Professional summary
- Skills section
- Experience bullets
- Tools and technologies
- Project highlights

Rules:
- Keep the resume truthful
- Add keywords naturally
- Make bullets achievement-focused
- Use strong action verbs
- Keep formatting ATS-friendly
- Do not add skills I do not have

Also provide:
- Keyword match list
- Missing skill gaps
- Suggested improvements`
      },
      {
        category: "Career Documentation",
        tags: ["Drafting", "ChatGPT", "Claude"],
        title: "Cover Letter Prompt",
        desc: "Create a concise, role-specific cover letter.",
        text: `Act as a career content writer.

Write a cover letter for the following role.

Candidate Profile:
[PASTE SUMMARY]

Job Description:
[PASTE JD]

Company: [COMPANY NAME]
Role: [ROLE NAME]
Tone: Professional, confident, and natural

Cover letter must include:
- Opening interest statement
- Relevant experience summary
- 2 to 3 role-specific strengths
- Why I fit the company/role
- Closing call to action

Keep it concise and recruiter-friendly.`
      },
      {
        category: "Sample Product Documentation",
        tags: ["Drafting", "ChatGPT", "Claude"],
        title: "Knowledge Base Article Prompt",
        desc: "Create searchable support articles for issues or features.",
        text: `Act as a knowledge base writer.

Create a knowledge base article for the following issue, feature, or process.

Topic: [TOPIC]
Audience: [End Users / Support Team / Operations Team / Developers]
Problem or Use Case: [DESCRIBE]
Source Inputs: [PASTE NOTES, SCREENSHOTS, OR ERROR DETAILS]

Write the article with:
- Title
- Summary
- When to use this article
- Prerequisites
- Step-by-step solution
- Expected result
- Troubleshooting tips
- Related articles

Rules:
- Keep the article searchable
- Use clear headings
- Use user-friendly language
- Add examples where helpful`
      },
      {
        category: "Sample Product Documentation",
        tags: ["Drafting", "ChatGPT", "Gemini"],
        title: "User Guide Prompt",
        desc: "Create a user guide section for a product feature.",
        text: `Act as a product documentation writer.

Create a user guide section for the following feature.

Feature Name: [NAME]
Product/Application: [NAME]
User Role: [ROLE]
User Goal: [WHAT THE USER WANTS TO DO]
Inputs: [PASTE SCREEN DETAILS, FIELD NAMES, AND WORKFLOW NOTES]

Write the guide with:
- Feature overview
- Who can use this feature
- Before you begin
- Step-by-step instructions
- Field descriptions
- Validation messages
- Expected outcome
- Troubleshooting

Use simple language and numbered steps.`
      },
      {
        category: "Sample Product Documentation",
        tags: ["Drafting", "ChatGPT", "Claude"],
        title: "Admin Guide Prompt",
        desc: "Create configuration documentation for admin users.",
        text: `Act as an admin documentation writer.

Create an admin guide section for the following configuration or setup.

Configuration Name: [NAME]
Application/System: [NAME]
Admin Role: [ROLE]
Purpose: [WHY THIS CONFIGURATION IS REQUIRED]
Inputs: [PASTE CONFIGURATION DETAILS]

Write the guide with:
- Overview
- Access path
- Required permissions
- Configuration steps
- Field description table
- Save/submit behavior
- Validation rules
- Impact of the configuration
- Troubleshooting`
      },
      {
        category: "Structure & Style",
        tags: ["Review", "ChatGPT", "Claude", "Gemini"],
        title: "Field Description Table Prompt",
        desc: "Create a field table for screens, forms, and APIs.",
        text: `Act as a technical documentation specialist.

Create a field description table for the following screen, API, or form.

Screen/API/Form Name: [NAME]
Audience: [USERS / ADMINS / DEVELOPERS]
Fields:
[PASTE FIELD LIST]

Create a table with:
- Field Name
- Description
- Required/Optional
- Data Type
- Example Value
- Validation Rule
- Notes

Rules:
- Keep descriptions short
- Use exact field names
- Do not assume missing values
- Mark unknown values as “To be confirmed”`
      },
      {
        category: "Strategy & Planning",
        tags: ["Review", "ChatGPT", "Claude"],
        title: "Publishing Checklist Prompt",
        desc: "Create a final quality and publishing checklist.",
        text: `Act as a documentation quality analyst.

Create a publishing checklist for the following document.

Document Name: [NAME]
Document Type: [SOP / API Guide / User Manual / Release Note / KB Article]
Audience: [AUDIENCE]
Reviewers: [SME / Product / QA / Compliance / Client]

Create a checklist for:
- Content accuracy
- Formatting
- Style guide compliance
- Terminology consistency
- Screenshot validation
- Link validation
- Version history
- Approval status
- Publishing readiness
- Post-publishing maintenance`
      }
    ];

    const categoryNav = document.getElementById("categoryNav");
    const promptsContainer = document.getElementById("prompts");
    const searchInput = document.getElementById("searchInput");
    const expandAll = document.getElementById("expandAll");
    const emptyState = document.getElementById("emptyState");
    const totalCount = document.getElementById("totalCount");
    const categoryCount = document.getElementById("categoryCount");
    const allCount = document.getElementById("allCount");
    const showingCount = document.getElementById("showingCount");
    const showingTotal = document.getElementById("showingTotal");

    let selectedCategory = "All";
    let selectedTool = "All";
    let allExpanded = false;

    const categories = [...new Set(prompts.map(p => p.category))];

    totalCount.textContent = prompts.length;
    showingTotal.textContent = prompts.length;
    categoryCount.textContent = categories.length;
    allCount.textContent = prompts.length;

    categories.forEach(category => {
      const button = document.createElement("button");
      const count = prompts.filter(p => p.category === category).length;
      button.className = "nav-item";
      button.dataset.filter = category;
      button.innerHTML = `${category} <span class="count">${count}</span>`;
      categoryNav.appendChild(button);
    });

    function getFilteredPrompts() {
      const query = searchInput.value.toLowerCase().trim();
      return prompts.filter(prompt => {
        const categoryMatch = selectedCategory === "All" || prompt.category === selectedCategory || prompt.tags.includes(selectedCategory);
        const toolMatch = selectedTool === "All" || prompt.tags.includes(selectedTool);
        const searchMatch =
          prompt.title.toLowerCase().includes(query) ||
          prompt.desc.toLowerCase().includes(query) ||
          prompt.category.toLowerCase().includes(query) ||
          prompt.text.toLowerCase().includes(query);
        return categoryMatch && toolMatch && searchMatch;
      });
    }

    function render() {
      const filtered = getFilteredPrompts();
      showingCount.textContent = filtered.length;
      promptsContainer.innerHTML = "";
      emptyState.style.display = filtered.length ? "none" : "block";

      const grouped = {};
      filtered.forEach(prompt => {
        if (!grouped[prompt.category]) grouped[prompt.category] = [];
        grouped[prompt.category].push(prompt);
      });

      Object.keys(grouped).forEach(category => {
        const section = document.createElement("section");
        section.className = "category";
        section.innerHTML = `
          <div class="category-title">
            <h2>&lt;-- ${category} --&gt;</h2>
            <span class="badge">${grouped[category].length} prompts</span>
          </div>
        `;

        grouped[category].forEach(prompt => {
          const card = document.createElement("article");
          card.className = "prompt-card" + (allExpanded ? " open" : "");
          card.innerHTML = `
            <div class="prompt-head">
              <div>
                <h3 class="prompt-title">${prompt.title}</h3>
                <p class="prompt-desc">${prompt.desc}</p>
              </div>
              <button class="copy-btn">Copy Prompt</button>
            </div>
            <div class="prompt-body">
              <pre>${escapeHtml(prompt.text)}</pre>
            </div>
          `;

          const head = card.querySelector(".prompt-head");
          const copyBtn = card.querySelector(".copy-btn");

          head.addEventListener("click", () => {
            card.classList.toggle("open");
          });

          copyBtn.addEventListener("click", async (event) => {
            event.stopPropagation();
            try {
              await navigator.clipboard.writeText(prompt.text);
              copyBtn.textContent = "Copied!";
              setTimeout(() => copyBtn.textContent = "Copy Prompt", 1200);
            } catch {
              copyBtn.textContent = "Copy failed";
              setTimeout(() => copyBtn.textContent = "Copy Prompt", 1200);
            }
          });

          section.appendChild(card);
        });

        promptsContainer.appendChild(section);
      });
    }

    function escapeHtml(str) {
      return str.replace(/[&<>"']/g, match => ({
        "&": "&amp;",
        "<": "&lt;",
        ">": "&gt;",
        '"': "&quot;",
        "'": "&#039;"
      }[match]));
    }

    document.querySelectorAll(".nav-item").forEach(item => {
      item.addEventListener("click", () => {
        document.querySelectorAll(".nav-item").forEach(i => i.classList.remove("active"));
        item.classList.add("active");
        selectedCategory = item.dataset.filter;
        render();
      });
    });

    document.querySelectorAll(".tab").forEach(tab => {
      tab.addEventListener("click", () => {
        document.querySelectorAll(".tab").forEach(t => t.classList.remove("active"));
        tab.classList.add("active");
        selectedTool = tab.dataset.tool;
        render();
      });
    });

    searchInput.addEventListener("input", render);

    expandAll.addEventListener("click", () => {
      allExpanded = !allExpanded;
      expandAll.textContent = allExpanded ? "Collapse All" : "Expand All";
      render();
    });

    render();
  </script>
</body>
</html>
