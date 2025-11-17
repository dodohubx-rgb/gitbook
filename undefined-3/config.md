# ⚙️ Config

> TH: กำหนดค่าพื้นฐานที่ใช้ควบคุมการทำงานของสคริปต์\
> EN: Basic configuration options to control script behavior

---

### 📋 Config Options

| Config               | Required | Default | TH (คำอธิบาย)                                                       | EN (Description)                                                               |
| -------------------- | -------- | ------- | ------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| **global_workspace** | no       | `true`  | ใช้ config ร่วมกันทุกบัญชี หรือแยกเป็นรายบัญชี                      | Use one shared config for all accounts, or separate per account                |
| **auto_hideui**      | no       | `false` | ซ่อน UI อัตโนมัติหลังจากเริ่มสคริปต์ หรือให้ UI แสดงอยู่            | Hide UI automatically after script initialization, or keep it visible          |
| **whitescreen**      | no       | `false` | เปิดหน้าจอขาวเพื่อช่วยลดการใช้ทรัพยากรเครื่อง                       | Enable white screen to help reduce system resource usage                       |
| **headless**         | no       | `false` | เปิดใช้งานโหมด headless เพื่อปิดการเรนเดอร์ UI ช่วยลดการใช้ทรัพยากร | Enable headless mode to disable UI rendering, helping to reduce resource usage |

---

### 🔧 รายละเอียดแต่ละค่า / Option Details

#### `global_workspace`

- **TH**\
  ใช้สำหรับกรณีที่ **เครื่องคอมพิวเตอร์เปิดหลาย instance หรือหลายหน้าจอ (multi-instance)** แล้วตัวเกม/สคริปต์มัน **แชร์ workspace เดียวกัน**
  - `true` → ทุก instance จะใช้ config ชุดเดียวกัน (เหมาะกับ multi-instance)
  - `false` → แต่ละ instance จะมี config แยกกัน ไม่ทับกัน
  - _ค่าเริ่มต้น (Default): `true`_
- **EN**\
  This option is mainly for cases where your **PC runs multiple instances/screens (multi-instance setup)** and the game/script **shares the same workspace**.
  - `true` → all instances use the same config (good for multi-instance).
  - `false` → each instance has its own separate config.
  - _Default: `true`_

---

#### `auto_hideui`

- **TH**
  - `true` → ซ่อน UI อัตโนมัติหลังจากเริ่มสคริปต์
  - `false` → ให้ UI แสดงอยู่
  - _ค่าเริ่มต้น (Default): `false`_
- **EN**
  - `true` → Hide UI automatically after script initialization
  - `false` → Keep UI visible
  - _Default: `false`_

---

#### `whitescreen`

- **TH**\
  เปิดโหมดหน้าจอขาว (white screen) เพื่อช่วยลดการใช้งานทรัพยากรเครื่อง เช่น GPU/CPU ขณะสคริปต์กำลังทำงาน
  - `true` → เปิดใช้งานโหมดหน้าจอขาว
  - `false` → ปิดการใช้งาน (แสดงหน้าจอปกติ)
  - _ค่าเริ่มต้น (Default)_: `false`
- **EN**\
  Enable white screen mode to help reduce system resource usage (e.g., GPU/CPU) while the script is running.
  - `true` → enable white screen mode
  - `false` → disable (show normal screen)
  - _Default_: `false`

---

#### `headless`

- **TH**\
  เปิดใช้งานโหมด headless (ไม่แสดง UI) เพื่อช่วยลดการใช้ทรัพยากรเครื่อง
  - `true` → เปิดใช้งานโหมด headless
  - `false` → ปิดการใช้งาน (แสดง UI ตามปกติ)
  - _ค่าเริ่มต้น (Default): `false`_
- **EN**\
  Enable headless mode (no UI rendering) to help reduce resource usage.
  - `true` → enable headless mode
  - `false` → disable (show UI normally)
  - _Default: `false`_

---

### 📝 ตัวอย่างการใช้งาน / Example Usage

```lua
getgenv().g_config = {
    global_workspace = true, -- (Default: true)
    auto_hideui = false, -- (Default: false)
    whitescreen = false, -- (Default: false)
    headless = false -- (Default: false)
}
```

> 📝 **คำแนะนำ (TH):**\
> กรุณาวางโค้ด `getgenv().g_config = { ... }` ไว้ที่ **ด้านบนสุดของสคริปต์** ก่อนคำสั่งอื่น ๆ เพื่อให้ค่าคอนฟิกทำงานถูกต้องตั้งแต่เริ่มต้น

> 📝 **Note (EN):**\
> Please place the `getgenv().g_config = { ... }` block at the **very top of your script**, before any other commands, to ensure that the configuration is applied correctly.
