# Automated KeePass Backup & Rotation (n8n)

Fully automated, secure backup and file-rotation system for an encrypted KeePass database stored in Dropbox, with redundant storage in Google Drive.

## Problem
Clients relying solely on Dropbox sync risk losing their primary KeePass database due to accidental deletion, corruption, or sync conflicts. Manual backups are inconsistent and unstructured.

## Solution
This n8n workflow continuously monitors a KeePass database file in Dropbox and automatically:
- Detects file changes
- Creates timestamped compressed backups
- Uploads them to Google Drive
- Enforces retention rules (automatic cleanup)

## Key Features
- Hourly monitoring
- Change detection via metadata hash & timestamp
- Secure compressed backups
- Cross-cloud redundancy (Dropbox → Google Drive)
- Automatic retention (max 10 backups)

## Tech Stack
- n8n (workflow automation)
- Dropbox API
- Google Drive API
- KeePass (.kdbx encrypted database)
- JavaScript (n8n Code node)

## Files
- `/workflow` – n8n workflow export (JSON)
- `/docs` – setup, security, retention logic
- `/samples` – example metadata and retention data
- `/CASE_STUDY.md` – business case & results

## Use Case
Ideal for:
- Security-conscious individuals
- IT admins
- Freelancers and consultants
- Small businesses storing critical credentials

