<img width="1120" alt="Screenshot 2023-01-18 at 11 21 43 PM" src="https://user-images.githubusercontent.com/43849911/213257086-3d197450-590c-4145-abd4-e0a9d1bdfeea.png">

<img width="1118" alt="Screenshot 2023-01-18 at 11 22 30 PM" src="https://user-images.githubusercontent.com/43849911/213257237-fb5297fe-43d9-4139-8909-a1b89a05df2b.png">

<img width="900" alt="Screenshot 2023-01-18 at 11 41 12 PM" src="https://user-images.githubusercontent.com/43849911/213260935-fe281611-341a-4292-a149-60ceede45eb6.png">

```
rps*
```

<img width="773" alt="Screenshot 2023-01-18 at 11 41 58 PM" src="https://user-images.githubusercontent.com/43849911/213261092-8bbd8fbc-1825-4ef5-8bab-1a17b17f01ea.png">

```
For server side rate limiting, we might need to deal with caching and coordination b/w multiple server instances which might not be supported.
```

<img width="974" alt="Screenshot 2023-01-19 at 12 11 57 AM" src="https://user-images.githubusercontent.com/43849911/213266908-33d5fa04-0201-4e51-957b-628112048dc1.png">

<img width="1058" alt="Screenshot 2023-01-19 at 12 12 43 AM" src="https://user-images.githubusercontent.com/43849911/213267068-a57ebdb2-3022-4eef-a370-6df83f80002f.png">

<img width="1087" alt="Screenshot 2023-01-19 at 12 36 06 AM" src="https://user-images.githubusercontent.com/43849911/213293109-70501c02-1012-480e-b5af-c3e2dd010702.png">

<img width="609" alt="Screenshot 2023-01-19 at 2 54 23 AM" src="https://user-images.githubusercontent.com/43849911/213298073-e7a16c59-4cfe-4d33-acf0-b02634b97ac9.png">

```
Circuit Breaker
```
<img width="573" alt="Screenshot 2023-01-19 at 2 54 45 AM" src="https://user-images.githubusercontent.com/43849911/213298149-bd9293ab-0dbf-4780-a696-f983d6037e40.png">


```
When everything is normal circuit breaker remains in closed state and all the calls passes through these services.

When the number of failures exceeds the threshold, circuit breaker will be in a open state and returns message without executing anything in the fn. 

After the timeout, it returns back to HALF_OPEN , of it succedds its sent to the CLOSED state otherwise OPEN
```

```
Once the server is down OPEN, we need to hit api permittedNumberOfCallsInHalfOpenState no. of time when its up again to convert status into CLOSED. STATUS will be HALF_OPEN in between
```

<img width="539" alt="Screenshot 2023-01-19 at 3 49 00 AM" src="https://user-images.githubusercontent.com/43849911/213307735-ab2dee14-699b-4519-b6fd-ea8ad34e0c7d.png">

