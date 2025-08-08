# Description
The code of this repository is referenced from: https://github.com/himanshuGaur684/Book-Summary

# Android Storage Classification

Android storage is broadly categorized into **internal** and **external** storage, with further **distinctions for** **app-specific** and **shared storage**. 
**Internal storage** is where the OS and apps are installed, while **external storage** can be either physical media like SD cards or emulated storage. 
**Scoped storage**, introduced in Android 10, restricts app access to shared storage, particularly for non-media files, prioritizing user privacy.

## 1. Internal Storage

-   **Description**:
    -   Located in the device's private memory.
    -   Only the app and the operating system can access it.
    -   When the app is uninstalled, all data in this area is deleted.
-   **Subcategories**:
    1.  **App-specific internal storage**
        -   App's private data (`/data/data/<package_name>/files` or
            `/data/data/<package_name>/cache`).
        -   Accessible only by that app.
    2.  **Shared internal storage**
        -   Rarely used, usually managed by the system.
-   **Examples**: Configuration files, SQLite databases, temporary
    cache.

## 2. External Storage

-   **Description**:
    -   Can be a **physical SD card** or **emulated storage**.
    -   Accessible by multiple apps (if permissions are granted).
-   **Subcategories**:
    1.  **App-specific external storage**
        -   App's data stored externally
            (`/storage/emulated/0/Android/data/<package_name>/files`).
        -   Other apps cannot access it without permission.
    2.  **Shared external storage**
        -   Common area shared among apps.
        -   Examples: `Pictures/`, `Music/`, `Movies/`, `Download/`.
    3.  **Scoped storage (Android 10 and above)**
        -   Limits access to shared storage, especially for non-media
            files.
        -   Apps can only access shared media files via **MediaStore
            API** or their own files.

## 3. Special Storage

-   **Examples**:
    -   **Cache**: Temporary storage that may be cleared by the system
        when needed.
    -   **Databases**: SQLite, Realm, etc., stored in internal storage.
    -   **Preferences**: SharedPreferences for storing key-value
        configuration.

------------------------------------------------------------------------

## Summary Table

 | Storage Type | App-specific | Shared | Access Rights                                                                |
 |:-------------|:-------------|:-------|:-----------------------------------------------------------------------------|
 | Internal     | Yes          | No     | App only                                                                     |
 | External     | Yes          | Yes    | Requires READ/WRITE permission, restricted by Scoped Storage from Android 10 |

