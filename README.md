


#  hCaptcha Enterprise & How to Detect it by Using CapSolver

When integrating or bypassing CAPTCHA challenges in your automation workflows, it’s crucial to understand the different versions of hCaptcha you might encounter—Normal and Enterprise. Additionally, identifying whether a CAPTCHA is of the Enterprise type can significantly impact how you approach solving it. This guide will walk you through the differences between hCaptcha Normal and Enterprise, and how to detect hCaptcha Enterprise using the [CapSolver](https://www.capsolver.com/?utm_source=github&utm_medium=repo&utm_campaign=hcaptchaenterprise) extension.

## Overview: hCaptcha Normal vs. hCaptcha Enterprise

### hCaptcha Normal

**Features**:
- **Basic Protection**: Provides standard security challenges, requiring users to solve tasks such as image recognition (e.g., selecting traffic lights) or text-based puzzles.
- **Revenue Model**: Free to use with an optional revenue-sharing model, enabling website owners to earn from the traffic by monetizing the challenges.

### hCaptcha Enterprise

**Features**:
- **Advanced Security**: Utilizes sophisticated machine learning models to detect abusive behaviors with higher accuracy.
- **Customizability**: Allows customization of security policies and challenge types to meet specific security needs.
- **Detailed Analytics**: Provides comprehensive reporting and analytics tools, offering insights into CAPTCHA interactions.
- **API Access**: Offers API access for deeper integration and control over CAPTCHA behavior and reporting.

Understanding these differences is critical when deciding how to interact with or solve these challenges programmatically. The methods and tools you use may vary depending on whether you are dealing with hCaptcha Normal or Enterprise.

## How to Identify if hCaptcha is Enterprise Using CapSolver Extension

In certain scenarios, knowing whether the hCaptcha on a site is Enterprise is crucial. This can affect how you programmatically solve the CAPTCHA, as Enterprise versions may have additional layers of security.

### Prerequisites: Install the CapSolver Extension

Before proceeding, ensure you have the CapSolver extension installed on your browser:

- **Chrome**: Install the [Captcha Solver Auto Solve](https://chrome.google.com/webstore/detail/captcha-solver-auto-bypas/pgojnojmmhpofjgdmaebadhbocahppod) extension.
- **Github**: [CapSolver](https://github.com/capsolver/capsolver-browser-extension/releases)

### Steps to Detect hCaptcha Parameters

Follow these steps to detect whether the hCaptcha on a website is of the Enterprise type:

#### Step 1: Prepare Your Environment
1. **Open Developer Tools**:
   - Press `F12` to open the Developer Tools.
   - Alternatively, right-click on the webpage and select "Inspect".

2. **Navigate to the CapSolver Panel**:
   - Go to the **Capsolver Captcha Detector** tab within the Developer Tools. If this tab isn’t visible, ensure that the CapSolver extension is correctly installed.

   ![Capsolver Captcha Detector Panel](https://assets.capsolver.com/prod/images/post/2023-10-31/2115f05d-a7eb-40b6-9693-53baa45d39a9.png)

#### Step 2: Trigger the hCaptcha Challenge
1. **Visit the Target Website**:
   - Navigate to the website where you intend to trigger the hCaptcha challenge.

2. **Trigger the hCaptcha**:
   - Interact with the element on the webpage that initiates the CAPTCHA (e.g., clicking a button or submitting a form).

3. **Do Not Close the Developer Tools**:
   - Keep the Developer Tools open throughout this process to capture the necessary data.

#### Step 3: Analyze the Detected Parameters
1. **Check the CapSolver Panel**:
   - After triggering the CAPTCHA, review the information displayed in the CapSolver Captcha Detector tab.
   - Look for the parameter labeled `Enterprise`. If the value is set to `true`, then the hCaptcha on the site is classified as Enterprise.

   ![hCaptcha Enterprise Detection](https://assets.capsolver.com/prod/images/post/2024-06-03/86c02d82-3db3-4309-9305-e42fbf3eb550.png)

2. **Other Identifiable Parameters**:
   - **Website URL**: The URL of the page where the hCaptcha was triggered.
   - **Site Key**: The site-specific key that hCaptcha uses to link the CAPTCHA to the correct website.
   - **Enterprise Status**: Indicates if the hCaptcha is Enterprise or Normal.
   - **Rqdata Requirement**: Identifies if additional `rqdata` is required for solving the CAPTCHA.

Once these parameters are detected, CapSolver provides a JSON output detailing how you should structure your CAPTCHA-solving request. This JSON file will include all necessary parameters, such as `siteKey`, `rqdata`, and whether the CAPTCHA is Enterprise, ensuring your automation script can handle the CAPTCHA correctly.

### Example JSON Output

Here’s an example of how the JSON output might look when detected by CapSolver:

```json
{
  "websiteURL": "https://example.com",
  "siteKey": "6LcR_okUAAAAAPYrPe-HK_0RULO1aZM15ENyM-Mf",
  "enterprise": true,
  "rqdataRequired": true,
  "rqdata": "some_rqdata_value"
}
```

### Conclusion

Detecting whether a hCaptcha is Enterprise using the CapSolver extension is a straightforward process that can be integrated into your automation workflow. This detection not only helps in solving the CAPTCHA more effectively but also ensures that your approach is tailored to the specific security level of the CAPTCHA.

**Note**: Always use automation tools responsibly and in compliance with the website’s terms of service. Unauthorized or unethical use of CAPTCHA-solving services can lead to legal consequences.

For further assistance or to report issues, contact CapSolver at [support@capsolver.com](mailto:support@capsolver.com).
