# ✉️💣 Email Header Analysis: Unmasking the Phish!

Ever wondered how attackers disguise malicious emails to look legit?  


Welcome to the *real detective work* — where we dive into the email's **raw headers** and reveal its true origin.

Let's break down a phishing email step-by-step and expose every hidden trick they play.

> Well, it's time to flip the script and **catch the phish before it bites!** 🎣🐟

---

<img width="300" height="350" alt="image" src="https://github.com/user-attachments/assets/70f538a5-09ed-419a-89cf-4a4b58a46f95" />
<img width="300" height="350" alt="Screenshot 2025-08-06 131450" src="https://github.com/user-attachments/assets/d20202b3-9bc9-4bb9-8bcf-4657d3275d6f" />


*Source: Reddit*

---


> **Subject:** *"We need to talk..."*  
>  
> *"Hey... I know it's been a while. I just wanted to say it wasn't you... it was me.
> 
> It was my mistake.. 😔
> 
> I stored all our memories from the beginning of our relation. Don’t ignore this💝. (link-to-attachment)"*
>

😳 Sounds like an emotional rollercoaster, right? Except — **it's not your ex**, it's a scammer wearing heartbreak as a disguise 💔.

---


## Checklist

### 🧾 Summary of Phishing Traits (as we saw in phishing.md file)
Wrap up our analysis in a clean table or bullet list of detected red flags.

| Trait            | Observation                            |
| ---------------- | -------------------------------------- |
| Spoofed Email    | `amazn-orders@freeshopz.click`         |
| Urgency Language | “Your package will be returned today!” |
| Suspicious Link  | `http://verify-now.tk`                 |
| Bad Grammar      | “Your adress is incorect.”             |
| Failed SPF/DKIM  | SPF: Fail, DKIM: None                  |
| Mismatched URLs  | Text: amazon.in → Link: zzhosting.cc   |
| Fake Branding    | Low-res logo, missing footer           |


---

## 🍏 Phishing Alert : "Someone Signed in Using Your Apple Account"

### 📸 Screenshot Proof:
<img width="400" height="400" alt="Screenshot 2025-08-06 131753" src="https://github.com/user-attachments/assets/d35b0a52-cfb0-4f35-ba4c-53522e9e8b2e" />
Screenshot: Fake Apple security alert asking for action.

---

### 🔍 Analysis Breakdown

| Aspect                      | Observation                                                                       | Verdict            |
| --------------------------- | --------------------------------------------------------------------------------- | ------------------ |
| **1. Sender’s Email**       | Not shown — may appear as `appleid@security-notify.com` or similar spoofed domain | ⚠️ Suspected spoof |
| **2. Urgent Sign-in Alert** | "Used to sign in to iMessage on iPhone 7" — triggers **panic** reaction           | ✅ Fear tactic      |
| **3. Hyperlink Provided**   | `https://account.apple.com` — appears safe, but **must be hovered and verified**  | ⚠️ Verify it!      |
| **4. Grammar / Tone**       | Language is **mostly clean**, but slightly stiff and impersonal                   | ⚠️ Mixed           |
| **5. Branding**             | No full Apple footer, no copyright, just a lonely gray apple logo 🫠              | ❌ Suspicious       |
| **6. Familiar Device Trap** | Using "iPhone 7" — an older device, likely to confuse users                       | ⚠️ Manipulative    |

---

##  Email Header Analysis

### 🔍 Step 1: Obtain Email Header
Gmail: 

- Locate a **three-dot icon** on the top-right corner of the email
- Select **Show Original** in the drop-down menu. You’ll be able to view raw data in a new window. 




<img width="1000" height="1000" alt="Screenshot 2025-08-06 012017" src="https://github.com/user-attachments/assets/a4bbf7db-64f7-4b98-8511-2fe442bd775c" />


(Obtaining Header depends on your mailbox Provider. We are seeing Gmail here).

- Click **'Copy to Clipboard'** --> This is our Header. 
<img width="1000" height="1000" alt="Screenshot 2025-08-06 012042" src="https://github.com/user-attachments/assets/e3f9d7df-01c7-44e0-8f66-f0a5b3012572" />

---

### 🔍 Step 2: Analyze Email Header

