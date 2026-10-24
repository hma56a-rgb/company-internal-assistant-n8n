# Company Internal Assistant (n8n)

n8n workflow that answers employee questions from company documents over chat and email, in English. Sensitive topics are escalated to HR instead of answered by the model.

## Setup

1. Import `company-assistant.workflow.json` into n8n.
2. Add an OpenAI credential to the **Chat Model** node.
3. Put `.txt` documents in `~/.n8n-files/company-docs/` and set the path in the **Read Files** node.
4. Add company facts to `companyInfo` in the **Build Knowledge** node.
5. Execute the workflow and send `test-request.json` to `/webhook-test/company-assistant`.

## Email (optional)

Add IMAP and SMTP credentials, then enable **HR Mailbox**, **Reply Email** and **Notify HR**. Set `OWN_ADDRESS` and `ALLOWED_DOMAINS` in the **Prepare** node.

## Notes

- Escalation keywords are defined in the **Prepare** node.
- Keep confidential files out of the documents folder.
