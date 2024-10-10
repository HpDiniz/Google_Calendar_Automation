
# Google Calendar Automation - README

## Setup Instructions

1. **Create Google Account Credential in UiPath Orchestrator**
   - Set up your Google account credential in the UiPath Orchestrator before running the automation.

2. **Configure Input, Output, and Temp Directories**
   - In the RPA's arguments, define the paths for the input, output, and temporary directories.

3. **Ensure Chrome and UiPath Extension**
   - Make sure you have Chrome installed and the UiPath extension enabled, with permission to run in incognito mode.

4. **Run the Automation**
   - Once all configurations are set, execute the automation via UiPath.

## Assumptions & Limitations

- **Google Login Challenges**: The automation may encounter issues with CAPTCHA or phone verification during Google login. To avoid this:
  - Perform a successful manual login first, complete any security checks (CAPTCHA, phone verification, etc.).
  - This increases the chances of seamless logins during the automation.

## Approach and Design Decisions

- **Optimized Calendar View**: The approach first checks for days with events, skipping unnecessary days to optimize time. This avoids the inefficiency of scanning all days.
  
- **Direct URL Access**: After identifying event days, the RPA accesses each day directly via URL, reducing on-screen interactions and improving reliability by minimizing clicks.

- **Regular Expressions for Data Extraction**: The use of HTML regex expressions allows fast and efficient data scraping without relying on perfect selectors.

- **Execution Summary**: At the end of the process, a template (from the input folder) is copied and used to generate a polished execution summary, including visual charts for easy understanding of daily event distribution.
