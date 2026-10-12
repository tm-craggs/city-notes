![[image-170.png]]

```
MEETING = (hello -> converse -> goodbye -> STOP).
```

![[image-171.png]]

```
JOB = (arrive -> work -> leave -> JOB).
```

![[image-172.png]]

You might think this is:

```
GAME = ( one -> win -> GAME
		| two -> win -> GAME
		| three -> lose -> GAME).
```

But this is incorrect, and gives you an extra state. This is because it does not know that a state has already been defined when running two. You need to indicate that there is already a state it can go to. 

![[image-174.png]]

Here is the correct solution:

```
GAME = ( one -> WIN
		| two -> WIN
		| three -> lose -> GAME),
	WIN = (win -> GAME).
```

This creates another process called win, that loops back to game. Game has the process one and two that lead to the declared win process. Three still points to lose. 

![[image-175.png]]

