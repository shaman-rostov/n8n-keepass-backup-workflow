# Security Considerations

- The KeePass database remains encrypted at all times
- No passwords or keys are logged
- No file content inspection is performed
- OAuth credentials are stored securely in n8n
- Backups are stored encrypted (KeePass native encryption)

This workflow never decrypts or processes sensitive data.
