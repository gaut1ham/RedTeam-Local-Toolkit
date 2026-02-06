# RedTeam-Local-Toolkit

RedTeam-Local-Toolkit 🔒⚡
A completely offline, self-contained offensive security suite for penetration testing and red team operations without external API dependencies.

https://img.shields.io/badge/Python-3.8%252B-blue.svg
https://img.shields.io/badge/License-MIT-yellow.svg
https://img.shields.io/badge/PRs-welcome-brightgreen.svg
https://img.shields.io/badge/No_External_APIs-100%2525-red.svg
https://img.shields.io/badge/Platform-Windows%2520%257C%2520Linux%2520%257C%2520macOS-lightgrey.svg

📦 What's Included
This toolkit provides four essential security tools that work completely offline:

1. 📧 Local Email Tracking System
Track email opens and clicks without any external services. Self-contained SMTP server with built-in tracking.

2. 🔐 Offline Breach Checker
Check passwords against known breaches using a local database. No API calls, no internet required.

3. 🌐 Self-Contained Network Scanner
Discover devices on your network using pure ARP scanning. No external lookups or services.

4. 📱 Mobile C2 Communication
Local WebSocket-based command and control server for mobile agent management.

🚀 Quick Start
bash
# Clone and install
git clone https://github.com/yourusername/Local-Only-Security-Toolkit.git
cd Local-Only-Security-Toolkit
pip install -r requirements.txt

# Run the toolkit
python main.py
🛠️ Usage Examples
Email Tracking
python
from email_tracker import TrackingSMTPServer
import asyncore

# Start local SMTP server on port 2525
server = TrackingSMTPServer(('localhost', 2525), None)
print("📧 SMTP server running on port 2525")
asyncore.loop()
Password Breach Check
python
from breach_checker import LocalBreachChecker

checker = LocalBreachChecker()
password = input("Enter password to check: ")

if checker.check_password(password):
    print("❌ Password found in breaches!")
else:
    print("✅ Password not in breach database")
Network Discovery
python
from network_scanner import LocalNetworkMapper

scanner = LocalNetworkMapper()
devices = scanner.scan_subnet("192.168.1.0/24")

print(f"Found {len(devices)} devices:")
for device in devices:
    print(f"  • {device['ip']} - {device['mac']}")
Mobile C2 Server
python
from c2_server import LocalC2Server

# Start WebSocket server
server = LocalC2Server()
server.start(port=8765)
