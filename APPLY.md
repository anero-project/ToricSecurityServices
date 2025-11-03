# 📝 Secure LhCorp. License Application Process

This document details the mandatory procedure for all anonymous services (Tor/I2P) seeking the **Licensed Hidden Corporation (LhCorp.)** status from **Toric Security Services (TSS)**. The process relies on verifiable **PGP signatures** to establish identity and message integrity, which is essential for establishing trust in the anonymous services sector.

---

## 1. 🔑 Obtain/Generate Your PGP Key

You **must** use a valid PGP key pair (**Public Key** / **Private Key**) to submit an application. This key will be used by TSS to verify your identity and the integrity of your application message.

* **Public Key Submission:** Your public key must be included in the application file (Section 2.A).
* **Key Security:** For greater trust, consider using a key that has existed for a reasonable period. Ensure the key you use has a valid Revocation Certificate stored securely.

---

## 2. 📄 Create the Application File

You will create a new Markdown file (`.md`) in the `applications/pending/` directory of the fork you made of this repository.

> **Naming Convention:** The file name should be your service's official name, converted to **lowercase**, with **hyphens** replacing spaces (e.g., `ServiceName.md`).

### A. Required Application Content

The file must contain the following information, clearly separated by headers:

1.  **Service Name:** The full name of your service (e.g., *[Service Name]*).
2.  **Network Address:** The current **`.onion`** or **`.i2p`** address for your service.
3.  **Source Code** Upload a zip file of your service's source code to some hosting service and make it private so the public cannot view it. Afterwards paste the private download link in this section (This application will be encrypted to keep your source code private)
4.  **Service Description:** A concise, detailed description of your service's purpose, functionality, and why it benefits the anonymous community.
5.  **PGP Public Key:** The full, **Fingerprint** of the public key you will use to encrypt the application.
6.  **Operator Contact:** A secure, anonymous contact method (e.g., encrypted email, jabber ID, or other hidden service contact address).
7.  **Attestation of Compliance:** A statement confirming that your service complies with the ethical and operational standards of Toric Security Services (TSS).

### B. The PGP Signing Block

The entire content of the application file must be **encrypted** to **The Toric Security Services** Public Key found in the ToricSecurityServices repository named "ToricPublic.key", using your **Private Key**. This message proves the message originated from the certified owner of the PGP Key, and ensures your source code remains private.

**Steps to Create the Encrypted Application:**

1.  Write the entire application content (Sections 1-6 above).
2.  Use your PGP software (e.g., GPG) to **encrypt** the application.
3.  Paste the resulting signed block (starting with `-----BEGIN PGP SIGNED MESSAGE-----` and ending with `-----END PGP SIGNATURE-----`) at the bottom of your application file. 

---

## 3. 📤 Submit the Application

1.  **Commit and Push:** Commit the new application file (`applications/pending/[service-name].md`) to your forked repository.
2.  **Create Pull Request (PR):** Open a Pull Request on the **Toric Security Services** main repository, targeting the `main` branch. The PR title **must** be: `[LhCorp Application] [Your Service Name]`.
3.  **Verification:** The Toric Security Services Authority will:
    * Verify the **PGP signature** against the Public Key provided.
    * Verify the service is live and accessible on the network address provided.
    * Perform due diligence on the service's reported operations, and run an audit on your source code.

### **Post-Approval:**

If approved:

* Your application file will be moved from `applications/pending/` to the official `licenses/issued/` directory.
* The TSS Authority will contact the service operator via the provided secure contact method to issue the official license package and instructions for displaying the license.

---

### **⚠️ Security Warning**

* **Never** share your PGP **Private Key**.
* Any application that fails PGP signature verification will be immediately rejected.
* Do not attempt to apply for a license using a key pair that does not belong to you or the service operator.
