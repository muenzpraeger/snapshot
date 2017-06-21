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

To purchase a Weather Company data package, ! [click here] (https://business.weather.com/product-categories/the-weather-company-data-solutions).

## Installing and Configuring the Component
### System Requirements
Snapshot is supported for Salesforce editions that include case management. Lightning Experience must be enabled. Snapshot is not supported in Salesforce Classic. Snapshot is supported on all browsers that are supported for Lightning Experience. For details, see (Supported Browsers for Lightning Experience) [https://help.salesforce.com/articleView?id=getstart_browsers_sfx.htm].

**Setting Up the Component**
Prerequisite: Prior to installation, ensure Lightning Experience is enabled (see Enable Lightning Experience). 
To set up the component:
1. Get the component from [GitHub] (https://github.com/TheWeatherCompany/Salesforce-Snapshot) and deploy it to Salesforce.
2. In Salesforce, create a CSP Trusted Site for https://api.weather.com to access the Weather Company APIs (see Create CSP Trusted Sites to Access Third-Party APIs).
3. Add the component to the case page by editing the page in the Lightning App Builder (see Configure Lightning Experience Record Pages). 
  - In the Lightning Components list, scroll down to the Custom – Managed section.
  - Click Weather Company Snapshot and drag the component to any place on the page.
  - In the properties pane, select the default type of units to display. 
  - Save and activate the updated page.
4. Add the Weather Location field and Weather Snapshots related list to the case page. The Snapshot component displays the weather for the location specified in the Weather Location custom field. The Weather Snapshots related list displays all the snapshots that are associated with the case.
  - In Setup > Object Manager, edit the page layout for the case object. 
  - Add the Weather Location field to the case detail section. 
  - Add the Weather Snapshots related list to the related lists section. 
5. Grant users the required permissions for the component. In Setup > Permission Sets, assign users the WeatherSnapshot permission set (see Assign a Permission Set to Multiple Users). 
6. Enter the API key. In Custom Metadata Types, edit the SUN_Weather API record (see Add or Edit Custom Metadata Records Declaratively). For the API Key field, specify the API key you received when you purchased the data package.  For the API User field, don’t specify a value.  Tip: If the API Key field is not displayed for the API record, edit its page layout.
7. Disable the sample data response and activate the API calls to Weather.com. In the src/aura/Snapshot/Snapshot.cmp file, change the useMockup attribute to false. Tip: To improve performance, configure Salesforce to automatically add geocodes to all Account, Contact, and Lead records (see Set Up Geocode Data Integration Rules). Snapshot then uses the geocode values instead of making API calls to determine the latitude and longitude for each address. 

### Extending the Component
You can extend Snapshot by purchasing a data subscription and customizing the code to add more historical snapshot information, such as: 
- Additional 24 hour historical weather details like hail, snow, and ice (included in the Severe Weather package)
- Older historical data to create weather snapshots back to 2011. This data includes surface temperature, wind speed, wind direction, relative humidity, atmospheric pressure, and dew point (included in the History on Demand package)

### Restrictions
Snapshot shows data for locations in the U.S. and Canada only. The user interface is available in English only.
