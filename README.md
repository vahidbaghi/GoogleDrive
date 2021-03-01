
<h1 dir="rtl">اتصال دامنه اختصاصی به گوگل درایو</h1>
<div dir="rtl">
<img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/32.jpg"/>
 
## مقدمه
گوگل درایو به صورت رایگان 15 گیگ فضا در اختیار شما قرار میده. یکی از دلایلی که ممکنه باعث بشه از گوگل درایو به عنوان هاست دانلود استفاده نکنید، عدم وجود لینک مستقیم اختصاصی است. در گوگل درایو شما می تونید با راست کلیک کردن روی فایل یا فولدر مورد نظرتون و انتخاب گزینه Get shareable link، لینک مستقیم از اون فایل یا فولدر درست کنید که به صورت زیر هست :
</p>
https://drive.google.com/open?id=1Qto6MHi9A8Uj3UiIVMTdWlfK-BiwBOB0
</p>
اگر سایت شما ظاهر خوبی داشته باشه ولی لینک های دانلودتون مثل بالا  باشه خیلی جالب به نظر نمیرسه. لینک مستقیم  اختصاصی یه چیز دیگه است! احتمالا شما هم مثل من بار ها دنبال راهی گشتید که از گوگل درایو یه هاست دانلود در بیارید ولی  همش به در بسته خوردید! سایت هایی مثل drv.tw وجود دارند که تا حدی میتونن این کار رو برای شما  انجام بدن اما کیفیت  نهایی اصلا خوب نمیشه. مثلا همین سایت (drv.tw) و سایت های مشابهش خیلی قطع و وصل میشن و اصلا نمیشه بهشون  اعتماد کرد. از طرف دیگه، لینکشون واقع مستقیم نیست! مثلا می تونید یه لینک مثل زیر درست کنید
:
</p>
<a dir="ltr">www.example.com/Video.mp4</a>
</p>
اما زمانی که کاربر بازش کنه و بخواد دانلود کنه، تو دانلود منیجر یه چیی مثل زیر میبینه :
</p>
https://r4---sn-vgqs7nlk.c.doc-0-0-sj.sj.googleusercontent.com/videoplayback?expire=1586970410&ei=yuqWXsj8OPPJ8gP3ma-gDw
</p>
اما راه های دیگه ای (با کیفیت خیلی بیشتر) هم برای اینکار وجود داره که در ادامه قصد دارم بررسیش کنم. منبع این مقاله  ریپازیتوری گیت هاب زیر هست :
</p>
https://github.com/donwa/goindex
</p>

## مرحله اول

اول باید یک client id وclient secret درگوگل درست کنید. برای اینکار وارد آدرس زیر بشید  (قبلش vpn روشن کنید) :
 </p>
 console.developers.google.com
 </p>
 روی  بخش 1 که در تصویر زیر مشخص کردم کلیک کنید ( چون من قبلا پروژه ای با نام Rclone ساختم برای همین  اسمش اینه.  برای شما قطعا  متفاوت هست). بعدش  New Project رو بزنید :
 </p>
 <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/1.jpg"/>
 </p>
 بعدش یه اسم برای پروژه انتخاب کنید و Create رو بزنید:  
 </p>
  <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/2.jpg"/>
 </p>
بعد OAuth consent screen رو انتخاب کنید و تیک External رو بزنید و در نهایت Create : 
</p>
   <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/4.jpg"/>
 </p>
 یه اسم برای پروژه انتخاب کنید و در انتهای صفحه save رو بزنید:   
 </p>
 <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/5.jpg"/>
 </p>
 حالا پروژه ای که ساختید رو انتخاب کنید  و Credentials رو انتخاب کنید و Create 
