# Weather Company Snapshot 
## Unmanaged Component Guide

Weather Company Snapshot allows you to see weather conditions associated with a case and save them for future use. For example, when a customer reports that their car was damaged by hail, the customer service representative can save a snapshot of the current weather information and add it to the case. When the claims analyst reviews the case, they can see the weather information to verify that the damage could have been caused by hail.

Snapshot adds the following weather data to case pages:
- Current weather conditions (temperature, chance of precipitation, and wind speed)
- Weather conditions for the past 24 hours

You can download the Snapshot unmanaged component from GitHub. To set it up, add the API key from your paid data package subscription from The Weather Company and customize it per your needs. Alternatively, you can use the code as a sample to understand how the API works and then build your own standalone app.

Tip: The component is shipped with mock data so you can try it out before you obtain an API key.

### Obtaining an API Key

By purchasing a data package and access key from The Weather Company, you can include any of the following data streams into Snapshot:
- Weather Company Data for Salesforce – Core: Daily forecasts for the next 10 days, hourly forecasts for the next 48 hours, and historical weather conditions for the past 24 hours
- Weather Company Data for Salesforce – Enhanced: More precise and frequent weather observations, precipitation forecast, 15-minute forecast, and Nowcast
- Weather Company Data for Salesforce – Severe Weather: Information on conditions including hail, lightning, and storms, and a power disruption index

To purchase a Weather Company data package, visit [https://business.weather.com/product-categories/the-weather-company-data-solutions].

## Installing and Configuring the Component
### System Requirements
Snapshot is supported for Salesforce editions that include case management. Lightning Experience must be enabled. Snapshot is not supported in Salesforce Classic. Snapshot is supported on all browsers that are supported for Lightning Experience. For details, see Supported Browsers for Lightning Experience.
```markdown

## Setting Up the Component
Prerequisite: Prior to installation, ensure Lightning Experience is enabled (see Enable Lightning Experience). 
To set up the component:
1. Get the component from [GitHub] (https://github.com/TheWeatherCompany/Salesforce-Snapshot) and deploy it to Salesforce.
2. In Salesforce, create a CSP Trusted Site for https://api.weather.com to access the Weather Company APIs (see Create CSP Trusted Sites to Access Third-Party APIs).

```
