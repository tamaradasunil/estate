# Estate Expo demo

## Run on a phone with Expo Go

1. Install dependencies with `npm install`.
2. Start the project with `npm start` (or `npm start -- --tunnel` when the phone is not on the same Wi-Fi).
3. Scan the terminal QR code using Expo Go on Android or the Camera app on iOS.

The current Expo Go session is using LAN mode. The phone and computer need to be on the same Wi-Fi network. The QR is regenerated each time the server starts.

## Build an installable APK

The project includes an EAS Build `preview` profile that produces an APK. Sign in to an Expo account once with `npx eas-cli login`, then start the build with `npx eas-cli build --platform android --profile preview`. EAS may ask to link this project to an Expo account and create Android signing credentials on the first build. The completed APK can be downloaded from the EAS build page or the CLI output.

## What's included

- Map and list exploration, global sample listings, sale/rent switch, text search, category and price filters.
- Device location permission with high accuracy request, reported accuracy, retry and failure states.
- Property preview/details, favorites, directions link, local enquiries, listing creation and photo selection.
- Local profile and listing management entry points.

## Demo limits and integration points

All sample homes are explicitly marked as sample listings and are geographically spread across multiple regions. New listings, favorites, profile fields and enquiries live only in app memory and reset when the app restarts. The account screen does not authenticate a user; there is no backend, database schema, live listing API, place autocomplete provider, or server-side photo storage configured. Consequently, real worldwide search, precise listing-location picking/public precision controls, cross-device persistence, enquiry delivery, and listing pause/reactivate/delete are not active integrations yet. The listing form currently saves an approximate location using device coordinates when available, or the clearly global fallback map center.

Price is formatted from each listing's currency. User-created demo listings use USD. Area units are shown per listing. Property photos are remote demo images; adding a photo to a listing only keeps its local URI during the current app session. Subscription and purchase restoration are unavailable because no store configuration is present.

Location permissions are requested while Explore opens. Accuracy is the platform-reported value; a high-accuracy request is not a guarantee of any particular precision. Map tiles and remote images require network access. `react-native-maps`, `expo-location`, and `expo-image-picker` are used through Expo Go compatible packages.
