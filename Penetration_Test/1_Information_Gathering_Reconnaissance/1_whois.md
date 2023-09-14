## What is Whois?
> "Whois" is a widely-used internet tool and protocol that allows you to look up information about domain names and IP addresses. It provides a way to query a database and retrieve information about the owner, registration date, contact details, and more for a specific domain or IP address.

--- 

## What Information Does It Provide?
The information provided by whois tool, according to input. Input can be either Domain name, or IP address:
1. **Domain Information:** For domain names, a Whois lookup typically provides information such as:
    - Domain registrant's name, organization, and contact details.
    - Domain registration and expiration dates.
    - Domain registrar's information (the company that registered the domain).
    - Domain name servers (DNS) used by the domain.

2. **IP Address Information:** For IP addresses, Whois can provide details such as:
    - The organization or entity that holds the IP address range.
    - Contact information for the IP address holder.
    - Information about the regional internet registry (RIR) that allocated the IP address. 

---

Note 1 : In recent years, concerns about privacy and data protection have led to changes in Whois policies. Many domain registrars and registries now offer services like "Whois Privacy" or "Domain Privacy" to mask the personal information of domain owners in public Whois records. This helps protect the privacy of individuals and organizations that own domain names.

Note 2 : Different domain extensions (e.g., .com, .org, .net, country-code domains) often have their own Whois databases and servers. These are maintained by domain registrars or relevant authorities.

Note 3 : The WHOIS protocol traditionally operates on port 43 for both querying the WHOIS databases and receiving responses. Port 43 is the well-known and standardized port for the WHOIS service.

---

### What language does the whois cli tool is written? How it connects to databases? What database does it connected to, because there are many whois databases maintained by many different authorites?
The Whois command-line interface (CLI) tool is typically written in various programming languages depending on the specific implementation. It's important to note that there isn't a single "official" Whois CLI tool, but rather multiple implementations by different organizations and developers. These tools can be written in languages like C, Python, Perl, Ruby, and others.

Here's a general overview of how a typical Whois CLI tool works and how it connects to databases:
1. Database Connection:
    - When you run a Whois command to look up information about a domain name or IP address, the CLI tool connects to a Whois server or service over the Internet.
    - The choice of which Whois server to connect to depends on the top-level domain (TLD) of the domain name being queried. Different TLDs often have their own designated Whois servers.

2. Querying the Database:
    - The CLI tool sends a query to the appropriate Whois server, requesting information about the specified domain or IP address.
    - The query is typically sent over the WHOIS protocol, which operates on TCP port 43. The specific format of the query can vary, but it usually includes the domain name or IP address you're interested in.

3. Response:
    - The Whois server processes the query and sends back a response containing the requested information.
    - This response is often in plain text and follows a standardized format, but the structure can vary based on the Whois server and the TLD in question.

4. Displaying Results:
    - The CLI tool receives the response from the Whois server and displays it to the user in a readable format.
    - This typically includes details about domain registration, ownership, contact information, and more.


Regarding the multiple Whois databases maintained by different authorities:
- Yes correct, There are many Whois databases, each managed by different authorities or organizations. These databases are responsible for specific TLDs, IP address ranges, or regional allocations. For generic top-level domains (gTLDs) like .com, .org, and .net, domain registrars and registries often maintain their own Whois databases. For example, Verisign manages the .com and .net TLDs. Country-code top-level domains (ccTLDs), such as .uk (United Kingdom) or .de (Germany), have their own designated Whois databases operated by the respective country's registry.
- Regional internet registries (RIRs), such as ARIN, RIPE NCC, and APNIC, manage IP address allocations and maintain their own Whois databases for IP address-related queries.

---

### Well-known and Widsely Used whois Dabases?
There are several well-known and widely used Whois databases, each serving a specific purpose within the realm of domain registration and IP address management. Here are some of the most prominent Whois databases and their primary uses:

1. IANA (Internet Assigned Numbers Authority) Whois Database:
    - Use: This database is responsible for managing global IP address space allocation and domain name system (DNS) root zone management.
    - Purpose: To provide information about top-level domains (TLDs) and their authoritative domain name servers.

2. ARIN (American Registry for Internet Numbers) Whois Database:
    - Use: ARIN manages IP address allocations in North America, including the United States, Canada, and parts of the Caribbean.
    - Purpose: To provide information about IP address allocations, resource utilization, and technical contacts for organizations in the ARIN region.

3. RIPE NCC (Réseaux IP Européens Network Coordination Centre) Whois Database:
    - Use: RIPE NCC manages IP address allocations in Europe, the Middle East, and parts of Asia.
    - Purpose: To provide information about IP address allocations, Autonomous System Numbers (ASNs), and technical contacts for organizations in the RIPE region.

4. APNIC (Asia-Pacific Network Information Centre) Whois Database:
    - Use: APNIC manages IP address allocations in the Asia-Pacific region.
    - Purpose: To provide information about IP address allocations, ASNs, and technical contacts for organizations in the APNIC region.

