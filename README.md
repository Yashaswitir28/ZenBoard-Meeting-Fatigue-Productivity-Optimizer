# ZenBoard-Meeting-Fatigue-Productivity-Optimizer

🧘 ZenBoard: Calendar Fatigue and Focus Analyzer
ZenBoard is a data-driven dashboard that visualizes personal meeting patterns, highlights focus gaps, and flags burnout risk. Built using Outlook calendar exports, Excel-based data wrangling, and Tableau visualizations.

📊 Features
ZenBoard extracts and computes actionable calendar metrics, including:

1. Daily Fatigue Score (0–10 scale)
2. Focus Duration (mins)
3. Back-to-Back Meeting Count
4. Late-Hour Meeting Flag
5. Meeting Attendees Count
6. % of Day Utilized (9 AM–6 PM)
7. Meeting Gaps & DND Blocks
8. Recurring Meeting Detection
9. Long Duration Meeting Count
10. First & Last Meeting Time
11. Daily Meeting Count

🛠 Tech Stack

| Component             | Technology                                  |
|-----------------------|---------------------------------------------|
| Data Source           | Microsoft Outlook                           |
| Processing            | Excel Power Query                           |
| Feature Engineering   | Excel formulas + Tableau Calculated Fields  |
| Visualization         | Tableau                                     |

🧰 Workflow
🔹 Step 1: Data Collection
1. Export calendar from Microsoft Outlook as .csv.
2. Ensure fields include: Start Time, End Time, Subject, Attendees, IsRecurring, etc.

🔹 Step 2: Data Cleaning (Excel Power Query)
1. Remove nulls, normalize time formats, drop unnecessary columns.
2. Convert datetime fields to Excel-compatible timestamps.

🔹 Step 3: Data Wrangling & Feature Engineering
3. Using Excel & Tableau Calculated Fields:

Field	Description
1. DND Start/End Time	User-defined deep work blocks
2. DND Duration	Time between DND start and end
3. DND Label	Focus category based on duration
4. FirstMeetingTime	Earliest meeting of the day
5. LastMeetingTime	Latest meeting of the day
6. MeetingDuration	Difference between start & end
7. RecurringFlag	Based on IsRecurring column
8. AttendeesCount	Parsed from attendee list
9. %DayUtilized	Total meeting time / 540 minutes
10. MeetingGap	Time between consecutive meetings
11. BackToBackFlag	Gap < 10 mins between meetings
12. LateHourFlag	Meetings post 5:00 PM
13. LongMeetingCount	Meetings > 60 mins
14. FatigueScore	Weighted index of total fatigue load
15. FocusTimeMinutes	Time not occupied by meetings
16. DailyMeetingCount	Count of meetings per day

🔹 Step 4: Data Storage
All processed data stored in .xlsx file, refreshed manually (weekly/monthly).

🔹 Step 5: Tableau Visualization
1. Import final Excel sheet into Tableau.
2. Create calculated fields, dashboards, filters, and interactivity.

Dashboards include:

1. Daily calendar views (color-coded by subject)
2. Fatigue & Focus score donuts
3. Bar graphs (DND duration, meeting counts)
4. Heatmaps for meeting patterns by day/hour

📈 Output:
Visual output includes:
1. Donut charts for focus category
2. Heatmaps of meeting load by weekday
3. Fatigue component breakdown (back-to-back, late, long)
4. Dynamic filters for individual analysis

🚀 Future Enhancements (WIP)
1. Automate refresh pipeline (Power Automate or Python)
2. Real-time integration via Google/Outlook Calendar APIs
3. Slack/Teams fatigue alerts
4. AI-based rescheduling suggestions

📂 Repository Structure

📁 /ZenBoard
├── 📄 README.md

├── 📄 zenboard_template.xlsx   # Processed sample dataset

├── 📄 fields_information.md      # Field definitions & formulas

├── zenboard_dashboard.twb  # Tableau workbook file

📌 Requirements
Excel 2016+
Tableau Desktop (2022+)
Outlook Calendar Export (.csv)

🧪 Reproducing the Project
1. Export your Outlook calendar for a date range as .csv
2. Open the zenboard_template.xlsx and paste the raw data in the RawData sheet.
3. Use Excel formulas (or Power Query) to generate computed fields.
4. Open zenboard_dashboard.twb in Tableau Desktop.
5. Connect to the .xlsx file as your data source.
6. Explore and analyze your own meeting fatigue and focus insights.

🧘 About the Project
ZenBoard is a solo productivity analytics experiment aimed at making time management more mindful using data.


