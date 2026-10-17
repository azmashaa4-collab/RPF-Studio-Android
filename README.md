# RPF Studio — Android starter project

An Android Studio starter for an OpenIV-inspired GTA V RPF editor UI.

## Current status

**Prototype only — not a working RPF editor APK yet.**

Implemented:
- Android project structure and launcher screen
- Android Storage Access Framework file picker for selecting an `.rpf` file
- UI placeholders for file listing, Extract, Replace, and Save As

Not implemented yet:
- Actual RPF7 archive parsing / file listing
- Extracting entries from an RPF
- Replacing an entry and rebuilding the archive
- GTA V encrypted archive key handling
- Validation against the user's XHYN Android GTA V files

## RPF engine plan

The intended backend is the open-source Rust crate `rpf-archive`:
https://github.com/VIRUXE/rpf-archive-rs

Its README documents RPF7 read/write support. Android integration still needs a Rust/JNI layer (for example, build the Rust library for Android ABIs with cargo-ndk, expose open/list/extract/rebuild calls over JNI, and call those methods from Kotlin). Retail/encrypted GTA V archives may require keys from the user's own game installation; the app must not claim that every archive can be opened without keys.

## Open in Android Studio

1. Extract this ZIP on a computer.
2. Open the `RPF_Studio_Android` folder in Android Studio.
3. Allow Gradle sync.
4. Build > Build APK(s).

This produces only the UI prototype until the Rust archive backend is integrated. It is not yet suitable for editing your real `update2.rpf`.
