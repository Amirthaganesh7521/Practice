# Phishing Email Analysis 

## Objective:
Identify phishing characteristics in a suspicious email sample by using, MXToolbox

Based on the MXToolbox analysis, this email appears legitimate with proper domain configurations (SPF, DKIM, DMARC), a clean IP reputation, and no signs of suspicious activity or tampering.

However, if any of these records were missing or invalid, it would indicate that the email may be suspicious, and further investigation would be required.


### here some snippets, to expalain the sample phishing mail details

---
<img width="1359" height="679" alt="IMG_20251021_173014" src="https://github.com/user-attachments/assets/6cc03566-cc1b-4d84-9480-841a4c522bbf" />


<img width="1366" height="685"<img width="1366" height="692" alt="IMG_20251021_172951" src="https://github.com/user-attachments/assets/f19325f9-dd3e-4bc3-8268-0aacf6ff18e5" />


<img width="1366" height="685" alt="IMG_20251021_172933" src="https://github.com/user-attachments/assets/8101429c-e519-4f83-8c40-302c0b16e649" />

---

## Email Analysis

### 1. **Sender Spoofing**
- **From:** `"support@mail.coinbase.com" <mssggeauthencti-cbspprt-325937197367@medisept.com.au>`
- The sender’s *display name* pretends to be Coinbase, but the **real domain** is `medisept.com.au` (not Coinbase).
- **Indicator:** Spoofed sender address — mismatch between display name and actual domain.

---

### 2. **Subject Line**
- **Subject (decoded):** `[Alert] Confirm your info is required [Case ID 153465]`
- **Indicator:** Uses urgency (“Confirm your info required”), a common phishing tactic.

---

### 3. **Email Header Check**
- **SPF:** None or inconsistent (`spf=none`, “medisept.com.au does not designate permitted sender hosts”)
- **DKIM:** None (message not signed)
- **DMARC:** None
- **Indicator:** Authentication mechanisms (SPF/DKIM/DMARC) missing → suspicious.

---

### 4. **Suspicious Attachments**
- Contains file: `"Coinbase -15392.docx"`
- **Indicator:** Malicious attachment likely disguised as a legitimate Coinbase document.

---

### 5. **Suspicious Links or Content**
- Body text: “Coinbase Support GQVH1” — minimal content, prompting user curiosity to open attachment.
- **Indicator:** Minimal context + attachment lure = phishing pattern.

---

### 6. **Urgent or Threatening Language**
- Subject includes “Confirm your info is required” — creates urgency.
- **Indicator:** Urgent tone intended to manipulate user response.




### 7. **Grammar/Spelling Errors**
- The header structure and random encoding (e.g., “=?UTF-8?Q?...”) suggest poor formatting.
- **Indicator:** Sloppy structure and encoded fragments often seen in phishing.

---

### 8. **Mismatched or Fake URLs**
- Not visible in plain text, but the sender domain (`medisept.com.au`) is unrelated to the content (Coinbase).
- **Indicator:** Mismatched domain identity.

---

## Summary Report of Phishing Indicators

| No. | Indicator | Description |
|-----|------------|-------------|
| 1 | Spoofed sender | Pretends to be Coinbase but uses medisept.com.au |
| 2 | Missing SPF/DKIM/DMARC | Email authentication failed or missing |
| 3 | Urgent subject | “Confirm your info required” creates pressure |
| 4 | Unrelated domain | medisept.com.au has no link to Coinbase |
| 5 | Suspicious attachment | “Coinbase -15392.docx” likely malware |
| 6 | Poor formatting | Encoded, unclear email body |
| 7 | Lack of context | No official Coinbase formatting or signature |
| 8 | Social engineering | Urgency to confirm personal info |

---

## Outcome:
Awareness of phishing tactics and ability to analyze suspicious emails by checking sender authenticity, header discrepancies, and malicious attachments.

---


