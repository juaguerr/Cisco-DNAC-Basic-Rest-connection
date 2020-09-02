README.md

Cisco-DNAC-Basic-Rest-connection

The Cisco DNA Center Solution, is part of the Cisco DNA Arquitecture for  digital transformation, it provide an easy/cost effective way to deploy, monitor and troubleshoot your networking devices. The solution have different major components and features, and one of those is the ability to beign managed via APIs.

DNA Center Basic Rest Connections

The main pourpose of this basic repository is show you how you can understand and create your own basic script to configure and maintain your network via APIs. Here you will find a basic python file where yu will be able to understand how to make calls to your DNA Center and how those works. The scripts do not have any particular functionality, you are the one who can  provide any API URL or payload that you want to check and execute the REST calls. You can find all the API documentation at your DNA Center in Platform or online at https://developer.cisco.com/docs/dna-center/api/1-3-3-x/#!intent-api-v1-3-3-x

NOTE: This script was mainly built to provide a basic understanding on how it works and interact APIs.

Requirements

    - Python3
    - User with the right permissions
    - Enable REST APIs in your DNA Center
    
   
Recomendations

    - You can check a few API calls in Postman or any similar software. There is a Postman collection already pre-built at https://documenter.getpostman.com/view/134222/SVmpZ2vT?version=latest
    - Always try to create a virtual enviroment for your Python tests.

Using the Script

Setup 

   1. Clone the script into your computer

   a. git clone https://github.com/juaguerr/Cisco-DNAC-Basic-Rest-connection.git

   b. Move to the folder created --> Cisco-DNAC-Basic-REST-Connection

   2. Create a Virtual Enviroment

     python3.8 -m venv venv
     source venv/bin/activate

   3. Install the requests module

     pip install requests


How to use it

   1. Setup the correct credentials for your own DNA Center enviroment credentials in the document "credentials.py". By default credentials are pointing out to DNAC Devnet server.

   2. open your python console and import "rest_connection" as dnac
   in your terminal:
         
      $python
      >>> import dnac_rest_connection as dnac

Now you can execute your own URL APIs in the interpreter. 

The script have 4 major functions that you can call to make your API Requests.
  a. get_request
  b. post_request
  c. put_request
  d. delete_request


Examples

1. get_request()
  Getting Devices
    To query your devices, you can use the function get_request built inside 'dnac_rest_connection.py'. Since that we already imported it in our interpreter, we can execute it with the URL API '/dna/intent/api/v1/network-device', to get a list of devices. You can find the API documentation in the links already provided.
    
       devices = dnac.dnac.get_request('/dna/intent/api/v1/network-device')
   The variable 'devices' now have the API response, so you can start to format your data.

NOTE: Since that the default credendials are for the DNAC Devnet server that is public, the only permission that we have with the default user is read-only, that's why it's not possible to make another API call from this script other than get_request(). If you want to test the other functions make sure to have access to a DNA Center with the right permissions or schedule some time at Devnet from Cisco.


 


