# দৈনিক খাতা — APK বানানোর নিয়ম (GitHub দিয়ে, বিনামূল্যে)

১. github.com এ অ্যাকাউন্ট খুলে নতুন repository বানান (Private রাখতে পারেন)।
২. এই ZIP খুলে ভেতরের সব ফাইল ও ফোল্ডার repository তে আপলোড করুন (Add file → Upload files)।
   `.github` ফোল্ডার আপলোড না হলে: Add file → Create new file, নাম লিখুন `.github/workflows/build-apk.yml`
   এবং এই প্রজেক্টের একই নামের ফাইলের লেখা পেস্ট করুন।
৩. Actions ট্যাব → "Build APK" → Run workflow চাপুন।
৪. ৫ থেকে ১০ মিনিট পর সবুজ টিক এলে ওই run খুলুন। নিচে Artifacts এ `khata-apk` নামান।
   ZIP খুললে `app-debug.apk` পাবেন।
৫. APK ফোনে নিয়ে খুলুন, "অজানা উৎস থেকে ইন্সটল" অনুমতি দিন। প্রথমবার অ্যাপ খুললে
   নোটিফিকেশনের অনুমতিতে "Allow" দিন।

## নোটিফিকেশন
- অ্যাপের সেটিংস → রিমাইন্ডার থেকে রাতের সময় ঠিক করুন।
- অ্যাপ প্রতিবার খুললে পরের ৩০ দিনের রিমাইন্ডার নতুন করে বসায়। মাসে অন্তত একবার অ্যাপ খুলুন।
- কিছু ফোনে (Xiaomi, Oppo, Vivo ইত্যাদি) অ্যাপকে ব্যাটারি সেভার থেকে বাদ দিন, নইলে রিমাইন্ডার দেরিতে আসতে পারে।

## ল্যাপটপে বানাতে চাইলে
Node.js, Java 17 ও Android Studio লাগবে।
`npm install` → `npx cap sync android` → `cd android && ./gradlew assembleDebug`
APK থাকবে `android/app/build/outputs/apk/debug/app-debug.apk` এ।
