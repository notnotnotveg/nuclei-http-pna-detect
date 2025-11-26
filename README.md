# nuclei-http-pna-detect
Detects if the server responds with Access-Control-Allow-Private-Network in response to a PNA preflight request.

This script sends an HTTP OPTIONS request with the Access-Control-Request-Private-Network header to test for Private Network Access (PNA) misconfigurations. If the response contains the Access-Control-Allow-Private-Network header, the target may be vulnerable.

Usage:
```
nuclei -t http-pna-detect.yaml -u [URL]  -silent 
```

This can be run on your internal networks or localhost as :
```
% nuclei -t http-pna-detect.yaml -u "https://127.0.0.1:8080"  -silent    
[http-pna-detect:Access-Control-Allow-Origin] [http] [info] https://127.0.0.1:8080 ["https://foo.example"]
[http-pna-detect:Access-Control-Allow-Private-Network] [http] [info] https://127.0.0.1:8080 ["true"]
```