- Suppose we have Sample **Phishing Email Header** (for Analysis)

          Delivered-To: victim123@gmail.com  
          Received: by 2002:a05:622a:1554:b0:29d:2c20:0 with SMTP id c20csp195312qkf;  
                  Mon, 5 Aug 2025 12:15:23 -0700 (PDT)  
          X-Received: by 2002:a17:902:b74c:: with SMTP id v12mr5029486pld.12.1691256923121;  
                  Mon, 05 Aug 2025 12:15:23 -0700 (PDT)  
          Return-Path: <bounces@mail-apple-alert.ru>  
          Received: from suspicious-host.ru (mail-apple-alert.ru. [185.244.25.108])  
                  by mx.google.com with ESMTPS id t19si282846qkb.13.2025.08.05.12.15.23  
                  for <victim123@gmail.com>  
                  (version=TLS1_3 cipher=TLS_AES_256_GCM_SHA384);  
                  Mon, 05 Aug 2025 12:15:23 -0700 (PDT)  
          Received-SPF: softfail (google.com: domain of transitioning mail-apple-alert.ru does not designate 185.244.25.108 as permitted sender)  
          Authentication-Results: mx.google.com;  
                 spf=softfail (google.com: domain of mail-apple-alert.ru does not designate 185.244.25.108 as permitted sender) smtp.mailfrom=bounces@mail-apple-alert.ru  
          From: Apple Support <support@apple-security-update.com>  
          To: victim123@gmail.com  
          Subject: Urgent: Apple ID login from new device  
          Date: Mon, 05 Aug 2025 21:15:21 +0200  
          Message-ID: <20250805121523.mailid123456@mail-apple-alert.ru>  
          MIME-Version: 1.0  
          Content-Type: text/html; charset=UTF-8  
          Content-Transfer-Encoding: quoted-printable
          
          
- Now, Go to **Google --> Email Header Analyzer --> Google ToolBox.**

  <img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/1b28142e-f84b-4968-856e-1c9e65419b21" />

- Click **Analyze the header above**

  <img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/ae60171f-460b-4ae4-9e4c-e8f81be7dd96" />

- Got Results

  <img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/27b87497-69d6-4d95-bbbb-6cb9d0190624" />


---

### 🧠 Red Flags You'll See

| Field          | Red Flag                                                       |
| -------------- | -------------------------------------------------------------- |
| `Return-Path:` | `mail-apple-alert.ru` — **Not an official Apple domain**       |
| `From:`        | `support@apple-security-update.com` — **Suspicious domain**    |
| `SPF:`         | Softfail — **Server not authorized** to send on Apple’s behalf |
| `Subject:`     | “Urgent” — **Uses panic language**                             |

---

**🚫 SPF (Sender Policy Framework) Result**

        Received-SPF: softfail


Why it’s suspicious:


> SPF tells us whether the email server was authorized to send on behalf of the domain.

- softfail = probably fake

- fail = definitely fake

- pass = trusted

  
✅ Legit Apple emails should pass SPF validation.

---

**💡 From Address (Sender Spoofing)**

        From: Apple Support <support@apple-security-update.com>
Why it’s suspicious:


Even though it says “Apple Support,” the domain is apple-security-update.com (a lookalike domain). This is classic spoofing.

> ✅ Legit should be like:
> 
> support@apple.com or no-reply@apple.com

---

**🕓 Date & Time**

        Date: Mon, 05 Aug 2025 21:15:21 +0200
Why it’s useful:


If you receive an "Apple login alert" at a time when you weren’t using Apple services, it’s another red flag.


You can cross-check the time and timezone to spot unusual behavior (e.g., login from a country you’re not in).

---

**🗂️ Message-ID**

        Message-ID: <20250805121523.mailid123456@mail-apple-alert.ru>
Why it’s suspicious:


The domain again doesn't match Apple. Real Apple messages will usually have message IDs like `<xxxxx@apple.com>`.

---

**📎 Content-Type / MIME**

        Content-Type: text/html; charset=UTF-8
Phishers often send HTML-based emails to hide links behind buttons or styled text.


✅ You can hover over links in these HTML emails to reveal mismatched URLs. (Steps Below)

        On Desktop (Windows/Linux/macOS):
        1. **Open the email** (but **don’t click** any links).
        
        2. **Move your mouse cursor over the link** (hover — don’t click).
        
        3. 🔍 You’ll see the **actual URL** appear:
        
          - In the **bottom-left corner** of your browser/email client.
        
          - Or as a **tooltip popup** near the cursor.
        
        **Example:**
        The link says Click here to reset your password
        Hover shows → http://malicious-login.xyz/reset.php

---

**📬 Subject Line**

        Subject: Urgent: Apple ID login from new device

Emotional trigger words like “Urgent,” “New Login,” “Account Blocked” are classic phishing bait to scare you into clicking.



---

> 🫖 Tea-Time Truth:
> 
> "Your account has been updated" — but I haven’t even updated my mood in 3 days.
> 
> Don’t sip panic — **sip logic and hover that link**.
>

---

**Author**: Me :)


Stay safe! Even the fonts you see... might be lying to you. 🤔
*'Cause, Nothing is what it seems!*
