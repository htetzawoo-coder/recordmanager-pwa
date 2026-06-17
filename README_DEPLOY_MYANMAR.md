# RecordManager_2D_Logic_Pro v1.5.0 PWA Install / Deploy

ဖိုင်ဖွဲ့စည်းပုံ:

```txt
RecordManager_PWA_v1.5.0/
├── index.html
├── manifest.json
├── sw.js
├── firebase.json
├── .firebaserc
├── firestore_rules_v1_5_0_safe.rules
└── icons/
    ├── icon-192.png
    └── icon-512.png
```

## Android Chrome တွင် Install လုပ်ရန်

PWA install ခလုတ်သည် app ကို HTTPS hosting ပေါ်တင်ပြီးမှ အလုပ်လုပ်ပါမည်။ Local file (`content://` သို့ `file://`) မှာ Service Worker မလုပ်နိုင်ပါ။

Hosting ပြီး URL ကို Chrome ဖြင့်ဖွင့်ပါ။

1. Login စမ်းပါ။
2. အပေါ်က `Install` ခလုတ်ပေါ်ရင် နှိပ်ပါ။
3. ခလုတ်မပေါ်လျှင် Chrome `⋮` → `Add to Home screen` သို့ `Install app` ကိုနှိပ်ပါ။

## Firebase Hosting ဖြင့် Deploy ရန်

PC/Termux/Cloud Shell တစ်ခုလိုနိုင်ပါသည်။

```bash
npm install -g firebase-tools
firebase login
cd RecordManager_PWA_v1.5.0
firebase deploy --only hosting
```

Deploy ပြီး Firebase Hosting URL ကို Chrome မှာဖွင့်ပြီး install လုပ်ပါ။

## Firestore Rules

`firestore_rules_v1_5_0_safe.rules` ကို Firebase Console → Firestore Database → Rules ထဲ paste လုပ်ပြီး Publish လုပ်ပါ။

## မှတ်ချက်

- PWA install သည် HTTPS လိုအပ်ပါသည်။
- Firebase REST login/data save/load က အရင် project config အတိုင်း ဆက်သုံးထားသည်။
- Offline app shell cache ပါပြီး internet ပြန်ရှိချိန် Cloud sync သုံးပါသည်။
