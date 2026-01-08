
## Question 1:

1)
#### Class **Booking**:

**Attributes**
- `- bookingID: int`
- `- startDate: string`
- `- duration: string`
- `- status: string = "on-hold"`
- `- userID: int`
- `- resourceID: int`
- `occupantsNum: int`
- `transactionID: int`

**Operations**
- `+ retriveID() : int`
- `+ retriveStartDate() : String`
- `+ retriveDuration() : int`
- `+ retriveStatus(String status) : String`
- `+ retriveResource() : Resource`
- `+ confirm() : void`
- `+ cancel() : boolean`
- `+ archive() : void`

#### Class **BookingAPI_Impl**:

**Attributes**
- `activeBookings : BookingCollection [1]`

**Operations**
- `requestBooking(reservationType: String, reservationID: int, )`
- `cancelBooking(bookingID: int): boolean`
- `validateBooking()`

**Operations**


#### Class **Room**:

#### Class **Equipment**:

#### Class **StorageAPI_Impl**:

**Attributes**:
- `- occupancyLimit : int [1]`
- `roomType : String [1]`

2)

`storageAPI -- StorageAPI_Impl`
Relationship: Implementation
Multiplicity: N/A
Navigability: Unidirectional

`BookingAPI_Impl -- BookingAPI`
Relationship: Implementation
Multiplicity: N/A
Navigability: Unidirectional

`BookingAPI_Impl -- BookingCollection`

Relationship: Composition
Multiplicity: 1 to 1
Navigability: Unidirectional 


`BookingAPI_Impl -- StorageAPI_Impl`
Relationship: Aggregation


`Resource -- Equipment`
Relationship: Inheritance
Multiplicity: N/A
Navigability: N/A

`BookingCollection -- Booking`


`Booking -- StorageAPI`

`BookingSqlHelper -- SQLHelper`

3)
`sql` has instance scope. This is because each instance of an SQL Helper class must have its own unique query string, therefore `sql` is directly attached to a specific instance of a class. 

4)
Resource is an abstract class. This is because Resource represents a general concept of a Room or Equipment in the CBS. It acts as a base class for other classes that will provide the implementation of manipulating resources. Resource requires a constructor, as it has attributes that should be initialised such as `ID, name, type`. 

5)
The attributes `ID, name, type, string` in `Resource` must be kept private. This is important to maintain encapsulation within the class and avoid unexpected behaviour. All operations should remain public, so they can be accessed by other classes such as `BookingAPI_Impl`. Any class attributes that need to be accessed can do so through getter and setter elements.

6)

#### Class **Booking**:


## Question 3

![[image-110.png]]

## Question 4

![[image-112.png]]

## Question 5

**Test 1: MakeABooking - Main Flow**

**Test 2: MakeABooking: InvalidBookingRequest - Alternative Flow**