Credentials رو بزنید. بعد گزینه OAuth client ID رو انتخاب کنید:   
 </p>
  <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/6.jpg"/>
 </p>
 حالا Web Application رو انتخاب کنید و در انتهای صفحه Create رو بزنید:   
 </p>
  <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/7.jpg"/>
 </p>
 اگر همه چیز درست پیش بره client id و secret رو نشون میده:   
 </p>
 <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/8.jpg"/>
 </p>
این کد ها رو در جایی ذخیره کنید چون در مراحل بعدی به اونها نیاز داریم. علاوه بر این شما باید Google Drive API رو هم فعال کنید. برای انجام این کار از منوی سمت چپ Library رو انتخاب کنید و در قسمت جستجو drive رو تایپ کنید و اینتر بزنید. بعد Google Drive API رو انتخاب کنید و در نهایت enable رو بزنید 

 ## مرحله دوم
 
 اول وارد لینک زیر بشید و rclone رو دانلود کنید:
 </p>
  https://rclone.org/downloads
 </p>
 برای ویندوز لازم نیست چیزی نصب کنید و فقط همون فایلش رو دانلود کنید و یه جا اکسترکت کنید. برای لینوکس باید از دستور زیر استفاده کنید:   
 </p>
  curl https://rclone.org/install.sh | sudo bash
 </p>
 من روی ویندوز توضیح میدم ولی فرقی با لینوکس نداره .CMD رو جایی که rclone رو اکسترکت کردید اجرا کنی د. بعد دستور زیر رو اجرا کنید:   
 </p>
  rclone config
 </p>
 بعد n رو تایپ کنید و اینتر بزنید :  
 </p>
  <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/9.jpg"/>
 </p>
 حالا ازتون یه اسم میخواد. من مثلا اسمش رو میذارم remote. حالا  برای اینکه به گوگل درایو متصل بشید بنویسید drive :  
 </p>
   <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/10.jpg"/>
 </p>
 بعدش میگه client id  و client secret رو بگید که همون چیزایی که در مرحله قبلی به دست آوردیم رو وارد کنید. مرحله بعدی گزینه 1 یعنی Full access all files رو انتخاب کنید .گز ینه های root_folder_id و همچنین service_account_file رو خالی 
بذارید. یعنی هیچی تایپ نکنید و اینتر بزنید. گزینه Edit advanced config رو هم No بزنید. گزینه Use auto config رو هم yبزنید. بعد یه لینکی مثل چیزی که در تصویر زیر مشخص کردم رو تولید میکنه که باید تو مرورگر بازش کنید:  

 </p>
 <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/11.jpg"/>
 </p>
 احتمال داره با خطای زیر رو به رو بشید:
 </p>
  <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/12.jpg"/>
 </p>
 اگر همچین خطایی داد. لینکی که در تصویر بالا با کادر قرمز مشخص کردم رو باز کنید. صفحه زیر رو خواهید دید:   
 </p>
 <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/13.jpg"/>
 </p>
 تو قسمت Autherized redirect URIs دقیقا اون آدرس لوکالی که تو مرحله قبل بازش کردید رو وارد کنید.  
 </p>
فوت کوزه گری :  اون / انتهای آدرس رو اگر نذارید بازم خطا میده  
بعد save رو بزنید و دوباره لینک رو باز کنید. حالا ازتون میخواد به rclone اجازه بدید به گوگل درایو شما دسترسی داشته باشه. 
اگر با صفحه زیر رو به رو شدید Advanced رو بزنید و بعد Go to.  

 </p>
 <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/14.jpg"/>
 </p>
 متن زیر رو که ببینید کار تمومه!  
 </p>
 <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/15.jpg"/>
 </p>
 بعد دوباره به cmd برگردید و Configure this as a team drive رو هم N بزنید. زمانی که کار تموم بشه یه token برای شما نمایش میده:   
 </p>
 <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/16.jpg"/>
 </p>
 بخش refresh_token رو هم یه جایی یادداشت کنید.  
 
 ## مرحله سوم
 </p>
 وارد گوگل درایو خودتون بشید و یک فولدر ایجاد کنید که من اینجا اسمش رو TestFolder  گذاشتم. این، فولدری هست که قراره به عنوان روت هاست دانلود شما نمایش داده بشه. بعد روی فولدر راست کلیک کنید وShare  رو بزنید:  
 </p>
 <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/17.jpg"/>
 </p>
 بعدش گزینه Get shareable link رو بزنید. زمانی که این کار رو انجام بدید لینک به اشتراک گذاری این فولدر ایجاد میشه که چیزی شبیه به لینک زیر است : 
 </p>
 https://drive.google.com/drive/folders/1Qto6MHi9A8Uj3UiIVMTdWlfK-BiwBOB0?usp=sharing
 </p>
 از این آدرس ما فقط به ID این فولدر نیاز داریم که به صورت زیر است :
 </p>
 1Qto6MHi9A8Uj3UiIVMTdWlfK-BiwBOB0
 </p>
 این رو هم در جایی یادداشت کنید
 </p>
  <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/18.jpg"/>
 </p>
 در نهایت Done رو بزنید تا تنظیمات اعمال بشه
 
 ## مرحله چهارم
 </p>
 فایل زیر رو دانلود کنید :
 </p>
  http://s17.picofile.com/file/8410879750/script_2_.txt.html
 </p>
 حالا فیلد هایی که در تصویر هم نشون دادم رو باید تکمیل کنید:  
 </p>
   <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/19.jpg"/>
 </p>
 root_pass : یه پسورد رو انتخاب کنید
 </p>
 client_id و client_secret : در مرحله دوم به دست آوردیم
</p>
root : آی دی فولدر گوگل درایو که تو مرحله سوم به دست آوردیم
</p>
یه بخش دیگه رو هم توی این اسکریپت باید تغییر بدید:  
</p>
   <img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/20.jpg"/>
</p>
با توجه به اینکه ریپازیتوری goindex حذف شده اگر بخشی که با کادر قرمز مشخص کردم رو جاگز ین نکنید در ادامه به مشکل میخورید. تو کادر بالا دو تا فایل  jquery.min.js
 و app.js داریم 
</p>
فایل jquery.min.js روی jsdeliver هست و مشکلی نداریم. اما لینک فایل app.js رو باید تغییر بدید. در بخش مقدمه یه فایلی به نام goindex_master.zip داشتیم که فایل app.js در داخل این فایل و در پوشه theme>classic قرار داره. 
این فایل رو هر جا خواستید آپلود کنید و لینک مستقیمش رو به جای لینک زیر بذارید :
</p>
 gh/YOUR_GITHUB_USERNAME/gdrive/theme/${authConfig.theme}/app.js
</p>
راه دیگه ای که وجود داره اینه که میتونید یه ریپازیتوری به نام gdrive در کیت هاب خودتون درست کنید و بعد فایل app.js رو داخلش آپلود کنید. بعد یه جای YOUR_GITHUB_USERNAME در لینک زیر نام کاربری خودتون رو قرار بدید و اون رو با لینک بالا جایگزین کنید :
</p>
gh/YOUR_GITHUB_USERNAME/gdrive/app.js

## مرحله پنجم
وارد سایت https://www.cloudflare.com بشید. بعد از اینکه لاگین کردید، در صفحه اصلی روی Workers کلیک کنید :
</p>
<img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/21.jpg"/>
</p>
سپس از صفحه ای که باز شده روی دکمه Create a Worker کلیک کنید :
</p>
<img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/22.jpg"/>
</p>
زمانی که این کار رو انجام بدید با صفحه زیر رو به رو میشید :
</p>
<img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/23.jpg"/>
</p>
محتویات فایل script.txt که در انتهای مرحله چهارم به دست آورده بودیم رو در بخش Script  که با کادر قرمز در تصویر بالا مشخص شده قرار بدید و در نهایت روی Save and Deploy  کلیک کنید. بعدش یک آدرس به شما نمایش میده که برای من به صورت زیر بود:  
</p>
 https://odd-rain-660e.vbaghi.workers.dev
