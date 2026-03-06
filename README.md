# CognitoSense

A mobile application for **dementia screening and cognitive risk assessment**. It combines questionnaires, cognitive games, and eye-tracking analysis to evaluate dementia risk.

> **Disclaimer:** Results are preliminary. Users should consult healthcare professionals for accurate diagnosis.

## Features

- **Questionnaire Assessment** — Multi-section questionnaire evaluating cognitive and health metrics
- **Cognitive Games** — Memory Dialer, Shopping List Recall, Laundry Sorter, Money Manager
- **Eye Tracking Analysis** — Camera-based eye tracking to detect cognitive patterns
- **Risk Score Visualization** — Animated display categorizing risk as Low, Moderate, High, or Very High
- **Multi-language Support** — English, Spanish, Hindi, Bengali, Tamil, Telugu, Marathi

## Tech Stack

- **Expo** ~54.0 with React Native 0.81 and React 19
- **Expo Router** v6 (file-based routing)
- **TypeScript**
- **React Native Reanimated** for animations
- **AsyncStorage** for local persistence
- **Axios** for API communication

## Getting Started

### Prerequisites

- Node.js 20+
- npm

### 1. Install dependencies

```bash
npm install
```

### 2. Configure environment

Copy `.env.example` to `.env` and fill in the values:

```env
API_URL=https://<your-api-url>/
EXPO_PUBLIC_API_URL=https://<your-api-url>/
```

### 3. Start the app

```bash
npx expo start
```

Then open the app in:

- [Expo Go](https://expo.dev/go) (quick preview)
- [Android emulator](https://docs.expo.dev/workflow/android-studio-emulator/)
- [iOS simulator](https://docs.expo.dev/workflow/ios-simulator/)
- [Development build](https://docs.expo.dev/develop/development-builds/introduction/)

## Docker (Web)

Build and serve the Expo web export:

```bash
docker build --build-arg EXPO_PUBLIC_API_URL=https://api.cognitosense.in/ -t cognitosense .
docker run -p 3000:3000 cognitosense
```

The web app will be available at `http://localhost:3000`.

## Project Structure

```
app/                  # Screens (file-based routing)
├── (tabs)/           # Tab navigation (Home, Explore)
├── games/            # Cognitive game screens
├── questionnaire/    # Assessment questionnaire
├── register.tsx      # User registration
├── access.tsx        # Dashboard with test options
├── eye-test.tsx      # Eye tracking test
└── result.tsx        # Risk score results
components/           # Reusable UI components
constants/            # Theme configuration
context/              # AuthContext, LanguageContext
hooks/                # Custom hooks
assets/               # Images, eye test HTML
```
