
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
- `cancelBooking(bookingID: int): boolean`
- `validateBooking(`

**Operations**


#### Class **Booking**:

