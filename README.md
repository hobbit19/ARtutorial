البداية

{% hint style="danger" %}
نحن غير مسئولون عما مايحدث في جهازك اثناء وبعد تثبيت الهاكنتوش
{% endhint %}

## المعرفه التقنية

قبل ما ابدء احتاج انبه ان الهاكنتوش **ليس نظام عادي** ويحتاج تدخل تقني اكثر بكثير من الويندوز بحيث مع كل تحديث يحتاج تجهيزات يدويه وايضا قد تحصل مشاكل في الاقلاع قد تمنعك من الوصول للنظام. الهاكنتوش يحتاج الكثير من البحث تعريفات على حسب القطع وحل مشاكل وغيره اذا كنت تحتاج جهازك يعمل بشكل دائم **بدون اي مشاكل** الهاكنتوش ليس لك. اذا كانت معرفتك التقنيه **ضعيفه** مثل عدم معرفه ماهو جيل المعالج و ماهو bios الهاكنتوش ليس لك. الهاكنتوش نظام اعقد ويتطلب معرفه تقنيه متقدمه مع صبر على مشاكله المعتاده

في هاذا الشرح سوف نثبت الماك الخام **\(vanilla\)** على معالجات **intel** لاكن ما يعني خام ؟ خام يعني ان النظام أصلي لم يتم التعديل عليه ابدا ويكون التعديل في قسم ال **EFI** المخصص للاقلاع القسم الاساسي لنظام الماك في الهاكنتوش يطابق الموجود في اجهزه الماك الاصليه

## اختصارات سيتم استخدامها اثناء الشرح :

راح تستخدم هاذه الاختصارات في الشرح

**كلوفر \(clover\)** : هو عبار عن **bootloader** البوت لودر هو البرنامج المسوؤل عن اقلاع النظام , اجهزه الماك يكون فيها برنامج مخصص للاقلاع لنظام الماك , بالنسبه للكمبيوتر العادي سوف نحتاج كلوفر للاقلاع. ايضا هو المسئول عن ادخال ال Kexts و الباتشات والعديد من المهام الاخرى.

**كيرنل بانك \(Kernel panic\)** اختصارها **KP** وهي **فشل في اقلاع النظام** وتعليق الجهاز في مرحله الاقلاع عندما تضع v- ويتوقف تحرك المكتوب بدون الاقلاع هاذا هو ال KP

**الكيكست \(kext\)** : معنى كلمه "kext" هي اختصار ل **Kernel extenions** او اضافات الكيرنل باختصار الكيكست هي التعريفات لنظام الماك

**الكونفق \(config.plist\)** : هو الملف الذي يقول لكوفر ماذا يفعل مبني على ترتيب XML الشبيه ب HTML وهو من اهم الاشياء في الهاكنتوش

**اووب \(OOB\)** : هو اختصار لكلمه **Out of the box** او انه يعمل بشكل مباشر بدون الحاجه الى اي نوع من التعديل

## الاحتيجات : 

هاذا الشرح يركز على الكمبيوتر **المكتبي** بالنسبه **الابتوبات** ستكون الخطوات أعقد و مخصصة لكل جهاز بشكل اكبر لاكن ستكون بالاساس شبيهه بالمكتبي.

