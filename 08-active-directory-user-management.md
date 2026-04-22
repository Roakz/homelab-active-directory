# Active Directory User Creation and Domain Login

## Overview

This phase covers creating a domain user in Active Directory, logging into a client machine using that account, and understanding how user profiles are handled across domain-joined systems.

---

# Environment

* Domain: lab.local
* Domain Controller: DC01
* Client Machine: CLIENT01

---

# 1. Accessing Active Directory Users and Computers

## Purpose

Use administrative tools to manage users within the domain.

## Method

On DC01, the Active Directory Users and Computers console was opened:

```plaintext id="1q3lgc"
dsa.msc
```

## Outcome

The domain structure and built-in user accounts were visible and ready for management.

## Screenshots

* AD Users and Computers console open
![An image of Active Directory Users and Computers Console Open on the client machine](./ActiveDirectoryUserManagement/ADUsersComputers)

---

# 2. Creating a Domain User

## Purpose

Create a new user account that can authenticate against the domain.

## Steps

1. Navigate to:

   ```
   lab.local → Users
   ```
2. Right-click:

   ```
   Users → New → User
   ```
3. Enter user details:

   ```
   First Name: Rory
   Last Name: Bell
   User logon name: rbell
   ```
4. Set password:

   ```
   Password123!
   ```
5. Configure options:

   * Unticked: User must change password
   * Ticked: Password never expires (lab use)

## Outcome

A new domain user (`rbell`) was successfully created.

## Screenshots

* New user creation wizard
![An image of Active Directory User Creation Wizard GUI](./ActiveDirectoryUserManagement/UserContainerNewUser)
* User visible in AD list
![Domain User container shows the new created user on DC01](./ActiveDirectoryUserManagement/UserInList)
---

# 3. Logging in as Domain User

## Purpose

Verify that the newly created user can authenticate and log into a domain-joined client machine.

## Steps

1. On CLIENT01, sign out of the current session
2. Select "Other user" on login screen
3. Enter credentials:

```plaintext id="rt8jcl"
rbell
```

or

```plaintext id="m80pmt"
rbell@lab.local
```

4. Enter password

## Outcome

* Login successful
* User profile created on CLIENT01
* Desktop environment loaded

## Screenshots

* Login screen
* Successful desktop login

---

# 4. Verification

## Command

```powershell id="uhq36b"
whoami
```

## Expected Output

```plaintext id="zdb8wd"
lab\rbell
```

## Outcome

Confirmed authentication against the Active Directory domain.

## Screenshots

* Login Screen
![Login screen on client machine showing credentials being entered for newly created domain user](./ActiveDriectoryUserManagement/rbellLabLogin)
* whoami output
* ![Image showing the output of whoami on the client machine once it was logged in](./ActiveDirectoryUserManagement/whoamiClient)
---

# 5. User Profile Behaviour

## Observation

After logging in, a user profile was created on the client machine:

```plaintext id="hf7r9f"
C:\Users\rbell
```

## Explanation

By default, Active Directory does not store user profiles centrally.

Instead:

* Profiles are created locally on each machine
* Each domain-joined machine creates its own copy

## Example

* Login on CLIENT01 → profile created locally
* Login on another machine → new profile created

## Key Concept

| Component     | Location                |
| ------------- | ----------------------- |
| User identity | Active Directory (DC01) |
| User profile  | Local machine           |

---

# 6. Key Concepts Learned

* Domain users are created and managed centrally in Active Directory
* Domain authentication works across all joined machines
* User profiles are created locally by default
* Active Directory manages identity, not user environment
* Multiple login formats are supported (DOMAIN\user and user@domain)

---

# Summary

A domain user was successfully created and used to log into a domain-joined client machine. Authentication was verified, and the behaviour of local user profiles was observed and understood.

This demonstrates the core Active Directory workflow of user creation and authentication across systems.

---

# Next Steps

* Create Organizational Units (OUs)
* Organise users and computers
* Create security groups
* Configure file shares and permissions
* Apply Group Policy
