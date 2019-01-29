# Watson-Tone-Analyzer-With-QlikSense
This Qlik Sense demo application is integrated with IBM Watson Tone Analyzer services to get the linguistic analysis to detect emotional and language tones. Qlik Sense app invokes the API call to Watson Tone analyzer services to retrieve the tone values at the document and sentence levels. Businesses can greatly benefit from this service by analyzing the customer's voice and take steps to improve the outcomes.

To make this work in Qlik Sense: 

•	First, need to create a Watson account and subscribe for the Watson tone analyzer service. There is a subscription fee for this service. However, free service has a limitation of 2500 calls per month. 

•	Get the tone analyzer API key, and this will be used in Qlik Sense to establish a call.

•	Qlik Sense app can connect to IBM Tone Analyzer using Qlik Sense REST connector (GET method). 

•	The request could be on-demand for a single paragraph with one or more sentences. Alternatively, a large volume of data can be processed by looping through the field and make multiple calls in Load Script.

This demo app (ToneAnalyzr_with_QlikSense.QVF) has both approaches. Load Script has the code for the Full reload and Partial reloads. Full reload script will read data from the file (in this case EXCEL file) and loop through each row and makes a call to retrieve the result from tone analyzer API. The application has the Sheet with a text box and a button to demonstrate the On-Demand request. Users can enter the text and click the ‘Analyze’ button which retrieves the value from Watson Tone Analyzer service and trigger the Partial reload.

Tone analyzer result will be a document and sentence level along with a confidence score. Watson Tone Analyzer sends the result in a JSON format. Qlik table retrieves the necessary columns to be used from the JSON output to the table in the data model.

This demo application has three sheets. 

First sheet with emojis to represent the signs of various linguistics such as analytical, anger, confident, tentative, joy, fear and sadness, accompanied by other charts presenting the analysis of different dimensions.
The second sheet shows the table with the conversation and a sentence level tones with a confidence score for each sentence. The third sheet allows users to enter some text and make on-demand calls directly from the sheet level.

Configuration:
1)	Input the API Key in Input_Param.txt file
2)	To validate whether the key works or not, open the Qlik Sense App, enter some texts and click the ‘Analyze’ button in On-demand request Sheet.
3)	If you need to analyze the more data, place the input data file and modify the load script to point to your file and field names to load.
