Execute the S360-Daily-ETA-Reminder skill to check for missing ETAs in S360 action items. 

CONFIGURATION:
- Target Service: CPS Customer Engagement FastTrack Subscriptions
- S360 Dashboard URL: https://vnext.s360.msftcloudes.com/blades/security?global=4:bc8ba3e6-226e-40e1-8e3d-766508baa641&blade=KPI:6a1e4c72-c344-49f1-af2d-f2c20827ad2d~SLA:3~AssignedTo:All~Forums:All~waves:All~Tab:Summary~_loc:Security&peopleBasedNodes=radhikad_team;v-tsukkala_team;rahay_team
- AUTO_SEND: false (Draft emails to Outlook for review)

WORKFLOW:
1. Navigate to S360 security dashboard and extract all action items
2. Identify items where ETA is blank or says "Set ETA"
3. For each missing-ETA item:
   - Find accountable owner's email address
   - Find their manager's email address
   - Draft professional reminder email to owner with manager CC
4. Create email drafts in Outlook Drafts folder for manual review
5. Send a summary Teams message to the user listing all drafted emails

EMAIL TEMPLATE REQUIREMENTS:
- Include warning header (⚠️ MISSING ETA - ACTION REQUIRED)
- Detailed action item table
- Context on why ETAs matter
- Direct S360 dashboard link with step-by-step instructions
- 24-hour completion deadline
- NO Timeline Context section
- NO "Best regards" section
- SIGNATURE: "Thanks, Pravin Kumar"

OUTPUT:
- If ETAs are missing: Create Outlook drafts with detailed reminder emails (ready to send)
- If no missing ETAs: Report "All action items have ETAs set ✓"
- Always provide: Count of items checked, count with missing ETAs, status of each email drafted
