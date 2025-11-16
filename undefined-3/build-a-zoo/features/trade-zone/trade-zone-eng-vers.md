# Trade Zone (Eng Vers)

## 🧩 Hold Pet Filter (Pets to Trade)

This function is used to **select which pet you want to trade**.\
The system will automatically choose a pet based on your configured conditions.

You can choose between **2 main modes:**

***

### 🌀 Filter Mode

Choose how the system filters pets.

* **Produce Speed** → The system selects pets based on their earning speed range.
* **Selection** → The system selects pets based on specific **names and mutations (buffs)** you define.

***

### 🏃‍♂️ Mode: Produce Speed

#### 🔢 Pet Value Range

Set the **earning speed range** (coins per second) for pets to be eligible for trading.\
Enter **Min (minimum)** and **Max (maximum)** values.\
The system will only choose pets whose coin-earning speed falls within this range.

💡 **Example:**\
If you set **Min = 1** and **Max = 100**,\
the system will only pick pets that earn between **1–100 coins per second**.

#### ↕ Sort Order

Determine the order in which pets are selected.

* **Desc** → Selects the pet that earns the **most coins first**.
* **Asc** → Selects the pet that earns the **least coins first**.

***

### 🐾 Mode: Selection

#### 🧬 Pet Names & Mutations

Select the **pet names** and **buffs (mutations)** you want the system to use for trading.\
You can select **multiple names**.\
The system will pick the first pet that matches your selected names or buffs as the trading pet.

⚠️ **Note:**\
When using **Selection Mode**, the **Pet Value Range** field will not be available.\
Use **Sort Order (Asc / Desc)** instead to prioritize which pet to pick first.

#### ↕ Sort Order

Used to sort when multiple pets match your filters.

* **Desc** → Selects the pet that earns the **most coins first**.
* **Asc** → Selects the pet that earns the **least coins first**.

***

### 🔒 Ignore Locked Pets

* **Enabled (✅)** → The system will **skip locked pets**.
* **Disabled (❌)** → The system will include **both locked and unlocked pets** in selection.

***

## 💱 Trade Options (Pets to be Traded)

This feature is used to **set automatic trade acceptance rules**.\
The system will decide whether to **accept or reject** trades based on the rules you configure.

***

### 🧾 Whitelisted Pets

Used to specify **pets you want to receive no matter what**.\
If a trade includes a pet listed in your Whitelist, the system will **instantly accept the trade** regardless of the pet’s earning speed.

💡 **Example:**\
If you want to always get **Toothless**, regardless of how much it earns,\
just add “Toothless” to your Whitelist.\
The system will **auto-accept the trade immediately** without checking the Minimum value.

***

### ⏩ Minimum Accept Speed

Defines the **minimum earning speed threshold** of pets you want to accept in trades.

#### 🔸 How It Works

* **If the pet in the trade is in the Whitelist:**\
  ✅ The system will **instantly accept** the trade, ignoring the Minimum value.
* **If the offered pet’s coin rate is greater than or equal to the Minimum:**\
  ✅ The system will **evaluate further** whether the offered pet is better than your current one (Holder).
  * If the offered pet is **better than the Holder:**\
    ✅ The system **accepts** the trade immediately.
  * If the offered pet **earns less** than the Holder:\
    ❌ The system **rejects** the trade.
* **If the offered pet’s coin rate is below the Minimum:**\
  ❌ The system will **reject** the trade immediately.

***

💡 **Example 1:**\
You set **Minimum = 200,000**\
→ The system only accepts pets that earn **≥ 200,000 coins per second**.\
If a pet earns **150,000**, the system **will not trade**.

💡 **Example 2:**\
You set **Minimum = 200,000**,\
but **Toothless** is on your Whitelist.\
→ The system will **trade instantly**, even if Toothless earns less than 200,000.

***

#### ⚙️ Summary

* **Minimum Accept Speed** → Sets the minimum coin-earning speed for pets you want to trade.
* **Whitelist** → Overrides all conditions; trades are accepted instantly, regardless of speed.

***

## 🤖 Auto Trade

Enables or disables **automatic trading**.

* **Enabled (✅)** → The system trades automatically following all configured rules.
* **Disabled (❌)** → The system will not auto-trade.

***

## 🧠 Overall Decision Flow

| Step | Condition                    | If Passed                                               | If Failed         |
| ---- | ---------------------------- | ------------------------------------------------------- | ----------------- |
| 1    | Whitelist                    | ✅ Instantly trade (skip all other conditions)           | Proceed to Step 2 |
| 2    | Minimum Accept Speed         | ✅ Proceed to Step 3                                     | ❌ Reject trade    |
| 3    | Better (Compare with Holder) | ✅ Trade                                                 | ❌ Reject trade    |
| 4    | Final Result                 | ✅ Trade if all conditions are met or pet is Whitelisted | ❌ Decline trade   |
