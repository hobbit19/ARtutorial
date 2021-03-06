# \(Kext\) اختيار التعريفات

## ايش التعريفات \(Kext\) الي أحتاجها ؟

الموضوع يختلف على حسب الجهاز طبعا بحيث يعتمد على القطع الموجودة في المذربورد

**التعريفات الأساسية موجوده في أرشيف** **ال Kexts** [من هنا](https://kextarchive.هاكنتوش.com/) **بحيث** **سيكون مكتوب وظيفه كل Kext مع رابط التحميل**

## كيكستات اساسية

طبعا [Virtualsmc.kext](https://github.com/acidanthera/VirtualSMC/releases) **أساسي يقنع النظام ان هذا جهاز ماك**

## الايثرنت Ethernet :

{% hint style="info" %}
**في حاله وجود عده نسخ من الكيكست دائما قم بتنزيل نسخه ال RELEASE**
{% endhint %}

بالنسبه للشبكه راح نعتمد على Ethernet\(السلك\) **وليس الواي فاي**

ا [SmallTreeIntel82576.zip](https://drive.google.com/file/d/0B5Txx3pb7pgcOG5lSEF2VzFySWM/view?usp=sharing) مخصص لتعريف كرت انتل I211-AT

**ا** [intellMausiEthernet.kext ](https://github.com/acidanthera/IntelMausi/releases)يعمل مع معظم كروت الشبكه الحديثه من انتل 

ا [appleintelE1000e.kext ](https://sourceforge.net/projects/osx86drivers/files/Kext/Snow_or_Above/AppleIntelE1000e.kext.zip/download)يعمل مع كروت الشبكه القديمه من انتل مشكلتها قد تسبب KP مع الاجهزه الجديده

ا [AtherosE2200Ethernet.kext ](https://github.com/Mieze/AtherosE2200Ethernet)- يعمل مع معظم كروت Atheros و KIller [**التحميل من هنا**](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455105&cid=FE4038DA929BFB23)\*\*\*\*

ا [RealteakRTL8111.kext](https://github.com/Mieze/RTL8111_driver_for_OS_X/releases) يعمل مع كروت Realtek بسرعه 1GB/s

ا [RealtekRTL8100.kext](https://github.com/Mieze/RealtekRTL8100) يعمل مع كروت Realtek بسرعه 10 -100mb/s [**التحميل من هنا** ](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455140&cid=FE4038DA929BFB23)



  


## مداخل \(USB\) :

راح تحتاج[ USBinjectAll,kext](https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads/) بحيث يقوم هذا الكيكست بتفعيل كل مداخل ال usb وتوجيهها الى chipset الخاص بالمذربورد ليتعامل معها النظام

في **10.11** ابل وضعت **حد 15 مدخل USB** **على كل USB Controller** يتبين ان 15 عدد كافي حتى يتبين لك ان كل مدخل **USB3** **يحسب كمدخلان.**

**على** **مذربوردات الجيل السادس فما فوق** **مداخل USB3** و **USB 2** يتم التحكم بها من **XHCI controllrer** وبما ان كل **مدخل USB3 يحسب 2 يمكن الوصول الحد بسهوله** لاكن **ممكن يتم تحويل مداخل USB2 الى ال** **EHCI Controller** باستخدام كيكست [FakePCIID.kext](https://bitbucket.org/RehabMan/os-x-fake-pci-id) **\(تشتغل على بعض المذربوردات فقط\)** وتشيل الضغط عن **XHCI Controller** او يمكن تعطيل حد ال 15 مدخل عنطريق تعديل الكونفق بعد تثبيت النظام [**الخطوات هنا \(انجليزي\)**](https://hackintosher.com/forums/thread/list-of-hackintosh-usb-port-limit-patches-10-15-updated.467/)\*\*\*\*

\*\*\*\*

## كرت الشاشة \(GPU\) :

بالنسبه **لكرت الشاشة** راح تحتاج تعريف [Whatevergreen.kext](https://github.com/acidanthera/WhateverGreen/releases) و هو اضافه لكيكست[ Lilu.kext](https://github.com/vit9696/Lilu/releases) بحيث استبدلو عدة **kexts** منها **Shiki** و **NvidiaGraphicsFixup** **وغيرها**

## الصوت \(Sound\) :

بالنسبه **للصوت** راح تحتاج تعريف [Applealc.Kext](https://github.com/acidanthera/AppleALC/releases) و وهو اضافه اخرى لكيكست [Lilu.kext](https://github.com/acidanthera/lilu/releases) \(تحتاجهم الاثنين\) اذا كان كرت الصوت عندك موجود في هاذه [القائمه](https://github.com/acidanthera/applealc/wiki/supported-codecs)   
اذا كان كرتك غير موجود هناك تعريف بديل [VoodoHDA.Kext](https://github.com/chris1111/VoodooHDA-2.9.2-Clover-V14/releases) مع دعم اوسع

## واي فاي وبلوتوث Wi-Fi / Bluetooth :

ابل دعمها لكروت **الواي فاي والبلوتوث** ضعيف جدا بحيث كروت **Intel و RealTek** غير مدعومه بشكل كامل أما **Atheros** مدعومه جزئيا بينما كروت **Broadcom** هي الكروت الأكثر دعما بحيت فيها من يتعرف تلقائي **OOB** ومنها من تحتاج بعض الكيكست.

### كروت مدعومة :

* BCM94360CD
* BCM94331CD
* BCM94360CS2
* BCM94352Z
* BCM94350ZAE

**High Sierra :**

* BCM943224
* AR9285
* AR9287
* AR9280
* AR9380

### كروت غير مدعومة :

**Wireless AX**

* Intel® Wi-Fi 6 AX201
* Intel® Wi-Fi 6 AX200

**Wireless AC**

* Intel® Wireless-AC 9560
* Intel® Wireless-AC 9462
* Intel® Wireless-AC 9461
* Intel® Wireless-AC 9260
* Intel® Dual Band Wireless-AC 3168
* Intel® Dual Band Wireless-AC 8265
* Intel® Dual Band Wireless-AC 8260
* Intel® Dual Band Wireless-AC 3165
* Intel® Dual Band Wireless-AC 7265
* Intel® Dual Band Wireless-AC 7260
* Intel® Dual Band Wireless-AC 3160
* Intel® Dual Band Wireless-AC 7260

**Wireless N**

* Intel® Dual Band Wireless-N 7265
* Intel® Wireless-N 7265
* Intel® Dual Band Wireless-N 7260
* Intel® Wireless-N 7260
* Intel® Centrino® Advanced-N 6230
* Intel® Centrino® Wireless-N 1030
* Intel® Centrino® Wireless-N 130
* Intel® Centrino® Advanced-N 6235
* Intel® Centrino® Wireless-N 135
* Intel® Centrino® Wireless-N 105
* Intel® Centrino® Wireless-N 2200
* Intel® Centrino® Wireless-N 2230
* Intel® Centrino® Wireless-N 1000
* Intel® Centrino® Advanced-N 6205
* Intel® Centrino® Wireless-N 100
* Intel® Centrino® Wireless-N + WiMAX 6150
* Intel® Centrino® Advanced-N + WiMAX 6250
* Intel® Centrino® Ultimate-N 6300
* Intel® Centrino® Advanced-N 6200
* Intel® Wireless WiFi Link 5100AGN
* Intel® Wireless WiFi Link 5300AGN
* Intel® Wireless WiFi Link 5350AGN
* Intel® Wireless WiFi Link 5150AGN

{% hint style="danger" %}
اذا كنت ناوي تغير كرت الواي فاي **انتبه** من **BIOS** جهازك هل به **Whitelist** تعمله شركات مثل **HP** و **Lenovo** مقال يشرح ما هي [هنا](https://www.thewindowsclub.com/bios-whitelist)
{% endhint %}

### تعريفات تحتاجها لتعريف الكروت المدعومة :

#### **تعريف** [**AirportBrcmFixup**](https://github.com/acidanthera/AirportBrcmFixup/releases) **:**

هذا ضروري لإصلاح **WIFI** على العديد من بطاقات **Broadcom** ، بينما لا تحتاجه جميع الكروت ، هو مطلوب بشكل عام عند استخدام بطاقات لاسلكية غير مصنوعة من **Apple** . لديه وظيفة إضافية لتشغيل تعريفات كروت **Broadcom** القديمة في إصدارات أحدث من الماك

#### **تعريف** [**BrcmPatchRAM**](https://github.com/the-darkvoid/BrcmPatchRAM/releases) **:**

مطلوب لجميع البطاقات اللاسلكية غير المصنوعة من **Apple**

#### **تعريف** [**BrcmBluetoothInjector**](https://github.com/RehabMan/OS-X-BrcmPatchRAM) **:**

يستخدم لتشغيل كرت **BCM20702** ، [**التحميل من هنا**](https://bitbucket.org/RehabMan/os-x-brcmpatchram/downloads/)\*\*\*\*

#### **تعريف** [**BT4LEContinuityFixup**](https://github.com/acidanthera/BT4LEContinuityFixup/releases) **:**

يستعمل لحل مشاكل **التزامن \(Continuity\)** التي تسمح بتشغيل :

* Handoff
* Instant Hotspot
* New Airdrop
* Apple Watch Unlock

**عامة غير ضروري تجنبو استخدامه ان لاحظتم وجود مشكل مع الكرت**

#### **تعريف** [**AirPortAtheros40**](https://github.com/khronokernel/Wifi-Buyers-Guide/blob/master/AirPortAtheros40.kext.zip) **:**

هدا الكيكست مطلوب **لكل كروت Atheros** التي تم **رفع الدعم عنها في اصدار \(Mojave 10.14\)**

* AR9285
* AR9287
* AR9280
* AR9380

لتنصيبه يجب نسخه على هذا المسار : **Library/Extensions** لا تلصقه هنا **\*\***~~**System/Library/Extensions**~~\*\*

تم انسخ هدا الامر على **Terminal**

```text
sudo chown -R root:wheel /L*/E*; sudo chmod -R 755 /L*/E*; sudo kextcache -i /
```

بشكل عام **افضل حل للواي فاي والبلوتوث هو كرت خارجي** مع تعريف من الشركه مثل **TP-Link** وغيرها من الشركات التي تعطي USB واي فاي **تاكد من وجود دعم للماك** و سوف تعمل معك.

## لواقط وايف فاي خارجية \(USB\) :

يبقى هادا هو الحل الاخير أمام العديد من مستخدمي الهاكنتوش لتشغيل **WIFI** على أجهزتهم نظرا لاستحالة تغيير الكرت الداخلي أو لفقدان الضمان من أجهزتهم.

#### نقاط مهمة عليك معرفتها :

* لن تعمل ميزات مثل **AirDrop** و **Handoff** وما إلى ذلك من مزايا
* غير مضمون أنها تشتغل **%100**
* تحتاج لاقط منفصل **للبلوتوث**
* تستخدم معظم البطاقات تعريف **32bit**  لتشغيل **WIFI \( تبقى رهين الشركة المصنعة  حتى  تصدر تحديث لتطبيقاتها الخاصة على اصدار Catalina \)**

ومع كل هذه المشكلات يبقى من الصعب للغاية التوصية بلاقط لاسلكي USB ولكن لا يزال هناك أمل :

### اليكم تعريف بعض لواقط **WIFI** المعروفة دات شرائح **Realtek :**

#### تعريف [Wireless-USB-Adapter-Clover](https://github.com/chris1111/Wireless-USB-Adapter-Clover/releases)

#### يعمل على العديد من اللواقط منها :

| **RTL8188CUS** | **RTL8192CU** | **RTL8192EU** | **RTL8188EUS** | **RTL8811AU** | **RTL8812BU** | **RTL8814AU** | **RTL8812AU** |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |


<table>
  <thead>
    <tr>
      <th style="text-align:left">Asus USB-N 10 Nano/N150</th>
      <th style="text-align:left">EDIMAX- EW-7722UTn V2</th>
      <th style="text-align:left">TL-WN823N v2</th>
      <th style="text-align:left">TL-WN725N v3</th>
      <th style="text-align:left">Archer T2U NANO</th>
      <th style="text-align:left">Archer T4U V3</th>
      <th style="text-align:left">Archer T9UH V2</th>
      <th style="text-align:left">
        <p>Linksys</p>
        <p>WUSB6300</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>#### تعريف [USB Wireless Utility](https://github.com/chris1111/USB-Wireless-Utility/releases)

تماما مثل [Wireless-USB-Adapter-Clover](https://github.com/chris1111/Wireless-USB-Adapter-Clover) ، يسمح **WIFI-Dlink** بدعم عدد لا بأس به من بطاقات **Mediatek / Ralink** ، لكن نظرًا لكونه تطبيق **32bit** غير معتمد على **أنظمة AMD** هناك إصدار أحدث **Catalina** يعتمد على **64bit** وهو الأفضل لأنظمة **AMD** أيضًا: [**WIFI-Dlink Catalina-Panel**](https://github.com/chris1111/WIFI-Dlink-Catalina-Panel-V2/releases)\*\*\*\*

* **RT3572 , RT3072 , RT3070 , RT3573 , MT7610 , MT7610 , MT7610 , RT5370**

  **RT2870 , RT3071 , RT2770 , RT3573 , RT5572 , RT3573 , RT3573 , RT5572 , RT3572**

## بقية الكيكست :

هناك الكثير من الكيكستات وتعتمد على حسب الجهاز مثل الابتوبات هناك كيكستات للبطاريه واضائه الكيبورد و العديد من الكيكستات الاخرى التي تعتمد على جهازك هنا في هاكنتوش العرب نحاول ارشفة جميع الكيكستات هنا وما وظيفتها مع رابط التحميل لاكن تحتاج بحث كبير منك خاصه لو كنت على لابتوب.