</p>
دفعه اول احتمالا از شما میخواد که یک اسم رو برایworker  خودتون انتخاب کنید که من اسمش روvbaghi  گذاشتم. حالا اگر این آدرس رو باز کنید میبیند که محتویات فولدری که در گوگل درایو داشتیم رو نشون میده! دفعه اول که بازش کنید ازتون رمز میخواد که همون رمزی هست که در مراحل قبلی انتخاب  کردید.  

## مرحله ششم

از اینجا به بعد باید مراحل رو با حوصله انجام بدید تا از غوره، حلوا درست کنید! 
</p>
ممکنه شما از آدرسی که در مرحله قبل برامون تولید کرد خوشتون نیاد که منطقی هم هست. خبر خوب اینه که میتونید دامنه اختصاصی خودتون رو به جای اون آدرس قرار بدید! من فرض میکنم شما یه دامنه دارید. مثلا سایت شما example.ir هست و حالا میخواید مثلا زیر دامنه cdn.example.ir رو به گوگل درایوتون متصل کنید. اول از همه برید داخل سایت Cloudflare و Add a Site رو بزنید و دامنه خودتون رو اضافه کنید. اگر هم از قبل دامنه به Cloudflare متصل هست که چه بهتر. آموزشش تو اینترنت زیاده :
</p>
https://mizbanfa.net/blog/other/web/install-and-used-cloud-flare-education
</p>
بعدش باید زیر دامنه تعریف کنید. نحوه تعریف زیر دامنه توی سی پنل تو لینک زیر توضیح داده شده:   
</p>
https://mizbanfa.net/blog/hosting/cpanel/create-sub-domain-in-cpanel
</p>
بعد باید توی Cloudflare ز یر دامنه رو تعریف کنید که بازم آموزشش تو اینترنت هست:   
</p>
https://mizbanfa.net/blog/other/web/enable-cloudflare-for-subdomain-issue
</p>
وقتی همه چیز اوکی شد و به سلامتی دامنه یا زیر دامنه شما به Cloudflare متصل شد، تو صفحه اصلیCloudflare  روی دامنه خودتون کلیک کنید تا صفحه زیر بیاد. بعد، از منوی بالای صفحهWorkers  رو انتخاب کنید:  
</p>
<img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/24.jpg"/>
</p>
حالا از صفحه باز شده رویAdd route  کلیک کنید :  
</p>
<img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/25.jpg"/>
</p>
در فیلدRoute  آدرس دامنه یا زیر دامنه مورد نظرتون رو بنویسید. مثلا اگر در مراحل قبل،DNS  هایCloudflare  رو برای دامنه yourdomain.ir تنظیم کردید، اینجا باید بنویسید:  
</p>
 yourdomain.ir/*
</p>
شما میتونید پوشه گوگل درایو خودتون رو به یک زیر دامنه هم متصل کنید. مثلا فرض کنید میخوایم سایت اصلی روی yourdomain.ir  باشه و هاست دانلود روی گوگل درایو با آدرسdl.yourdomain.ir  باشه. در این صورت اول باید زیر دامنه رو در 
Cloudflare  تنظیم کنید و بعد تو این مرحله در فیلدRoute  مقدار زیر رو قرار بدید. 
</p>
dl.yourdomain.ir/
</p>
حالاWorker  ای که در مراحل قبل ساختیم رو از منویWorker  انتخاب کنید و در نهایتSave  رو بزنید. 
</p>
حالا دوباره برید صفحه اصلی وWorkers  رو انتخاب کنید:  
</p>
<img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/26.jpg"/>
</p>
از صفحه باز شده worker خودتون رو انتخاب کنید و در بخشAdditional routs  باید دامنه ای که تنظیم کردید رو مشاهده کنید:  
</p>
<img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/27.jpg"/>
</p>
حالا کار تمومه و با نوشتن نام دامنه مورد نظر، فولدر گوگل درایوی که در مراحل قبل مشخص کرده بودیم نمایش داده میشه. 
</p>
حالا قصد دارم چند تا نکته اضافه تر رو هم خدمتتون عرض کنم. 
</p>
نکته اول : به صورت پیش فرض زمانی که یک نفر آدرس دامنه شما رو در مرورگر خودش بزنه، ازش رمز میخواد. کد مربوط به رمز از خط 89 به بعد هست:  
</p>
<img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/28.jpg"/>
</p>
اگر جاوا اسکریپت بلد هستید می تونید یک مقدار امنیت اینجا رو بیشتر کنید. مثلا یکwhite list  درست کنید که فقط ازIP  خاصی بشه متصل شد و کار های دیگه...  
</p>
نکته دوم : می تونید چند تا اکانت جیمیل درست کنید تا حجم بیشتری داشته باشید و مثلا اکانت اول آدرسش بشه 
s1.example.ir ، اکانت دوم آدرسش بشهs2.example.ir  و ...  اما توجه داشته باشید که هر اکانت گوگل درایو به یک آدرس میتونه متصل بشه. یعنی دو تا اکانت گوگل درایو رو نمیتونید به یک دامنه متصل کنید.
</p>
البته می‌نوید چند تا گوگل درایو رو با هم مرج کنید. چه جوری؟ وارد گوگل درایو اول بشید و روی فولدری که ساختید راست کلیک کنید و share رو بزنید. بعد ایمیل اکانت دوم رو در بخشی که با کادر قرمز مشخص کردم وارد کنید :
</p>
<img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/29.jpg"/>
</p>
زمانی که ایمیل رو انتخاب کنید صفحه زیر رو میبینید :
</p>
<img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/30.jpg"/>
</p>
دقت کنید که سطح دسترسی Editor باشه و بعد Send رو بزنید
</p>
الان موفق شدید پوشه رو  share کنید ولی برای دسترسی به این پوشه از طریق گوگل درایو دوم باید وارد بخش Shared with me بشید. اما میتونید کاری کنید که این فولدر با گوگل درایو اکانت دوم مرج بشه. برای این کار دوباره روی فولدر راست کلیک کنید و share رو بزنید. این بار Make owner رو انتخاب کنید :
</p>
<img src="https://github.com/vahidbaghi/GoogleDrive/raw/main/31.jpg"/>
</p>
نکته سوم : هر چیزی رو آپلود نکنید. ممکنه یه چیزی بذارید که قانون کپی رایت رو نقض کنه و اکانتتون بسته بشه. مثلا اگر به عنوان هاست فیلم و سریال ازش استفاده کنید ممکنه حسابتون بسته بشه. یا اینکه فیلم رو زیپ کنید و بعد آپلود کنید. 
</p>
نکته چهارم: اگر بخوایم از نظر ریسک پریدن اطلاعات بحث کنیم. به نظرم بین تفاوتی بین هاست دانلود شرکتی و گوگل درایو وجود نداره. چه بسا ریسک گوگل درایو کمتر باشه. چون تقریبا همه شرکت هایی که هاست دانلود میفروشن (حداقل جاهایی که من میدونم و باهاشون کار کردم) میگن بک آپ نمیگیرم و مسئولیت پریدن اطلاعات رو بر عهده نمیگیرن. برای همینم هست که قیمت هاست دانلود و بک آپ با هاست اشتراکی خیلی فرق میکنه. با این شرایط، به نظرم گوگل درایو گزینه بهتری هست. 
</p>
منبع بخشی از این مطالبی که گفتم ویدئو یوتیوب زیر هست:  
</p>
https://youtu.be/HjKjB8JKa08
</div>
