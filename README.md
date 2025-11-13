# Smart-Parking-System-AWS
A fully serverless Smart Parking System built using AWS Lambda, DynamoDB, SNS, and API Gateway. It provides real-time parking slot availability, vehicle entry/exit tracking, user notifications, admin management, and automated reporting. Built as part of a Cognizant internship project.

# Smart Parking System – AWS Serverless Real-Time Parking Management  
### Cognizant Internship Project | Python + AWS Lambda + DynamoDB + SNS

This project is a **Smart Parking Management System** designed using AWS serverless technologies.  
It provides **real-time parking status**, manages vehicle entry/exit, sends user notifications, and generates analytical reports — without the need to manage servers.

This system helps reduce congestion and improves parking efficiency in urban environments.

---

##  Problem Statement

Urban areas face serious challenges due to increasing numbers of vehicles and limited parking resources.  
Drivers waste time searching for available parking spots, causing:

- Traffic congestion  
- Fuel wastage  
- Stress & delays  
- Inefficient use of parking spaces  

**Solution:**  
A real-time, automated, serverless parking management system that updates slot status instantly and notifies users when slots become available.

---

##  Key Features

### **1. Parking Slot Entry/Exit System (Python + AWS Lambda)**
- Simulates vehicle entry & exit  
- Assigns nearest available slot  
- Frees slot on vehicle departure  
- Logs timestamps  
- Updates DynamoDB in real-time  

### **2. Real-Time Slot Availability API (API Gateway + Lambda)**
- REST API for current slot availability  
- Filter by zone/floor  
- Returns estimated wait time if full  
- Syncs with DynamoDB instantly  

### **3. User Notification Module (SNS + Lambda)**
- Users subscribe to notifications  
- Alerts sent when a slot becomes available  
- Booked slot expiration alerts  
- Area-wise notification preferences  

### **4. Admin Dashboard (Lambda)**
- View live occupancy  
- Add / edit / delete parking zones  
- Mark slots as unavailable  
- Manual override for slot assignment  
- View system logs & alerts  

### **5. Reporting & Analytics (Scheduled Lambda + S3/Redshift/CSV)**
- Daily usage summary  
- Peak hour detection  
- Entry/exit trends  
- Slot utilization heatmap  
- Exportable reports  

---

##  Technologies Used

### **Programming Language**
- Python (Boto3)

### **AWS Services**
- AWS Lambda  
- Amazon DynamoDB  
- Amazon SNS  
- Amazon API Gateway  
- CloudWatch Logs  
- (Optional) Redshift / S3 for analytics  

### **Others**
- JSON  
- REST APIs  
- Agile methodology  

---

##  System Architecture

Vehicle Entry/Exit → Lambda → DynamoDB
↓
Real-Time Availability API (API Gateway)
↓
User Notifications (SNS)
↓
Admin Dashboard (Lambda)
↓
Reporting & Analytics (Scheduled Lambda)


---

## 📂 Project Structure (Recommended GitHub Structure)

Smart-Parking-System/
│
├── lambdas/
│ ├── entry_exit/
│ ├── availability_api/
│ ├── notifications/
│ ├── admin/
│ └── reporting/
│
├── dynamodb/
│ └── tables.json
│
├── docs/
│ ├── Smart Parking - Case Study.pdf
│ ├── architecture-diagram.png
│ └── api-samples.md
│
├── frontend/
│ └── (Your UI code from front-end.zip)
│
└── README.md


---

##  Sample API Payload

### **Vehicle Entry**
```json
{
  "vehicle_id": "MH12AB1234",
  "entry_time": "2025-06-18T09:00:00",
  "lot_id": "A1"
}


