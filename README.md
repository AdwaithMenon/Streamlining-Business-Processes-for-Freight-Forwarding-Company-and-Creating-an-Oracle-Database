## _Streamlining Business Processes for Freight Forwarding Company & Creating an Oracle Database_

## **Project Description**

### **Business Context**

The organization that we have considered is a freight forwarding company. The name of our freight 
forwarder company is FFC. A freight forwarding company facilitates shipments of goods / materials 
between two parties ,i.e exporter and importer. The goods are shipped in containers in large carrier ships 
(also known as vessels) from the port of loading to the port of destination. The freight forwarder is 
responsible for documentation, inward & outward movement of goods, and handoffs.

### **Scope**

We have only considered exports of sea consignments for the purpose of this project. The customer in the 
current scope is the Exporter. The words “customer” and “exporter” have been used interchangeably in 
the project description. For this project, The FFC’s scope ends once the estimated time of arrival (ETA) at 
the destination has been updated to the exporter.

### **Key Assumptions & Business Rules**

**Note:** There are gaps in the AS-IS process and some of the below mentioned business rules and 
assumptions have not been incorporated in the AS-IS process - these are the gaps we want to address in 
our TO-BE process. However, to avoid redundancy, we have listed all relevant applicable assumptions 
and rules. All of these assumptions and business rules are incorporated in the proposed TO-BE 
process.The Enhanced ERD is based on the following rules & assumptions.

1. The customer lead is received online through the website only.
2. The customer has to fill up the online query form before getting accounted in the database.
3. All the necessary documents required for shipping have to be provided by the customer online 
through the website portal.
4. Customers can submit the query without providing any document. However, this delays the 
process of shipping. Since the shipment document (See item 13 & 14 below) can only be 
prepared on the basis of the packing list provided by the customer.
5. Customer leads are processed in the FIFO (First In First Out) method. 
6. On receiving the customer lead, the sales executive opens the case (Case Status = Open) and 
assigns a case id.
7. A shipment refers to goods or cargo that are shipped together. The words “shipment” and 
“consignment” are used interchangeably in this project.
8. Shipments (consignments) are transported (shipped) in containers.
9. One consignment can be shipped in one or more containers. However, every container can be 
associated with one and only one consignment.
10. Containers are kept in the shipping vessels owned by shipping lines. A shipping line can have 
zero or more shipping vessels. Each vessel can be owned by one and only shipping line.
11. Each customer can have zero or more shipments. However, each shipment will be associated with 
one and only one customer.
12. Each consignment will be associated with one and only one shipping line. One shipping line can 
have zero or more consignments.
13. Each shipment will be carried on one and only one vessel and each vessel can carry one or more 
consignments.
14. A freight forwarding company issues a shipping document (referred as Bill of Lading henceforth) 
(B/L) to the exporter. The B/L contains the name of the port of loading, port of discharge, cargo 
description, cargo weight, cargo volume, number of packages, container id, and the name of 
exporter. One B/L can include one or more containers. A container can have one and only one 
B/L
15. An exporter provides a packing list for a consignment to help freight forwarding company 
prepare the (B/L). The packing list contains the number of packages, cargo weight, cargo volume, 
INCO terms and cargo description.
16. One shipment can have one or more packing lists combined. However, each packing list can be 
associated with one and only one shipment.
17. Each vessel can carry one or more containers. But each container will be linked to one and only 
one vessel.
18. One B/L can have one or more packing lists combined. However, each packing list can be 
associated with one and only one B/L.

### **Key Stakeholders, User Requirements, and User Responsibilities**

**Note 1:** Some of the stakeholders are not present in the AS-IS process. These process gaps and additional 
enablers are accounted for in the TO-BE process. However, we have highlighted the responsibilities of the 
stakeholders as per the TO-BE Process.

**Note 2:** In As Is Process, the Customer Service Executive performs the responsibilities of sales, operations, 
and support together. There are multiple customer service executives. All these three roles are separately 
added and mentioned in the TO-BE process.

**1. Freight Forwarding Company / Freight Forwarder:**

a. A freight forwarding company is an organization that acts as a mediator between the 
exporter and the shipping line and that coordinates shipments on behalf of the exporters. 

