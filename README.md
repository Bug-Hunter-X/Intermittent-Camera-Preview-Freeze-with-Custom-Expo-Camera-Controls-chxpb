# Expo Camera Preview Freeze Bug

This repository demonstrates a bug encountered when using the Expo Camera API with custom controls.  The camera preview intermittently freezes, displaying a black screen or distorted image before recovering. This issue only occurs with custom controls; the standard Expo Camera functionality works as expected.

## Bug Description

When adding custom controls (buttons or other UI elements) to interact with the Expo Camera (e.g., toggling flash, switching between front and rear cameras), the camera preview will occasionally freeze.  The freeze is temporary, but it significantly impacts user experience.

## Reproduction Steps

1. Clone this repository.
2. Run `npm install`.
3. Run the app in an Expo Go or managed workflow environment.
4. Interact with the custom camera controls (flash button, camera switch button).
5. Observe that the camera preview occasionally freezes.

## Solution

The solution involves ensuring that all state updates related to the camera are handled correctly within the `useEffect` hook, preventing race conditions and asynchronous issues.  The updated code handles camera updates in a more controlled way, eliminating the intermittent freeze.