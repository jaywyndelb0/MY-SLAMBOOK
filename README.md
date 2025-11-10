# MySlamBook (Android)

A modern, multi-screen Android app for creating, viewing, and managing personal “slam book” entries. It guides users through a three-part form with rich validation, lets them attach a profile photo (camera or gallery), and stores entries locally for quick listing, editing, and detailed viewing.

## Overview
- Multi-step form collects personal info, favorites, and reflections.
- Robust input validation and helpful feedback messages throughout.
- List screen with add, edit, delete, and empty-state UI.
- Details screen presents a clean summary of each entry.
- Local persistence via `SharedPreferences` and JSON (Gson).
- Profile image capture with Camera and Gallery, using `FileProvider`.
- ## Features
- Personal info: name, nickname, contact, address, birth date, gender, status.
- Favorites: songs, movies; plus hobbies and skills with rating.
- Reflections: definitions of love/friendship, memorable experience, describe me, advice.
- Profile picture: capture via camera or select from gallery.
- Validation: comprehensive checks with inline errors and snackbars.
- Persistence: save, update, delete entries; survives app restarts.

## Tech Stack
- Android, Kotlin, ViewBinding
- Material Components, RecyclerView, Navigation
- Gson for local JSON storage
- Glide for image loading

## Project Structure
- `app/src/main/java/com/kodego/bagsic/jaywyndel/myslambook/`
  - Activities: `MainActivity`, `MenuActivity`, `SlamBookListActivity`, `SlamBookDetailsActivity`, `FormActivity`, `Form1Activity`, `Form2Activity`, `Form3Activity`
  - Adapters: `SlamBookListAdapter`, `AdapterSong`, `AdapterMovie`, `AdapterHobbies`, `AdapterSkill`
  - Model: `SlamBook` (+ `Song`, `Movie`, `Hobbies`, `Skill`)
  - Data: `SlamBookDataManager` (SharedPreferences + Gson)
  - Utils: `ValidationUtils`
- Resources: layouts, drawables, themes, navigation
- Manifest: permissions, `FileProvider`, activity declarations

## Requirements
- Android Studio (Giraffe/Koala or newer)
- Android SDK: compile/target `33`, min `23`
- JDK 11 (wrapper configured via `gradle.properties`)
- Gradle wrapper: `gradle-8.5`

## Setup
1. Clone the repository: `git clone https://github.com/<your-username>/MySlamBook.git`
2. Open the project in Android Studio.
3. Let Android Studio sync Gradle and download dependencies.
4. Run the app on an emulator or a device (Android 6.0+).

## Build and Test (CLI)
- Windows: `gradlew.bat assembleDebug`
- Mac/Linux: `./gradlew assembleDebug`
- Instrumentation tests (if added): `./gradlew connectedAndroidTest`

## Usage
- Launch the app to open the Menu.
- Tap “Slam Book List” to view entries and add a new one.
- Complete the Form pages (Personal Info → Favorites → Reflections).
- Optionally add a profile picture via Camera or Gallery.
- Save to persist locally; edit or delete from the list.
- Tap an entry to view full details.

## Permissions
Declared in `AndroidManifest.xml`:
- `CAMERA` for capturing photos.
- `READ_MEDIA_IMAGES` (API 33+) or `READ_EXTERNAL_STORAGE` for gallery access.
- `FileProvider` is configured via `xml/file_paths` for secure image sharing.

## Data Persistence
- Entries are serialized to JSON using Gson and stored in `SharedPreferences`.
- Key: `slam_books` within `SlamBookDataManager`.
- Includes fields for profile image URI and rating.

## Notes
- The app focuses on local storage and does not use a remote backend.
- Some legacy storage permissions may be present for compatibility; on API 33+ `READ_MEDIA_IMAGES` is used.

This repository contains my SLAMBOOK project files.

📦 **Download the full project (ZIP file):**  
👉 [Click here to download from Google Drive](https://drive.google.com/file/d/1lt7WKQzxPBecH7y-v-ipOuqWeTVFlG8m/view?usp=drive_link)


