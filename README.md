# Email Validation Service (MVP)

A beginner-friendly but production-oriented **Email Validation Service** inspired by ZeroBounce and NeverBounce.  
This project validates email addresses **without sending any real emails**, using:

- Syntax & RFC checks  
- DNS / MX record lookup  
- SMTP handshake (EHLO → MAIL FROM → RCPT TO)  
- Confidence scoring  
- Reason codes  
- Single-email REST API  
- Bulk CSV validation  

This is the **MVP version**, created as part of my learning journey in backend development, email infrastructure, and SaaS architecture.

## 🚀 Features (Current MVP)
### Core Validation
- Validate a single email address  
- Syntax check  
- DNS lookup (MX, A/AAAA fallback)  
- SMTP RCPT-TO probing (no DATA → no real email sent)  
- Detect deliverable / undeliverable / risky / unknown  
- Reason codes (e.g., `smtp_250_ok`, `mx_not_found`)

### API
- POST /validate — Validate one email  
- POST /bulk — Upload CSV and validate multiple emails

## 📦 Project Structure
email-validation-service/
│
├── README.md              
├── requirements.txt       
│
├── validator/
│   ├── core_validator.py  
│   └── __init__.py
│
├── api/
│   ├── views.py           
│   ├── urls.py
│   └── serializers.py
│
└── examples/
    ├── sample.csv         
    └── result.json        

## 🔧 Tech Stack
- Python 3.11+
- Django 5
- Django REST Framework
- dnspython
- aiosmtplib
- email-validator
- uvicorn

## 📘 How It Works (Simple)
1. Syntax check  
2. DNS/MX lookup  
3. SMTP RCPT-TO test (no DATA)  
4. Scoring + reason codes  

## 🗺️ Roadmap
- MVP (done)  
- Catch-all / disposable / role detection  
- CSV export  
- Celery + Redis jobs  
- Dashboard UI  
- API keys + webhooks  

## 📄 License
MIT License
