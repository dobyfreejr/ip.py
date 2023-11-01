import requests

def ip_lookup(ip_address):
    url = f"https://ipinfo.io/{ip_address}/json"
    response = requests.get(url)

    if response.status_code == 200:
        data = response.json()
        print("IP Address: " + data.get("ip"))
        print("Hostname: " + data.get("hostname", "N/A"))
        print("City: " + data.get("city", "N/A"))
        print("Region: " + data.get("region", "N/A"))
        print("Country: " + data.get("country", "N/A"))
        print("Location: " + data.get("loc", "N/A"))
        print("Organization: " + data.get("org", "N/A"))
    else:
        print("Failed to retrieve information for the IP address.")

if __name__ == "__main__":
    ip_address = input("Enter an IP address: ")
    ip_lookup(ip_address)

