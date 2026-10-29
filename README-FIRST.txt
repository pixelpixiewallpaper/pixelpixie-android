PIXELPIXIE WALLPAPERS — ANDROID CLOUD BUILD STARTER

IMPORTANT: This is a demo app wrapped in Android WebView, NOT a production-ready paid wallpaper app. Checkout is simulated. Do not publish for sale yet.

PHONE-ONLY BUILD USING GITHUB ACTIONS
1. Create a PRIVATE GitHub repository, e.g. pixelpixie-android.
2. Upload the CONTENTS of this ZIP to the root of the repository (including the .github folder). GitHub's mobile website may make uploading folders difficult; you may need a GitHub-capable mobile Git client or cloud IDE. Do not upload the ZIP alone.
3. In GitHub repository Settings > Secrets and variables > Actions, create TWO repository secrets:
   PIXELPIXIE_STORE_PASSWORD = a strong password of your choice
   PIXELPIXIE_KEY_PASSWORD = the SAME strong password
4. Open Actions > Build Pixelpixie Android test bundle > Run workflow.
5. After the workflow succeeds, download artifact 'pixelpixie-signed-aab'. Extract it to obtain the .aab file.
6. IMPORTANT: Download artifact 'IMPORTANT-save-upload-key' and store pixelpixie-upload.jks securely with your passwords. Future releases MUST reuse this upload key. Store an additional backup. On later builds, add PIXELPIXIE_KEYSTORE_BASE64 secret containing base64 of the original .jks file; otherwise workflow generates a different key. An upload key reset may be possible through Play Console but is not automatic.
7. In Play Console open your app > Testing > Internal testing > Create new release > upload .aab. Finish required declarations and testers, then roll out internal testing.

LIMITATIONS
- This is a build starter. It has not been compiled or tested here.
- No real Google Play Billing, secure delivery, cloud catalogue, admin authentication, privacy policy, or production backend.
- The app package name au.com.pixelpixie.wallpapers must be checked before first upload; after upload the package ID cannot be changed for that app.
- Android app bundles are not directly installable on phones; Play Console distributes installable versions to testers.
- Never put signing passwords or the .jks file in public repositories.
