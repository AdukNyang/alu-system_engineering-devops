# Load Balancer

This project implements a load balancer using HAProxy to distribute traffic between two web servers running Nginx.

## Tasks

### 0. Double the number of webservers
Configures Nginx on web-01 and web-02 to include a custom HTTP response header `X-Served-By` with the server's hostname.

**File:** `0-custom_http_response_header`

### 1. Install your load balancer
Installs and configures HAProxy on lb-01 to distribute traffic between web-01 and web-02 using round-robin algorithm.

**File:** `1-install_load_balancer`

## Server Information
- **web-01:** 3.86.250.240
- **web-02:** 54.152.16.128
- **lb-01:** 54.152.31.168

## Usage

Run the scripts with sudo privileges:
```bash
sudo ./0-custom_http_response_header
sudo ./1-install_load_balancer
```

## Testing

Test the load balancer:
```bash
curl -I 54.152.31.168 | grep -i x-served-by
```

The response should alternate between web-01 and web-02.
