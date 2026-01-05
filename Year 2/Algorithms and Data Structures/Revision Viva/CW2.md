
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


3)
The scope is protected, represented by **#**. 

4)
The attributes `ID, name, type, string` in `Resource` must be kept private. This is important to maintain encapsulation within the class and avoid unexpected behaviour. All operations should remain public, so they can be accessed by other classes such as `BookingAPI_Impl`. Any class attributes that need to be accessed can do so through getter and setter elements.


#### Class **Booking**:

## Question 4



