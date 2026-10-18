# attendance-sheet-maker
Offline-first attendance sheet maker. Import students and courses from CSV/Excel, combine classes, and export A4 PDF. Data stays in your browser.

<div align="center">

# ✅ Attendance Sheet Maker
### 出勤名单生成器

**Make attendance lists in seconds. Combine classes. Export A4 PDF.**
**Works offline. Your data never leaves your device.**

<br>

![PWA](https://img.shields.io/badge/PWA-installable-0b4d1b?style=for-the-badge)
![Offline](https://img.shields.io/badge/works-offline-1c6330?style=for-the-badge)
![No server](https://img.shields.io/badge/no%20server-100%25%20local-3b8050?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-2e8b48?style=for-the-badge)

[🚀 **Open the app**](https://YOUR-USERNAME.github.io/attendance-sheet-maker/) · [📖 **How to use**](#-how-to-use) · [📄 **CSV formats**](#-csv-formats) · [❓ **FAQ**](#-faq)

<br>

<!-- Replace with your own screenshot. Use fake names only. -->
<img src="docs/screenshot.png" alt="Attendance Sheet Maker screenshot" width="780">

</div>

---

## 📌 What is it?

**Attendance Sheet Maker** is a small web app for teachers. You load your students and your timetable once. After that, each class takes three steps: pick a date, tap the marks, export the PDF.

It runs fully in the browser. There is no account, no server and no database. Everything is saved on your own phone or computer, so student names and photos stay private.

> 为老师设计的出勤名单工具。导入一次学生和课程，之后每节课只需：选日期 → 点名 → 导出 PDF。数据只保存在你自己的设备上，不会上传到任何服务器。

---

## ✨ Features

| | Feature | What it does |
|---|---|---|
| 🏫 | **Many majors** | Each class or major keeps its own courses, students, photos and attendance. |
| 👥 | **One student list per major** | Import once. Every course uses the same list in the same order. |
| 🔢 | **Permanent student number** | Each student gets a hidden internal number. You can change or even empty an ID without losing attendance or photos. |
| 📅 | **Timetable from CSV or Excel** | One row per weekly meeting. Dates are worked out from the Week 1 date. |
| 🗓️ | **Flexible weeks** | Every week, odd weeks, even weeks, or custom weeks such as `1,3,5,8-12`. |
| 🔗 | **Combine 2 to 4 classes** | Make one all-day sheet from classes on the same date. |
| 🖼️ | **Photos** | Import from an Excel file, or add one photo at a time. |
| ✔️ | **Four marks** | √ Present, L Late, O Approved leave, X Absent. |
| 📄 | **A4 PDF export** | Clean print layout. 18 students per page, more pages are added automatically. |
| 💾 | **Backup and restore** | One `.json` file per major. Move your data between devices. |
| 🌙 | **Dark mode** | Auto, Light or Dark. The printed sheet always stays white. |
| 📲 | **Install as an app** | Add it to your Android home screen. It opens even without internet. |

---

## 🚀 Quick start

### Use it online

Open **https://YOUR-USERNAME.github.io/attendance-sheet-maker/** in Chrome, Edge or Safari. Nothing to install.

### Install on Android

1. Open the link in **Chrome**.
2. Tap the **⋮** menu.
3. Choose **Add to Home screen** or **Install app**.

### Run it on your own computer

```bash
git clone https://github.com/YOUR-USERNAME/attendance-sheet-maker.git
cd attendance-sheet-maker
python3 -m http.server 8080
```

Then open `http://localhost:8080`. A local server is needed for the offline (service worker) feature. Opening `index.html` directly also works, but without offline caching.

---

## 📖 How to use

### The three cards

The left side has three cards. Only one is open at a time. Tap a title to open it.

| Card | Use it for |
|---|---|
| **1 · Class day 上课** | Pick a date, open a class, combine classes, quick marks, **Export PDF**. This is your daily work. |
| **2 · Courses 课程** | Choose a course or session, create, edit, move or delete courses, import the course file, set Week 1. |
| **3 · Students 学生** | Import students and photos, edit, reorder and delete students. |

Backup, Restore, Help and the theme switch are always in the top bar. On a phone, use the **Sheet / Setup / PDF** bar at the bottom.

### First-time setup (about 5 minutes)

1. **Name your class.** In the welcome window, enter the Chinese name, the English name and the date of **Week 1** (a Monday). This name is printed at the top of every sheet.
2. **Import students.** Open **Students → Import students / photos** and choose your CSV or Excel file.
3. **Import photos** (optional). Choose an `.xlsx` file with pictures placed in the cells. Photos are matched to students by row order.
4. **Import courses.** Open **Courses → Import courses**, or tap **New course** to type one in.
5. **Take your first attendance.** Open **Class day**, pick a date, tap a Check In or Check Out cell, and choose a mark.

### Every class after that

1. Open **Class day** and pick the date.
2. Tap a class in the list. If the day has two or more classes, they are combined into one all-day sheet automatically.
3. Tap cells on the sheet, or use **All Check In √** and **All Check Out √** for a quick start.
4. Tap **Export PDF (A4)**.

### Attendance marks

| Mark | Meaning | Counted as |
|:---:|---|---|
| **√** | Present | Present |
| **L** | Late | Late **and** Present |
| **O** | Approved leave | Leave |
| **X** | Absent | Absent |

Marking a student **O** or **X** at Check In fills Check Out with the same mark, if it is empty.

### Combine classes

1. Open a class on the date you want.
2. In **Class day → Combine classes**, tick 2 to 4 classes, or tap **Select all classes of this day**.
3. Turn on **Use combined all-day sheet**.

Only classes on the **same date** can be combined.

### Edit or move a course

- **Edit course** changes the title, teacher, days, times and weeks for the whole course. Sessions that stay in the new schedule **keep their attendance**. The form tells you how many are kept, added and removed.
- **Move session** changes the date and time of **one** class only, for example a make-up class.

### Reorder students

Use **▲ ▼** next to a student, or type a serial number and a new position, then tap **Move**. The order applies to every course, the sheet and the photo import.

---

## 📄 CSV formats

Both `.csv` and `.xlsx` files work. The header row is optional. Save CSV files as **CSV UTF-8** so Chinese characters stay correct.

### Students

| Column 1 | Column 2 | Column 3 |
|---|---|---|
| ID 序号 / 学号 | Passport name 护照姓名 | Chinese name 中文名字 |

```csv
序号 ID,护照姓名 Passport name,中文名字 Chinese name
672612140114,JOHN SMITH,约翰
672612140115,MARIA GARCIA,玛丽亚
```

- The **ID can be empty**. Two students cannot share one ID.
- **Importing again** updates a student whose ID matches. A row **without an ID** is matched by passport name. Anything else is added as a new student.
- Rows without a passport name are skipped.
- Format long ID columns as **Text** in Excel, so they are not turned into `6.7E+11`.

### Courses

**One row is one weekly class meeting.** A course that meets twice a week needs two rows.

| Column | Write | Accepted examples |
|---|---|---|
| 1 Course 课程 | Chinese name, a space, English name | `社会学概论 Introduction to Sociology` |
| 2 Teacher 教师 | Teacher name | `Teacher B` |
| 3 Weeks 周次 | Range, list, odd or even | `第1-16周` · `1-16` · `1,3,5,7` · `单` / `odd` · `双` / `even` · `all` |
| 4 Day 星期 | Chinese, English or 1 to 7 | `星期一` · `周三` · `Monday` · `Mon` · `1` |
| 5 Class time 节次 | Period range | `第3-4节` · `3-4` · `6-7` · `13` |

```csv
课程 Course title,教师 Teacher,周次 Weeks,星期 Day,节次 Class time
网络与新媒体概论 Introduction to Network & New Media,Teacher A,第1-16周,星期一,第6-7节
社会学概论 Introduction to Sociology,Teacher B,第1-16周,星期三,第3-4节
新闻传播学新生研讨,Teacher C,第1-8周,星期二,第3-4节
```

**Valid periods:** `1-2`, `3-4`, `5-6`, `6-7`, `7-8`, `8-9`, `9-10`, `11-12`, `13`.

Sessions that already exist are skipped, so importing the same file twice is safe. Templates for both files can be downloaded inside the app.

---

## 📤 PDF export

- A4 size, one sheet per page, 18 students per page. With 19 or more students, the next page is added automatically.
- Student photos, passport names and Chinese names are included. The internal student number is **never** printed.
- File names:
  - One class: `课程名-第N周-日期-出勤名单.pdf`
  - Combined: `班级名-第N周_日期-出勤名单.pdf`

---

## 💾 Backup and restore

Your data lives in the browser's storage. Clearing browser data erases it, so back up regularly.

| Action | How |
|---|---|
| **Backup** | Tap **Backup** in the top bar. You get one `.json` file for the current major. |
| **Restore** | Tap **Restore** and choose the file. It replaces the major with the same name, or creates it. |
| **Move to a new phone** | Back up on the old device, restore on the new one. |

A line under the cards shows when you last made a backup. It turns red after 7 days.

> ⚠️ Backup files contain student names and photos. Keep them private and **never commit them to a public repository**.

---

## 🔒 Privacy

- No server, no account, no tracking, no analytics.
- All data stays in your browser's local storage.
- The only network requests load four open-source libraries from a CDN (see below). These are cached after the first load.

---

## 🧰 Tech

A single static page. No build step.

| Part | Used for |
|---|---|
| Plain HTML, CSS and JavaScript | The whole app |
| [html2canvas](https://html2canvas.hertzen.com/) + [jsPDF](https://github.com/parallax/jsPDF) | PDF export |
| [SheetJS](https://sheetjs.com/) | Reading CSV and Excel files |
| [JSZip](https://stuk.github.io/jszip/) | Reading photos from `.xlsx` files |
| Service worker + manifest | Offline use and installing as an app |

### Project files

```
attendance-sheet-maker/
├── index.html              the whole app
├── sw.js                   service worker (offline cache)
├── manifest.webmanifest    install settings
├── icon.svg                app icon
├── netlify.toml            optional, for Netlify
└── README.md
```

---

## 🌐 Deploy your own copy

<details>
<summary><b>GitHub Pages</b></summary>

1. Fork or upload the files to your repository.
2. Open **Settings → Pages**.
3. Set **Source** to **Deploy from a branch**, choose `main` and `/ (root)`, then **Save**.
4. Your app is live at `https://YOUR-USERNAME.github.io/REPO-NAME/`.

In `manifest.webmanifest`, keep `start_url` and `scope` as `"./"` and use relative icon paths.
</details>

<details>
<summary><b>Netlify</b></summary>

Drag the project folder onto [app.netlify.com/drop](https://app.netlify.com/drop), or connect the repository.
</details>

### Releasing an update

Phones keep the old version until the cache name changes. **Every time you change the app, edit the first line of `sw.js`:**

```js
const CACHE = 'attendance-v11';   // increase the number
```

After you open the updated app online, **reload twice**. On Android, close the app fully and reopen it. After an update, open the app online once so the libraries are cached again.

> Data is stored **per web address**. A GitHub Pages copy and a Netlify copy do not share data. Use Backup and Restore to move data between them.

---

## ❓ FAQ

<details>
<summary><b>Chinese text looks broken (乱码).</b></summary>

Save the file again as **CSV UTF-8 (Comma delimited)** in Excel, or use a plain `.xlsx` file.
</details>

<details>
<summary><b>Photos are in the wrong order.</b></summary>

Photos are matched by **row order**, so the picture order in the Excel file must match the student list. Fix the order with ▲ ▼, or add single photos with the camera button.
</details>

<details>
<summary><b>Some course rows were skipped.</b></summary>

The import message lists the row numbers. Check that each row has a title, a valid week, a day and one of the valid periods.
</details>

<details>
<summary><b>PDF export or Excel import does not work offline.</b></summary>

The libraries load from a CDN the first time. Open the app online once, then it works offline.
</details>

<details>
<summary><b>I changed a student's ID. Did I lose attendance?</b></summary>

No. Attendance and photos are tied to a permanent internal number, not to the ID.
</details>

<details>
<summary><b>My data disappeared.</b></summary>

Browser data was probably cleared, or you opened a different web address. Restore your latest backup file.
</details>

---

## 🤝 Contributing

Issues and suggestions are welcome. Please do **not** attach real student data, photos or backup files to an issue.

## 📜 License

Released under the [MIT License](LICENSE).

---

<div align="center">

**Developed by Badhon · 开发者：巴栋**

If this tool saves you time, a ⭐ on the repository is appreciated.

</div>
