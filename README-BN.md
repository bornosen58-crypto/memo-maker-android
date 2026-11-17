# Memo Maker Android — প্রাথমিক Capacitor প্যাকেজ

এই ফোল্ডারে Memo Maker V12-এর HTML ফাইল Capacitor-এর `www/index.html` হিসেবে রাখা হয়েছে। এটি Android wrapper তৈরির প্রাথমিক সোর্স প্রজেক্ট; এটি এখনো APK/AAB নয়।

## প্রয়োজনীয় সফটওয়্যার
- Node.js 22 বা তার পরের সংস্করণ
- Android Studio (সাথে Android SDK)
- Android Studio-তে Android 16 / API 36 SDK ইনস্টল করা

## Android প্রজেক্ট তৈরি
এই ফোল্ডারে Terminal/Command Prompt খুলে চালান:

```bash
npm install
npx cap add android
npx cap sync android
npx cap open android
```

Android Studio খুললে Gradle sync শেষ হতে দিন। তারপর ফোন USB debugging দিয়ে যুক্ত করে Run চাপুন, অথবা Build মেনু থেকে APK তৈরি করুন।

## গুরুত্বপূর্ণ
- `com.memomaker.app` একটি প্রাথমিক Application ID; Play Store-এ প্রকাশের আগে আপনার পছন্দের স্থায়ী, অনন্য ID নিশ্চিত করতে হবে। প্রকাশের পরে এটি বদলানো যায় না।
- Play Store-এ জমা দেওয়ার জন্য পরে Android App Bundle (AAB), release signing key, app icon, screenshots, privacy policy এবং Data safety form প্রস্তুত করতে হবে।
- V12-এর browser-based Web Share API Android WebView-এ সব ডিভাইসে একইভাবে কাজ নাও করতে পারে। তাই Android ফোনে পরীক্ষা করে প্রয়োজন হলে Capacitor native Share integration যোগ করতে হবে।
- HTML-এর localStorage-এ থাকা মেমোগুলো Android WebView-এর app data-তে থাকবে; অ্যাপ uninstall বা data clear করলে সেগুলো মুছে যেতে পারে। Backup/restore ব্যবহার করে আলাদা ব্যাকআপ রাখতে হবে।