b. The freight forwarder is responsible for negotiating the freight rates with the shipping 
line and ensuring the availability of containers required for the shipment.

c. However, freight forwarders do not own containers or do not operate /own vessels.

d. The freight forwarder prepares the required shipment related documents that are 
necessary to complete the shipment and are mandatory for the importer to take control of 
the cargo at the destination port.These documents are handed over to the exporter, who 
then sends these documents to the importer /consignee.



**2. Shipping Line / Liner:**

a. The shipping line is a company that owns the shipping vessels & containers which 
facilitate the shipment of cargo / goods from one port to another. The shipping line is also 
called “Liner”.

b. Liners allot space for containers to be shipped on a particular vessel. 

c. The freight rates are fixed by the shipping lines / liners based on the industry they are 
operating. For e.g. the rates for shipping chemical materials would be higher than the 
rates for shipping of consumer durable goods.

d. Liners are responsible for ensuring that the consignment reaches the destination port as 
per the planned schedule.

e. Once a shipping vessel and container is assigned to the shipment, as mentioned in the 
B/L, the liner must ensure that the shipment is not moved to any other container due to 
exigency such as lack of space or delay in schedule. 

f. Liner provides the necessary documents / proofs in order for the exporter to go for a 
claim in instances where the vessel has met with an accident and there has been damage 
to the cargo / goods.



**3. Customer:**

a. The customer (also called as exporter) contacts the freight forwarding company online to 
initiate the export shipment process

b. Receives quotes from the freight forwarder after submitting the shipment details 

c. Provides following information while filling up the online form that includes shipment 
details. The details to be provided before the shipment include:
i. H.S. Code of the cargo
ii. Cargo Weight
iii. Cargo Volume
iv. Cargo Description
v. Cargo Ready Date (CRD)
vi. Type of Container Required
vii. Material Safety Data Sheet (MSDS) - for hazardous cargoes

d. After the liner is finalized and the container assigned to the shipment, the shipment is said 
to be confirmed. The exporter is now responsible for picking up the empty containers 
from the liner using booking confirmation. The exporter will bring the loaded containers 
to the port of loading.

e. After the shipment is confirmed, the exporter is responsible for coordinating with the 
freight forwarder and providing the required consignment details well in advance

f. Exporter verifies the shipment documents prepared by the freight forwarder, ensures 
necessary changes are made before approving the same to proceed with the final 
documentation

g. Exporter hands over the final documents along with the shipment. The final documents 
are to be produced at the destination port by the importer.



**4. Customer Sales Executive:**
a. Opens the case when a new customer query comes online and assigns case number
b. Gathers customer’s input through the form filled online. This is required to identify 
relevant shipping lines and the type of services required for the customer.



**5. Customer Operations Executive:**

a. Uses customer cases generated by customer sales executives to connect with multiple 
shipping lines. 

b. Operations executives connect with multiple shipping lines to gather the best possible 
freight rates and shipping vessel schedules for every given case number.

c. Ensures that the empty container is available for pick up by the exporter if the shipment is 
confirmed.



**6. Customer Support Executive:** 

a. Connects with the exporter with available shipping rates and vessel schedules

b. Negotiates the final rates with the shipping line and the exporter.

c. Takes confirmation of the shipping order from the customer.

d. Requests the customer for additional shipment details if the shipment has been confirmed

e. Sends the booking confirmation to the customer

f. Updates the customer about changes in vessel schedules and estimated time of arrival 
(ETA) and closes the case (Case Status = Closed)



**7. Customer Documentation Executive:**

a. Creates a job corresponding to the shipment / consignment

b. Requests the customer for additional documents such as packing list (PL)

c. Prepares the drafts for the shipment documents based on the PL

d. Sends the drafts of the shipping documents to the exporter for approval

e. Submits the final approved shipment details to the shipping line



## **Swimlane Diagram For Sea Freight Container Booking Process (AS-IS)**


<img width="785" alt="image" src="https://user-images.githubusercontent.com/70052374/225168536-e4bcda94-ae65-469a-807a-806184fa2e08.png">



## **Swimlane Diagram For Sea Freight Container Booking Process (TO-BE)**


