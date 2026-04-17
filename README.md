\# IAM OAuth Demo



A Python Flask web application demonstrating OAuth 2.0 and OpenID Connect (OIDC) login flow using Google as the Identity Provider.



\## What it does



\- User clicks Login with Google

\- App redirects to Google for authentication

\- Google confirms identity and returns a token

\- App reads the token and displays user's name, email and profile picture

\- User can log out and session is cleared



\## IAM concepts demonstrated



\- OAuth 2.0 authorisation code flow

\- OpenID Connect (OIDC) for identity verification

\- Token handling and claims extraction

\- Third party Identity Provider (IdP) integration

\- Session management and secure logout



\## Tech stack



\- Python 3

\- Flask

\- Authlib (OAuth 2.0 client)

\- Google OAuth 2.0

\- Bootstrap 5



\## How to run



```bash

git clone https://github.com/YourUsername/iam-oauth-demo.git

cd iam-oauth-demo

python -m venv venv

venv\\Scripts\\activate

pip install -r requirements.txt

```



Create a `.env` file in the root folder:

GOOGLE\_CLIENT\_ID=your\_google\_client\_id

GOOGLE\_CLIENT\_SECRET=your\_google\_client\_secret

SECRET\_KEY=supersecretkey



Then run:

```bash

python app.py

```



Open your browser at `http://127.0.0.1:5000` and click Login with Google.



\## How to get Google credentials



1\. Go to console.cloud.google.com

2\. Create a new project

3\. Go to APIs and Services → OAuth consent screen → External

4\. Go to APIs and Services → Credentials → Create OAuth 2.0 Client ID

5\. Add `http://127.0.0.1:5000/callback` as an authorised redirect URI

6\. Copy the Client ID and Client Secret into your `.env` file



\## OAuth 2.0 flow explained

User → clicks Login with Google

→ Flask redirects to Google

→ Google asks user to confirm

→ Google sends back authorisation code

→ Flask exchanges code for token

→ Flask reads user info from token

→ User sees their profile on dashboard



\## Project structure

iam-oauth-demo/

├── app.py            ← Flask app with OAuth routes

├── templates/

│   ├── home.html     ← Login page

│   └── dashboard.html ← User profile and token info

├── .env              ← Your credentials (never commit this)

├── .gitignore        ← Excludes .env from GitHub

└── requirements.txt

