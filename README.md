# Debt Structure Analysis on an Organizational Level

Many times when one is looking to analyze the Debt Structure of an issuer within the desktop using Refinitiv Workspace / Eikon, the first thought is to look at the Debt Structure page. This is an excellent resource to analyze all bonds that meet specific requirements be it Maturity, Capital Tier, Coupon Class amongst many other categories. Not only does this information give us insight into the debt obligations of said organization, but it also sheds light into the burdens of future coupon payments, the distribution of risk and the implications in new areas such as Green Bonds.

With this article we would like to bring this kind of analysis to life through the use of the Refinitiv Data Platform Library and the Eikon Data API. We will go through some simple steps to search for all the bonds for a given issuer, look at some of the most relevant fields for the active bonds, and we will standardize the currency so we can look at the total value of the obligations in a single currency. This is done with the intent of explaining how to use the Search API functionality, how we can organize the properties/fields we're interested in, how to implement FX conversion from the currency of issue to a chosen FX snapshot and then ultimately look at the overall obligations by subsidiary but also as a whole.

Refer to the [Debt Structure Article](https://developers.refinitiv.com/en/article-catalog/article/debt-structure-analysis-on-an-organizational-level) defined within the Refinitiv Developer Community for more details.

## <a id="disclaimer"></a>Disclaimer
The source code presented in this project has been written by Refinitiv only for the purpose of illustrating the concepts of creating example scenarios using the Refinitiv Data Platform Library for Python.

***Note:** To [ask questions](https://community.developers.refinitiv.com/index.html) and benefit from the learning material, I recommend you to register on the [Refinitiv Developer Community](https://developers.refinitiv.com)*

## <a name="prerequisites"></a>Prerequisites

To execute any workbook, refer to the following:

License(s):

- A Refinitiv desktop license (Refinitiv Eikon or Refinitiv Workspace) that has API access 

  **OR**

- A [Refinitiv Data Platform (RDP)](https://developers.refinitiv.com/refinitiv-data-platform/refinitiv-data-platform-apis) license with access to the [Search endpoint](https://api.refinitiv.com/) data services

[Development Environment](https://developers.refinitiv.com/en/api-catalog/eikon/eikon-data-api/tutorials#setting-up-a-python-development-environment)

- Notebook can be directly loaded into Refinitiv CodeBook
- Packages: [rdp](https://pypi.org/project/refinitiv-dataplatform/) [pandas](https://pypi.org/project/pandas/) numpy matplotlib
- RDP for Python installation:  '**pip install refinitiv-dataplatform**' (if running outside of CodeBook)

## <a name="setup"></a>Setup

The package includes a single Jupyter Notebooks demonstrating features of the service.  Depending where you plan to access the content from, you will need provide the proper credentials:
* **Desktop Access**
  
  The notebook has been set up and tested to access data within the desktop, whether Refinitiv Workspace or Eikon.  For each, you simply need to replace the **'Your API Key here'** with your own [generated application API key](https://developers.refinitiv.com/en/api-catalog/eikon/eikon-data-api/quick-start#quick-start-guide-for-windows).
  
* **Platform Access**
  
  If you have an RDP license, you will need to replace the session code segment at the top of each notebook.  Replace the following line:
  
  ```
  rdp.open_desktop_session('Your API Key here')
  ```
  
  With the following:
  
  ```python
  rdp.open_platform_session(
    "Your API Key here",
      rdp.GrantPassword(
          username = "<YOUR MACHINE ID>",
          password = "<PASSWORD>"
      )
  )
  ```

### <a id="authors"></a>Authors

* **Nick Zincone**
* **Simone Da Costa**



