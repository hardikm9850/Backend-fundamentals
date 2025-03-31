## How a Router Assigns IP Addresses and Handles Internet Requests

1. **The ISP assigns a public IP to the router.**  
2. **The router assigns itself a private IP** (e.g., `192.168.1.1`).  
   - This is done automatically and is pre-configured in the router.  
   - Default private IPs are usually `192.168.1.1` or `10.0.0.1`, but they can be changed in the router settings.  
3. **The router is already configured with NAT** (Network Address Translation).  
   - NAT allows multiple devices on the local network to share one public IP.  
4. **The router assigns private IPs to all devices in the local network via DHCP.**  
   - Example private IPs:  
     - MacBook → `192.168.1.100`  
     - Phone → `192.168.1.101`  
     - Smart TV → `192.168.1.102`  
5. **The local network is a private space where devices communicate without using the internet.**  
   - Example: A MacBook can send files to a printer using its private IP.  
6. **If a device needs to access the internet, the router translates the private IP into its public IP using NAT and sends the request to the internet.**  
   - When data comes back, the router forwards it to the correct device inside the local network.  

### Example:  
- Your **MacBook (`192.168.1.100`)** requests `www.google.com`.  
- The **router replaces the private IP with its public IP** and sends the request.  
- Google responds to the **router's public IP**.  
- The router **knows the request came from `192.168.1.100`** and sends the response back to the MacBook.  

