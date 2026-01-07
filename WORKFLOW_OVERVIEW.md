# Workflow Logic Overview

## Trigger
Hourly Cron trigger checks file status every 60 minutes.

## Step 1: Dropbox – Get File Metadata
Retrieves:
- Server modified timestamp
- Content hash

## Step 2: Change Detection
Compares current metadata with last stored values.
- No change → workflow exits
- Change detected → continue

## Step 3: Archive Creation
The KeePass database is compressed into a timestamped archive: pass_kdbx_DDMMYYYY_HH-mm.zip

## Step 4: Google Drive Upload
Archive is uploaded to a dedicated backup folder.

## Step 5: Retention Management
- List all files in the backup folder
- If count > 10:
  - Sort by creation date
  - Delete oldest files

## Design Principles
- Idempotent execution
- Minimal API calls
- No plaintext secrets
- Fail-safe behavior
