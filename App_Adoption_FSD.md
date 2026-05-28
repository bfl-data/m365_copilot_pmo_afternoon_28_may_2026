# Functional Specification Document – App Adoption (DIY Servicing Feature)

## 1. Document Header
**Version:** 1.0  
**Date:** 28 May 2026  
**Status:** Draft  

---

## 2. Purpose and Scope
This document provides detailed functional specifications for the DIY servicing feature covering mobile and web platforms.

---

## 3. System Overview
Mobile + Web frontend integrating with backend APIs for service management and tracking.

---

## 4. Actors and Roles
- End User
- Admin
- Support Agent

---

## 5. Functional Specifications

### FR-01 Login and Access
- Authenticate users via credentials / OTP
- Redirect to dashboard on success

### FR-02 Service Catalogue
- Display list of available services
- Enable search and filters

### FR-03 Submit Requests
- Allow request submission with details
- Generate unique request ID

### FR-04 Guided Troubleshooting
- Step-by-step resolution guide
- Option to escalate to request

### FR-05 Track Requests
- Show request status timeline
- Enable filtering

---

## 6. Non-Functional Requirements
- Performance: <3 seconds
- Security: Encryption + RBAC
- Availability: 99.5%

---

## 7. Data Requirements
Entities: User, Service, Request, Troubleshooting Steps

---

## 8. Security
- Encrypted communication
- Role-based access

---

## 9. Notifications
- Triggered on submission and updates

---

## 10. Open Issues
- Communication channel not finalised
- SLA not defined

---

## 11. Glossary
- DIY: Do-It-Yourself servicing
