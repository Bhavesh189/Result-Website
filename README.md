# Result-Website

A stylish, unofficial result dashboard for BTU (Bikaner Technical University) students — enter your roll number to see your semester results, CGPA, SGPA, subject-wise marks, and semester history, all in one place.

## What it does

- **Roll number search** — type a roll number (e.g. `22BTCS001`) and hit Search (or press Enter) to fetch the result
- **Student info card** — name, father's/mother's name, roll number, enrollment, college, branch
- **Exam info card** — course, semester, examination, declaration date, category, exam type
- **Stat cards** — CGPA (with an animated count-up), SGPA, credits registered, and a PASS/FAIL badge
- **Subject-wise marks table** — subject code, title, credits, external/internal/total marks, color-coded grade pill, grade point, credit point, and score % with a progress bar
- **Semester history** — cards for previous semesters showing SGPA, CGPA, and pass/fail status
- **Recent searches** — last 6 roll numbers saved in the browser (localStorage) as clickable chips, with a clear option
- **Quick actions** — Print / Save as PDF, copy roll number, share result via a deep link (`?roll=...`), and jump to the subjects section
- **Extras** — live IST clock, scroll-to-top button, toast notifications, and 3D tilt hover effects on the cards
- **Animated background** — a rotating Three.js starfield over floating gradient orbs, in a dark glassmorphism theme

## Tech stack

- Pure **HTML + CSS + JavaScript** — no build tools, no frameworks, no dependencies to install
- **Three.js** (via CDN, r128) for the animated particle background
- **Google Fonts**: Syne (headings) and DM Sans (body)
- Result data is fetched from a third-party API: `https://bturesult.moreproductive.in/api/result` (POST with `rollNumber` and `examId`)

## Project structure

```
Result-Website/
├── index.html   # entry point: hero section, search box, action buttons, output container
├── Result.js    # all logic: API fetch, result rendering, search history, animations
└── Result.css   # dark theme: glassmorphism cards, orbs, toasts, responsive layout
```

## Run it locally

No build step — just open `index.html` in a browser. Or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Notes

- This is an **unofficial** dashboard for BTU Bikaner students; the hero banner notes it currently shows Semester 1 results.
- Result data depends on the external API above being reachable — if it's down, you'll see a friendly connection-error message.
- One roll number (`25ELDCS010`) is restricted in the code and shows an "access restricted" toast.

Built with ❤️ by [Bhavesh Sharma](https://bhavesh189.github.io/Bhavesh-Portfolio/)
