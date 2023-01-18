
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

