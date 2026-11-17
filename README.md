# WallFlow Privacy Policy

Effective date: November 13, 2026

This policy describes information handled by the WallFlow desktop application (“WallFlow”), what stays on your PC, and what is sent to connected services when you use their features.

## 1. Information stored on your PC

WallFlow stores app settings, favorites, search history, download history, wallpaper history, user-uploaded image records, and account display details in its local app data folder. Preview thumbnails and wallpaper search response caches are also stored locally. Images uploaded from this PC are copied into WallFlow’s local wallpaper library. Downloaded wallpapers are saved only when you choose a download action and remain in the download folder selected in Settings.

If you use the Developer/Admin Control Center, WallFlow stores local request counters, provider status, timestamps, and non-reversible API-key fingerprints. It does not store raw API keys in these counters or store search terms in the counters.

Account display details such as name, email address, account creation date, and a cached Google profile picture are stored locally in WallFlow settings or its thumbnail cache. Firebase and Google refresh tokens are stored in the Windows credential store. WallFlow does not save your email password in its settings.

## 2. Information sent to connected services

**Wallpaper search.** When you search or browse a category, WallFlow sends the search text, page request, and the configured provider credential to the applicable wallpaper API. Supported search providers are Wallhaven, Nexwall, and Pixabay. Pexels is not queried by this version of WallFlow. Providers may receive your network address, request time, and standard connection information when your PC contacts their services. Wallpaper images are fetched from the image hosts returned by those providers so WallFlow can show previews or fulfill a download you choose.

**Account sign-in.** If you create an account or sign in with email and password, WallFlow sends that information to Firebase Authentication over HTTPS. Firebase returns authentication tokens and profile details. WallFlow does not save your email password. If you choose Google sign-in, the app opens Google in your default browser and requests only OpenID, email, and basic profile access. The installed-app flow uses PKCE and does not rely on a client secret. Google provides an identity token and basic profile details; WallFlow passes the identity token to Firebase Authentication to create or sign in to the WallFlow account. Google and Firebase process information under their own policies.

**API credentials.** Provider keys are read from your local `.env` file or environment settings; Wallhaven may also be read from Windows Credential Manager. WallFlow sends a key only to its corresponding provider when it makes an API request. Keep your `.env` file private and do not share it.

**Public Community uploads and trends.** If you choose **Share publicly** after adding a wallpaper, WallFlow sends an optimized image copy, title, and tags to the configured Community service. Firebase verifies the signed-in account; Supabase stores the public image and wallpaper record. A Firebase account ID is stored privately with the record so the signed-in profile can list that account's uploads; that ID is not shown to other users. Other WallFlow users can search, view, download, and retain copies. Searches made while signed in can be counted once per account per day for the rolling seven-day trending list. The trend service stores a one-way hash of the account ID for deduplication, plus the search term and date, for up to 45 days; it does not store email or display name. Do not share images you do not have permission to publish.

## 3. Information WallFlow does not send

WallFlow does not send downloaded files, local-only wallpapers, favorites, local history, general settings, or local Control Center counters to a WallFlow-operated server. Public wallpapers are sent only after you accept the sharing prompt. This build does not include a WallFlow analytics or advertising service. Search text and account information are sent to the services needed to fulfill the search, community-trend, or sign-in feature as described above.

## 4. Retention and your choices

Local settings and history remain on your PC until you clear or reset them or manually remove the relevant app data. Uninstalling WallFlow may not remove files in your app data or Downloads folders. **Clear Cache** removes cached previews, profile pictures, and wallpaper search responses. **Clear Search History** removes saved search terms. Resetting application data resets preferences, favorites, search history, and wallpaper history, while keeping download history, account details, downloaded files, and imported image files. Imported image records are reset, so imported files may need to be removed manually. Downloaded wallpapers remain until you delete them yourself. Local Control Center counters remain in WallFlow app data until that data is removed.

Signing out removes saved local authentication tokens and account details from WallFlow. A cached Google profile picture may remain until you clear the cache. Signing out does not delete your Firebase account. WallFlow currently has no in-app account deletion control. Google access revocation is requested during sign-out when possible.

You can review or change your Google or Firebase account information through the account controls provided by those services. Their retention and privacy practices are controlled by those services.

## 5. Security

WallFlow stores authentication refresh tokens in Windows Credential Manager and keeps preferences and profile display details in local app data. API keys in `.env` are plain-text configuration values on your PC. Use Windows account protections, keep your PC secure, and do not share your private configuration file.

No method of local or internet storage is completely risk-free. Wallpaper APIs, Google, Firebase, and Supabase receive only the requests needed for the features you use and handle them under their own security and privacy practices. Community wallpaper images are public after you approve sharing; there is currently no in-app delete or moderation workflow for those public uploads.

## 6. Children and changes

WallFlow is a general desktop application and is not designed to collect information from children. This policy may be updated with a later release; the current version is included with WallFlow and available from Settings or About.

## 7. Pinterest integration

Pinterest integration is not included in this version of WallFlow. The app does not request or store a Pinterest API key, connect to Pinterest, or send Pinterest account or wallpaper data to Pinterest. Do not add an API key to this policy, source code, or a distributed app package. If a future version adds Pinterest features, this policy will be updated before release to describe the data shared, how credentials are protected, and the choices available to users.

