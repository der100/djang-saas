


https://github.com/roperi/YaSaas/assets/9901508/f7d47c5d-953f-49aa-bade-41fe3aee13f9


<h1 align="center">YaSaas - Monetize your data</h1>
<h2 align="center">Open-source Django REST Framework + React SaaS Boilerplate</h2>

---

YaSaas is an open-source SaaS boilerplate built on Django REST Framework and React, offering a flexible foundation for entrepreneurs looking to monetize their data. 

With seamless integration of Stripe subscriptions and leveraging Django admin functionalities, YaSaas simplifies the process of selling various data products. Whether it's financial data, market insights, or custom datasets, YaSaas provides a practical starting point for individuals keen on exploring data monetization. 

As an open-source solution, YaSaas is freely available, making it accessible for those who want to kickstart their data-driven ventures.


### Rationale: Or why YaSaas uses Django Admin for end-users

YaSaas leverages Django's robust permission system, utilizing Groups and User permissions for precise data access control. In Django, a Group is a collection of Users, and permissions can be assigned to both Users and Groups. YaSaas utilizes Django admin's intuitive interface to manage these permissions effectively.

Entrepreneurs can create Groups representing different roles or access levels within their application. For example, a "Data Access" Group can be defined. Within this Group, specific permissions related to data access are assigned, ensuring that only authorized users can view or modify sensitive data.

By giving staff privileges to end-users and associating them with relevant Groups, YaSaas provides a flexible and secure way to control access to valuable data. This approach ensures that each user, based on their role or responsibilities, has precisely defined permissions, aligning with the principle of least privilege. This technical foundation empowers entrepreneurs to tailor access controls according to their specific data product offerings.

---

## Features

* Authentication and authorization: User signup, login, logout, email verification, account management, social login support.
* Subscriptions: Set up plans and collect recurring payments with Stripe Subscriptions. 
* Emails
* Admin dashboard to edit frontend data
* Contact form 
* Light/dark mode
* And more!


---

## Tech stack 
### Front-end stack 
* React 18
* Typescript 4
* Material UI 5

### Backend stack 
* Django 4 
* Django Rest Framework 3 

### Third-party
* Stripe
* AWS Simple Email Service
* Google Analytics

---

### Prerequisites

Install the following prerequisites:

