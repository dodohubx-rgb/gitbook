# 🔧 How to setting

### วิธีการตั้งค่า Account Hub / Webhook

{% stepper %}
{% step %}
#### **เข้าสู่เว็บไซต์** [https://account.dodohub.dev/](https://account.dodohub.dev/)
{% endstep %}

{% step %}
**Login ด้วย Discord**

ใช้บัญชี Discord ที่ **เชื่อมกับสคริปต์** ในการเข้าสู่ระบบ\


<div align="left"><figure><img src="../../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
#### **Generate API Token**

* เมื่อเข้าสู่ระบบแล้ว จะเห็น **API Token**
* กดปุ่ม **Generate** แล้ว **Copy Token** เก็บไว้

<div align="left"><figure><img src="../../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
**ใส่ Token ใน Webhook**

* ไปที่แท็บ **Webhook ในสคริปต์**จะเห็นช่อง **Account Hub Token ที่อยู่ด้านล่าง**
* ให้วาง Token ที่ Copy ไปใส่ในช่อง

<div align="left"><figure><img src="../../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
**ตั้งค่าความถี่การอัปเดต**

* เลือกระยะเวลาการแจ้งเตือนที่ต้องการ
* **ต่ำสุด:** ทุก 5 นาที
* **สูงสุด:** ทุก 60 นาที

<div align="left"><figure><img src="../../../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
**ติ้ก Automatic Sync**

<div align="left"><figure><img src="../../../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
กลับไปที่เว็บไซต์ [https://account.dodohub.dev/](https://account.dodohub.dev/)

* จะเห็นปุ่ม **Build A Zoo** กด **Go to Game** เพียงเท่านี้ คุณก็จะเห็น **ทุก Account ของคุณ** แสดงผลในระบบแล้ว

<div align="left"><figure><img src="../../../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}
{% endstepper %}

{% hint style="success" %}
#### &#x20; หมายเหตุ: เหมือนกับ Discord Webhook คือ **1 Token สามารถใช้กับหลายตัวได้**
{% endhint %}
