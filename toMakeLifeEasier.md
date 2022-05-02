# smtplib

If gmail, be sure to allow less secure app by going into settings.
```python
import smtplib

SENDER_EMAIL = username@example.domain
RECEIVER_EMAIL = anything@email.com

USERNAME = username
PASSWORD = password

connection = smtplib.SMTP('smtp.gmail.com')
connection.starttls()
connection.login(
	user=USERNAME,
	password=PASSWORD
)

connection.sendmail(
	from_addr=SENDER_EMAIL,
	to_addrs=RECEIVER_EMAIL,
	msg=f"Subject:Subject of your message\n\nActual message")

connection.close()
```

# twilio

```python
from twilio.rest import Client

ACCOUNT_SID = something
AUTH_TOKEN = somehting

TWILIO_NUMBER = +1 0123456789
RECEIVER_NUMBER = +91 0123456789

client = Client(ACCOUNT_SID, AUTH_TOKEN)
client.messages.create(
	body='Anything.',
	from_=TWILIO_NUMBER,
	to=RECEIVER_NUMBER)
```


