---
id: azks8ajrta08dkh3dcan5nv
title: 3 - Content Security Policy (CSP)
desc: ''
updated: 1716213242711
created: 1716209624585
---

Content Security Policy (CSP) **is a** `security feature` **that helps** `prevent` `various types of` `attacks` **such as Cross-Site Scripting** (`XSS`) `and data injection attacks`. CSP is `implemented via` `HTTP headers` **and can be** `configured` `to control` `which resources` **the** `browser is allowed` `to load for` **a given** `page`. By `restricting` **the** `sources of` `content`, **CSP** `reduces` **the** `risk of` `malicious content` `being executed`.

Here’s a breakdown of how to implement and use CSP effectively:

### 1. Setting Up CSP
To set up CSP, you need to `add` **the** `Content-Security-Policy` `header to` **your** `HTTP response`. This `header contains` `directives that` `define` **the** `allowed sources for` `different types of` `resources`.

For **example**, **the following CSP header allows resources to be loaded only from the same origin (self)**:

```http
# Content-Security-Policy header to enhance security by restricting content sources
Content-Security-Policy: default-src 'self'
```

**You can add this header in your server configuration. Here's an example for an Apache server:**

```apache
# Ensure the headers module is enabled
<IfModule mod_headers.c>
    Header set Content-Security-Policy "default-src 'self'; script-src 'self'; style-src 'self';"
</IfModule>
```

For an **Nginx server**, it would look like this:

```nginx
# Add Content-Security-Policy header to enhance security
add_header Content-Security-Policy "default-src 'self'; script-src 'self'; style-src 'self';";
```

### 2. CSP Directives
CSP directives specify the allowed sources for various types of resources. Here are some common directives:

- `default-src`: `Sets` **the** `default policy for` `all resource types` **if not explicitly specified**.
- `script-src`: `Defines` **the** `sources from` `which scripts` **can be** `loaded`.
- `style-src`: `Defines` **the** `sources` `from which` `stylesheets` **can be** `loaded`.
- `img-src`: `Defines` **the** `sources` `from which` `images` **can be** `loaded`.
- `connect-src`: `Defines` **the** `sources` `for AJAX`, `WebSocket`, **and** `EventSource` `connections`.
- `font-src`: `Defines` **the** `sources` `from which` `fonts` **can be** `loaded`.
- `object-src`: `Defines` **the** `sources` `from which` `plugins` `such as` `Flash` **can be** `loaded`.

Here’s an **example of a more comprehensive CSP**:

```http
Content-Security-Policy: default-src 'self'; script-src 'self' https://apis.example.com; style-src 'self' 'unsafe-inline'; img-src 'self' data:; connect-src 'self'; font-src 'self' https://fonts.example.com; object-src 'none';
```

### 3. Handling Inline Scripts and Styles
**CSP by** `default` `blocks` `inline scripts and styles` **because they pose significant security risks**. However, `sometimes` you `need to` `allow` **specific** `inline scripts or styles`. This can be `achieved using` `nonces or hashes`.

#### Nonces
A nonce **is a** `random value` **that you** `generate on` **the** `server for` `each request` `and include in` **your CSP** `policy and` **your** `inline script/style tags`.

```http
# http
Content-Security-Policy: script-src 'self' 'nonce-abc123';
```

```html
<!-- html -->
<script nonce="abc123">
  // Your inline script
</script>
```

#### Hashes
`Alternatively`, **you can** `use` **a** `hash of` **the** `script/style content`.

```http
# http
Content-Security-Policy: script-src 'self' 'sha256-abc123hash=';
```

```html
<!-- html -->
<script>
  // Your inline script
</script>
```

### 4. Reporting and Monitoring
CSP can also be configured `to report` `violations to` **a specified** `URI` `without blocking` **the** `content`. This is **useful for** `monitoring` **and** `adjusting` the `policy`.

> URI: Uniform Resource Identifier

```http
# Header to monitor security policy violations without enforcing them

Content-Security-Policy-Report-Only: 
    # Allow all content to be loaded only from the same origin
    default-src 'self'; 
    # Report any policy violations to the specified URI
    report-uri /csp-violation-report-endpoint;
```

### 5. Testing and Tuning
`Start` **with a** `loose` **CSP policy** `and progressively tighten` **it** `as you` `identify` `legitimate resources that` **your** `application` `needs to` `load`. `Use` the `Content-Security-Policy-Report-Only` **header** `during` **the** `initial phases` `to collect` `reports` `without` `affecting` **the** `user experience`.

`By implementing` **a** `robust` `CSP`, **you significantly** `enhance` **the** `security posture of` **your web** `application`, `mitigating` **the** `risk of` `various types of` `web-based attacks`.



<!-- start of 'security posture' section -->
<details>
    <summary>Definition: security posture</summary>

#
The security posture **refers to the** `overall strength` `and effectiveness of` **an** `organization's` `security measures` `and practices`. It encompasses **various factors such as** `policies`, `procedures`, `technologies`, `and controls` `implemented` `to protect against` `security threats and risks`. A strong security posture indicates that an organization has taken proactive steps `to identify` `vulnerabilities`, `mitigate risks`, `and safeguard` **its** `assets`, `data`, `and operations from` **potential** `security breaches or attacks`.

---
</details>
<!-- end of 'security posture' section -->