أداة تنزيل الماك ونسخه \(GibmacOS\) من المطور الرهيب **corpnewt** تحميل من [هنا](https://github.com/corpnewt/gibMacOS)

ايضا سوف نحتاج اداه السيريل للماك \(GenSMbios\) من نفس المطور تحملها من [هنا ](https://github.com/corpnewt/GenSMBIOS)

سوف نحتاج سكربت packappwin.py من حزمه MakeInstallmacOS تحملها من [هنا](https://github.com/doesprintfwork/MakeInstallmacOS)

{% hint style="info" %}
التحميل من الروابط في الاعلى يكون من زر Clone or download ثم اختار download zip ثم انشئ ملف تفك في ضغط الملفات
{% endhint %}

نحتاج برنامج Basic disk utilty \(bdu\) تحمله من[ هنا ](https://www.softpedia.com/get/System/Boot-Manager-Disk/Bootdisk-Utility.shtml)

ايضا النسخه المجانيه من برنامج paragon disk manger تحملها من [هنا](https://www.paragon-software.com/free/pm-express/#resources) 

يو اس بي **\(USB\)** مساحته **8GB** و أكثر

كيكست [Virtualsmc.kext](https://github.com/acidanthera/VirtualSMC/releases) هاذا يستبدل **Fakesmc** بحيث سيكون محاكي ال [smc](https://en.wikipedia.org/wiki/System_Management_Controller) القطعه المسئوله عن التحكم في النظام في اجهزه ابل بدونها لا يمكن الاقلاع

التعريفات **\(Kext\)**  سوف تكون على حسب جهازك. **سنشرح هاذا في القسم القادم**

**شويه صبر وعزم واحتراف في البحث على الانترنت**

## الشروط :

راح تكون هناك شروط حتى يكون جهازك مدعوم من هاكنتوش العرب :

### المعالج : 

 لازم يكون من **الجيل الثالث** فما **فوق**. كيف تعرف معالجك اي جيل ؟ بسيطه من الويندوز ابحث عن **About Your PC** او **حول هاذا الكمبيوتر**

عند قسم المعالج يجب ان يكون اول رقم بعد اسم المعالج اكثر من 2 يعني **core i7-4790k** او **core i3 6100** او حتى **core i9 9900k** اذا كان اول رقم اقل من **3** مثل **core i7 2700k** فنحن لانقدم المساعده له. لا يعني انه مستحيل تثبيت الهاكنتوش عليه لاكن يستحسن ان تغير الجهاز لانه قديم.

### الرام :

بالنسبه للرام فجهازك يجب ان يحتوي على الاقل **4 جيجا** رام لاكن الحد الفعلي هو **8 جيجا** رام وهو التي تنصح ابل فيه لاخر اصدر من الماك

### كرت الشاشة :

بالنسبه لكروت الشاشه **المنفصله في الابتوبات غير مدعومه** وسوف يتم استخدام **الكرت الداخلي \(intel\)** للماك كانت هناك محاولات ناجحه لتفعيل الكروت المنفصله في الابتوات لاكنها ليست مؤكده لكل الاجهزه 

بالنسبه للكمبيوتر المكتبي فكروت **AMD** هي افضل خيار لانها مدعومه بشكل مباشر من النظام ابتعد عن كروت **XFX** لانها تواجه احيانا بعض المشاكل ابل تدعم بشكل رسمي هاذي الكروت

* **Radeon RX 470**
* **Radeon RX 480**
* **Radeon RX 570**
* **Radeon RX 580**
* **Radeon Pro WX 7100**
* **Radeon RX Vega 56**
* **Radeon RX Vega 64**
* **Radeon RX Vega Frontier Edition**
* **Radeon Pro WX 9100**

ال **RX 590** و **560** ايضا مدعومين لانهم من نفس المعماريه طبعا هاذي القائمه لا تشمل جميع الكروت لاكنها هي الكروت التي المؤكد عملها من داخل النظام مثلا كرت Radeon Vii يعمل مباشره من النظام بينما كرت **R9 380** احتاج كيكست [**WhateverGreen**](https://github.com/acidanthera/WhateverGreen) ليعمل

 ايضا كروت **Nvidia** من فئه **600** و **700** فقط مدعومه في النظام

بالنسبه لكروت **Nvidia الاخرى** بشكل عام انا انصح ان تبقى على الويندوز لان البرامج على ويندوز مصممه لاستخدام كروت انفيديا بشكل افضل لاكن اذا كنت تريد تثبيت الماك مع كرت انفيديا ستكون محدود الى اصدار **High Sierra 10.13** بحيث هاذا **اخر اصدار سمحت أبل لانفيديا باصدار التعريفات له** 

### الدعم :

سنوفر الدعم **للطريقه الرسميه فقط لن نقدم الدعم لنسخ معدله** مثل ~~**Zone**~~ والنسخ الجاهزه مثل ~~**Olarila**~~ ايضا سنتجنب برامج **توني ماك** \(**unibeast** و **multibeast**\) قدر المستطاع بسبب انها **مغلقه المصدر** ونقص بعض الاشياء الاساسيه في الكونفق التي قد تؤدي الى حجب حساب ال **iCloud** المرتبط بالهاكنتوش وعيوب [اخرى](https://github.com/khronokernel/Tonymcx86-stance) 