5. AFRINIC (African Network Information Centre) Whois Database:
    - Use: AFRINIC manages IP address allocations in Africa.
    - Purpose: To provide information about IP address allocations, ASNs, and technical contacts for organizations in the AFRINIC region.

6. LACNIC (Latin America and Caribbean Network Information Centre) Whois Database:
    - Use: LACNIC manages IP address allocations in Latin America and the Caribbean.
    - Purpose: To provide information about IP address allocations, ASNs, and technical contacts for organizations in the LACNIC region.

7. Verisign Whois Database:
    - Use: Verisign operates the .com and .net TLDs and maintains Whois databases for these domains.
    - Purpose: To provide information about domain names registered under .com and .net TLDs, including registrants and contact details.

8. Registrar Whois Databases:
    - Use: Domain registrars often maintain their own Whois databases for domains they manage.
    - Purpose: To provide detailed information about domain names registered through a specific registrar, including registrant details, registration and expiration dates, and domain status.

9. Country Code TLD (ccTLD) Whois Databases:
    - Use: Each country code TLD (e.g., .uk, .de, .jp) typically has its own Whois database.
    - Purpose: To provide information about domain names registered under specific country code TLDs, including registrants and contact details.

---

### Simple Implementation of whois in C and Python
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <arpa/inet.h>
#include <netdb.h>

#define WHOIS_SERVER_PORT 43
#define MAX_BUFFER_SIZE 4096

// Function to send a Whois query to a Whois server
void sendWhoisQuery(const char *server, const char *query) {
    int sockfd;
    struct sockaddr_in server_addr;
    char buffer[MAX_BUFFER_SIZE];

    // Create a socket
    sockfd = socket(AF_INET, SOCK_STREAM, 0);
    if (sockfd == -1) {
        perror("Socket creation failed");
        exit(EXIT_FAILURE);
    }

    // Set up the server address structure
    server_addr.sin_family = AF_INET;
    server_addr.sin_port = htons(WHOIS_SERVER_PORT);

    // Convert server hostname to IP address
    struct hostent *he = gethostbyname(server);
    if (he == NULL) {
        herror("gethostbyname");
        exit(EXIT_FAILURE);
    }
    server_addr.sin_addr = *((struct in_addr *)he->h_addr);

    // Connect to the Whois server
    if (connect(sockfd, (struct sockaddr *)&server_addr, sizeof(server_addr)) == -1) {
        perror("Connection to server failed");
        exit(EXIT_FAILURE);
    }

    // Send the Whois query
    send(sockfd, query, strlen(query), 0);

    // Receive and display the response
    while (recv(sockfd, buffer, sizeof(buffer), 0) > 0) {
        printf("%s", buffer);
    }

    close(sockfd);
}

int main(int argc, char *argv[]) {
    if (argc != 2) {
        fprintf(stderr, "Usage: %s <domain or IP address>\n", argv[0]);
        return EXIT_FAILURE;
    }

    char *query = argv[1];

    // Check if the input is an IP address
    struct sockaddr_in sa;
    if (inet_pton(AF_INET, query, &(sa.sin_addr)) == 1) {
        // It's an IP address, query ARIN Whois server
        sendWhoisQuery("whois.arin.net", query);
    } else {
        // It's a domain name, query IANA Whois server
        sendWhoisQuery("whois.iana.org", query);
    }

    return EXIT_SUCCESS;
}
```

```python
import socket
import sys

WHOIS_SERVER_PORT = 43
BUFFER_SIZE = 4096

def send_whois_query(server, query):
    try:
        # Create a socket
        with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
            # Connect to the Whois server
            s.connect((server, WHOIS_SERVER_PORT))

            # Send the Whois query
            s.sendall(query.encode())

            # Receive and display the response
            while True:
                data = s.recv(BUFFER_SIZE)
                if not data:
                    break
                print(data.decode(), end='')

    except Exception as e:
        print(f"An error occurred: {e}")

def main():
    if len(sys.argv) != 2:
        print("Usage: python whois.py <domain or IP address>")
        sys.exit(1)

    query = sys.argv[1]

    # Check if the input is an IP address
    try:
        socket.inet_pton(socket.AF_INET, query)
        # It's an IP address, query ARIN Whois server
        send_whois_query("whois.arin.net", query)
    except socket.error:
        # It's a domain name, query IANA Whois server
        send_whois_query("whois.iana.org", query)

if __name__ == "__main__":
    main()
```

---

### How Entities (Domain Resgistrars) Know Whether a Domain is Available? 
Entities, such as domain registrars and domain registries, know whether a domain is available or not through a centralized domain name system (DNS) database. This database contains information about domain ownership, expiration dates, and availability status.

To check if a domain is available, you can use domain registrar websites or Whois lookup tools, which query the central database to determine the domain's status. If a domain is available, you can proceed to register it through the registrar of your choice, as long as no one else registers it before you.

It's essential to keep track of your domain's expiration date and renew it on time if you want to maintain ownership and prevent others from registering it when it becomes available again. Additionally, some registrars offer auto-renewal services to help ensure that you don't accidentally lose your domain due to non-renewal.