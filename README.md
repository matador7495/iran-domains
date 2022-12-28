<div dir=rtl>

#  دامنه‌های میزبانی شده در ایران

بسیاری از سرویس‌ها و دامنه‌های خارج از ایران سانسور و مسدود شده‌اند و باید برای دسترسی به آن‌ها از VPN و Proxy هایی با امنیت بالا استفاده کنیم، جدای از این مسئله دسترسی به بعضی سرویس‌های ایرانی از طریق IP خارجی مسدود شده است. حال برای دور زدن این سرویس ها لیستی از دامنه‌های داخلی را جمع کرده‌ایم تا با اضافه کردن آن‌ به کلاینت‌های مورد استفاده، دیگر نیاز به قطع کردن VPN برای دسترسی به سرویس‌های داخلی نباشد.

## مشکلات VPN و Proxy در ایران
مشکلات زیر هنگام بازدید برخی از وب‌سایت‌های داخلی از طریق IP خارجی بوجود می‌آید:

- برای دسترسی ممکن است کاربر را مجبور به داشتن IP داخلی کنند.
- برخی از ISP ها درصورت مصرف پهنای باند داخلی تخفیف ۵۰ درصد اعمال می‌کنند.
- برخی از سایت‌ها ممکن است سرعت و پهنای باند کاربران خارجی را محدود کنند.


## روش استفاده

### [Clash](https://github.com/Dreamacro/clash) (Like [ClashX](https://github.com/yichengchen/clashX) / [clash_for_windows_pkg](https://github.com/Fndroid/clash_for_windows_pkg) / [Clash .NET](https://github.com/ClashDotNetFramework/ClashDotNetFramework/releases) / ...)

1. صفحه‌ی پروفایل/تنظیمات فعلی خود را که استفاده می‌کنید باز کنید.  
2. این خطوط را به فایل اضافه کنید:  
```yaml
rule-providers:
  iran:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/matador7495/iran-domains/main/clash_rules.yaml"
    path: ./ruleset/database-iran.yaml
    interval: 86400
```
* بصورت خودکار هر 24 ساعت آپدیت می شود.

3. سپس خط زیر را به بخش قوانین `Rules` اضافه کنید:  
```yaml
  - RULE-SET,iran,DIRECT
```

4. فایل را ذخیره کنید.  
5. بستگی به نوع کلاینت، ممکن است لازم باشد نرم‌افزار را روی حالت `Rule‍` تنظیم کنید.  

   
## منابع

- دامنه‌های ایران:
  - [سازمان فناوری اطلاعات ایران](https://g2b.ito.gov.ir/index.php/site/list_ip)
  - [سامانه مدیریت اینترنت مشتریان شرکت مخابرات ایران](https://adsl.tci.ir/panel/sites)
  - لیست شخصی
- تبلیغات:
  - [PersianBlocker](https://github.com/MasterKia/PersianBlocker) (لایسنس AGPL-3.0)

اگر شما منابع دیگری می‌شناسید و یا وب‌سایتی پیدا کرده‌اید که اینجا نیست لطفا یک
[issue] باز کنید 

