Problem : Open connection faied: Unable to open tcp connection with host 'localhost:1433': dial tcp 127.0.0.1:1433: connectex: No connection could be made because the target machine actively refused it.
exit status 1

Solution :
	to connect with database server using sql server, 
		1.TCP/IP protocol should have to be enabled.
		2.sql server browser must be running.
		3.need to define tcp port(1433 deafult port for sql server)
	1.To enable TCP/IP protocol from "Sql server configuration manager"
		--goto "Sql server network configuration"
		--goto Protocols for "Server Name"
		--In the right side you will get TCP/IP option.Right click on TCP/IP and Click enable and click ok.
	
	
	2.Running sql server browser:
		->Open sql server configuration manager.
		->Click sql server services.
		->Right click on "Sql Server Browser" and select start.
		
		(after previous steps if you get error like Sql Server Browser is disabled or have nothing assigned to it)
			The reason behind this is may be your sql server has no tcp port assigned.
			
	3.To assign tcp port in your sql server follow the steps:
				:Open "SQL server configuration manager"
				->Sql server network configuration
				->Protocols for "Server Name"
				->double click on the TCP/IP then goto IP Addresses
				->set TCP Port to 1433(default for sql ser server) and click ok.
	
