# Intelligent Invoice Follow-Up Automation (n8n)

## 📌 Overview  
This project automates **invoice follow-ups** using [n8n](https://n8n.io).  
It ensures overdue invoices don’t get lost or ignored by sending **context-aware, AI-generated follow-up emails** at specific intervals (7, 14, 21, 28 days).  

Instead of sending repetitive reminders, the workflow analyzes **email history + invoice data** to create **personalized, professional messages** that feel like they’re coming directly from you.  

---

## 🎯 Why This Matters  
For many businesses, unpaid invoices create serious **cash flow problems**.  
Manually tracking who owes what — and remembering to send follow-ups — is tedious and error-prone.  

This automation:  
- Tracks invoices automatically.  
- Knows when and how often to follow up.  
- Avoids duplicate or irrelevant emails by analyzing prior conversations.  
- Helps businesses recover thousands of dollars that would otherwise be delayed.  

---

## ⚙️ How It Works  

1. **Fetch Invoice Data**  
   - Pulls records from Google Sheets (can be replaced with Stripe, QuickBooks, Xero, etc.).  

2. **Check Days Overdue**  
   - Calculates how many days an invoice has been outstanding.  
   - Triggers different follow-up stages (7, 14, 21, 28 days).  

3. **Review Email History**  
   - Retrieves the last X emails with the client via Gmail.  
   - Ensures no duplicate reminders are sent if the invoice was already discussed.  

4. **AI Drafting (OpenAI)**  
   - AI decides if a reminder should be sent.  
   - Generates a **polite, human-like email** tailored to the conversation.  

5. **Send Follow-Up**  
   - Emails are sent via Gmail, appearing as if they were personally written by you.  

6. **(Optional) Auto-Resolve**  
   - If connected to Stripe/QuickBooks, the system marks invoices as *Paid* to stop further reminders.  

---

## 🛠️ Tech Stack  
- **n8n** – workflow automation  
- **Google Sheets** – invoice data source (demo)  
- **Gmail API** – fetch & send emails  
- **OpenAI API** – intelligent drafting  
- **JSON Processing & Filters** – n8n nodes for logic  

---

## 📂 Repository Structure  
```markdown
/n8n-invoice-followup
│── README.md        # Documentation
│── workflow.json    # Exported n8n workflow
│── templates/       # Example email templates
│── examples/        # Sample Google Sheets data
````

---

## 🚀 Getting Started

### Prerequisites

* [n8n installed](https://docs.n8n.io/getting-started/installation/) (self-hosted or cloud)
* A Google account (for Sheets + Gmail API)
* OpenAI API key

### Setup

```bash
# 1. Clone this repo
git clone https://github.com/yourusername/n8n-invoice-followup.git
cd n8n-invoice-followup

# 2. Import workflow.json into n8n
#    (n8n → Import → Upload workflow.json)

# 3. Configure credentials
#    - Google Sheets & Gmail API
#    - OpenAI API key

# 4. Replace Google Sheets with your system
#    (Stripe, QuickBooks, Xero, etc.)

# 5. Customize templates in /templates/

# 6. Run automation on schedule (e.g., daily 7:30 AM)
```

---

## 📧 Example Output

### 7-Day Reminder Example

```markdown
Subject: Friendly Reminder – Invoice Payment  

Hi [Client Name],  

Hope you’re doing well. I just wanted to check in on the invoice I sent you earlier.  
If there’s anything unclear or if you need assistance, please let me know.  

Thanks,  
[Your Name]  
```

### 21-Day Reminder Example (firmer tone)

```markdown
Subject: Urgent: Invoice Overdue  

Hi [Client Name],  

This is a reminder that Invoice #[Number] is still outstanding after 21 days.  
We’d appreciate it if you could arrange payment at the earliest to avoid any service interruptions.  

Thank you,  
[Your Name]  
```

---

## 💡 Customization Ideas

* Adjust follow-up frequency (daily, weekly, custom intervals).
* Add Slack/WhatsApp notifications for internal tracking.
* Integrate with CRM (HubSpot, Salesforce).
* Auto-update invoice status when payment is received (Stripe/QuickBooks webhooks).

---

## 🏆 Value Proposition

* **Saves hours** of manual follow-up time.
* **Prevents lost revenue** from forgotten invoices.
* **Scales effortlessly** across dozens of clients.
* **Human-like personalization** via AI keeps communication professional.

---

## 📜 License

MIT License – free to use and adapt.


