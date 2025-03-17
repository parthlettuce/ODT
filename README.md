import network
import time
from machine import Pin

# Define your Wi-Fi credentials
ssid = 'wifi id'      # Replace with your Wi-Fi SSID
password = 'password'  # Replace with your Wi-Fi password

led = Pin(2, Pin.OUT)
led.value(0)

# Create a station interface object
wifi = network.WLAN(network.STA_IF)

# Activate the interface
wifi.active(True)

# Connect to the Wi-Fi network
wifi.connect(ssid, password)

# Wait for connection
print('Connecting to WiFi...')
while not wifi.isconnected():
    pass

# Print network details once connected
print('Connected to WiFi!')
print('IP Address:', wifi.ifconfig()[0])
led.value(1)

# Write your code here :-)
