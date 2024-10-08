# Doctors-Portal

### Doctor's portal is an advanced web application that utilizes a powerful stack of technologies, including React, Tailwind CSS, Stripe, JWT (JSON Web Tokens), DaisyUI, Axios, Firebase, Context API, TanStack React Query, React Hooks, and React Router. This comprehensive platform enables patients to sign up, log in, schedule appointments, and make secure transactions, while doctors can register, log in, manage their availability, and provide medical services seamlessly. 

### Project Features
**User Authentication:** Doctor's-Portal offers a secure and reliable user authentication system. Patients can create accounts, log in, and access personalized features, while doctors can register, log in, and manage their professional profiles.

**Patient Dashboard:** Patients have access to a user-friendly dashboard upon logging in. They can view their appointment history, manage personal information, and schedule appointments with available doctors.

**Doctor Dashboard:** Doctors have a dedicated dashboard that allows them to manage their professional profile, set availability slots for appointments, and view their appointment history. They can also access patient medical records securely.

**Appointment Scheduling:** Patients can search for available doctors, view their profiles, and book appointments based on their availability slots. Doctors can publish their availability slots, manage bookings, and receive notifications for new appointments.

**Stripe Integration:** Doctor's-Portal incorporates Stripe, a secure payment gateway, to facilitate seamless and secure transactions. Patients can make payments for their appointments through Stripe, ensuring a smooth and reliable payment process.

**Integration with Firebase:** Firebase integration provides a scalable and reliable backend infrastructure for MediConnect. It enables real-time data synchronization, user authentication, and database management, ensuring efficient data handling.

**Context API and React Hooks:** Doctor's-Portal utilizes Context API and React Hooks to manage global state and provide a smooth and responsive user interface. These technologies enhance performance and optimize the user experience.

**Responsive Design with Tailwind CSS:** Doctor's-Portal follows a responsive design approach using Tailwind CSS, ensuring that the portal is accessible and visually appealing across various devices and screen sizes.

---

## View live demo: [www.doctor's-portal.com](https://doctors-portal-4ref.onrender.com/)

# Demo :movie_camera:

