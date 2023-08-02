![[Pasted image 20230520115504.png]]

Two things that are needed : 
	![[Pasted image 20230520115546.png]]

![[Pasted image 20230520115730.png]]

![[Pasted image 20230520115931.png]]

Site to Site VPN Connection establishing steps : 

To create a site-to-site VPN connection in AWS, you can follow these steps:

1. Set up the Virtual Private Cloud (VPC) network:
   - Create a VPC: Create a VPC with appropriate IP address ranges for your network.
   - Create subnets: Create subnets within the VPC to define the network segments for each site.

2. Configure the customer gateway:
   - Create a customer gateway: Define a customer gateway, which represents the external device or software at the on-premises site.
   - Specify the public IP address or endpoint of the customer gateway device.

3. Configure the virtual private gateway (VGW):
   - Create a virtual private gateway: This represents the VPN endpoint within AWS.
   - Attach the VGW to the VPC: Associate the VGW with the VPC you created in step 1.

4. Create a VPN connection:
   - Create a VPN connection: Specify the customer gateway and virtual private gateway, and select the appropriate routing options.
   - Define the pre-shared key: Configure the pre-shared key to establish a secure connection.

5. Configure routing:
   - Update route tables: Modify the route tables associated with the subnets in your VPC to route traffic through the VPN connection.

6. Verify and test the connection:
   - Check the VPN connection status: Ensure that the VPN connection is active and the tunnel is up.
   - Test connectivity: Ping or access resources on the remote network to confirm successful communication.

AWS provides detailed documentation and guides to help you through each step of setting up a site-to-site VPN connection. It's recommended to refer to the AWS documentation for specific instructions and to ensure you have the necessary permissions and resources in place for configuring the VPN connection.
