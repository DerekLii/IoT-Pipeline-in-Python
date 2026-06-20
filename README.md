📡 IoT Pipeline: MQTT → MongoDB (WSL + Windows Setup)

This project demonstrates a simple IoT data pipeline where sensor data is published via MQTT and stored in MongoDB using Python. The system runs across WSL (Ubuntu) and Windows (Compass).

MQTT Publisher  →  MQTT Broker (localhost:1883)
                         ↓
                Python Subscriber (WSL)
                         ↓
                MongoDB (WSL)
                         ↓
        MongoDB Compass (Windows)

WSL (Ubuntu)
Python 3.10+
MongoDB Community Server

pip packages:

pip install pymongo paho-mqtt
Windows
MongoDB Compass

MongoDB Setup (WSL)
1. Create data directory
mkdir -p ./data/db
2. Start MongoDB
mongod --dbpath ./data/db --bind_ip_all

mongodb://172.xx.xx.xx:27017

Find IP with:

hostname -I

Run these separately in their own WSL terminals:
1. mongod --dbpath ./data/db --bind_ip_all
2. uv run publisher.py
3. uv run mongoDB.py