1. [Python 3.8, 3.9, 3.10 or 3.11](https://www.python.org/downloads/)
<br> This project uses **Django v4.2.4**. For Django to work, you must install a correct version of Python on your machine. More information [here](https://django.readthedocs.io/en/stable/faq/install.html).
2. [Node.js](https://nodejs.org/en/)
3. [Visual Studio Code](https://code.visualstudio.com/download) (Windows)
---

### Installation

#### Backend

#### 1. Create a virtual environment

From the **root** directory, run:

```bash
cd backend
```
```bash
python -m venv venv
# or
virtualenv -p python3.8 ~/.virtualenvs/YaSaas  #  Example using python3.8.
```

#### 2. Activate the virtual environment

From the **backend** directory, run:

On macOS or Linux:

```bash
source venv/bin/activate
# or 
source ~/.virtualenvs/YaSaas/bin/activate

```

On Windows:

```bash
venv\scripts\activate
```

#### 3. Install required backend dependencies

From the **backend** directory, run:

```bash
pip install -r requirements.txt
```

#### 4. Run migrations

From the **backend** directory, run:

```bash
python manage.py makemigrations
```
```bash
python manage.py migrate
```

#### 5. Create an admin user to access the Django Admin interface

From the **backend** directory, run:

```bash
python manage.py createsuperuser
```

When prompted, enter a username, email, and password.

#### Frontend

#### 1. Install required frontend dependencies

From the **root** directory, run:

```bash
cd frontend
```
```bash
npm install
```

### Run the application

To run the application, you need to have both the backend and the frontend up and running.

#### 1. Run backend

From the **backend** directory, run:

```bash
python manage.py runserver
```

#### 2. Run frontend

From the **frontend** directory, run:

```bash
npm start
```

#### 3. View the application

Go to http://localhost:3000/ to view the application.

### Add data to the application

Add data through Django Admin.

Go to http://127.0.0.1:8000/admin to access the Django Admin interface and sign in using the admin credentials.

### Customize the application

This section describes how to customize the application. 

#### Changing Section Titles and Subtitles 

#### 1. Products

To modify the title and subtitle of the **Products** section, make changes in the ```frontend/src/components/Products.tsx``` file.

#### 2. Services

To modify the title and subtitle of the **Services** section, make changes in the ```frontend/src/components/Services.tsx``` file.

#### 3. Pricing

To modify the title and subtitle of the **Pricing** section, make changes in the ```frontend/src/components/Pricing.tsx``` file.

#### 4. About

To modify the title and subtitle of the **About** section, make changes in the ```frontend/src/components/About.tsx``` file.

#### 5. Contact

To modify the title and subtitle of the **Contact** section, make changes in the ```frontend/src/components/Contact.tsx``` file.

#### Changing Colors

To modify the colors in the application, make changes in the ```frontend/src/theme/palette.ts``` file.

#### Changing Fonts

To modify the fonts in the application, first, add a new font to the ```frontend/public/index.html``` file, and then make changes in the ```frontend/src/theme/theme.ts``` file.

#### Changing Logo

To modify the logo in the application, make changes in the ```frontend/src/layout/Header.tsx``` and ```frontend/src/layout/Sidebar.tsx``` files.

#### Changing Buttons in the Hero Section

To modify the two buttons in the Hero section, make changes in the ```frontend/src/components/HeroButtons.tsx``` file.


### Configurations 

1. Append to the virtual environment file you created above (either `~/.virtualenvs/YaSaas/bin/activate`, `venv/bin/activate`,  or `venv\scripts\activate`). Make sure to put your own Stripe and AWS keys and don't forget to re-activate the virtual environment once you are done.
```
# Django
export DJANGO_SECRET_KEY='YOUR-DJANGO-SECRET-KEY'

# Stripe
export STRIPE_PUBLISHABLE_KEY='YOUR-STRIPE-PUBLISHABLE-KEY'
export STRIPE_SECRET_KEY='YOUR-STRIPE-SECRET-KEY'
export STRIPE_ENDPOINT_SECRET='YOUR-STRIPE-ENDPOINT-SECRET'
export STRIPE_CUSTOMER_PORTAL_LINK=https://billing.stripe.com/p/login/test_YOUR-CUSTOMER-PORTAL-ID
export STRIPE_PRICING_TABLE_ID='YOUR-STRIPE-PRICING-TABLE-ID'

# AWS Email
export AWS_SES_ACCESS_KEY_ID='YOUR-SES-ACCESS-KEY'  # You can also use the AWS access key
export AWS_SES_SECRET_ACCESS_KEY='YOUR-SES-SECRET-ACCESS-KEY'  # You can also use the AWS Secret Key
```
   
2. As for the frontend, create a `.env` file to hold the env variables used by React in the frontend and put the following in it (put your Stripe keys). Save it on the frontend root folder (i.e. `frontend/.env`).
```
REACT_APP_BASE_URL=http://127.0.0.1:8000/
REACT_APP_REDIRECT_SIGNUP_URL=http://127.0.0.1:8000/accounts/signup
REACT_APP_DASHBOARD_URL=http://localhost:8000/
REACT_APP_SITE_URL=http://localhost:3000/
REACT_APP_PUBLISHABLE_KEY='YOUR-STRIPE-PUBLISHABLE-KEY'
REACT_APP_PRICING_TABLE_ID='YOUR-STRIPE-PRICING-TABLE-ID'
```
 
3. Update Google-Analytics references

   Update the following three files located in the frontend folder and put your Google Measurement ID in each of them.
```
# frontend/public/index.html
  <!-- Google tag (gtag.js) -->
  <script async src="https://www.googletagmanager.com/gtag/js?id=YOUR-GOOGLE-MEASUREMENT-ID"></script>
  <script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());

    gtag('config', 'YOUR-GOOGLE-MEASUREMENT-ID');

# src/App.tsx
ReactGA.initialize('YOUR-GOOGLE-ANALYTICS-MEASUREMENT-ID');

# src/index.tsx
ReactGA.initialize('YOUR-GOOGLE-ANALYTICS-MEASUREMENT-ID');
```
 
4. Customise Django Admin with Jazzmin
* Jazzmin spices up the "ugly" Django Admin styles. 
* Some configurations were already applied in YaSaas (see bottom of `backend/settings.py` file). 
* See [Django Jazzmin](https://django-jazzmin.readthedocs.io/) for further customisation.

5. Customising django-allauth
* django-allauth is an integrated set of Django applications addressing authentication, registration, account management as well as 3rd party (social) account authentication
* Already installed and working in YaSaas. 
* See [Django All-auth docs](https://docs.allauth.org/en/latest/account/configuration.html) for further customisation.

6. Styling the Django-allauth templates with django-auth-style
* All django-allauth rendered templates will automatically be overridden with styled alternatives.
* Already installed and working in YaSaas. 
* For further customisation see [Django-auth-style](https://github.com/girder/django-auth-style)

7. Update `backend/settings.py` to your liking.
```
# CUSTOM TITLES AND HEADERS
INDEX_TITLE = "Data Dynamo"
SITE_TITLE = "API Portal"
SITE_HEADER = "Data Dynamo API"
```
 
8. Update the title tag in `frontend/public/index.html` to your liking.
``` 
<title>Data Dynamo</title>
```

9. In the `frontend/public/` folder update the favicon.ico and logo.svg with your own ones.

```
# frontend/public/img/logo.svg
# frontend/public/favicon.ico
```

### Stripe Subscriptions Workflow (see video at the top)
1. User clicks on a place-holder pricing table in homepage
2. User gets redirected to a signup page to give email, username and password.
3. User gets redirected to another page holding Stripe's pricing table 
4. User selects a subscription plan 
5. User gets redirected to a Stripe checkout page
6. User pays - Stripe will send us a checkout event and our event handler will give staff status and grant Group permission to the user).
7. User gets redirected to Django admin interface already logged-in as staff and with Group permission to see his or her data. 
8. User's subscription ends - Stripe will send an event telling us the subscription is over and our handler will then revoke user's staff and group permissions.

_IMPORTANT_: The reason why there's place-holder pricing table in the homepage, and not the proper Stripe's pricing table in the homepage is to force the user to a signup page in order to get their user ID which Stripe pricing table script requires (in our case we use the ID from the newly registered user). If we don't do this the user will end up paying as anonymous and he or she will end up in some sort of limbo and YaSaas won't be able to grant staff or Group permissions to the user.  


### Stripe webhooks for local development

*  Install stripe client (linux)
```
cd ~/opt
wget https://github.com/stripe/stripe-cli/releases/download/v1.18.0/stripe_1.18.0_linux_x86_64.tar.gz 
tar -xvf stripe_1.18.0_linux_x86_64.tar.gz 
mv stripe /usr/local/bin
```
  
* In order to test the Stripe webhook we need to open up our computer to the external world to listen for Stripe events. In another terminal execute the following:
  
```    
  stripe listen --forward-to localhost:8000/webhook
  ``` 

* All the logic related to handling Stripe events is in the `backend/subscriptions/views.py` module. The most basic events are already being handled by YaSaas (like `checkout.session.completed` or `customer.subscription.deleted`). Please feel free to expand the if/else clauses to handle your specific use-cases (there are tons of events!).

### Structure your Stripe subscription plans around Django Groups and User models
This is the most crucial aspect for monetising your data using Django Admin. YaSaas leverages the Django Admin to provide access to end-users as staff members with Group privileges. That way you can group users based on how much data access you want to give them. For instance, a subscription named "Basic Plan" might give a user permission to view a single table. Whereas a subscription named "Premium Level" might give a user permission to view multiple tables.  

Things to consider:

* In Stripe lingo Pricing Tables are made up Products. Say, your Pricing Table "A" contains three products: "Basic Plan", "Advanced Plan" and "Premium Plan". 
* YaSaas gives end-users staff privileges otherwise they won't be able to access Django Admin. End-users will be able to enter the Django Admin interface but they will only be able to view whatever you give them permission to view.  
* __Make sure to name your Django User Groups exactly as your Stripe subscription plan's products__
* For instance, if you name the Product in your plan as "Basic Plan" then your User Group must be named "Basic Plan" too.  
* Review the following code to make sure you understand how Staff and Group permissions are granted to the user after he/she pays:

```
## Excerpt from backend/subscriptions/views.py
...
product_name = stripe.Product.retrieve(subscription.plan.product).name

# Add Group to user
logger.info(f'Adding {user.username} (user #{user.id}) to Group `{product_name}`')
user.groups.add(Group.objects.get(name=product_name))

# Add staff status to user
logger.info(f'Granting {user.username} (user #{user.id}) with staff status')
user.is_staff = True
user.save()
...

```


### Deployment

To deploy you could use Nginx, Gunicorn and Django in tandem. 


### TODO
* Expand more on the Stripe subscriptions topic.
* Expand deployment section.s
* Adding an email confirmation page
---


### Copyright and licences
Copyright © 2022 Bob's Programming Academy. MIT Licence.

Copyright © 2023 Roperi. MIT Licence.
