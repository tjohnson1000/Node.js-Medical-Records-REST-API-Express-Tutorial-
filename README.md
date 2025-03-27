# Node.js REST API for Medical Records – Express Tutorial

## Overview
This project follows a REST API tutorial for beginners to build a simple, **fully functional RESTful API** using **Node.js** and **Express**. The example centers around managing **patient and medical records**, with full **CRUD operations** and **header-based authentication**.

## Tools & Technologies
- **Node.js**
- **Express.js**
- **Postman** (for testing)
- **body-parser**
- **nodemon** (for auto-reloading)

## Core Features
1. **Express Server Setup** – Initializes Node project, sets up `index.js`.
2. **CRUD Routes** –
   - `GET /records` – View medical records
   - `POST /` – Add new patient
   - `PUT /` – Update patient phone number
   - `DELETE /` – Remove patient & records
3. **Mock Data Storage** – Patient data stored in JavaScript objects (using SSN as key).
4. **Authentication** – Uses request headers (`first name`, `last name`, `SSN`) to identify users.
5. **Status Codes** – Returns meaningful HTTP codes (200, 201, 404, etc.).
6. **Request Testing** – Verifies all endpoints using Postman.

## File Structure (example)
```
├── index.js               # Main Express app
├── package.json           # Dependencies
├── README.md              # Documentation
└── routes/
    ├── patientRoutes.js   # All CRUD endpoints
```

## Sample Code Snippet (Route Example)
```js
app.get('/records', (req, res) => {
  const { firstName, lastName, ssn } = req.headers;
  const patient = patients[ssn];
  if (patient && patient.firstName === firstName && patient.lastName === lastName) {
    res.status(200).send(patient.records);
  } else {
    res.status(404).send('Patient not found');
  }
});
```

## Conclusion
This REST API lab demonstrates how to use **Node.js and Express** to build a **real-world medical records API**, covering authentication, data operations, and error handling. Perfect for backend beginners or portfolio-ready full-stack demos.

---
**Author:** Travis Johnson  
**Company:** 10Digit Solutions LLC  
**GitHub Repository:** [Add link when available]
