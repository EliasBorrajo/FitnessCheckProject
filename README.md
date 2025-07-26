# FitnessCheckProject 🏃‍♀️📊

> **Self‑assessment of physical activity, mobility & overall health risks — built with React 18 & Firebase**

---

## 📚 Project Overview

*FitnessCheck* is a single‑page React application developed during the **Web Development Project** (Semester 6 – Spring 2023) at **HES‑SO Valais‑Wallis**.

The app modernises a preventive‑health **Excel spreadsheet** created by **Dr Marc‑André Raetzo (HUG, Genève)** by embedding its logic directly into an interactive web questionnaire.
Users complete two concise forms, then immediately see their **IMC (BMI)** and multi‑category **risk scores** (cardiac, cerebrovascular, cancer, diabetes…). Results appear on an interactive radar plot and are stored in **Cloud Firestore** so they can be exported or reviewed later.

---

## 🧠 Scientific Background & Algorithm

The original Excel formulas have been **translated manually into the questionnaire code (plain JavaScript)**. Each answer feeds weighted coefficients and produces the final risk values at submit time.

**TODO** – document the coefficient mapping in detail and add automated regression tests against the spreadsheet.

> ⚠️ **Disclaimer** – For educational use only. The results do **not** constitute medical advice.

---


## 🧪 Tech Stack

| Layer           | Libs / Tools                                                     | Notes                |
| --------------- | ---------------------------------------------------------------- | -------------------- |
| **Front‑end**   | React 18 · React Router 6                                        | CRA setup            |
| **Charts**      | @nivo/radar                                                      | Radar visualisation  |
| **Algorithm**   | Plain **JavaScript**                                             | Embedded formulas    |
| **Data / Auth** | Firebase v9 (Auth + Firestore)                                   | Modular SDK          |
| **UI flows**    | react‑firebaseui                                                 | Pre‑built auth flows |
| **DevOps**      | Multi‑stage **Dockerfile** · **Docker Compose** + Traefik labels | Prod & local         |

---

## 🎯 Objectives & Use‑case

* **Authenticate** with Google or e‑mail and complete:

  * **Part A – Physical Activity**
  * **Part B – Mobility & Lifestyle**
* **Visualise** results instantly via radar plot along with personalised tips.
* Extras:

  * **IMC (BMI) calculator**
  * **Export** results (TXT download or e‑mail attachment)
  * **Group‑leader dashboard** to track participants

---

## 🔧 Key Features & Success Criteria

| Item / Criterion                  | Status | Notes                                       |
| --------------------------------- | ------ | ------------------------------------------- |
| Firebase **Email & Google Auth**  | ✅      | `react‑firebaseui` (modular SDK)            |
| **Dynamic survey** (Parts A & B)  | ✅      | Branch logic in `components/Questionnaire/` |
| Survey **storage in Firestore**   | ✅      | One document per user                       |
| **Radar plot** visualisation      | ✅      | `components/Results/RadarChart.js` (Nivo)   |
| **IMC (BMI) calculator**          | ✅      | `screens/IMC-Calculator.js`                 |
| Results **export** (TXT / e‑mail) | ✅      | `exportToTxt`, `sendMail` utils             |
| **Admin back‑office**             | ✅      | `screens/Admin.js` + seed helpers           |
| **Group‑leader dashboard**        | ✅      | `screens/GroupLeader.js`                    |
| Dark / light **theme toggle**     | ✅      | Implemented                                 |
| **Docker + Traefik** deployment   | ✅      | Multi‑stage build, labels in compose        |


---

## Developers

* François Brouchoud
* Elias Borrajo
* Théo Clerc
* Arthur Avez
* Julienne Bétrisey



## 📝 Notes

Proof‑of‑concept for academic purposes; no clinical validation or exhaustive tests.

## Status

📁 **Archived** — no active maintenance. Fork & experiment!

## License

GPL‑3.0 — see [LICENSE](./LICENSE).

---

### **Academic Info**

*Course: Project 645‑1 – Web Development* 

*Instructors: Roger Schaer & Alexandre Cotting* 

*Context : HES‑SO Valais‑Wallis — Bachelor of Science in Business IT, 6th semester*
