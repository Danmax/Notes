# Board Meeting Manager

A single-file browser app for preparing agendas, recording attendance, tracking motions and votes, assigning action items, and generating printable minutes.

The app can be used by HOAs, nonprofit boards, churches, civic boards, school boards, and other organizations. Organization-specific setup is saved locally or exported as a reusable board profile.

## Features

- Organization setup with templates for:
  - HOA / Community Association
  - Nonprofit
  - Church
  - School / Civic Board
  - Custom
- Configurable member / seat types and officer roles.
- Reusable board profiles with local save/load and JSON import/export.
- Attendance tracking for present, absent, late arrival, and departed early.
- Agenda builder with recurring items, New Business, and printable agenda output.
- Discussion notes, motions, movers, seconders, vote counts, and individual votes.
- Unanimous vote shortcut and non-unanimous per-person vote recording.
- Action item tracking with assignees and due dates.
- Printable minutes with high-contrast styling for PDF or paper output.

## How To Use

Open `index.html` in a browser.

All meeting data is stored in the browser's local storage unless you export it. Use the top-right Save / Load buttons to export or import a full meeting JSON file.

## Organization Profiles

In Setup, choose an Organization Type or select Custom. You can define:

- Organization name
- Meeting location and address
- Manager / administrator
- Member / seat types
- Officer roles
- Board roster

Use Save Board Profile to store recurring setup locally. Use Export Profile to save a reusable JSON profile that can be imported later or shared.

## Printing

- Print Agenda creates a formal agenda with meeting details, agenda items, and a New Business section.
- Generate Minutes compiles the current meeting record into an editable minutes preview.
- Print / Export PDF opens the browser print dialog for the generated minutes.

Print margins are set to `0.6in` for letter paper.

## Development

This is a static app with no build step. The primary file is:

- `index.html`

For a quick syntax check of the embedded script:

```bash
node -e "const fs=require('fs'); const html=fs.readFileSync('index.html','utf8'); const script=html.match(/<script>([\\s\\S]*)<\\/script>/)[1]; new Function(script); console.log('script syntax ok');"
```
