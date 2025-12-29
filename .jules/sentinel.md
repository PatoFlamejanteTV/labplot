## 2025-01-29 - [Critical] Plain text password storage in MQTTClient
**Vulnerability:** The MQTT password was being stored in plain text in the project file (XML).
**Learning:** This existed because the `MQTTClient::save` method wrote the password attribute directly to the XML stream.
**Prevention:** Avoid saving sensitive information in project files. If necessary, use a secure storage mechanism (e.g., KWallet, OS keychain). In this case, we simply stop saving the password.
