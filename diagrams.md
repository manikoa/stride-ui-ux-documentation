# Architectural Diagrams

## Overview

This document contains architectural diagrams that visualize the key workflows and system interactions within the Stride platform. These diagrams provide a technical and user experience perspective on how different components interact, helping both developers and designers understand the overall architecture.

## Signup & Onboarding Flows

### Individual Signup Flow
```mermaid
sequenceDiagram
    actor User
    participant Frontend
    participant Auth Service
    participant User Service
    participant Database
    participant Email Service
    
    User->>Frontend: Clicks "Sign Up" / "Get Started"
    Frontend->>Frontend: Displays individual signup form
    User->>Frontend: Submits personal information
    Frontend->>Auth Service: POST /api/auth/register/
    Auth Service->>Database: Validate email uniqueness
    Auth Service->>Database: Create user (inactive)
    Auth Service->>User Service: Create user profile
    Auth Service->>Email Service: Send verification email
    Email Service-->>User: Verification email
    Auth Service-->>Frontend: Return registration success
    Frontend->>Frontend: Show verification instructions
    
    User->>Email Service: Clicks verification link
    Email Service->>Auth Service: Verify token
    Auth Service->>Database: Activate user account
    Auth Service-->>Frontend: Redirect to onboarding
    
    Frontend->>Frontend: Display onboarding flow
    User->>Frontend: Sets preferences (timezone, notifications)
    Frontend->>User Service: POST /api/users/preferences/
    User Service->>Database: Save user preferences
```