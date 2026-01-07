
## Question 1:

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

**Attributes**:
- `- occupancyLimit : int [1]`
- `roomType : String [1]`

2)

**`storageAPI -- StorageAPI_Impl`**
Relationship:
Multiplicity: N/A
Navigability: Unidirectional

`BookingAPI_Impl -- BookingAPI`


`BookingAPI_Impl -- BookingCollection`




3)
Is it a class scope or an instance scope? Instance scope

4)
The attributes `ID, name, type, string` in `Resource` must be kept private. This is important to maintain encapsulation within the class and avoid unexpected behaviour. All operations should remain public, so they can be accessed by other classes such as `BookingAPI_Impl`. Any class attributes that need to be accessed can do so through getter and setter elements.


#### Class **Booking**:


## Question 3

![[image-110.png]]

## Question 4

![[image-112.png]]

## Question 5

**Test 1: MakeABooking - Main Flow**

**Test 2: MakeABooking: InvalidBookingRequest - Alternative Flow**

