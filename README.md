# GlassEcho: offline web app

A guideline-based, computer-assisted echocardiography interpretation and teaching tool. (Formerly "Echo workbook".)

Built 2026-10-20. Version cdf2cee33de5 (v61: ASE 2025 indeterminate diastology panel and Study overview diastolic card; PASP can be entered on the Diastology page; reading timer, coded indication, image quality and protocol items, counts on Saved studies; quality dashboard; wall motion fill by territory and culprit vessel; image-quality defaults, normal-valve button; compare with attending and agreement statistics; LVEF range in 5% intervals; LVEF category follows the reported interval; attending diastology vs 2016/2025; prefill the attending read from pasted text; all at-a-glance items compared, attending comparison shown with the study; comparison organised like the Echo page; PH grade and multiple critical findings; attending comparison opens from Saved studies; measurements prefilled from the official report; GE EchoPAC labels; narrative report format; indications without "Known" or "follow-up"; one-tap paste from the clipboard; phone menu scrolls; 2016 myocardial disease set from LVEF, wall motion and LV hypertrophy; agreement with entered items only; renamed GlassEcho; title screen and cut-glass logo).

## What is in this folder

- `index.html`: the whole workbook in one file.
- `sw.js`: keeps a copy on the device so the app opens without a connection.
- `manifest.webmanifest` and the four `.png` icons: the name and icon used on the home screen.

Keep all of these files together at the top level of one folder (no subfolders).

## 1. Put it on a web address

The address must use **https**. Any host that serves plain files works. Two common choices:

**GitHub Pages (free)**
1. Create a GitHub account and a new repository (public; private needs a paid plan for Pages).
2. Upload everything in this folder to the repository.
3. Settings → Pages → Source: "Deploy from a branch" → branch `main`, folder `/ (root)` → Save.
4. After a minute the app is at `https://<your-user>.github.io/<repository>/`.

**Your institution's web server**
Ask IT for a folder served over https and copy the files there.

The page asks search engines not to index it, but anyone who has the address can open the tool. No patient data is stored on the server: everything typed stays on the device that typed it.

## 2. Install it on the iPhone

1. Open the address in **Safari** (not another browser) while online.
2. Tap Share → **Add to Home Screen** → Add.
3. Open it once from the new icon while still online. A message "Ready to use offline" confirms the copy is stored.

From then on it opens full screen, with or without a connection.

## 3. Where your studies live

- Saved studies are kept **on that phone only**, inside the home-screen app. They do not sync to other devices or to the Claude version.
- Deleting the icon deletes its saved studies. Use Saved studies → **Export backup** regularly, and **Import backup** to move them to another device.
- On the iPhone, exports open the share sheet so you can save to Files or send them.

## 4. Updating

Replace `index.html` and `sw.js` on the server with the new ones (they change together; in this update `manifest.webmanifest` changed too). The app picks up the new version the next time it is opened online, and shows it on the following launch.

## Notes

- Educational aid; not a medical device. See "Educational use and legal notice" in the Guide.
- Do not enter protected health information unless your institution's policies allow it.
- The two web fonts load from Google the first time and are then kept on the device; without them the app uses the phone's own fonts.
