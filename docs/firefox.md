# Firefox

## Credit card autofill / autocomplete

* [Mozilla wiki](https://wiki.mozilla.org/Firefox/Features/Form_Autofill#Release)
* [Reddit](https://www.reddit.com/r/firefox/comments/kcdacw/no_credit_card_auto_fill_option_already_tried/)

about:config settings
```
extensions.formautofill.available = 'on'
extensions.formautofill.creditCards.available = true
extensions.formautofill.creditCards.enabled = true
extensions.formautofill.supportedCountries = 'US,CA'
```

## Right-click bug with BSPWM

Right-click automatically selects the option under the mouse when the mouse button is released. This makes it difficult to use the right-click context menu. This bug only occurs in certain window managers such as BSPWM or i3 when the firefox window is not fullscreen.

### Workaround

In about:config set `ui.context_menus.after_mouseup: true`

* [bugzilla issue](https://bugzilla.mozilla.org/show_bug.cgi?id=1472544)
* [reddit discussion](https://www.reddit.com/r/i3wm/comments/88k0yt/right_mouse_btn_instantly_clicks_first_option_in/) 

## Add-ons (browser extensions) in Firefox Nightly on Android

- [Expanded extension support in Firefox for Android Nightly](https://blog.mozilla.org/addons/2020/09/29/expanded-extension-support-in-firefox-for-android-nightly/)
- [Firefox add-ons](https://addons.mozilla.org/en-CA/firefox/)
- [Andornaut's add-on collection](https://addons.mozilla.org/en-CA/firefox/collections/)

In Firefox Nightly for Android:

1. Settings -> About Firefox Nightly
1. Tap the logo 5 times
1. Back in Settings, click Custom Add-on collection
1. Enter eg. Collection owner: 16021357, Collection name: android
