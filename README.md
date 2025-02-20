# Expo iOS StatusBar.setBarStyle TypeError

This repository demonstrates a bug encountered when using the `StatusBar.setBarStyle` method in Expo on iOS. The issue is that on iOS, `StatusBar.setBarStyle` throws a `TypeError: undefined is not an object (evaluating 'StatusBar.setBarStyle')` while working correctly on Android.

## Bug Description

The `StatusBar` API from `react-native` is used to set the bar style.  This works fine on Android but fails on iOS with the error described above.  The code attempts to set the status bar style to `dark-content`.

## Solution

The solution involves ensuring that the `StatusBar` API is used correctly *after* the component has mounted.  This can be achieved by using the `useEffect` hook to conditionally apply the status bar style.