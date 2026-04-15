
# 3.3 Data Protection Strategies

Data must be protected in all three states using specific cryptographic and administrative methods.

## States of Data
* **Data-at-Rest:** Data stored on a device (e.g., HDD, Cloud bucket). Protected by Full Disk Encryption (FDE).
* **Data-in-Transit:** Data moving across a network. Protected by TLS or IPsec.
* **Data-in-Use:** Data currently being processed in RAM. Protected by memory encryption/secure enclaves.

## Protection Methods
* **Encryption:** Converting data into ciphertext to maintain confidentiality.
* **Hashing:** Ensuring data integrity by creating a unique fixed-length string (e.g., SHA-256).
* **Masking:** Hiding specific data (e.g., showing only the last 4 digits of a credit card).
* **DLP (Data Loss Prevention):** Tools that identify and block the unauthorized transfer of sensitive data.
