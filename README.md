 **PROBLEM STATEMENT**
      The agency receives applications throughout the year but lacks visibility into monthly trends.
      Identifying the months with the highest and lowest application counts helps optimize staffing, marketing, and resource planning.

 **DATA**
      The original dataset contains a column where the **month is represented numerically** (e.g., `1` for January, `2` for February). The goal is to identify the 
      month with the highest and lowest number of applications.

 **PREPARE**
      1.EXTRACTED MONTH NAME
            - I created another worksheet and used an Excel formula to convert the numeric month into text 
            - =TEXT('raw data'!B2, "mmmm") 
            - In Excel, TEXT is a function used to convert a number or a date into a formatted text string using a specific format you define.
            - 'raw data'!B2 refers to B2 cell in raw data[given data sheet] worksheet. 
            - "mmmm"  Convert the date to its full month name [convert 1.1.2025 to january]

**ANALYSIS PROCESS**
     1.Calculated how many applications recieved in every month with the extracted data .
         - =COUNTIF('month extracted'!G:G,A2)
         -  COUNTIF is an Excel function that counts how many cells meet a certain condition.
         -  'month extracted'!G:G this specifies the range where Excel looks for the condition — in this case, entire column G on the sheet named "month extracted".
         -  A2 This is the criteria — Excel counts how many cells in column G exactly match the value in cell A2.If A2 contains January then It counts how many 
            january is present in the total G Column
     2.Calculated which month in a particular year recieved the highest and lowest data
         -  =INDEX(A2:A13, MATCH(MIN(B2:B13), B2:B13, 0)) for lowest number of application recieved by a month in a year.
         -  MIN(B2:B13) finds the minimum value from the column in the given range
         -  MATCH(MIN(B2:B13), B2:B13 ,0) Searches for that minimum value inside B2:B13 and returns the position (row number relative to the range) where the 
            minimum value is found.The 0 means it looks for an exact match.
         -  INDEX(A2:A13, ...) Returns the value from the range A2:A13 at the position found by MATCH.Essentially, it picks the value from A2:A13 that aligns with 
            the minimum value in B2:B13.
         -  The month which recieved **lowest** number of application in a year - **February**
         -  =INDEX(A2:A13, MATCH(MAX(B2:B13), B2:B13, 0)) for highest number of appplication recieved by a month in a year.
         -  It works similar to minimum formula.
         -  The  month which recieved **highest** number of application in a year - **July**
     
**Data-Driven Suggestions**

Based on the analysis of application counts by month, I observed that:

- 📈 **July** had the highest number of applications
- 📉 **February** had the lowest number of applications

Here are my recommendations for the agency:

### 1. **Enhance Support During High-Application Months**
- Allocate more staff or extend operational hours during peak months like **[Month]** to ensure timely processing and reduce backlog.
- Use automation tools (e.g., auto-responses or filtering) to manage large volumes efficiently.
- Analyze **what campaigns or events** might have caused the spike, and replicate successful strategies.

### 2. **Investigate Low-Application Months**
- Look into possible causes: Were there fewer marketing efforts, system downtime, or external factors like holidays?
- Consider surveying applicants to understand why interest was low.
- Reevaluate timing and messaging of recruitment drives or announcements.

### 3. **Run Targeted Campaigns in Low Months**
- Launch awareness or engagement campaigns specifically during slow months like **[Month]** to smooth out seasonal dips.
- Offer time-sensitive benefits (e.g., early-bird perks, application fee waivers) to encourage applications during that time.

### 4. **Plan Annual Operations Using This Insight**
- Use the insights to build a monthly forecast for next year.
- Inform budgeting, hiring cycles, and communication strategies using this data.
- Continuously update the dataset and repeat this analysis to track changes year over year.


