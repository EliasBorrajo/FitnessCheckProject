# FitnessCheckProject 🏃‍♀️📊

> Self‑assessment of physical activity and mobility — built with **React 18 + Firebase**.

## Introduction

**FitnessCheck** is a React application that gathers user fitness data, offers personalised advice and visualises the results through an interactive radar plot for easy understanding. The data is stored in **Firestore**.

Developed as part of the **Web Development Project** at the University of Applied Sciences **HES‑SO Valais‑Wallis**.



## Project Goal

Provide an easy‑to‑use web questionnaire that lets anyone:

- Sign up with Google or email, then fill in two short surveys about **physical activity** and **mobility**.
- Instantly visualise their scores on a radar chart and receive tailored recommendations.
- Calculate their **IMC/BMI** in a dedicated tool.
- Save, download or email the results.

*Built in semester 6 at ****HES‑SO – Informatique de gestion**** as a learning project.*

## Features

- 🔐 **Firebase Authentication** (email + Google) & automatic user profile creation.
- 📝 Dynamic, branch‑logic **survey** (Part A & B) stored in Firestore.
- 📈 Radar‑plot visualisation with **@nivo/radar**.
- ⚙️ **Admin** back‑office to seed / edit questions & messages.
- 🧑‍🤝‍🧑 **Group leader** view to consult participant results.
- 🏗️ Dark / light theme toggle (Context API).
- 📤 Export results: e‑mail or plain‑text download.

## Tech Stack

| Layer       | Libs / Tools                                                        |
| ----------- | ------------------------------------------------------------------- |
| Front‑end   | React 18, React Router 6, @nivo/radar                               |
| Data/Auth   | Firebase v9 (Auth + Firestore)                                      |
| UI flows    | react‑firebaseui                                                    |
| Dev / Build | Create‑React‑App, ESLint, Jest                                      |
| Ops         | Multi‑stage **Dockerfile** + **Docker Compose** with Traefik labels |

## 📁 Structure

```
.
├── src/
│   ├── components/     # Questionnaire, results, admin forms
│   ├── screens/        # Routed pages (Home, Questionnaire, Resultats, Admin…)
│   ├── ThemeContext.js # light/dark toggle
│   └── initFirebase.js # Firebase boot‑strap
├── public/             # CRA static files
├── Dockerfile          # Build & runtime stages
└── docker-compose.yml  # One‑click container startup
```

## Installation

```bash
git clone https://github.com/EliasBorrajo/FitnessCheckProject.git
cd FitnessCheckProject
cp .env.sample .env      # add your Firebase keys
yarn install
yarn start               # http://localhost:3000
```

## Docker (+ Traefik)

```bash
# build & run
docker compose up -d
```

Labels inside `docker-compose.yml` expose the app through Traefik; adjust `TRAEFIK_URL` in `.env`.

## Requirements

- Node 16+ & Yarn
- A Firebase project with **Email/Google Auth** and a **Firestore** database
- (Optional) Docker 23+ and Traefik reverse‑proxy

## Developers

- François Brouchoud
- Julienne Bétrisey
- Arthur Avez
- Elias Borrajo
- Théo Clerc

## 📝 Notes

This is a **proof of concept / educational** project; security hardening and exhaustive tests are out of scope.

## Status

📁 **Archived** — no active maintenance. Feel free to fork & experiment!

## License

GPL‑3.0 — see [LICENSE](./LICENSE).

