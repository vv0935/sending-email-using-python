# sending-email-using-python
Python Automate sending an email using the Gmail SMTP server
from email.message import EmailMessage
import ssl
import smtplib
sender='vaishudummy334@gmail.com'
password='urruqjvnlwrwvgkv'
receiver='veeramallavaishnavi@gmail.com'
subject='check out my new mail'
body="""
 Hi this is automated mail generated using python. Using youtube I created this
mail
"""

em=EmailMessage()
em['From']=sender
em['To']=receiver
em['Subject']=subject
em.set_content(body)

context=ssl.create_default_context()
with smtplib.SMTP_SSL('smtp.gmail.com',context=context) as smtp:
    smtp.login(sender,password)
    smtp.sendmail(sender,receiver,em.as_string())
