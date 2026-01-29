# ADR-014: Use Supabase RLS with Microsoft Entra ID for Authentication

## Introduction
This ADR documents the decision to integrate Microsoft Entra ID directly with Supabase Row Level Security (RLS), instead of using Supabase’s built-in SSO functionality, for enterprise user authentication.

---

## Prologue (Summary)

> **In the context of** an internal enterprise web application,  
> **facing** UX consistency requirements and existing user familiarity with Microsoft authentication,  
> **we decided for** Microsoft Entra ID–based authentication integrated with Supabase RLS,  
> **to achieve** a seamless and familiar login experience aligned with corporate standards,  
> **accepting** additional custom implementation effort and increased application complexity.

---

## Discussion (Context)

### Problem
The application required secure, role-based access control backed by Supabase while integrating with the organization’s existing Microsoft identity ecosystem. A consistent login experience was considered critical for user adoption.

### Forces at Play

- **Technical**
  - Supabase RLS required user identity claims for authorization
  - Need to map Entra ID users to database roles and policies
  - Token validation and session handling needed to be implemented manually

- **UX / Product**
  - Users are already accustomed to the Microsoft login popup
  - Supabase SSO would introduce a different UI/UX flow
  - Avoiding user confusion and support overhead was a priority

- **Organizational**
  - Microsoft Entra ID is the enterprise standard
  - Security team prefers centralized identity management
  - Willingness to accept some “JMT” (just-more-time) engineering cost

### Options Considered
- **Option A:** Supabase built-in SSO  
- **Option B:** Custom authentication with Microsoft Entra ID (Chosen)

---

## Solution (Decision)

We decided to authenticate users via **Microsoft Entra ID** and propagate identity and role claims into Supabase, enforcing authorization through **Row Level Security (RLS)** policies.

Implementation includes:
- Entra ID OAuth/OpenID Connect login flow
- Backend token validation and user mapping
- Custom JWT claims consumed by Supabase RLS
- Application-managed session lifecycle

**Why this works:**
- Preserves a familiar Microsoft login experience
- Aligns with enterprise identity and security standards
- Keeps authorization logic centralized at the database layer

---

## Consequences (Results)

### Positive
- Consistent UX with existing Microsoft-based applications
- Centralized identity management via Entra ID
- Fine-grained, database-enforced authorization using RLS

### Negative / Trade-offs
- Additional custom code for authentication and token handling
- Increased maintenance burden compared to Supabase SSO
- Longer initial delivery time (JMT impact)

### Long-Term Impact
The solution scales well for enterprise use and aligns with organizational standards, but requires ongoing ownership of custom authentication logic and periodic review as Supabase and Entra ID capabilities evolve.

---

## Status
☑ Accepted  

**Date:** <YYYY-MM-DD>  
**Owner:** <Team / Role>

---

### Notes
Supabase SSO may be reconsidered in the future if UX parity with Microsoft authentication improves or if organizational identity standards change.
