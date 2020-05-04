
# The Vision  
PlatformX is the platform for **suppliers** and **tour operators**  
who want to use **high performance cache systems** to **distribute travel offers**  
and benefit from a **fast integration**, **quick offer updates** and a **high data quality** 
while staying in **control over their respective portfolios**  

# For Accommodation Suppliers
## One API to enter the Peakwork Network
The Peakwork Network consists of numerous different tour operator players that need to be fed with data. Currently, there needs to be a separate data delivery for every redistributor or tour operator in the Peakwork Network, even if some offers might be identical. 
With PlatformX, accommodation suppliers are enabled to send every offered accommodation to the Peakwork Network **only once** by using PlatformX' public API, regardless of how many redistributors may use those offers.

## Minimize Time-to-Market
Current cache data production processes rely on batch data deliveries and batch processing of said data. This regularly leads to unnecessary long production times. 
PlatformX sets out to heavily **shorten offers' time-to-market** by accepting single accommodation updates from the accommodation supplier's inventory systems just as they occur and **directly stream offers** to authorized redistributors or tour operators.

## Control your portfolio within the Peakwork Network.
With PlatformX, accommodation suppliers are enabled to lodge information like point-of-sale (i.e. which market should an offer be sold in) and allowed distribution channgels (i.e. tour operator to end-customer / meta searcher to end-customer) and product tpye (e.g. hotel-only vs. package). It is no longer necessary to create multiple data deliveries to convey this kind of information. But how your offer's may be used is explicetely defined in PlatformX' data format.

## Easily connect to the Peakwork Network and to tour operators
PlatformX' data format was created as straight-forward and easy-to-implement as possible while respecting key features in the tourism industry and the way how offer data is currently handled in inventory systems.
In the past, connecting a data feed to a tour operator typically included setting up a project. With PlatformX, connection to a tour operator can be established with a simple click and the integration may then be achieved by iterating from there.

# First Steps
## GRPC and JSON  
PlatformX offers two data formats to receive data. To minimize the needed bandwith and to ensure swift processing and response times, PlatformX' API is based on Protocol Buffers (GRPC). Nevertheless the API does also support receiving a JSON representation of the Protocol Buffer definition.
The format definition features an easy to understand structure and syntax to enable easy integration into the Peakwork Network.
The JSON representation of the format is ideal for first steps and very small datasets. However, for a production setup we strongly recommend using the Protocol Buffer format over JSON as the data amount is  reduced by up to 90%.
​
## Data Structure  ​
In tourism, different types of data are updated in different intervals. To enable high performance and a huge flexibility, this fact is reflected by PlatformX data structure.
PlatformX knows three types of data for Accommodations: 
* Base Data 
* Offer Data and 
* Allotment Data.

Each data type can be updated independently. 
​
While Accommodation Base Data and Accommodation Offer Data represent mandatory information, Accommodation Allotment Data is optional. The entirety of this data represents the portfolio of a supplier.
​
### Base Data  
Accommodation Base Data represents the general definition of all entities like:
* Accommodations
* Rooms
* Boards
* Rates

Accommodation Base Data describes general definitions and attributes that change rather seldom like names, locations, which types of room and board types exist.  
Please note that rooms, boards and rates do not denote specific rooms in specific accommodations but rather types of rooms, boards and rates that must be unique throughout the whole portfolio.
​
### Offer Data  
Accommodation Offer Data represents the price structure definition which references the entities defined in the Accommodation Base Data.
Offer Data describes for **which price** specific combinations of room, board, length of stay, number of occupants, rate type are available.
Currently, it is possible to transmit all offers of one accommodation contract to PlatformX in **one call**. 
​
While the PlatformX format was designed to be as straight-forward as possible, it still allows to accommodate sophisticated and flexible price structures, such as:
* arrival-based **and** daily prices
* object prices
* person prices 
* age-range dependend prices like child-prices 
* assigning prices to the n-th person of a certain age-range 
​
Transmitting single offers or multiple single offers to PlatformX in one API call is currently being investigated.
​
### Allotment Data (coming soon)  
Accommodation Allotment Data represents the allotment definition which also references the entities defined in the Accommodation Base Data.
Allotment Data describes **how many** specific offers are available to the tour operator who distributes the offers.
​
## Getting started  
The API definition can be found on the sub pages in the navigation on the left.  

A basic example implementation using Java/Maven and the prerequisites to send data to the API can be found here: [INSERT LINK TO GITHUB REPOSITORY]​


More information on the product can be found in our Product Requirements Document [here](https://peakwork.sharepoint.com/:w:/r/sites/PO-Group/_layouts/15/Doc.aspx?sourcedoc=%7B0A1B5DC7-A427-4AAC-A2BC-0053737B3A51%7D&file=PX-PRD_current.docx&wdLOR=c21470D96%2d6DF8%2d40F8%2d8B2C%2dA173571AF21F&action=default&mobileredirect=true).

## Glossary

Most important Terms and Vocabulary used in Peakwork and PlatformX is available [here](https://confluence.peakwork.lan/display/PX/Glossary)