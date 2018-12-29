# plant-sensor
Scripts to monitor and alert plant health

#get libraries
import RPi.GPIO as GPIO
import smtplib
import time
import os

#get config from the environment
email_uname = os.environ.get('PLANT_NAME')
email_pswd = os.environ.get('PLANT_PASS')
email_host = os.environ.get('EMAIL_HOST')
email_port = 25 #standard email port. change it if your provider uses something different

smtp_sender = email_uname
smtp_receivers = os.environ.get('RECEIVERS')

#message parts

#needs water message
message_you_killing_me_yo = """From: Thirsty Plant <email_uname>
To: You <smtp_receivers>
Subject: I'm thirsty yo!

Aye, I'm thirsty yo! You gonna water me or nah?
"""

#water good message
message_I_am_good = """From: Thirsty Plant <email_uname>
To: You <smtp_receivers>
Subject: I'm good yo!

Thanks for the drink. I'm good now homeie!
"""
