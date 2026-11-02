# 8Vim — two-language fork

This is an **unofficial fork** of [8Vim](https://github.com/8VIM/8VIM), a gesture-based Android keyboard inspired by 8pen and Vim. It keeps the original circular input method and adds quick switching between **two user-selected keyboard layouts**.

## Changes in this fork

- **Choose two layouts:** open **8Vim settings → Layouts** and select **Language 1** and **Language 2** from the built-in or imported YAML layouts. Defaults: English and Russian.
- **Switch with one tap:** use the language icon in the keyboard's side toolbar to alternate between your two chosen layouts.
- **Remember your choices:** both selected layouts and the currently active layout are saved.
- **Android navigation bar spacing:** keep the embedded keyboard's gesture area above the system navigation bar, including on newer Android versions.
- **Cloud-buildable APK:** build a separate debug app using [Build custom 8Vim APK](https://github.com/GuardCat/8VIM/actions/workflows/manual-debug-apk.yaml). Run the workflow on `master`, then download the APK from the run's **Artifacts** section. You may need to enable Actions for your fork.

The debug build installs separately from the original 8Vim. This fork is not an official release of the upstream project.

## Permanently signed APK (for sharing with friends)

The [signed APK workflow](https://github.com/GuardCat/8VIM/actions/workflows/build-signed-apk.yaml) builds the distinct `8Vim Custom` app (`inc.flide.vi8.custom`) with a persistent signing certificate and incrementing build number. It can coexist with upstream 8Vim and with our debug build.

To configure it, create a PKCS12 keystore locally using `keytool` with the **`8vim-custom`** alias. Never commit the key, password, or base64-encoded keystore. Back up the original keystore and password somewhere secure.

Set these two **repository Actions secrets**:

- `VIM8_RELEASE_KEYSTORE_BASE64`: unwrapped base64 of the keystore file (`base64 -w 0 8vim-release.jks`).
- `VIM8_RELEASE_KEYSTORE_PASSWORD`: the keystore password (also used for the key password with PKCS12).

Run **Build signed 8Vim Custom APK** from Actions and download `8vim-custom-signed-apk` under Artifacts. The workflow verifies the APK signature before uploading it. For public distribution, attach the built APK to a GitHub Release. Future signed builds using the **same keystore and alias** can update earlier signed builds in place. Previously installed debug builds are a different app and do not share data.

---

## Original 8Vim project


[![Project Dashboard](https://sourcespy.com/shield.svg)](https://sourcespy.com/github/flide8vim/)

The application was started essentially as a clone of 8pen, which for some reason they have stopped distributing. (I can no longer install it, even though I paid for it!)

To exactly understand this keyboard, please watch the [video](https://www.youtube.com/watch?v=q3OuCR0EpGo)

|                                                                                    Stable [![Stable](https://img.shields.io/github/v/release/8VIM/8VIM)](https://github.com/8VIM/8VIM/releases/latest) ![F-Droid](https://img.shields.io/f-droid/v/inc.flide.vi8)                                                                                     |  Beta [![Beta](https://img.shields.io/github/v/release/8VIM/8VIM?include_prereleases)](https://github.com/8VIM/8VIM/releases) ![F-Droid](https://img.shields.io/badge/dynamic/yaml?url=https%3A%2F%2Fraw.githubusercontent.com%2F8VIM%2Ffdroid%2Fmain%2Fbadges.yaml&query=%24%5B'8vim_rc'%5D&label=Private%20F-droid%20RC&color=orange)  | Debug ![F-Droid](https://img.shields.io/badge/dynamic/yaml?url=https%3A%2F%2Fraw.githubusercontent.com%2F8VIM%2Ffdroid%2Fmain%2Fbadges.yaml&query=%24%5B'8vim_debug'%5D&label=Private%20F-droid%20Debug&color=orange) |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| [<img src="https://fdroid.gitlab.io/artwork/badge/get-it-on.png" alt="Get it on F-Droid" height="80" />](https://f-droid.org/packages/inc.flide.vi8/) [<img src="https://play.google.com/intl/en_us/badges/images/generic/en-play-badge.png" alt="Get it on Google Play" height="80" />](https://play.google.com/store/apps/details?id=inc.flide.vi8) | [<img src="https://fdroid.gitlab.io/artwork/badge/get-it-on.png" alt="Get it on F-Droid" height="80" />](https://github.com/8vim/fdroid) [<img src="https://play.google.com/intl/en_us/badges/images/generic/en-play-badge.png" alt="Get it on Google Play" height="80" />](https://play.google.com/store/apps/details?id=inc.flide.vi8) |                                       [<img src="https://fdroid.gitlab.io/artwork/badge/get-it-on.png" alt="Get it on F-Droid" height="80" />](https://github.com/8vim/fdroid)                                        |

**Manual**: Download and install the APK from the release page.

## Become a Beta Tester

To become a beta tester please click [here](https://play.google.com/apps/testing/inc.flide.vi8)

## Usability Guide

The full guide is available [here](https://8vim.github.io/docs/)
