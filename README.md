# Data-Security-and-Privacy-Project
# Team Members
Pingili Gayathri
Sai Sharan Eruventy
Naga Sudha Pavani Tirumalasetty
GitHub Repository
Project Repository

Introduction
In recent years, Database-as-a-Service (DBaaS) has gained popularity as a cloud computing model, offering scalability and ease of use. However, security and privacy concerns remain a challenge. This project aims to develop a secure healthcare database system that ensures data confidentiality, access control, and query integrity. The system employs encryption techniques, user authentication mechanisms, and secure query verification.

System Design
Architecture Overview
The system comprises three main components:

Client-Side (User Interface):

A web-based UI allows users to log in and interact with the database.
Users belong to two groups:
Group H (Healthcare Providers): Full access to all records.
Group R (Researchers): Restricted access; personal identifiers are anonymized.
Sensitive fields (e.g., gender, age) are encrypted and decrypted only on the client-side.
Server-Side (Database & Logic):

Built using Flask (Python).
Utilizes MySQL for data storage.
Implements secure authentication, access control, and query validation.
Security Features:

User Authentication: Secure password hashing (bcrypt/Argon2).
Access Control: Role-based access control (RBAC).
Data Confidentiality: AES encryption for sensitive fields.
Query Integrity: Uses HMAC and Merkle Trees for tamper detection.
Implementation of Security Features
1. User Authentication
Passwords are securely hashed before storage.
Login authentication compares hashed passwords.
2. Access Control
Group H: Can view and modify all data.
Group R: Cannot access personal identifiers (e.g., first and last names).
3. Query Integrity Protection
HMAC: Ensures individual records have not been altered.
Merkle Trees: Guarantees completeness of query results.
4. Data Confidentiality
AES encryption secures sensitive fields (e.g., gender, age).
Decryption occurs only on the client-side for authorized users.
5. Extra Feature: Order-Preserving Encryption (OPE)
OPE allows range queries on encrypted numerical data (e.g., weight).
Enables secure queries like SELECT * WHERE weight BETWEEN X AND Y.
Contributions and Commit History
Team Member	Role	Contributions
Gayathri Pingili	Frontend Developer	Developed UI components, login/dashboard pages
Sai Sharan Eruventy	Backend Developer	Implemented Flask API, authentication, access control
Naga Sudha Pavani Tirumalasetty	Security Specialist	Implemented AES encryption, HMAC, and Merkle Tree security
Limitations
Performance Overhead: Encryption/decryption may impact speed.
Query Complexity: Limited support for complex SQL joins on encrypted data.
Cloud Trust Model: Assumes a semi-trusted cloud environment.
Screenshots
