### Hi, I'm Soroush 👋 سلام

```
  Into networks, but AI/ML most of all.
  I like staying in touch, so feel free to message me.
```

I write JavaScript/TypeScript and Python, and lately most of my free hours go into two things:
building small tools I actually use every day, and fixing bugs in open source libraries that
a lot of people depend on without ever thinking about them (form libraries, mail senders,
search clients, checkout pages, government sites...).

A theme I keep running into, almost by accident: **software that breaks the moment the text isn't English.**
Persian that renders left-to-right, CSV exports that turn `índice` into `Ã­ndice`, tokens that
fail on non-ASCII rules. I read and write a right-to-left language every day, so those bugs are
personal to me.

---

### 🔨 Things I've built

**[Dynamic-RTL](https://github.com/soroush5/Dynamic-RTL)** ⭐ 49 &nbsp;·&nbsp; 7 forks &nbsp;·&nbsp; my own browser extension

It watches every page you open and, the moment it sees Persian or Arabic text (a paragraph,
a chat bubble, a tweet, a text field you're typing in), it flips that element to right-to-left
and gives it a readable font ([Vazirmatn](https://github.com/rastikerdar/vazirmatn)).
Made for the web the way a Persian reader actually sees it: chat apps, X, Notion, Google.

- Three builds, **Chrome / Firefox / Safari**, same detection logic, each one styled like its host browser
- No flash of wrong direction: styles are registered before the first paint
- Handles streaming content, `contenteditable` editors and open shadow roots
- URLs and inline code inside RTL paragraphs keep reading left-to-right, so links in Google results no longer come out backwards
- Latest release: **v3.2** (September 2026)

**[sefid](https://github.com/soroush5/sefid)** &nbsp;·&nbsp; work in progress

A Persian, fully RTL website built with Next.js (App Router), Tailwind CSS v4 and a customized
shadcn/ui kit, with light and dark themes and a living design-system page. Very early, changing daily.

---

### 🌱 Open source I've contributed to

Most of these started the same way: I hit something odd, wrote a failing test, and then sent the
smallest fix I could. Numbers are merged PRs.

| Project | Area |
|---|---|
| [react-hook-form](https://github.com/react-hook-form/react-hook-form) | Field arrays, dirty/touched state, resolver and delayError edge cases (18 merged) |
| [nodemailer](https://github.com/nodemailer/nodemailer) | SMTP pool, MIME encoding, cookies, well-known services (7 merged) |
| [meilisearch-js](https://github.com/meilisearch/meilisearch-js) | Tenant tokens, request options, error handling (5 merged) |
| [woocommerce](https://github.com/woocommerce/woocommerce) | Receipts and Blocks order confirmation fatals (2 merged) |
| [next-intl](https://github.com/amannn/next-intl) | Route params and base path cookies (2 merged) |
| [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) | Backend type conversion (2 merged) |
| [dify](https://github.com/langgenius/dify) | CSRF whitelist path matching (1 merged) |
| [KiroCrew](https://github.com/kirodotdev/KiroCrew) | Memory retention settings (1 merged) |
| [OmniRoute](https://github.com/diegosouzapw/OmniRoute) | Request translator for tool calls (1 merged) |
| [data.gov](https://github.com/GSA/data.gov) | Metrics CSV encoding (1 merged) |
| [design-system-react](https://github.com/cfpb/design-system-react) | Tabs keyboard accessibility (1 merged) |

#### A few I remember well

- **nodemailer**: seven fixes landed over two days, from cookies that ignored their `Path`
  ([#1861](https://github.com/nodemailer/nodemailer/pull/1861)) to pooled connections that
  never got released after hitting the rate limit ([#1866](https://github.com/nodemailer/nodemailer/pull/1866)).
  One idea of mine got rewritten by the maintainer with much better edge-case tests than I had written.
  Fair enough, and since then I write the ugly edge cases (UNC paths, empty input, unicode) first.
- **data.gov**: the metrics CSVs came out garbled in Excel for anything non-English. It turned out to be a
  missing BOM and a missing charset on upload. Tested it with Portuguese and Korean titles
  ([#6322](https://github.com/GSA/data.gov/pull/6322)).
- **meilisearch-js**: tenant tokens broke when search rules contained non-ASCII characters
  ([#2230](https://github.com/meilisearch/meilisearch-js/pull/2230)). Same family of bug, different library.
- **react-hook-form**: a long run of small state fixes: errors that stayed after `reset()`, dirty flags
  that survived removed field-array rows, `delayError` timers that kept firing after a parent was cleared.
  Forms look simple until you start removing rows while validation is still running.
- **cfpb/design-system-react**: making Tabs follow the WAI-ARIA roving tabindex pattern
  ([#642](https://github.com/cfpb/design-system-react/pull/642)). I missed a lint step on the first try,
  the maintainer patiently pointed at it, and I learned that fork PRs there can't trigger CI for security reasons.
- **woocommerce**: a receipt that fataled when the parent product of a variation had been deleted
  ([#68369](https://github.com/woocommerce/woocommerce/pull/68369)).

<details>
<summary><b>All 41 merged PRs</b> (click to expand)</summary>

<br>

**react-hook-form** (18)
[#13725](https://github.com/react-hook-form/react-hook-form/pull/13725) FileList in flatten and FormData ·
[#13727](https://github.com/react-hook-form/react-hook-form/pull/13727) nested container errors ·
[#13730](https://github.com/react-hook-form/react-hook-form/pull/13730) parent error with nested errors ·
[#13731](https://github.com/react-hook-form/react-hook-form/pull/13731) resolver root errors on submit ·
[#13732](https://github.com/react-hook-form/react-hook-form/pull/13732) trigger on a parent ·
[#13733](https://github.com/react-hook-form/react-hook-form/pull/13733) stale resolver result after reset ·
[#13734](https://github.com/react-hook-form/react-hook-form/pull/13734) replace() leftovers ·
[#13735](https://github.com/react-hook-form/react-hook-form/pull/13735) resetField validating state ·
[#13736](https://github.com/react-hook-form/react-hook-form/pull/13736) nested delayError timers ·
[#13737](https://github.com/react-hook-form/react-hook-form/pull/13737) criteriaMode at runtime ·
[#13738](https://github.com/react-hook-form/react-hook-form/pull/13738) dirty state with setValueAs ·
[#13739](https://github.com/react-hook-form/react-hook-form/pull/13739) dirty state for removed rows ·
[#13750](https://github.com/react-hook-form/react-hook-form/pull/13750) null array default ·
[#13758](https://github.com/react-hook-form/react-hook-form/pull/13758) removed register rules ·
[#13761](https://github.com/react-hook-form/react-hook-form/pull/13761) stale built-in validation after reset ·
[#13765](https://github.com/react-hook-form/react-hook-form/pull/13765) deps revalidation on setValue ·
[#13767](https://github.com/react-hook-form/react-hook-form/pull/13767) stale field array root error ·
[#13769](https://github.com/react-hook-form/react-hook-form/pull/13769) delayError timers on resetField

**nodemailer** (7)
[#1859](https://github.com/nodemailer/nodemailer/pull/1859) well-known primary domains ·
[#1861](https://github.com/nodemailer/nodemailer/pull/1861) cookie Path ·
[#1862](https://github.com/nodemailer/nodemailer/pull/1862) httpHeaders and tls for href alternatives ·
[#1863](https://github.com/nodemailer/nodemailer/pull/1863) missing SES client error ·
[#1865](https://github.com/nodemailer/nodemailer/pull/1865) Buffer base64 mime words ·
[#1866](https://github.com/nodemailer/nodemailer/pull/1866) rate-limited pool connections ·
[#1867](https://github.com/nodemailer/nodemailer/pull/1867) line breaks in multipart boundary

**meilisearch-js** (5)
[#2229](https://github.com/meilisearch/meilisearch-js/pull/2229) redact Authorization in timeout errors ·
[#2230](https://github.com/meilisearch/meilisearch-js/pull/2230) non-ASCII tenant tokens ·
[#2234](https://github.com/meilisearch/meilisearch-js/pull/2234) non-JSON error bodies ·
[#2235](https://github.com/meilisearch/meilisearch-js/pull/2235) per-request extraRequestInit ·
[#2236](https://github.com/meilisearch/meilisearch-js/pull/2236) single string fields in getDocument

**woocommerce** (2)
[#68369](https://github.com/woocommerce/woocommerce/pull/68369) receipt with deleted parent product ·
[#68584](https://github.com/woocommerce/woocommerce/pull/68584) array-valued key on order confirmation

**next-intl** (2)
[#2406](https://github.com/amannn/next-intl/pull/2406) `$` patterns in route params ·
[#2410](https://github.com/amannn/next-intl/pull/2410) base path detection for the cookie

**AutoGPT** (2)
[#14486](https://github.com/Significant-Gravitas/AutoGPT/pull/14486) whitespace in bool conversion ·
[#14488](https://github.com/Significant-Gravitas/AutoGPT/pull/14488) strings in set/tuple conversion


**dify** [#42118](https://github.com/langgenius/dify/pull/42118) exact match for CSRF whitelist paths

**KiroCrew** [#8246](https://github.com/kirodotdev/KiroCrew/pull/8246) negative keep_days fallback

**OmniRoute** [#12691](https://github.com/diegosouzapw/OmniRoute/pull/12691) non-array tool_calls

**data.gov** [#6322](https://github.com/GSA/data.gov/pull/6322) UTF-8 CSV downloads

**design-system-react** [#642](https://github.com/cfpb/design-system-react/pull/642) Tabs roving tabindex

</details>

Lately I've also been reading through public-sector open source: GOV.UK Notify, data.gov,
Singapore's FormSG and Postman, New Zealand's CWAC, Canada's Tracker. Code a lot of people rely on
and very few people read.

---

### 🧭 How I like to work

- Reproduce it first. If I can't make it fail in the real app, I don't send it.
- One bug per PR, as small as I can make it, with a test that fails before the fix.
- Read the project's recent merged PRs and CONTRIBUTING before the first message, so I sound like I belong there.
- If a maintainer says no, that's the answer. Their project, their call.

---

### 🧰 Stack

![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white)
![React](https://img.shields.io/badge/-React-61DAFB?style=flat&logo=react&logoColor=black)
![Node.js](https://img.shields.io/badge/-Node.js-339933?style=flat&logo=node.js&logoColor=white)
![Next.js](https://img.shields.io/badge/-Next.js-000000?style=flat&logo=next.js&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/-Tailwind_CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)
![SQLite](https://img.shields.io/badge/-SQLite-003B57?style=flat&logo=sqlite&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/-Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/-Git-F05032?style=flat&logo=git&logoColor=white)
![VS Code](https://img.shields.io/badge/-VS_Code-007ACC?style=flat&logo=visual-studio-code&logoColor=white)

Also comfortable with: browser extensions (Manifest V3), Vitest and Jest, pytest, RTL layouts and bidi text.

---

### 📊 Stats

| Merged upstream PRs | Repos with merges | Languages I ship |
|:---:|:---:|:---:|
| 41 | 11 | TypeScript, Python, JavaScript |

[![streak](https://streak-stats.demolab.com?user=soroush5&hide_border=true)](https://github.com/soroush5)

---

### 💬 Say hi

The issues on this repo are open. Feel free to ask me about anything: https://github.com/soroush5/soroush5/issues

If you maintain one of the projects above and I got something wrong in a PR, tell me. I'd rather hear it.
