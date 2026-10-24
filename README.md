# EnglishFantasyAds

Monthly Facebook Ads expense report builder for English Fantasy, Fantasy Publication, Fantasy Global Education and Rajon Sir Page.

একটা মাত্র ফাইল (`index.html`)। ব্রাউজারে খুললেই চলে, কোনো সার্ভার বা ইনস্টল লাগে না। সব হিসাব আপনার ব্রাউজারেই হয়, কোনো ডাটা কোথাও পাঠানো হয় না।

## কীভাবে ব্যবহার করবেন

1. `index.html` ব্রাউজারে খুলুন (অথবা GitHub Pages চালু করে লিংক থেকে খুলুন)।
2. দুই ad account-এর Ads Manager export দিন (campaign level, পুরো মাস, xlsx বা csv):
   - English Fantasy ad account
   - Fantasy Publication ad account
3. Exchange rate দিন (১ USD = কত টাকা)। একবার দিলে পরের বার মনে থাকে।
4. Other Costs (Date, Tool, Dollar Spent) পেস্ট করুন। যেমন: `Payment Cancel	27*0.50 = 13.5`
5. ক্যাম্পেইন যাচাই করুন। যে ক্যাম্পেইন বোঝা যায়নি সেটা হলুদ থাকবে, ড্রপডাউন থেকে কোম্পানি বেছে দিন। এই বাছাই ব্রাউজারে মনে থাকে।
6. "PDF তৈরি করুন" চাপুন। ৫টি এক পেজের A4 PDF হবে:
   1. English Fantasy (দুই অ্যাকাউন্টের English Fantasy ক্যাম্পেইন + Other Costs)
   2. Fantasy Publication (যে অ্যাকাউন্টেই Book ক্যাম্পেইন থাকুক)
   3. Fantasy Global Education (দুই অ্যাকাউন্ট মিলিয়ে)
   4. Rajon Sir Page
   5. Grand Total Summary (সব কোম্পানি + cross-check)

## কোম্পানি চেনার নিয়ম (ক্যাম্পেইনের নাম থেকে)

| নামে যা থাকলে | কোম্পানি |
|---|---|
| global, fge | Fantasy Global Education |
| book, boi, publication, pre order, vocab | Fantasy Publication |
| job, hiring, recruit | English Fantasy (Recruitment) |
| rajon (Book ছাড়া) | Rajon Sir Page |
| course, ielts, spoken, batch, residential, EF, English Fantasy | English Fantasy |
| abroad, visa, study abroad | Fantasy Global Education (কোর্সের শব্দও থাকলে জিজ্ঞেস করবে) |
| শুধু WA / WP / WhatsApp / Sales Campaign | English Fantasy অ্যাকাউন্টে Course, অন্য অ্যাকাউন্টে জিজ্ঞেস করবে |

দুই কোম্পানির শব্দ একসাথে থাকলে বা কোনো শব্দ না থাকলে নিজে থেকে বসায় না, আপনাকে বেছে দিতে বলে।

## হিসাবের নিয়ম

- শুধু যে ক্যাম্পেইনে খরচ হয়েছে (Amount spent > 0) সেগুলো ধরা হয়।
- সব টাকা সেন্টে (integer) হিসাব হয়, তাই যোগফল পয়সা পর্যন্ত মেলে।
- BDT = USD × exchange rate।
- Share % যোগ করলে সবসময় ঠিক 100.00% হয়।
- Grand Total = দুই অ্যাকাউন্টের মোট খরচ + Other Costs, এটা PDF-এ cross-check হিসেবে দেখানো থাকে।

## Libraries

CDN থেকে লোড হয়: SheetJS (xlsx 0.18.5), jsPDF 2.5.1, jspdf-autotable 3.8.2, JSZip 3.10.1।
