# CashCow

This project is a Python-based payment application similar to PhonePe. It allows users to register, save bank details, authorize transactions, and manage saved contacts for quick payments. 


## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [ER Diagram](#er-diagram)
- [Usage](#usage)
- [Database Schema](#database-schema)

## Overview

The application is designed to allow users to:

Register and store their credentials securely.
Save multiple bank accounts.
Initiate transactions to other users.
Save frequently-used contacts (other users) for quick payments.
Securely verify bank details before authorizing transactions.

## Features

User Management: Users can create an account by providing credentials such as name, email, and password. A user can save their bank details, including account numbers and routing numbers.

Bank Account Storage: Users can associate multiple bank accounts with their profile and verify them securely.

Transaction Handling: Users can authorize transactions between their accounts and saved users.

Saved Users: Users can store contacts for frequently sent payments to streamline the payment process.

Security: All transactions require password verification, and the user's sensitive details are handled securely.

## ER Diagram

The ER diagram represents the structure of the application's database. It includes the following key entities:

Credentials/User: Stores user credentials like email, password, name, and an optional phone number. Each user has a one-to-many relationship with their bank details.

UserBankDetails: Stores the user’s bank information, such as account numbers, routing numbers, and optional bank names. A user can have between 1 and 5 bank accounts.

Transaction: Records details of each transaction, including sender and receiver account numbers, routing numbers, and transaction dates. The transaction is linked to the user's bank details and authorized through a verification process.

SavedUsers: Allows users to store information about other users they frequently send payments to, including their account and routing numbers.

Bank: Stores bank-related information and ensures proper routing of transactions by verifying account details through the BankAuth entity.

## Usage

Once the app is up and running, users can:

Register: Create an account with their name, email, and password.
Login: Securely log in with their credentials.
Add Bank Details: Users can store multiple bank accounts.
Make Payments: Authorize transactions to other users, either manually or through saved contacts.
View Transaction History: Review transaction history and balances.

## Database Schema

Credentials/User: The table contains fields for UserID, Email, Password, PhoneNumber (Optional), and ConfirmPassword.

UserBankDetails: The table stores each user's UserAccountNumber, UserRoutingNumber, and Balance. Each user can have multiple bank accounts (1 to 5).

Transaction: This table contains the transaction details, including TID, SenderAccNo, ReceiverAccNo, and the corresponding routing numbers.

SavedUsers: A reference table to store contacts that a user frequently sends payments to. This includes SUserID, SUserAccountNumber, and SUserRoutingNumber.

BankAuth: Handles the verification process for transactions using the sender's and receiver's bank details.