<img width="862" alt="image" src="https://user-images.githubusercontent.com/70052374/225169337-b0b73d5c-1c2d-4d06-9ee0-ac8bc3e861c4.png">



## **Enhanced Entity Relationship Diagram (EERD)**


<img width="672" alt="image" src="https://user-images.githubusercontent.com/70052374/225167813-31ccfc55-e081-429f-8df6-2c4abe209b8a.png">


## **SQL Query Report**

#### **1. What is the revenue contribution of each shipping line to the overall FFC revenue?**

**Context:**

The business requires us to establish relationships with several shipping lines so that we have options to ship consignments of different customers to the required destination port, optimizing the cost and profitability. A shipping line can vary in size, cost and ports at which they conduct operations.

**KPI/Business Metric:**

Primary KPI that can be monitored through this query
-	Revenue Growth Month on Month
-	Revenue contribution per shipping line
Secondary KPIs that can be tracked
-	Cost of doing business with each shipping line


**SQL Query:**

SELECT SHIPPING_LINE.LINER_NAME, SUM(DISTINCT SHIPPING_LINE.COMMISSION_PCT*BILL_OF_LADING.OCEAN_FREIGHT) AS COMMISSION
FROM SHIPPING_LINE INNER JOIN CONSIGNMENT
ON SHIPPING_LINE.LINER_ID=CONSIGNMENT.LINER_ID
INNER JOIN CONTAINER
ON CONSIGNMENT.CONSIGNMENT_ID=CONTAINER.CONSIGNMENT_ID
INNER JOIN BILL_OF_LADING
ON BILL_OF_LADING.BL_ID=CONTAINER.BL_ID
GROUP BY SHIPPING_LINE.LINER_NAME
ORDER BY COMMISSION DESC;

**Output:**

<img width="262" alt="image" src="https://user-images.githubusercontent.com/70052374/225171151-d7e635e3-daf6-4b03-9a20-e1ca96fce129.png">


#### **2.	Generate a report that shows the calculated revenue % earned by each category of cargo shipped.**

**Context:**

The cargo being shipped can be categorized based on the type of product being shipped. Each category impacts overall profitability differently. Electronics for instance may require special packaging, frozen food may need special temperature conditions. These can lead to additional cost of shipping. Scrap on the other hand, may not require special (costly) shipping conditions. The cost will vary depending on the cargo being shipped. 

**KPI/Business Metric:**

KPI/Business Metric:
Primary KPI that can be monitored through this query
-	Revenue percentage contribution per cargo type
-	Category-wise revenue growth
Secondary KPIs that can be tracked
-	Customer wise profitability


**SQL Query:**

SELECT PACKING_LIST.CARGO_DESCRIPTION, (TO_CHAR(ROUND(SUM(DISTINCT SHIPPING_LINE.COMMISSION_PCT*BILL_OF_LADING.OCEAN_FREIGHT)/31950*100,2))||'%') AS REVENUE_PCT
FROM SHIPPING_LINE INNER JOIN CONSIGNMENT
ON SHIPPING_LINE.LINER_ID=CONSIGNMENT.LINER_ID
INNER JOIN CONTAINER
ON CONSIGNMENT.CONSIGNMENT_ID=CONTAINER.CONSIGNMENT_ID
INNER JOIN BILL_OF_LADING
ON BILL_OF_LADING.BL_ID=CONTAINER.BL_ID
INNER JOIN PACKING_LIST
ON PACKING_LIST.BL_ID= BILL_OF_LADING.BL_ID
GROUP BY PACKING_LIST.CARGO_DESCRIPTION
ORDER BY REVENUE_PCT DESC;

**Output:**

<img width="273" alt="image" src="https://user-images.githubusercontent.com/70052374/225171401-9747da4b-3629-4a56-9c1e-4f6e75d66765.png">




#### **3.	Generate a report that shows the conversion rate per customer based on the number of inquiries (cases) converted into successful shipments.**

**Context:**

Each inquiry made by the customer is stored in the database as a case. Based on the process that follows from logging the case to finalizing, the case is updated in the database as success, closed or open. ‘Success’ refers to the cases which are successfully shipped by the shipping line. 

**KPI/Business Metric:**

Primary KPI that can be monitored through this query
-	Conversion percentage per customer segment (industry type) based on the total cases 


**SQL Query:**

SELECT CUSTOMER.CUSTOMER_NAME, 
TO_CHAR(ROUND(SUM(CASE WHEN CASES.CASE_STATUS='SUCCESS' THEN 1 ELSE 0 END)/COUNT(CASES.CASE_ID)*100,2))||'%' 
AS CONVERSION_RATE
FROM CASES
INNER JOIN CUSTOMER
ON CASES.CUSTOMER_ID=CUSTOMER.CUSTOMER_ID
GROUP BY CUSTOMER.CUSTOMER_NAME
ORDER BY CONVERSION_RATE DESC;


**Output:**

<img width="211" alt="image" src="https://user-images.githubusercontent.com/70052374/225171610-1afeaf1b-95f1-4ea0-8189-2b4175ce73af.png">



#### **4.	Generate a report that shows the volume (in cubic meters) of the cargo that is shipped from each Port of Loading.**

**Context:**

High volume cargo being shipped from the port of loading can be of business interest with respect to connectivity, geographical location, etc. However, this could also impact the cost of shipping from that port. The shipping lines that we contact may have longer term contracts with certain ports of loading which can be a deciding factor for connecting customers to shipping lines. 


**KPI/Business Metric:**

Primary KPI that can be monitored through this query
-	Monthly shipping capacity per port 
Deduced KPI that can be monitored through this query
-	Business lost due to delay in shipping through busy ports. This would require additional information logging of fields that are currently not part of the current database.


**SQL Query:**

SELECT VESSEL.PORT_OF_DISCHARGE,
SUM(CASE WHEN CONTAINER.CONTAINER_TYPE='20FT' THEN 1 ELSE 0 END) NO_OF_20FT_CONTAINERS ,
SUM(CASE WHEN CONTAINER.CONTAINER_TYPE='40FT' THEN 1 ELSE 0 END)  NO_OF_40FT_CONTAINERS
FROM VESSEL
INNER JOIN CONTAINER
ON CONTAINER.VESSEL_ID = VESSEL.VESSEL_ID
GROUP BY VESSEL.PORT_OF_DISCHARGE;


**Output:**

<img width="464" alt="image" src="https://user-images.githubusercontent.com/70052374/225171767-3460098f-7678-48de-9e73-355f4cc75de0.png">



#### **5.	 Generate a report that shows the number of each type of container that has reached a particular Port of Discharge.**

**Context:**

Each container in the database has a specific port of loading (source location) and port of discharge (destination location) associated with it. Different types of containers (for example, 40ft, 20ft)  are used  depending on the nature, weight and volume of the cargo. The containers that reach a particular port of discharge are destuffed and the empty containers are stored in the container yard.


**KPI/Business Metric:**

Primary KPI that can be monitored through this query :
-	Containers available per port of discharge


**SQL Query:**

SELECT VESSEL.PORT_OF_DISCHARGE,
SUM(CASE WHEN CONTAINER.CONTAINER_TYPE='20FT' THEN 1 ELSE 0 END) NO_OF_20FT_CONTAINERS ,
SUM(CASE WHEN CONTAINER.CONTAINER_TYPE='40FT' THEN 1 ELSE 0 END)  NO_OF_40FT_CONTAINERS
FROM VESSEL
INNER JOIN CONTAINER
ON CONTAINER.VESSEL_ID = VESSEL.VESSEL_ID
GROUP BY VESSEL.PORT_OF_DISCHARGE;

**Output:**

<img width="485" alt="image" src="https://user-images.githubusercontent.com/70052374/225171950-71338004-d733-4784-b88f-9478c1ae69af.png">


## **Conclusions**

* FFC earns more than 60% of their revenue from top 2 shipping lines.

* Container availability can have a major impact on ocean freight rates.

* Ports where the volume of cargo shipped out is high should be the FFC’s priority while filing freight rate contracts with the shipping line.

* Customer conversion rate is an important metric that can help FFC to find ‘low-cost high revenue’ customers.
