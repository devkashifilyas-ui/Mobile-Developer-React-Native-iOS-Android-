
# React Native + Expo Mobile Architecture Demo

This repository contains an interactive architecture demonstration for a production-grade mobile application built with React Native, Expo, and NestJS APIs.

The purpose of this demo is to show how a scalable mobile application can be structured, deployed, and maintained across both iOS and Android using a single codebase.

The architecture focuses on stability, maintainability, predictable build pipelines, and clean separation between application layers.

---

# Overview

This demo illustrates a complete mobile application stack including:

React Native application architecture
Expo SDK managed workflow
NestJS backend API integration
JWT authentication and secure token storage
Push notification architecture
Expo EAS cloud build pipeline
Mobile CI/CD automation
App Store and Google Play release process
Performance optimization strategies

The dashboard included in this repository visually explains how these systems work together in a production environment.

---

# Technology Stack

Mobile Framework
React Native with Expo SDK

Backend Integration
NestJS REST APIs

Authentication
JWT tokens with encrypted storage using Expo SecureStore

Networking
Axios API client with interceptors and retry logic

State Management
Zustand and React Query

Navigation
Expo Router

Push Notifications
Expo Push Service with APNs and FCM

Build System
Expo EAS Build

Deployment Targets
Apple App Store
Google Play Store

---

# Mobile Application Architecture

Example structure:

mobile-app/
src/
screens/
components/
navigation/
services/
hooks/
store/
api/

Each layer has a clear responsibility.

Screens handle UI logic.
Components contain reusable UI elements.
Services contain business logic and API communication.
Hooks encapsulate reusable application behavior.
The API layer manages network requests and authentication.

This separation keeps the codebase maintainable as features expand.

---

# Authentication Flow

Authentication is handled using JWT tokens issued by the NestJS backend.

Login process:

1. User submits credentials
2. Mobile app sends request to NestJS authentication endpoint
3. Backend validates credentials and returns JWT token
4. Token stored securely using Expo SecureStore
5. Axios interceptor automatically attaches token to API requests

---

# API Integration

The mobile app communicates with NestJS APIs through a centralized API client.

Key features:

Axios client with request interceptors
Automatic JWT attachment
Retry handling for transient failures
Token refresh support

React Query manages request caching, loading states, and background refetching.

---

# Push Notification Architecture

Push notifications use the Expo Push Notification system.

Workflow:

1. Device registers for push notifications
2. Expo push token generated
3. Token stored in backend user record
4. Backend triggers push notifications on events
5. Expo routes notifications through APNs or FCM
6. Mobile device receives notification

---

# Build and Deployment Pipeline

The project uses Expo Application Services (EAS).

EAS provides:

Cloud builds for iOS and Android
TestFlight distribution
Google Play internal testing releases
Production store submissions

This eliminates the need for local build environments.

---

# Mobile CI/CD Pipeline

Recommended workflow:

Developer pushes code to repository
GitHub Actions triggers automated pipeline
EAS build generates preview builds
QA tests builds
Approved builds promoted to production

This ensures predictable releases.

---

# Release Management

Two update types:

OTA Updates
JavaScript or UI updates can be delivered instantly using Expo Updates without store approval.

Store Releases
Native changes require a new build and store submission.

---

# Performance Optimization

Performance strategies include:

Lazy loading screens
Memoized components
Efficient list rendering
API response caching
Background task processing

---

# Running the Demo

This repository includes a standalone HTML architecture demo.

To run locally:

1. Download the repository
2. Open the file:

rn-mobile-architecture-demo.html

The dashboard will open in your browser.
