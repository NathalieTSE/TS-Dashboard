# Release Metrics Dashboard

A simple, client-side dashboard for visualizing product release metrics. No backend required - just HTML, CSS, and JavaScript!

## Features

- **Per-release overview**: Deep dive into individual release metrics
- **Comparative analysis**: Compare the last 10 releases side-by-side
- **Dynamic data loading**: Automatically reads from CSV file
- **Export functionality**: Export dashboards as PNG or PDF
- **Responsive design**: Works on desktop and mobile devices

### Updating Data

To add new release data:

1. **Edit the CSV file** (`Release Metrics - release (summarised).csv`) directly on GitHub:
   - Click on the CSV file in your repository
   - Click the pencil icon (✏️) to edit
   - Add your new release row following the existing format
   - Click **Commit changes**

2. **Or update locally and push**:
   ```bash
   # Edit the CSV file locally
   git add "Release Metrics - release (summarised).csv"
   git commit -m "Add release 2025.4.3.0 metrics"
   git push
   ```

3. **Refresh the dashboard** - it will automatically load the new data!

## CSV Format

The CSV file should have the following columns (in order):

- `Release` - Release version (e.g., "2025.4.1.0")
- `Date` - Release date (format: M/D/YYYY)
- `MPR` - Major Product Release (TRUE/FALSE)
- `LXP bugs solved` - Number of LXP bugs solved
- `LXP ZD tickets solved` - Number of LXP Zendesk tickets solved
- `LXP SF associations solved` - Number of LXP Salesforce associations solved
- `ACM bugs solved` - Number of ACM bugs solved
- `ACM ZD tickets solved` - Number of ACM Zendesk tickets solved
- `ACM SF associations solved` - Number of ACM Salesforce associations solved
- `Total bugs solved` - Total bugs solved (sum of LXP + ACM)
- `Total ZD tickets solved` - Total Zendesk tickets solved
- `Total SF associations solved` - Total Salesforce associations solved
- `Bugs opened` - Total bugs opened
- `ZD tickets opened` - Total Zendesk tickets opened
- `SF associations opened` - Total Salesforce associations opened
- `Net new bugs created` - Net new bugs (opened - solved)
- `P2 within SLA` - P2 tickets resolved within SLA
- `P2 over SLA` - P2 tickets resolved over SLA
- `P3 within SLA` - P3 tickets resolved within SLA
- `P3 over SLA` - P3 tickets resolved over SLA
- `Trend Summary` - Text analysis of the release (optional, multi-line supported)
- `Product Team` - Breakdown of teams affected (optional, format: "Team1:10, Team2:5, ...")
- `Hotfixes` - Number of hotfixes after the release (optional)

## Notes

- The dashboard automatically loads data from the CSV file on page load
- No server-side processing required - everything runs in the browser
- Data is read-only in the browser - to update, edit the CSV file on GitHub
