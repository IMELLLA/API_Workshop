# Deploying Gateway to API



**Stay on the API Platform Cloud,the next step is to create API and deploy the gateway to the API.**


**Step 1:** Choose **APIs** on the API Platform Cloud, and click on **Create** on the top right
	![](images/xxx.png)

**Step 2:** Fill out the form:

	![](images/xxx.png)

**Step 3:** Your new API is created now, and click on it
	![](images/xxx.png)
	
**Step 4** Configure the API Request:

   	a. From the APIs tab, click the TicketService<nn> API you created in the previous task
   
   	![](images/Picture5.png)
   
   	b. Click on API Implementation
   
   ![](images/Picture6.png)
   
   c. Hover over the API Request policy, and then click Edit
   
   ![](images/Picture7.png)
   
   d. On the Edit Policy Dialog, complete these fields:
        i. Select HTTP from the Protocol list. This is the protocol on which the 
        gateway receives requests for this API.
        ii. Enter stickets<nn>/1 into the API Endpoint URL field. Example: If your 
        instructor assigned you with 05, then you would enter stickets05/1 in this 
        field and Click Apply
   
   ![](images/Picture8.png)

>Note: Configure the API Request - The API request is the endpoint to which requests for your API are sent. The full address to which requests are sent consists of the protocol used, the gateway hostname, the API request endpoint, and any private resource paths available for your service. For example: http://<host>:<port>/stickets<nn>/1/tickets. Where http is the protocol over which the gateway receives requests and where <host>:<port> is the hostname and port of the gateway instance this API is deployed to stickets<nn>/1 is the API endpoint you chose (currently this is hard-coded as /the API name/its version). Remember, the “nn” is just an example, you want to use your attendee number instead. /tickets is considered the private resource path of the API. Anything beyond the API endpoint is passed to the backend service  

**Step 7:** To configure the service request:

   a. Hover over the Service Request policy and then click Edit
   ![](images/Picture9.png)
   b. Edit Policy Dialog, choose to enter a URL:
        i. Enter the Apiary Mock Service URL in Enter a URL field
        ii.	Remove the “/tickets” from the mock-service URL so the API can be 
        designed to call multiple end- points such as “/incidents”
        iii. Leave the Service Account as None, Click Apply and Save Changes
   ![](images/Picture10.png)
   
>NOTE: The service request is the URL at which your backend service receives requests. When a request meets all policy conditions, the gateway routes the request to this URL and calls your service. The service request URL can point to any of your service’s resources, not just its base URL. This way you can restrict users to access only a subset of your API’s resources.

**Step 8:** To deploy an API to the Gateway:

   a. Click the Deployments tab (the cog icon at the left margin)
   
   ![](images/Picture11.png)
   
   b. Click Deploy API
   
   ![](images/Picture12.png)
   
   c. Select the Development Gateway, Select Active as the Initial Deployment State, Complete the description field in as 
   you like, and Click Deploy
   
   ![](images/Picture13.png)
    
**Step 9:** Now that the API is deployed, you can invoke it in your favorite REST client. Then click Send
    
    URL: http://gtwy-node.apip.oracle.com:9021/stickets<nn>/1/tickets
    Note: replace <nn> with your student number.
	Method: GET
	Headers: (optional)
	Accept: application/json
![](images/Picture14.png)

**Now you should be able to receive your mock data!**





