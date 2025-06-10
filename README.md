# My Tasks App

Developer: Harsh Dixit

### Description

This is a simple React Native mobile application called "My Tasks," built using Expo. The app allows users to add, view, complete, and delete tasks. It features local notifications for task reminders and persists tasks using AsyncStorage. The app includes a clean UI with visual distinction for completed tasks and supports notification cancellation when tasks are completed.

### Setup Instructions

1. **Prerequisites**:

   - Node.js (v16 or later)
   - Expo CLI: Install globally using `npm install -g expo-cli`
   - EAS CLI: Install globally using `npm install -g eas-cli`
   - A physical device (Android/iOS) for testing (Expo Go has limitations with notifications on SDK 53+)

2. **Clone the Repository**:

   ```bash
   git clone https://github.com/HarshDikshit/my-task-app.git
   cd my-task-app
   ```

3. **Install Dependencies**:

   ```bash
   npm install
   ```

4. **Create a Development Build**:

   - **Configure EAS Build**:

     ```bash
     eas build:configure
     ```

   - **Build for Android**:

     ```bash
     eas build --profile development --platform android
     ```

     - Follow the prompts to sign in to your Expo account.
     - Once the build completes, download the APK and install it on your Android device.

   - **Run the Development Client**: Start the development server:

     ```bash
     npx expo start --dev-client
     ```

     Scan the QR code with your device to run the app on the development build.

5. **Dependencies**:

   - `react-native`
   - `expo`
   - `@react-native-async-storage/async-storage`
   - `expo-notifications`
   - `expo-checkbox`

### Features

- **Core Functionality**:
  - Add tasks via a text input and button.
  - Display tasks in a scrollable list with completion status (checkbox).
  - Toggle task completion with a strikethrough effect for completed tasks.
  - Delete tasks using a trash icon.
  - Schedule local notifications 10 seconds after task creation with task name and reminder message.
- **Bonus Features**:
  - Persist tasks using AsyncStorage.
  - Cancel notifications when tasks are marked complete.
  - Basic error handling
  - Simple UI enhancements.

### Challenges & Design Choices

- **Notifications**: Used Expo Notifications for local reminders, scheduling them 10 seconds after task creation for testing purposes. Cancelled notifications on task completion to avoid unnecessary alerts.
- **Persistence**: Implemented AsyncStorage to save tasks, ensuring data persists across app restarts.
- **UI**: Chose a minimalistic design with checkboxes for completion and a trash icon for deletion, prioritizing usability and clarity.
- **Error Handling**: Added validation to prevent empty tasks and included try-catch blocks for AsyncStorage operations.

### Running the App

- Use a development build to fully test notifications (required for Android due to Expo Go limitations).
- Ensure notifications are enabled on your device for reminders to work.
- Test on a physical device for the best experience, as some features (e.g., notifications) may not work fully in simulators or Expo Go.