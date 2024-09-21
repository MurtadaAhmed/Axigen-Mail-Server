# Axigen-Mail-Server

Instructions:

1. Run the docker compose file from this directory:

`docker compose up --build`

2. Open the admin panel:

`http://localhost:9000/`

Choose the free license and finish the setup.

3. Add domain and email account:

From Domain & accounts >> Manage Domains >> add domain and set a password >> quick add

From Domain & Accounts >> Manage Accounts >> add account name and password >> quick add

4. If using cloudflare using the following dns settings:

The Custom SSL/TLS settings in cloudflare should be set to **Full**.


```
Type: MX

Name: @

Mail server: mail.yourwebsite.com
```

```
Type: TXT

Name:@

Content: v=DMARC1; p=none; rua=mailto:dmarc@yourwebsite.com
```

```
Type: A

Name: mail

IPv4 address: YOUR_SERVER_IP_ADDRESS

ProxyStatus: off
```

```
Type: TXT

Name: @

Content: v=spf1 ip4:YOUR_SERVER_IP_ADDRESS include:spf.axigen.com -all

```

5. Start testing receiving and sending emails by accessing your domain directly and login to the account that you created in step 3

