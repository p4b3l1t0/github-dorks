**GitHub Dorks for Vulnerability Patterns**

- PHP XSS: `/\becho\b.*\$_GET\b/` or `/echo\s+\$_REQUEST/`
- PHP XSS: `/^.*\becho\s+\$_GET\b.*$/`
- PHP XSS (most FP-prone): `/^.*\becho\s+\$\b.*$/`
- PHP SQL Injection: `/(SELECT|INSERT|UPDATE|DELETE)\s(.*\$_POST|.*\$_GET|.*\$_REQUEST)/`
- PHP OS Command Injection: `/(exec\(|system\(|shell_exec\(|passthru\()(.*\$_POST|.*\$_GET|.*\$_REQUEST)/`
- Host Header Injection (Node.js & PHP): `req.headers.host path:*pass*` and `/\$_SERVER\['host'\]|gethostname\(\).*(reset|forgot)/`
- .NET Host Header Injection: `/(Request\.Headers\["Host"\]|Request\.Host\.Value|HttpContext\.Current\.Request\.Headers\["Host"\]|HttpContext\.Request\.Host\.Value)/ forgot`
- Host Header Injection generic: `host path:**/*forgot*/**`
- Insecure Deserialization in PHP: `/(unserialize\()(.*\$_POST|.*\$_GET|.*\$_REQUEST)/`

Python XSS:
- `/\bprint\b.*\brequest\.GET\b/ or /print\s+request\.GET/`
- `/^.*\bprint\s+request\.GET\b.*$/`
- `/^.*\bprint\s+\$\b.*$/`

Python SQL Injection:
- `/(SELECT|INSERT|UPDATE|DELETE)\s(.*request\.POST|.*request\.GET|.*request\.data)/`

Python OS Command Injection:
- `/(os\.system\(|subprocess\.call\(|subprocess\.Popen\()(.*request\.POST|.*request\.GET|.*request\.data)/`

C++ XSS:
- `/\bcout\b.*\bcin\b/ or /cout\s+cin/`
- `/^.*\bcout\s+cin\b.*$/`
- `/^.*\bcout\s+\$\b.*$/`

C++ SQL Injection:
- `/(SELECT|INSERT|UPDATE|DELETE)\s(.*std::cin|.*std::getline)/`

JavaScript XSS:
- `/\bconsole\.log\b.*\breq\.query\b/ or /console\.log\s+req\.query/`
- `/^.*\bconsole\.log\s+req\.query\b.*$/`
- `/^.*\bconsole\.log\s+\$\b.*$/`

JavaScript SQL Injection:
- `/(SELECT|INSERT|UPDATE|DELETE)\s(.*req\.params|.*req\.query)/`

Spring Boot XSS:
- `/model\.addAttribute.*\brequest\.getParameter\b/ or /model\.addAttribute\s+request\.getParameter/`
- `/^.*model\.addAttribute\s+request\.getParameter\b.*$/`
- `/^.*model\.addAttribute\s+\$\b.*$/`

Spring Boot SQL Injection:
- `/(SELECT|INSERT|UPDATE|DELETE)\s(.*request\.getParameter|.*request\.getQueryString)/`

Laravel XSS:
- `/\becho\b.*\brequest->input\b/ or /echo\s+request->input/`
- `/^.*\becho\s+request->input\b.*$/`
- `/^.*\becho\s+\$\b.*$/`

Laravel SQL Injection:
- `/(SELECT|INSERT|UPDATE|DELETE)\s(.*request->input|.*request->all)/`

Symfony XSS:
- `/\becho\b.*\b\$request->query\b/ or /echo\s+\$request->query/`
- `/^.*\becho\s+\$request->query\b.*$/`
- `/^.*\becho\s+\$\b.*$/`

Symfony SQL Injection:
- `/(SELECT|INSERT|UPDATE|DELETE)\s(.*\$request->request|.*\$request->query)/`

.NET XSS:
- `/\bConsole\.WriteLine\b.*\bRequest\.QueryString\b/ or /Console\.WriteLine\s+Request\.QueryString/`
- `/^.*\bConsole\.WriteLine\s+Request\.QueryString\b.*$/`
- `/^.*\bConsole\.WriteLine\s+\$\b.*$/`

.NET SQL Injection:
- `/(SELECT|INSERT|UPDATE|DELETE)\s(.*Request\.Form|.*Request\.QueryString)/`

Generic Host Header Injection:
- `host path:**/*forgot*/**`

Insecure Deserialization:
- `/(unserialize\()(.*\$_POST|.*\$_GET|.*\$_REQUEST)/`
