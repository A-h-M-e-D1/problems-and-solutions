### المشكلة:
**Could not open /dev/vmmon: No such file or directory.**  
يحدث غالبًا بعد تحديث الكيرنل أو عند عدم وجود kernel headers.

---

###  الاسباب:
-عدم تثبيت حزمة `linux-headers`

-تحديث الكيرنل ولم يتم إعادة بناء الـ VMware modules

---

###  الحل:
1. تأكد من وجود الـ kernel headers:
   ```bash
   sudo apt install build-essential linux-headers-$(uname -r)

2. أعد بناء modules الخاصة بـ VMware:
   ```bash
    sudo vmware-modconfig --console --install-all
   ```

3. roboot the system 
