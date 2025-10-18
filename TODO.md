# FocusLoop Enhancement TODO

## 1. Dependencies and Assets
- [ ] Install new dependencies: `expo install react-native-linear-gradient expo-av react-native-reanimated lottie-react-native react-native-toast-message`
- [ ] Add audio assets: Download or source rain.mp3, piano.mp3, nature.mp3 to assets/sounds/ (or use Expo Asset for bundling)

## 2. Theme and Global Components
- [ ] Create src/theme.js: Define colors (violet '#8B5CF6', teal '#0D9488', orange '#F59E0B'), gradients, mood functions
- [ ] Create src/components/AnimatedBackground.js: Reanimated background gradient evolving with level/XP
- [ ] Create src/components/XPProgressBar.js: Reanimated progress bar for XP to next level
- [ ] Create src/components/AnimatedCircle.js: Lottie/Reanimated circular progress for focus loops

## 3. Core App Updates
- [ ] Update App.js: Wrap navigator in AnimatedBackground and add Toast provider
- [ ] Update AppNavigator.js: Apply theme to tab styles/icons
- [ ] Update storage.js: Add save/loadSoundPreference and badge persistence if needed

## 4. Screen-Specific Updates
- [ ] Update HomeScreen.js: Add animated circles, XP progress bar, theme styles
- [ ] Update FocusTimerScreen.js: Add sound selection/UI, audio playback logic, toast on XP earn, theme styles
- [ ] Update HabitsScreen.js: Add toast on streak milestones, theme styles
- [ ] Update RewardsScreen.js: Add XP progress bar, dynamic badge unlocks with toasts, theme styles
- [x] Update BreakScreen.js: Theme styles, optional sound pause
  - [x] Implement imports: React, View, Text, TouchableOpacity, StyleSheet, useNavigation, AnimatedBackground, theme
  - [x] Define BreakScreen component: Wrap in AnimatedBackground, add centered View with title ("Take a Break!"), subtitle ("Relax for a moment to recharge your focus."), and "End Break" button
  - [x] Style: Use flex centering, white text, teal button background with white text
  - [x] Add navigation: Button calls navigation.goBack() or navigate to 'Focus'
  - [x] Integrate BreakScreen: Update AppNavigator.js to add StackNavigator for Focus tab with BreakScreen
  - [x] Modify FocusTimerScreen.js: Remove inline break UI, navigate to 'Break' on focus end
  - [x] Enhance BreakScreen.js: Add 5-min countdown timer, random exercises array, "Next Exercise" button
  - [x] Test: Run `npx expo start`, start a focus session, complete it, verify navigation to BreakScreen with timer, exercises, gradient background, and non-blank output; end break returns to select phase

## 5. Testing and Polish
- [ ] Test app: Run `expo start`, verify gradients, animations, sounds, pop-ups on device/emulator
- [ ] Edge cases: Audio permissions, animation performance, web compatibility
- [ ] Polish: Accessibility labels, loading states, refine animations
