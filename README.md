mermaid
sequenceDiagram
    participant U as User
    participant C as Client
    participant S as Server
    participant DB as Database
    U ->> C : Fill username
    U ->> C : Fill password
    C ->> U : Enable "Login" button
    U ->> C : Click "Login" button
    C ->>+ S : POST /login
    S ->>+ DB : SELECT FROM users
    Note over S,DB: See login.py for impl. details
    DB -->>- S : results
    S -->>- C : { authenticated: true }
    C ->> U: redirect /home
```
![image](https://user-images.githubusercontent.com/113495023/204536235-5a0e027f-7ce5-491d-9e76-19f9f16d555e.png)
S
