# Google Form: Roadmap — Vote & Submit (Fields + Setup)

This document provides the complete setup for the Google Form used to collect community votes and feature submissions for the CurationsLA roadmap.

## Form URL
[CurationsLA Roadmap — Vote & Submit](https://docs.google.com/forms/d/e/1FAIpQLSdT8YSJcY4EUxIGhy5H_U7jVnPMuct5_-VI488fgEtVizcbWg/viewform?usp=publish-editor)

## Recommended form settings
- **Require sign-in / collect email addresses**: Yes (to reduce spam and duplicate submissions)
- **Limit to 1 response per account**: Optional (recommended to reduce duplicates)
- **Allow multiple submissions**: No (recommended). If you want multiple votes, explain how to cast multiple votes.
- **Responses**: Link to a Google Sheet for automatic collection and tallying

## Form field list (in order)

### 1. Form title
**Title**: CurationsLA Roadmap — Vote & Submit

### 2. Form description
"Pick a feature to upvote from the dropdown, or use 'Submit a new idea' to propose something new. We collect email addresses to reduce spam."

### 3. Email collection
**(Auto) Collect email addresses**: ON (set in form's settings)

### 4. Single-choice / Dropdown (Required)
**Question**: "I want to upvote (choose one)"
**Options**:
- Ability for Curators (Subscribers) to upvote
- Curators can submit their business to feature on neighborhood pages
- Other (I will describe below)

*Note: Maintain manually or update periodically as new features are added to the roadmap.*

### 5. Paragraph (Optional)
**Question**: "Submit a new idea (if 'Other' or for a new submission)"

### 6. Short answer (Optional)
**Question**: "Why this matters (1–2 sentences)"

### 7. Short answer (Optional)
**Question**: "Related neighborhood / category (optional)"

### 8. Checkbox (Optional)
**Question**: "I am a:"
**Options**:
- Curator
- Business owner
- Community member
- Other

### 9. Paragraph (Optional)
**Question**: "Any additional notes"

### 10. Timestamp
*(Captured automatically by Google Forms)*

---

## Response sheet layout
When you link the form to a Google Sheet, the columns will be:

- **Column A**: Timestamp
- **Column B**: Email Address
- **Column C**: Upvote choice (dropdown answer)
- **Column D**: New idea text
- **Column E**: Why this matters
- **Column F**: Category / Neighborhood
- **Column G**: Role (I am a...)
- **Column H**: Additional notes

---

## Auto-tally script (Apps Script)

Open the linked response spreadsheet → **Extensions** → **Apps Script** → create a new script file and paste this snippet.

This script tallies the "Upvote choice" column (Column C by default) and writes counts to a "Tally" sheet.

```javascript
function tallyVotes() {
  const ss = SpreadsheetApp.getActiveSpreadsheet();
  const resp = ss.getSheetByName('Form Responses 1'); // adjust if your sheet name differs
  const tallySheetName = 'Tally';
  let tally = ss.getSheetByName(tallySheetName);
  if (!tally) tally = ss.insertSheet(tallySheetName);

  const values = resp.getRange(2, 3, resp.getLastRow() - 1, 1).getValues(); // Column C
  const counts = {};
  values.forEach(function(r) {
    const v = (r[0] || '').toString().trim();
    if (!v) return;
    counts[v] = (counts[v] || 0) + 1;
  });

  // Clear tally sheet and write results
  tally.clearContents();
  tally.getRange(1,1).setValue('Feature');
  tally.getRange(1,2).setValue('Votes');
  const rows = Object.keys(counts).map(function(k){ return [k, counts[k]]; });
  if (rows.length) {
    tally.getRange(2,1,rows.length,2).setValues(rows);
    // Optional: sort by votes descending
    tally.sort(2, false);
  }
}
```

### Automation options

**Option A: Time-driven trigger**
- In Apps Script, set up a time-driven trigger to run `tallyVotes()` every 1–6 hours
- This keeps the tally sheet updated automatically

**Option B: On form submit**
- Set up an on-form-submit trigger
- This updates the tally immediately after each submission

**Option C: Manual**
- Open the sheet and run `tallyVotes()` from the Apps Script editor whenever you want to update tallies
- Alternatively, use a Pivot Table for live counts

---

## Publishing tallies

### Option A: Publish to web
1. In the Google Sheet: **File** → **Publish to web**
2. Select the "Tally" sheet
3. Choose "Web page" format
4. Copy the published URL
5. Embed this link in `docs/index.md` or `ROADMAP.md`

### Option B: Manual updates
- Maintain a small "Top items" table in `ROADMAP.md`
- Update manually on a weekly basis based on the Tally sheet

---

## Security and anti-gaming suggestions

- **Collect email addresses** (already configured)
- **Optionally**: Require verification (e.g., check domain for known partners)
- **Monitor patterns**: Watch for suspicious activity like many votes from same email or same IP
- **Treat tallies as signals**: Use Google Form tallies as a prioritization signal, not an absolute mandate
- **Combine with GitHub Issues**: Cross-reference form votes with GitHub issue engagement

---

## Maintenance workflow

1. **Weekly review**: Check new form submissions
2. **Create issues**: For accepted ideas, create GitHub Issues using the roadmap template
3. **Update dropdown**: Add new features to the form dropdown as they're added to the roadmap
4. **Monitor tallies**: Review the Tally sheet to inform prioritization decisions
5. **Update roadmap**: Reflect changes in `ROADMAP.md` and `docs/index.md`

---

## Additional resources

For pre-populated CSV imports or custom embeddable upvote UI implementations, contact the CurationsLA team.
