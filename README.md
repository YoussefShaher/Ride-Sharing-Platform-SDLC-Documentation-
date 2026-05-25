# Ride-Sharing Platform SDLC Documentation

A well-authored comprehensive Software Development Lifecycle (SDLC) blueprint for an Uber-scale architecture, mapping out functional requirements, risk threat modeling, and deployment strategies from planning through maintenance.

## 📋 Project Overview

This repository contains the complete Software Requirements Specification (SRS) and architectural documentation for a mobile-based Ride Booking System that connects riders with drivers for transportation services.

**Prepared by:**
- Youssef Shaher Shoukry (ID: 241015139)
- Ibrahim Mahmoud Mohamed (ID: 241015503)
- Aly Eldeen Ahmed (ID: 241016698)
- Youssef Mohamed Said (ID: 241015841)
- Youssef Ahmed Mohamed (ID: 241015925)

**Supervised by:** Dr. Ashraf Draz / Engineer Jana

---

## 📑 Table of Contents

1. [Introduction](#introduction)
2. [Overall Description](#overall-description)
3. [System Features](#system-features)
4. [External Interface Requirements](#external-interface-requirements)
5. [Non-Functional Requirements](#non-functional-requirements)
6. [System Diagrams](#system-diagrams)

---

## 🎯 Introduction

### Purpose
This document defines the software requirements for the Ride Booking System (RBS), a mobile-based application that connects riders with drivers for transportation services. It provides a detailed description of system functionality, constraints, and expected behavior.

### Intended Audience
- **Developers** → Implementation
- **Testers** → Validation
- **Project Managers** → Planning
- **Stakeholders** → Review

### Project Scope
The Ride Booking System is designed to:
- ✅ Allow users to request rides
- ✅ Match riders with nearby drivers
- ✅ Provide real-time trip tracking
- ✅ Handle secure payments

**Out of Scope:**
- Vehicle maintenance systems
- Offline ride booking

---

## 🔍 Overall Description

### Product Perspective
The system is a client-server mobile application integrated with:
- GPS services
- Payment gateways
- Cloud database
- External payment gateway for secure card payments

### Product Features
- User registration & login
- Ride request & matching
- Real-time tracking
- Payment processing
- Admin dashboard

### User Classes and Characteristics

#### Rider
- Basic mobile user
- Requests rides and pays
- Access to ride history and pricing

#### Driver
- Registered & verified
- Accepts and completes trips
- Manages availability status

#### Admin
- Full system access
- Manages users and trips
- Views analytics and reports

### Operating Environment
- **OS:** Android / iOS
- **Backend:** Cloud server
- **Database:** MySQL / Firebase
- **Internet:** Required

### Constraints
- Requires GPS-enabled devices
- Requires internet connection
- Must support real-time updates

---

## ✨ System Features

### 1. User Authentication (High Priority)
Allows users (riders & drivers) to securely log in.

**Functional Requirements:**
- FR-1: User shall be able to register
- FR-2: User shall be able to login
- FR-3: System shall validate credentials

### 2. Ride Request (High Priority)
Allows riders to request a ride.

**Functional Requirements:**
- FR-4: User shall be able to request ride
- FR-5: User shall accept/reject drivers
- FR-6: System shall show nearby drivers
- FR-7: System shall calculate fare

### 3. Ride Management (High Priority)
Handles trip lifecycle.

**Functional Requirements:**
- FR-8: Driver shall accept / reject rides
- FR-9: System shall track trip in real time
- FR-10: System shall mark trip as completed

### 4. Payment System (High Priority)
The payment system handles fare transactions between riders and drivers using secure payment methods integrated through an external payment gateway.

**Functional Requirements:**
- FR-11: The system shall process payments through an external payment gateway
- FR-12: The system shall support multiple payment methods
- FR-13: The system shall generate a receipt after each completed transaction
- FR-14: The system shall confirm whether a transaction is successful or failed
- FR-15: The system shall store payment details associated with each trip

---

## 🔌 External Interface Requirements

### User Interface
- Mobile app screens
- Dashboard
- Notifications

### Hardware Interface
- GPS sensors
- Smartphones

### Software Interface
- Payment APIs
- Maps API
- Database

### Communication Interface
- **Protocol:** HTTPS
- **Format:** JSON
- **Real-time updates:** WebSocket/Real-time database

---

## 📊 Non-Functional Requirements

### Performance Requirements
- The system should respond to user requests within 3 seconds under normal conditions
- The system should support many concurrent users without performance degradation
- The system should efficiently handle real-time ride requests and driver updates
- The system should minimize delay in location tracking and trip updates

### Security Requirements
- The system should encrypt user passwords using secure hashing algorithms
- The system should ensure secure authentications for all users (Rider, Driver, Admin)
- The system should use HTTPS for all data communication
- The system should protect user data from unauthorized access
- The system should not store sensitive payment information directly

### Reliability Requirements
- The system should maintain 99.9% uptime
- The system should recover automatically from system failures
- The system should ensure data consistency during unexpected shutdowns
- The system should handle errors gracefully without crashing

### Usability Requirements
- The system should provide a simple and user-friendly interface
- The system should ensure easy navigation across all features
- The system should allow users to complete key tasks in minimal steps
- The system should provide clear messages and feedback to users

### Scalability Requirements
- The system should be scaled to support increasing numbers of users and drivers
- The system should handle growth in ride requests without affecting performance

### Availability Requirements
- The system should be available 24/7 for users
- The system should minimize downtime during maintenance

### Maintainability Requirements
- The system should be easy to maintain and update
- The system should allow future feature enhancements without major refactoring

---

## 📐 System Diagrams

### 1. Activity Diagram
Illustrates the flow of activities from login through ride completion and payment.

![Activity Diagram](https://github.com/YoussefShaher/Ride-Sharing-Platform-SDLC-Documentation-/raw/main/images/activity-diagram.jpg)

This diagram shows:
- User login process
- Ride request and driver availability check
- Driver assignment and acceptance
- Ride tracking and completion
- Payment processing (Cash or Card)
- Trip finalization

### 2. Class Diagram
Shows the structural relationships between system entities.

![Class Diagram](https://github.com/YoussefShaher/Ride-Sharing-Platform-SDLC-Documentation-/raw/main/images/class-diagram.jpg)

Key Classes:
- **Admin:** Manages users and system operations
- **User:** Base class for all users with authentication methods
- **Rider:** Extends User, handles ride requests
- **Driver:** Extends User, manages ride acceptance and completion
- **Ride:** Contains ride details, location, and fare information
- **Payment:** Processes transaction details
- **Location:** Tracks geographic information

### 3. Sequence Diagram
Depicts the interaction flow between system components during key operations.

![Sequence Diagram](https://github.com/YoussefShaher/Ride-Sharing-Platform-SDLC-Documentation-/raw/main/images/sequence-diagram.jpg)

Interactions include:
- Rider requesting a ride through the App
- System notifying available drivers
- Driver acceptance and confirmation
- Real-time ride tracking and updates
- Payment processing through the Payment Gateway
- Ride completion and confirmation

### 4. State Diagram
Represents the different states of a ride throughout its lifecycle.

![State Diagram](https://github.com/YoussefShaher/Ride-Sharing-Platform-SDLC-Documentation-/raw/main/images/state-diagram.jpg)

Ride States:
- **Requested:** Initial state when rider requests a ride
- **Accepted:** Driver accepts the ride request
- **In Progress:** Ride is currently active
- **Completed:** Ride successfully finished
- **Cancelled:** Ride was cancelled by either party
- **Paid:** Payment has been processed

---

## 🛠️ Technical Stack

- **Frontend:** Android / iOS
- **Backend:** Cloud Server (Node.js / Django / Spring Boot)
- **Database:** MySQL / Firebase (Real-time)
- **APIs:** Google Maps API, Payment Gateway API
- **Communication:** HTTPS, WebSocket, JSON

---

## 📝 Document Conventions

- **Shall** → Mandatory requirements
- **Should** → Recommended requirements

**Abbreviations:**
- **FR** = Functional Requirement
- **NFR** = Non-Functional Requirement

---

## 📚 References

- IEEE SRS Standards
- Mobile Application Design Guidelines
- RESTful API Design Best Practices
- Software Engineering Documentation Standards

---

## 🚀 Getting Started

For implementation details and technical specifications, refer to the complete SRS document included in this repository.

---

## 📞 Contact & Support

For questions or clarifications regarding this SDLC documentation, please contact the project team members listed above.

---

**Last Updated:** 2026-05-25

*This is a comprehensive blueprint for an enterprise-scale ride-sharing platform with complete SDLC documentation including requirements, architecture, and design patterns.*
