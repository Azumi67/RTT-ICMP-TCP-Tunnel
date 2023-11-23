![R (2)](https://github.com/Azumi67/PrivateIP-Tunnel/assets/119934376/a064577c-9302-4f43-b3bf-3d4f84245a6f)
نام پروژه : ریورس تانل و تانل ICMP بین سرور و کلاینت
---------------------------------------------------------------
----------------------------------

**توضیح کوتاه در مورد این پروژه :**

- بوسیله دو مدل تانل ICMP اقای james و hans بین کلاینت و سرور تانل را برقرار کنید و سپس بوسیله ایپی ساخته شده توسط ریورس تانل اقای رادکسوت، تانل را برقرار کنید.
- من این روش را قبلا با FRP و پورت فوروارد انجام میدادم و سرعت خوبی هم داشت.
- لطفا اگر فیدبکی داشتید بگید.
- من در وقت آزاد این را درست کردم و ممکن است اشتباهاتی هم داخلش باشد. پیشاپیش ببخشید.
- خودم داخل سرور های مختلف تست کردم و جواب داده . بر روی دبیان 12 و اوبونتو 20 تست شده است.
- به زودی تانل های ICMP دیگر که با پورت فوروارد انجام میشود هم در Repo دیگر قرار میدهم.
------------------------

![R (a2)](https://github.com/Azumi67/RTT-Wireguard/assets/119934376/3f64bfa8-3785-4a0b-beba-366b3cb73719)
**دسترسی سریع به اسکریپت**


- [کلیک - click](https://github.com/Azumi67/RTT-ICMP-Tunnel#%D8%A7%D8%B3%DA%A9%D8%B1%DB%8C%D9%BE%D8%AA-%D9%85%D9%86)
------------------------
![check](https://github.com/Azumi67/PrivateIP-Tunnel/assets/119934376/13de8d36-dcfe-498b-9d99-440049c0cf14)
**امکانات**

- تانل ICMP با دو روش متفاوت و استفاده از ایپی های آن تانل در ریورس تانل RTT
- پشتیبانی از TCP و UDP
- قابلیت تانل تک پورت و چندین پورت برای TCP
- قابلیت تانل تک پورت برای UDP
- مناسب برای V2ray و Openvpn و Wireguard
- امکان حذف و استارت و استاپ سرویس

 ------------------------------------------------------

![147-1472495_no-requirements-icon-vector-graphics-clipart](https://github.com/Azumi67/V2ray_loadbalance_multipleServers/assets/119934376/98d8c2bd-c9d2-4ecf-8db9-246b90e1ef0f)
 **پیش نیازها**

 - لطفا سرور اپدیت شده باشه.
 - میتوانید از اسکریپت اقای [Hwashemi](https://github.com/hawshemi/Linux-Optimizer) و یا [OPIRAN](https://github.com/opiran-club/VPS-Optimizer) هم در صورت تمایل استفاده نمایید. (پیش نیاز نیست)


----------------------------

  
  ![6348248](https://github.com/Azumi67/PrivateIP-Tunnel/assets/119934376/398f8b07-65be-472e-9821-631f7b70f783)
**آموزش**
-
![OIP2 (1)](https://github.com/Azumi67/V2ray_loadbalance_multipleServers/assets/119934376/3ec2f05f-3308-4441-8cce-62ab4776f4e2)
**تانل Hans با ریورس تانل RTT - تک پورت - TCP**
----------------------------------
![green-dot-clipart-3](https://github.com/Azumi67/6TO4-PrivateIP/assets/119934376/902a2efa-f48f-4048-bc2a-5be12143bef3) **سرور خارج**

**مسیر : hans RTT > single port > kharej**


 <p align="right">
  <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/28f80b62-bd0b-437a-8c00-ea974406e6b0" alt="Image" />
</p>



- نخست RTT را نصب کنید و سپس سرور خارج را کانفیگ میکنیم .
- کانفیگ را از سرور خارج شروع میکنیم.
- پس از نصب پیش نیاز ها، تانل ICMP شما در سرور خارج فعال میشود و حالا نوبت کانفیگ RTT در سرور خارج است.
- من پورت ایران 443 گذاشتم و این پورت جدید کانفیگ های من خواهد بود.
- من یک کانفیگ vmess با پورت 8080 دارم پس پورت خارج را 8080 قرار میدم.
- در قسمت SNI، گیت هاب را قرار میدهم. شما میتوانید SNI دیگری قرار دهید.
- در قسمت Restart Service مقدار 24 را قرار میدم. شما زمان مورد نیاز را بر اساس نیاز خودتان تغییر دهید.
----------------------

![green-dot-clipart-3](https://github.com/Azumi67/6TO4-PrivateIP/assets/119934376/902a2efa-f48f-4048-bc2a-5be12143bef3) **سرور ایران** 

**مسیر : hans RTT > single port > iran**
<p align="right">
  <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/f89b6d3c-ba7e-48c5-93c9-b52db2e612fc" alt="Image" />
</p>


- مانند سرور خارج، نخست RTT را نصب کنید و سپس کانفیگ سرور ایران را انجام دهید.
- پس ار نصب پیش نیاز ها، از شما ایپی 4 سرور خارج را میخواهد که وارد میکنید و تانل ICMP بر روی سرور ایران فعال میشود. سپس کانفیگ RTT را بر روی سرور ایران را انجام میدهیم.
- پورت ایران را من 443 قرار داده بودم
- قسمت SNI هم که گیت هاب گذاشته بودم.
- ریستارت سرویس هم که مانند قبل بر اساس نیازتان، مقدارش را مشخص کنید.

------------------

  ![Exclamation-Mark-PNG-Clipart](https://github.com/Azumi67/6TO4-GRE-IPIP-SIT/assets/119934376/1b367bc9-aaed-4a8d-84a6-a2a1fc31b831)**نکات**
  
  - در صورت ریبوت شدن سرور ایران ، یک ایپی جدید برای تانل ICMP انتخاب میشود و این باعث میشود که در تانل شما اختلال پیش بیاید.
  - دقت نمایید این مشکل در تانل HANS است و تنها در صورتی اتفاق میوفتد که سرور ایران ریبوت شود و خارج ریبوت نشود.
  - از طریق دو راه میشه این مشکل را حل کرد . با ادیت سرویس تانل رادکسوت در سرور خارج و تغییر ایپی قدیمی به ایپی جدید در سرور ایران.
  - برای روش اول، این مسیر سرویس تانل RTT میباشد. etc/systemd/system/radkesvattunnel-kharej.service/
  - با nano ویرایش کنید و ایپی جدید ایران هم در سرور ایران با دستور ip a بدست اورید.
  - راه دوم هم ریبوت کردن سرور خارج و ایران میباشد که درست میشود.(این روش ساده تر است)
  

--------------------------------------
![OIP2 (1)](https://github.com/Azumi67/V2ray_loadbalance_multipleServers/assets/119934376/3ec2f05f-3308-4441-8cce-62ab4776f4e2)
**تانل Hans با ریورس تانل RTT - چندین پورت - TCP**
--------------------------------

![green-dot-clipart-3](https://github.com/Azumi67/6TO4-GRE-IPIP-SIT/assets/119934376/756f468e-8d6c-45bd-9a4a-a9d056011147)**سرور خارج**

**مسیر : hans RTT > multi port > kharej**

<p align="right">
  <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/7b8d63a6-bfde-4452-93d4-af9b01695230" alt="Image" />
</p>



- نخست RTT را نصب کنید و سپس سرور خارج را کانفیگ میکنیم .
- کانفیگ را از سرور خارج شروع میکنیم.
- پس از نصب پیش نیاز ها، تانل ICMP شما در سرور خارج فعال میشود و حالا نوبت کانفیگ RTT در سرور خارج است.
- من پورت ایران 443 گذاشتم.
- در قسمت SNI، گیت هاب را قرار میدهم. شما میتوانید SNI دیگری قرار دهید.
- در قسمت Restart Service مقدار 24 را قرار میدم. شما زمان مورد نیاز را بر اساس نیاز خودتان تغییر دهید.
- کانفیگ شبیه تک پورت میباشد ولی من برای مولتی پورت تمام پورت ها را باز گذاشتم.
- در مالتی پورت، پورت کانفیگ شما تغییری نخواهد کرد و همان پورت قبلی خواهد بود. تنها ایپی ادرس شما به ایپی ادرس ایران تغییر خواهد کرد.
- به طور مثال من دو کانفیگ VMESS با پورت های 8080 و 8081 دارم و پس از تانل، تنها نیاز است که ایپی ادرس را به ایپی ادرس ایران تغییر بدم.
  
 ---------------------------------------
 
 ![green-dot-clipart-3](https://github.com/Azumi67/6TO4-PrivateIP/assets/119934376/49000de2-53b6-4c5c-888d-f1f397d77b92)**سرور ایران**

**مسیر : hans RTT > multi port > IRAN**

 <p align="right">
  <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/36cb1abd-003b-4cdf-8919-18fc522cb420" alt="Image" />
</p>


- مانند سرور خارج، نخست RTT را نصب کنید و سپس کانفیگ سرور ایران را انجام دهید.
- پس ار نصب پیش نیاز ها، از شما ایپی 4 سرور خارج را میخواهد که وارد میکنید و تانل ICMP بر روی سرور ایران فعال میشود. سپس کانفیگ RTT را بر روی سرور ایران را انجام میدهیم.
- پورت ایران را من 443 قرار داده بودم
- قسمت SNI هم که گیت هاب گذاشته بودم.
- ریستارت سرویس هم که مانند قبل بر اساس نیازتان، مقدارش را مشخص کنید.
- کانفیگ شبیه تک پورت میباشد ولی من برای مولتی پورت تمام پورت ها را باز گذاشتم.
- در مالتی پورت، پورت کانفیگ شما تغییری نخواهد کرد و همان پورت قبلی خواهد بود. تنها ایپی ادرس شما به ایپی ادرس ایران تغییر خواهد کرد.

------------------

  ![Exclamation-Mark-PNG-Clipart](https://github.com/Azumi67/6TO4-GRE-IPIP-SIT/assets/119934376/1b367bc9-aaed-4a8d-84a6-a2a1fc31b831)**نکات**
  
  - در صورت ریبوت شدن سرور ایران ، یک ایپی جدید برای تانل ICMP انتخاب میشود و این باعث میشود که در تانل شما اختلال پیش بیاید.
  - از طریق دو راه میشه این مشکل را حل کرد . با ادیت سرویس تانل رادکسوت در سرور خارج و تغییر ایپی قدیمی به ایپی جدید در سرور ایران.
  - برای روش اول، این مسیر سرویس تانل RTT میباشد. etc/systemd/system/radkesvattunnel-kharej.service/
  - با nano ویرایش کنید و ایپی جدید ایران هم در سرور ایران با دستور ip a بدست اورید.
  - راه دوم هم ریبوت کردن سرور خارج و ایران میباشد که درست میشود.(این روش ساده تر است)
  - دقت نمایید این مشکل در تانل HANS است و تنها در صورتی اتفاق میوفتد که سرور ایران ریبوت شود و خارج ریبوت نشود.
  
  --------------------------------------
![OIP2 (1)](https://github.com/Azumi67/V2ray_loadbalance_multipleServers/assets/119934376/3ec2f05f-3308-4441-8cce-62ab4776f4e2)
**تانل ICMPTUNNEL با ریورس تانل RTT - تک پورت - TCP**
--------------------------------

![green-dot-clipart-3](https://github.com/Azumi67/6TO4-GRE-IPIP-SIT/assets/119934376/756f468e-8d6c-45bd-9a4a-a9d056011147)**سرور خارج**

**مسیر : icmptunnel RTT > single port > kharej**

<p align="right">
  <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/c4c796b9-bf9f-461d-b448-0def3c18bc60" alt="Image" />
</p>



- نخست RTT را نصب کنید و سپس سرور خارج را کانفیگ میکنیم .
- کانفیگ را از سرور خارج شروع میکنیم.
- پس از نصب پیش نیاز ها، تانل ICMPTUNNEL شما در سرور خارج فعال میشود و حالا نوبت کانفیگ RTT در سرور خارج است.
- من پورت ایران 443 گذاشتم.این پورت جدید کانفیگ شما میباشد.
- من یک کانفیگ vmess با پورت 8080 دارم پس پورت خارج را 8080 قرار میدم.
- در قسمت SNI، گیت هاب را قرار میدهم. شما میتوانید SNI دیگری قرار دهید.
- در قسمت Restart Service مقدار 24 را قرار میدم. شما زمان مورد نیاز را بر اساس نیاز خودتان تغییر دهید.
- در اینجا مشکل عوض شدن ایپی در صورت ریبوت شدن سرور ایران، مانند تانل HANS وجود ندارد
- از IFCONFIG برای اضافه شدن ایپی استفاده شده است.
  
 ---------------------------------------
 
 ![green-dot-clipart-3](https://github.com/Azumi67/6TO4-PrivateIP/assets/119934376/49000de2-53b6-4c5c-888d-f1f397d77b92)**سرور ایران**

**مسیر : icmptunnel RTT > single port > iran**

 <p align="right">
  <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/628538f7-3df7-4bb3-bd61-dd01639ceeaa" alt="Image" />
</p>


- مانند سرور خارج، نخست RTT را نصب کنید و سپس کانفیگ سرور ایران را انجام دهید.
- پس ار نصب پیش نیاز ها، از شما ایپی 4 سرور خارج را میخواهد که وارد میکنید و تانل ICMP بر روی سرور ایران فعال میشود. سپس کانفیگ RTT را بر روی سرور ایران را انجام میدهیم.
- پورت ایران را من 443 قرار داده بودم
- قسمت SNI هم که گیت هاب گذاشته بودم.
- ریستارت سرویس هم که مانند قبل بر اساس نیازتان، مقدارش را مشخص کنید.
- در اینجا مشکل عوض شدن ایپی در صورت ریبوت شدن سرور ایران، مانند تانل HANS وجود ندارد
- از IFCONFIG برای اضافه شدن ایپی استفاده شده است.

--------------------------------------
![OIP2 (1)](https://github.com/Azumi67/V2ray_loadbalance_multipleServers/assets/119934376/3ec2f05f-3308-4441-8cce-62ab4776f4e2)
**تانل ICMPTUNNEL با ریورس تانل RTT - چند پورت - TCP**
--------------------------------

![green-dot-clipart-3](https://github.com/Azumi67/6TO4-GRE-IPIP-SIT/assets/119934376/756f468e-8d6c-45bd-9a4a-a9d056011147)**سرور خارج**

**مسیر : icmptunnel RTT > multi port > kharej**

<p align="right">
  <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/55d1059e-d83a-4bce-8815-b5d330654a7d" alt="Image" />
</p>



- نخست RTT را نصب کنید و سپس سرور خارج را کانفیگ میکنیم .
- کانفیگ را از سرور خارج شروع میکنیم.
- پس از نصب پیش نیاز ها، تانل ICMPTUNNEL شما در سرور خارج فعال میشود و حالا نوبت کانفیگ RTT در سرور خارج است.
- من پورت ایران 443 گذاشتم.
- در قسمت SNI، گیت هاب را قرار میدهم. شما میتوانید SNI دیگری قرار دهید.
- در قسمت Restart Service مقدار 24 را قرار میدم. شما زمان مورد نیاز را بر اساس نیاز خودتان تغییر دهید.
- در اینجا مشکل عوض شدن ایپی در صورت ریبوت شدن سرور ایران، مانند تانل HANS وجود ندارد
- از IFCONFIG برای اضافه شدن ایپی استفاده شده است.
- کانفیگ شبیه تک پورت میباشد ولی من برای مولتی پورت تمام پورت ها را باز گذاشتم.
- در مالتی پورت، پورت کانفیگ شما تغییری نخواهد کرد و همان پورت قبلی خواهد بود. تنها ایپی ادرس شما به ایپی ادرس ایران تغییر خواهد کرد.
  
 ---------------------------------------
 
 ![green-dot-clipart-3](https://github.com/Azumi67/6TO4-PrivateIP/assets/119934376/49000de2-53b6-4c5c-888d-f1f397d77b92)**سرور ایران**

**مسیر : icmptunnel RTT > multi port > iran**

 <p align="right">
  <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/ac4a6821-404c-4687-bcf1-ae8940869540" alt="Image" />
</p>


- مانند سرور خارج، نخست RTT را نصب کنید و سپس کانفیگ سرور ایران را انجام دهید.
- پس ار نصب پیش نیاز ها، از شما ایپی 4 سرور خارج را میخواهد که وارد میکنید و تانل ICMP بر روی سرور ایران فعال میشود. سپس کانفیگ RTT را بر روی سرور ایران را انجام میدهیم.
- پورت ایران را من 443 قرار داده بودم
- قسمت SNI هم که گیت هاب گذاشته بودم.
- ریستارت سرویس هم که مانند قبل بر اساس نیازتان، مقدارش را مشخص کنید.
- در اینجا مشکل عوض شدن ایپی در صورت ریبوت شدن سرور ایران، مانند تانل HANS وجود ندارد
- از IFCONFIG برای اضافه شدن ایپی استفاده شده است.
- کانفیگ شبیه تک پورت میباشد ولی من برای مولتی پورت تمام پورت ها را باز گذاشتم.
- در مالتی پورت، پورت کانفیگ شما تغییری نخواهد کرد و همان پورت قبلی خواهد بود. تنها ایپی ادرس شما به ایپی ادرس ایران تغییر خواهد کرد.

--------------------------------------
![OIP2 (1)](https://github.com/Azumi67/V2ray_loadbalance_multipleServers/assets/119934376/3ec2f05f-3308-4441-8cce-62ab4776f4e2)
**تانل Hans با ریورس تانل RTT - تک پورت - UDP**
--------------------------------

![green-dot-clipart-3](https://github.com/Azumi67/6TO4-GRE-IPIP-SIT/assets/119934376/756f468e-8d6c-45bd-9a4a-a9d056011147)**سرور خارج**

**مسیر :  Hans RTT > single port > kharej**

<p align="right">
  <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/783418cd-a0ff-4f08-8099-edd4b405e879" alt="Image" />
</p>



- نخست RTT را نصب کنید و سپس سرور خارج را کانفیگ میکنیم .
- کانفیگ را از سرور خارج شروع میکنیم.
- پس از نصب پیش نیاز ها، تانل ICMP شما در سرور خارج فعال میشود و حالا نوبت کانفیگ RTT در سرور خارج است.
- پورت وایرگارد من 50824 میباشد.
- من پورت ایران 443 گذاشتم و این پورت جدید وایرگارد من خواهد شد.
- در قسمت SNI، گیت هاب را قرار میدهم. شما میتوانید SNI دیگری قرار دهید.
- در قسمت Restart Service مقدار 24 را قرار میدم. شما زمان مورد نیاز را بر اساس نیاز خودتان تغییر دهید.
------------------

  ![Exclamation-Mark-PNG-Clipart](https://github.com/Azumi67/6TO4-GRE-IPIP-SIT/assets/119934376/1b367bc9-aaed-4a8d-84a6-a2a1fc31b831)**نکات**
  
  - در صورت ریبوت شدن سرور ایران ، یک ایپی جدید برای تانل ICMP انتخاب میشود و این باعث میشود که در تانل شما اختلال پیش بیاید.
  - از طریق دو راه میشه این مشکل را حل کرد . با ادیت سرویس تانل رادکسوت در سرور خارج و تغییر ایپی قدیمی به ایپی جدید در سرور ایران.
  - برای روش اول، این مسیر سرویس تانل RTT میباشد. etc/systemd/system/radkesvattunnel-kharej.service/
  - با nano ویرایش کنید و ایپی جدید ایران هم در سرور ایران با دستور ip a بدست اورید.
  - راه دوم هم ریبوت کردن سرور خارج و ایران میباشد که درست میشود.(این روش ساده تر است)
  - دقت نمایید این مشکل در تانل HANS است و تنها در صورتی اتفاق میوفتد که سرور ایران ریبوت شود و خارج ریبوت نشود.
  
 ---------------------------------------
 
 ![green-dot-clipart-3](https://github.com/Azumi67/6TO4-PrivateIP/assets/119934376/49000de2-53b6-4c5c-888d-f1f397d77b92)**سرور ایران**

**مسیر : Hans RTT > single port > iran**

 <p align="right">
  <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/c3b9cd31-d397-47be-8fd6-8ae91cd1ad63" alt="Image" />
</p>


- مانند سرور خارج، نخست RTT را نصب کنید و سپس کانفیگ سرور ایران را انجام دهید.
- پس ار نصب پیش نیاز ها، از شما ایپی 4 سرور خارج را میخواهد که وارد میکنید و تانل ICMP بر روی سرور ایران فعال میشود. سپس کانفیگ RTT را بر روی سرور ایران را انجام میدهیم.
- پورت ایران را من 443 قرار داده بودم
- قسمت SNI هم که گیت هاب گذاشته بودم.
- ریستارت سرویس هم که مانند قبل بر اساس نیازتان، مقدارش را مشخص کنید.

--------------------------------------
![OIP2 (1)](https://github.com/Azumi67/V2ray_loadbalance_multipleServers/assets/119934376/3ec2f05f-3308-4441-8cce-62ab4776f4e2)
**تانل Icmptunnel با ریورس تانل RTT - تک پورت - UDP**
--------------------------------

![green-dot-clipart-3](https://github.com/Azumi67/6TO4-GRE-IPIP-SIT/assets/119934376/756f468e-8d6c-45bd-9a4a-a9d056011147)**سرور خارج**

**مسیر :  ICMPTunnel RTT > single port > kharej**

<p align="right">
  <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/bdc3a93b-d684-4005-9d13-a643d9dc82b2" alt="Image" />
</p>



- نخست RTT را نصب کنید و سپس سرور خارج را کانفیگ میکنیم .
- کانفیگ را از سرور خارج شروع میکنیم.
- پس از نصب پیش نیاز ها، تانل ICMP شما در سرور خارج فعال میشود و حالا نوبت کانفیگ RTT در سرور خارج است.
- پورت وایرگارد من 50824 میباشد.
- من پورت ایران 443 گذاشتم و این پورت جدید وایرگارد من خواهد شد.
- در قسمت SNI، گیت هاب را قرار میدهم. شما میتوانید SNI دیگری قرار دهید.
- در قسمت Restart Service مقدار 24 را قرار میدم. شما زمان مورد نیاز را بر اساس نیاز خودتان تغییر دهید.
- در اینجا مشکل عوض شدن ایپی در صورت ریبوت شدن سرور ایران، مانند تانل HANS وجود ندارد
- از IFCONFIG برای اضافه شدن ایپی استفاده شده است.
  
 ---------------------------------------
 
 ![green-dot-clipart-3](https://github.com/Azumi67/6TO4-PrivateIP/assets/119934376/49000de2-53b6-4c5c-888d-f1f397d77b92)**سرور ایران**

**مسیر : Hans RTT > single port > iran**

 <p align="right">
  <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/c3b9cd31-d397-47be-8fd6-8ae91cd1ad63" alt="Image" />
</p>


- مانند سرور خارج، نخست RTT را نصب کنید و سپس کانفیگ سرور ایران را انجام دهید.
- پس ار نصب پیش نیاز ها، از شما ایپی 4 سرور خارج را میخواهد که وارد میکنید و تانل ICMP بر روی سرور ایران فعال میشود. سپس کانفیگ RTT را بر روی سرور ایران را انجام میدهیم.
- پورت ایران را من 443 قرار داده بودم
- قسمت SNI هم که گیت هاب گذاشته بودم.
- ریستارت سرویس هم که مانند قبل بر اساس نیازتان، مقدارش را مشخص کنید.
- در اینجا مشکل عوض شدن ایپی در صورت ریبوت شدن سرور ایران، مانند تانل HANS وجود ندارد
- از IFCONFIG برای اضافه شدن ایپی استفاده شده است.

--------------------------------------
**اسکرین شات**

<details>
  <summary align="right">Click to reveal image</summary>
  
  <p align="right">
    <img src="https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/a76d15bd-e4da-40db-a3e0-6bf43e3e02e4" alt="menu screen" />
  </p>
</details>


------------------------------------------
![scri](https://github.com/Azumi67/FRP-V2ray-Loadbalance/assets/119934376/cbfb72ac-eff1-46df-b5e5-a3930a4a6651)
**اسکریپت های کارآمد :**
- این اسکریپت ها optional میباشد.


 
 Opiran Script
```
apt install curl -y && bash <(curl -s https://raw.githubusercontent.com/opiran-club/VPS-Optimizer/main/optimizer.sh --ipv4)
```

Hawshemi script

```
wget "https://raw.githubusercontent.com/hawshemi/Linux-Optimizer/main/linux-optimizer.sh" -O linux-optimizer.sh && chmod +x linux-optimizer.sh && bash linux-optimizer.sh
```

-----------------------------------------------------
![R (a2)](https://github.com/Azumi67/PrivateIP-Tunnel/assets/119934376/716fd45e-635c-4796-b8cf-856024e5b2b2)
**اسکریپت من**
----------------


```
apt install python3 -y && apt install pip -y &&  pip install colorama && pip install netifaces && apt install curl -y && python3 <(curl -Ls https://raw.githubusercontent.com/Azumi67/RTT-ICMP-Tunnel/main/rtt-icmp.py --ipv4)
```
--------------------------------------
 <div dir="rtl">&bull;  دستور زیر برای کسانی هست که پیش نیاز ها را در سرور، نصب شده دارند</div>
 
```
python3 <(curl -Ls https://raw.githubusercontent.com/Azumi67/RTT-ICMP-Tunnel/main/rtt-icmp.py --ipv4)
```
--------------------------------------
 <div dir="rtl">&bull; اگر سرور شما خطای externally-managed-environment داد از دستور زیر اقدام به اجرای اسکریپت نمایید.</div>
 
```
bash -c "$(curl -fsSL https://raw.githubusercontent.com/Azumi67/RTT-ICMP-Tunnel/main/managed2.sh)"
```

---------------------------------------------
![R (7)](https://github.com/Azumi67/PrivateIP-Tunnel/assets/119934376/42c09cbb-2690-4343-963a-5deca12218c1)
**تلگرام** 
![R (6)](https://github.com/Azumi67/FRP-V2ray-Loadbalance/assets/119934376/f81bf6e1-cfed-4e24-b944-236f5c0b15d3) [اپیران- OPIRAN](https://github.com/opiran-club)

---------------------------------
![R23 (1)](https://github.com/Azumi67/FRP-V2ray-Loadbalance/assets/119934376/18d12405-d354-48ac-9084-fff98d61d91c)
**سورس ها**


![R (6)](https://github.com/Azumi67/RTT-ICMP-Tunnel/assets/119934376/4aaca07f-8685-48a6-9bb5-6d84f40f5128)[سورس های RTT](https://github.com/radkesvat)

![R (9)](https://github.com/Azumi67/FRP-V2ray-Loadbalance/assets/119934376/33388f7b-f1ab-4847-9e9b-e8b39d75deaa) [سورس های icmptunnel](https://github.com/jamesbarlow/icmptunnel)

![R (9)](https://github.com/Azumi67/FRP-V2ray-Loadbalance/assets/119934376/33388f7b-f1ab-4847-9e9b-e8b39d75deaa) [سورس های hans](https://github.com/friedrich/hans)

![R (9)](https://github.com/Azumi67/FRP-V2ray-Loadbalance/assets/119934376/33388f7b-f1ab-4847-9e9b-e8b39d75deaa) [سورس های OPIRAN](https://github.com/opiran-club)

![R (9)](https://github.com/Azumi67/6TO4-GRE-IPIP-SIT/assets/119934376/4758a7da-ab54-4a0a-a5a6-5f895092f527)[سورس های Hwashemi](https://github.com/hawshemi/Linux-Optimizer)



-----------------------------------------------------

![youtube-131994968075841675](https://github.com/Azumi67/FRP-V2ray-Loadbalance/assets/119934376/24202a92-aff2-4079-a6c2-9db14cd0ecd1)
**ویدیوی آموزش**

-----------------------------------------


