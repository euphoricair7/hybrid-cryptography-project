# hybrid-cryptography-project


**Hybrid Cryptographic System for Secure RFID Data Transmission**


**Technical Highlights**

* **RFID Tag Data Collection:**  Leverages an Arduino-based scanner to capture unique identifiers (UIDs) from RFID tags.
* **Hybrid Cryptography:**  Combines the strengths of two encryption methods: AES for data confidentiality and ECDH for secure key exchange.
* **End-to-End Security with mTLS:**  Utilizes mutual TLS (mTLS) to establish trust between devices and safeguard data throughout its journey.
* **Cross-Device Communication:**  Facilitates the secure transfer of data from the RFID scanner to a server and ultimately to a client device.

**Workflow**

1. **RFID UID Collection:**  An Arduino equipped with an RFID sensor is used to collect unique identifiers from RFID tags. A Python script (rfid_from_scanner.py) then transmits this data to a server.
2. **Server-Side Encryption:**  The server safeguards the data before transmission by encrypting it using the AES algorithm. To generate a secure encryption key, the system relies on ECDH.
3. **Secure Data Transmission with mTLS:**  A secure connection, established using mutual TLS (mTLS), is created between the server and the client device. This ensures that only authorized devices can participate in the communication.
4. **Client-Side Decryption:**  The encrypted data is sent to the client device, where it's decrypted to retrieve the original UID, enabling secure access.


**Getting Started**

**Prerequisites:**

* An Arduino board with an RFID sensor
* Two devices (laptops or similar) to act as the server and client
* Python 3.x installed on both devices
* Required Python libraries: cryptography, PyNaCl

**Steps:**

1. **Set Up the RFID Scanner:**  Upload the rfid_reader.ino sketch to your Arduino and connect the RFID scanner according to the provided circuit diagram.
2. **Install Dependencies:**  Using pip, install the necessary Python libraries (cryptography and pynacl) on both the server and client devices.
3. **Run the Server:**  Execute the tls_server.py script on the designated server device.
4. **Run the Client:**  On the client device, execute the tls_client.py script.
5. **Start the RFID Data Transmission:**  Run the rfid_from_scanner.py script to initiate sending RFID data to the server.

**License**

This project is covered under the MIT License. Refer to the LICENSE file for more details.
