# coach-huddle-app

אפליקציית Android (WebView + FCM push) שעוטפת את מערכת "חדר מאמנים":
https://coach-huddle-circle.lovable.app

הבנייה אוטומטית ב-GitHub Actions (`.github/workflows/build.yml`) — כל push ל-main
בונה APK ומפרסם אותו כ-GitHub Release (`releases/latest`).

## חבילה (package)
`com.apex.coachhuddle` — יש להשתמש בדיוק בשם הזה כשמוסיפים אפליקציית Android ב-Firebase.

## חובה לפני בנייה: google-services.json
1. צור פרויקט חדש ב-Firebase Console.
2. הוסף אפליקציית Android עם package name: `com.apex.coachhuddle`.
3. הורד את `google-services.json` ושים אותו ב-`app/google-services.json`.
4. ב-Firebase → Build → Cloud Messaging ודא שה-API מופעל.

בלי הקובץ הזה הבנייה תיכשל (תוסף google-services דורש אותו).

## בדיקת פוש (ללא שרת)
האפליקציה נרשמת אוטומטית לטופיק `all`. אחרי התקנת ה-APK:
Firebase Console → Messaging → "Send test message" / קמפיין לטופיק `all` → הפוש מגיע למכשיר.
