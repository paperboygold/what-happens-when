# What Happens When You Type google.com in Your Browser and Press Enter?

## 1. User Interface Interaction
- Keyboard input is processed through hardware → OS → browser
- Browser's autocomplete suggests URLs based on history/bookmarks
- Browser determines if input is URL or search term
- If valid URL pattern found, proceeds with URL processing

## 2. URL Processing
- Browser parses URL components (protocol, domain, path)
- Checks HSTS list to determine if HTTPS is required
- Converts any Unicode characters to Punycode if needed

## 3. DNS Resolution (Domain → IP)
1. Check browser DNS cache
2. Try secure DNS first (DNS-over-HTTPS/DNS-over-TLS)
3. Check OS DNS cache
4. Query DNS resolver (usually ISP's DNS)
5. Recursive DNS lookup if needed:
   - Root nameservers → TLD nameservers → Authoritative nameservers

## 4. Connection Establishment
1. ARP process to find MAC address of gateway
2. Establish TCP connection (3-way handshake)
3. TLS handshake for HTTPS:
   - Verify certificate chain
   - Exchange keys
   - Establish encrypted session

## 5. HTTP Communication
1. Browser sends HTTP(S) request
2. Server processes request
3. Server sends response
4. Browser begins processing response

## 6. Browser Rendering
1. Parse HTML → DOM Tree
2. Parse CSS → CSSOM
3. Combine into Render Tree
4. Layout computation (positions/dimensions)
5. Paint elements to screen
6. Composite layers

## Key Security Considerations Throughout
- Input validation at keyboard level
- DNS security (DNSSEC, DoH/DoT)
- Network security (TLS, HSTS)
- Content security (CSP, SOP)
- Certificate validation
- Secure rendering pipeline

## Modern Optimizations
- Parallel processing
- Predictive pre-fetching
- Resource prioritization
- Hardware acceleration
- Caching at multiple levels

## Follow-up Topics
- TCP vs UDP
- HTTP versions (1.1, 2, 3)
- DNS record types
- TLS handshake details
- Browser architecture
- Rendering pipeline
- Security vulnerabilities
- Performance optimization