![Appreciate Nature (5 second video) (1)](https://media.githubusercontent.com/media/alfatcse/gifTest/main/docPPP.gif)

### Usage
* Run npm start:dev to start the application.
* Connect to the API using Postman on port 5009.
## Live Link:     [www.doctor's-portal-server.com](https://doctors-portal-server-henna-nine.vercel.app/)  
### API Endpoints
| HTTP Verbs | Endpoints | Action |
| --- | --- | --- |
| GET |api/v1/appointmentOptions | To retrieve all appointment data |
| GET |api/v1/users?userType={Patient or Doctor} | To retrieve all users based on query (with JWT-authentication)|
| GET |api/v1/slot/{Doctor's email} | To retrieve all slots of the specific doctor (with JWT-authentication)|
| GET |api/v1/bookings?email={User's email} | To retrieve all bookings of the specific user (with JWT-authentication)|
| GET |api/v1/user?email={User's email} | To retrieve all data of the specific user (with JWT-authentication)|
| GET |api/v1/appointmentSpecialty | To retrieve all services|
| GET |api/v1/jwt?email={User's email} | To create JWT token|
| GET |api/v1/booking/:id | To retrieve information of a specific booking (with JWT-authentication)|
| GET |api/v1/booking-doctor?email={Doctor's Email} | To retrieve all patient of a specific doctor (with JWT-authentication)|
| POST|api/v1/users | To create a new user account |
| POST|api/v1/bookings | To create a booking (with JWT-authentication) |
| POST|api/v1/slots | To create a appointment with slot data (with JWT-authentication) |
| POST|api/v1/create-payment-intent | To create a new payment intent (with JWT-authentication) |
| POST|api/v1/payment | To create a payment with payment data  (with JWT-authentication) |
| PATCH | api/v1/slot |  To Update Slot data (with JWT-authentication)  |
| PATCH | api/v1/users?id={user id} |  To Update user role (with JWT-authentication)  |
| PATCH | api/v1/slots |  To Update Slot data (with JWT-authentication)  |
| DELETE | api/v1/users/:id | To delete a single user (with JWT-authentication)  |

### Technologies Used
* [NodeJS](https://nodejs.org/) This is a cross-platform runtime environment built on Chrome's V8 JavaScript engine used in running JavaScript codes on the server. It allows for installation and managing of dependencies and communication with databases.
* [ExpressJS](https://www.expresjs.org/) This is a NodeJS web application framework.
* [MongoDB](https://www.mongodb.com/) This is a free open source NOSQL document database with scalability and flexibility. Data are stored in flexible JSON-like documents.
* [JSON Web Token](https://jwt.io/) JSON Web Token is a proposed Internet standard for creating data with optional signature and/or optional encryption whose payload holds JSON that asserts some number of claims. The tokens are signed either using a private secret or a public/private key.
* [Mongoose ODM](https://mongoosejs.com/) This makes it easy to write MongoDB validation by providing a straight-forward, schema-based solution to model to application data.
<hr>
### Sample Data: (User)

```json
{
     "name": "Müller",
     "email": "müller@gmail.com",
     "role": "Patient",
     "image": "https://i.ibb.co/jgntChz/Screenshot-2022-12-14-at-6-27-13-PM.png"
}
```
### Create a new User 
 Route:  api/v1/users (POST)
 Request body:
 ```json
 {
  "name": "Müller",
  "email": "müller@gmail.com",
  "role": "Patient",
  "image": "https://i.ibb.co/jgntChz/Screenshot-2022-12-14-at-6-27-13-PM.png"// Image for upload
}
```
 Response: The newly created user object.
 Response Sample Pattern:
```json
 {
      "success": true, 
      "statusCode":200,
      "message": "Users created successfully",
      "data": {
               "name": "Müller",
               "email": "müller@gmail.com",
               "role": "Patient",
               "image": "https://i.ibb.co/jgntChz/Screenshot-2022-12-14-at-6-27-13-PM.png"
              }, 
}
```        
### Get All Users

 Route:  api/v1/users?userType={Patient or Doctor} (GET)
 
 Response: The user's array of objects.
 
 Response Sample Pattern:
 
```json
  {
      "success": true, 
      "statusCode":200,
      "message": "Users retrieved successfully",
      "data": [{},{}], 
  }
```


### Get a Single User

Route:  /api/v1/users/:id (GET)

Request Param: :id

Response: The specified user object.

Response Sample Pattern:

```json
  {
      "success": true, 
      "statusCode":200,
      "message": "User retrieved successfully",
      "data": {}, 
  }
  ```  
  ### Delete a User

 Route:  /api/v1/users/:id ( DELETE)
 
 Request Param: :id
 
 Response:  The deleted user object.
 
 Response Sample Pattern:
 
```json
  {
      "success": true, 
      "statusCode":200,
      "message": "Uers deleted successfully",
      "data": {}, 
  }
```

### Create new appointment data

 Route:  api/v1/slots (POST)

Request body:

```json
 {
    "docEmail": "alfat.cse.21@gmail.com",
    "docSlot": [
        {
            "date": "Saturday, May 27, 2023",
            "slot": [
                "12.00 AM-02.00 PM",
                "03.00 Pm-04.00 PM"
            ]
        },
        {
            "date": "Friday, May 23, 2023",
            "slot": [
                "12.00 AM-02.00 PM",
                "03.00 Pm-04.00 PM"
            ]
        }
    ]
}

```
 
 Response: The newly created appointment data.

 Response Sample Pattern:

```json
 {
      "success": true, 
      "statusCode":200,
      "message": "Appointment data created successfully",
      "data":  {
                 "docEmail": "alfat.cse.21@gmail.com",
                 "docSlot": [
                                {
                                  "date": "Saturday, May 27, 2023",
                                  "slot": [
                                            "12.00 AM-02.00 PM",
                                            "03.00 Pm-04.00 PM"
                                          ]
                                },
                                {
                                "date": "Friday, May 23, 2023",
                                "slot": [
                                          "12.00 AM-02.00 PM",
                                          "03.00 Pm-04.00 PM"
                                        ]
                                }
                          ]
            }, 
  }
```
           
### Get all appointment option

 Route: api/v1/appointmentOptions (GET)

 Response: The array of objects.

 Response Sample Pattern:

```json
{
    "status": "Success",
    "message": "All Service Type Found",
    "data": [
        {
            "_id": "6385cfeef6afce75f83b4fc6",
            "name": "Teeth Orthodontics"
        },
        {
            "_id": "6385cfeef6afce75f83b4fc7",
            "name": "Cosmetic Dentistry"
        },
        {
            "_id": "6385cfeef6afce75f83b4fc8",
            "name": "Teeth Cleaning"
        },
        {
            "_id": "6385cfeef6afce75f83b4fc9",
            "name": "Cavity Protection"
        },
        {
            "_id": "6385cfeef6afce75f83b4fca",
            "name": "Pediatric Dental"
        },
        {
            "_id": "6385cfeef6afce75f83b4fcb",
            "name": "Oral Surgery"
        }
    ]
}
```
Route:  /api/v1/users?
Query parameters:  (Case Insensitive)
- page: The page number for pagination (e.g., ?page=1).
- limit: The number of cow listings per page (e.g., ?limit=10).
- searchTerm: The search query string for searching users (e.g., ?query=Dhaka). (Search Fields should be name, email, and userType) 
Response: An array of cow listing objects that match the provided filters, limited to the specified page and limit.
Response Sample Pattern:
```json
  {
      "success": true, 
      "statusCode":200,
      "message": "Users retrieved successfully",
      "meta": {
        "page": 3,
        "limit": 10,
        },
      "data": [
             {
               "name": "Müller",
               "email": "müller@gmail.com",
               "role": "Patient",
               "image": "https://i.ibb.co/jgntChz/Screenshot-2022-12-14-at-6-27-13-PM.png"
            }
        ]
 }
```
### Get a Single Booking

Route:  /api/v1/booking/:id (GET)

Request Param: :id

Response: The specified booking object.

Response Sample Pattern:

```json
  {
    "status": "Success",
    "message": "Bookings Found.",
    "data": {
        "_id": "648f6975c2ad6f6721a559d0",
        "patient_name": "habisdsbiiiöäüü",
        "patient_id": "63a029b84ccc9fde32696387",
        "patient_email": "maseattonima@gmail.com",
        "patient_Phone": 12345,
        "appointmentData": [
            {
                "doctor_email": "kori@gmail.comn",
                "treatment": "Tooth ",
                "price": 34,
                "AppointmentDate": "Monday, January 12,2023",
                "slot": "10-12",
                "_id": "648f6975c2ad6f6721a559d1"
            }
        ]
    }
}
```


### Post a Booking

 Route: api/v1/bookings (POST)
 
  Request body:
 ```json
 {
  "name": "Müller",
  "email": "müller@gmail.com",
  "role": "Patient",
  "image": "https://i.ibb.co/jgntChz/Screenshot-2022-12-14-at-6-27-13-PM.png"// Image for upload
}
```
 Response Sample Pattern:

```json
  {
      "success":  "Success", 
      "statusCode":200,
      "message": "Booking Confirmed.Please Check your email", 
  }

```  
### Post a Payment Intent 
 Route:  api/v1/create-payment-intent (POST)
 Request body:
 ```json
 {
  "price": 100,
}
```
 Response:Payment intent created
 
 Response Sample Pattern:

```json
{
    "status": "Success",
    "message": "Payment Intent Created",
    "clientSecret": Client Secret
}
```
### Post a Payment Information
 Route:  api/v1/payment (POST)
 Request body:
 ```json
{
        "price":1442,
        "transactionid": Trasaction ID,
        "bookingID": 23784546756625,
        "email":"alfaddst@g.com"
}
```
 Response:Payment intent created
 
 Response Sample Pattern:

```json
{
    "status": "Success",
    "message": "Payment Data Posted",
}
```   
### Error Handling:
Error Response Object include the following properties:
- success  →  false
- message → Error Type → Validation Error, Cast Error, Duplicate Entry
- errorMessages 
- stack

### Sample Error Response

```json
   {
    "success": false,
    "message": "E11000 duplicate key error collection: univerity-management.students index: email_1 dup key: { email: \"user2@gmail.com\" }",
    "errorMessages": [
        {
            "path": "",
            "message": "E11000 duplicate key error collection: univerity-management.students index: email_1 dup key: { email: \"user2@gmail.com\" }"
        }
    ],
    "stack": "MongoServerError: E11000 duplicate key error collection: univerity-management.students index: email_1 dup key: { email: \"user2@gmail.com\" }\n    at H:\\next-level-development\\university-management-auth-service\\node_modules\\mongodb\\src\\operations\\insert.ts:85:25\n    at H:\\next-level-development\\university-management-auth-service\\node_modules\\mongodb\\src\\cmap\\connection_pool.ts:574:11\n    at H:\\next-level-development\\university-writeOrBuffer (node:internal/streams/writable:391:12)"
}
```
