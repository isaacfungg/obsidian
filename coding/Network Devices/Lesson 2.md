***
#### OSI Model
**Layer 1 - Physical - Transporting Bits**
* Computing data exists in the form of bits
* Something has to transport those bits between hosts
* L1 Technologies Cables, Wifi, Repeaters, Hubs

**Layer 2 - Data Link  - Hop to Hop**
* Interacts with the Wire (Physical Layer)
* NIC - Network Interface Cars/ Wi-Fi Access Cards
* Addressing scheme - MAC addresses
	* 48 bits, represented as 12 hex digits
* L2 Technologies: NOCS, Switches

**Layer 3 - Network - End to End**
* Addressing Scheme - IP address
	* 32 bits as 4 octets
* L3 TechnologiesL Routers, Hosts

**Layer 4 - Transport - Service to Service**
* Distinguish data streams
* Addressing Scheme - Ports
	* 0-65535 - TCP - favours reliability
	* 0-65535 - UDP favours efficiency
* Server listen for requests to pre-defined Ports
* Clients select random Port for each connection

**Layer 5, 6, 7 - Session, Presentation, Application**
* Distinction between these layers is somewhat vague
* Other networking models combine these into one layer
* 