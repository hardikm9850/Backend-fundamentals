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


## Network Flow for Accessing google.com

1. **Initiating the Request:**
   - The MacBook wants to visit `google.com`.
   - The browser sends a request to `google.com`.

2. **DNS Lookup (Domain Name System):**
   - The MacBook checks its local DNS cache to see if it already has the IP address for `google.com`.
   - If not, the MacBook sends a DNS query to its configured DNS server (often provided by the ISP or a public DNS like Google DNS or Cloudflare).

3. **DNS Resolution:**
   - The DNS server looks up the IP address of `google.com` in its records.
   - If it does not have the IP in its cache, it will recursively query other DNS servers to resolve the IP.
   - Once resolved, the DNS server sends the IP address of `google.com` (e.g., `142.250.72.78`) back to the MacBook.

4. **Private IP to Public IP Conversion (NAT - Network Address Translation):**
   - The MacBook has a private IP address assigned by the router (e.g., `192.168.1.10`).
   - Before sending the request to Google, the router performs NAT.
   - The router converts the MacBook's private IP address to its own public IP address (e.g., `203.0.113.5`), so the request can be routed across the internet.
   - When an internal device sends a request to the internet (e.g., to visit a website), NAT changes the source IP of the packet from the device’s private IP to the router's public IP. It also records the port number associated with that device in the translation table.
   - When the response comes back, NAT uses the port number to look up the correct internal device that initiated the request, and then forwards the data to the right device on the local network.

5. **Routing the Request:**
   - The router forwards the request to the destination server (Google’s web server) using the public IP address.
   - The router ensures that the request can pass through the public internet infrastructure.

6. **Google’s Server Response:**
   - Google's web server receives the request on the public IP.
   - Google’s server sends back the requested web content (HTML, images, etc.) to the router’s public IP.

7. **Reverse NAT (Mapping Response to Private IP):**
   - The router receives the response from Google.
   - The router performs reverse NAT, converting the public IP back to the private IP of the MacBook (e.g., `192.168.1.10`).
   
8. **Delivering the Response to the MacBook:**
   - The router forwards the response to the MacBook.
   - The MacBook receives the content from Google and displays the website in the browser.


The router uses a private IP address for local network communication, NAT, and security, ensuring that only the public-facing interface (with the public IP) communicates directly with the outside world. The internal interface with a private IP allows local devices to route their traffic through the router without the need for a unique public IP address for each device.
