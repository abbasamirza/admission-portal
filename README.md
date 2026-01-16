# 🎓 Admission Portal

A console-based user authentication system built in C++ as part of an Object-Oriented Programming (OOP) project. This application provides secure account management with features like NIC-based identification, password validation, and admin verification.

## 📋 Overview

This Admission Portal is a command-line application that handles user registration and authentication using National Identity Card (NIC) numbers as unique identifiers. The system implements robust validation, secure password handling, and admin verification through random password generation.

## ✨ Features

### Authentication System
- **Login & Signup**: Complete user authentication flow with NIC-based identification
- **Password Security**: 
  - Password masking during input
  - Length validation (8-24 characters)
  - Support for alphanumeric and special characters
- **NIC Validation**: 13-digit NIC number verification with real-time input feedback
- **Account Management**:  Persistent storage using file-based system

### User Experience
- **Maximized Console Window**: Automatic full-screen display for better visibility
- **Color-Coded Messages**: 
  - Red for errors
  - Green for success
  - Blue for headers
- **Input Validation**: Real-time character-by-character validation for all inputs
- **Error Handling**: Maximum 3 attempts for password entry with clear feedback

### Admin Features
- **Admin Verification**: Random password generation for admin account creation
- **Secure Admin Registration**: 13-character alphanumeric password verification

### Smart Navigation
- Seamless transition between login and signup flows
- Intelligent error recovery with menu navigation
- Account existence checking before operations

## 🏗️ Architecture

### Object-Oriented Design

```
User (Base Class)
├── Properties: name, NIC, password
└── Methods: getters/setters

OutputScreen (Display Management)
├── Console manipulation
├── Window maximization
└��─ Formatted message display
```

### Key Components
- **User Class**: Encapsulates user data with proper encapsulation
- **OutputScreen Class**: Handles all console output formatting and styling
- **File Management**: Text-based storage (`Users.txt`) for user credentials
- **Admin Security**:  Separate file (`Admin Random.txt`) for admin verification

## 🚀 Usage

### Prerequisites
- Windows OS (uses Windows-specific libraries:  `windows.h`, `conio.h`)
- C++ compiler (MinGW, MSVC, or similar)

### Compilation

```bash
g++ main.cpp -o admission-portal. exe
```

### Running the Program

```bash
./admission-portal.exe
```

## 📖 Program Flow

### Main Menu
```
1. Login
2. Signup
3. Forgot Password
4. Exit
```

### Login Flow
1. Enter 13-digit NIC number
2. Enter password (masked with asterisks)
3. System validates credentials from `Users.txt`
4. Maximum 3 password attempts allowed
5. Success:  Display login confirmation
6. Failure: Option to signup with entered NIC

### Signup Flow
1. Enter 13-digit NIC number (validated)
2. Check if NIC already exists
3. Enter name (1-30 alphabetic characters)
4. Create password (8-24 characters)
5. Admin verification (optional):
   - System generates random 13-character password
   - Admin must enter the displayed password
   - Maximum 3 verification attempts
6. Account created and saved to file

## 🔒 Security Features

- **Password Masking**: All password inputs displayed as asterisks
- **NIC Uniqueness**:  Prevents duplicate account creation
- **Input Sanitization**: Character-by-character validation
- **Attempt Limiting**: Maximum 3 tries for password/verification
- **Admin Verification**: Random password generation for admin accounts

## 📁 File Structure

```
admission-portal/
├── Program/
│   └── main.cpp              # Main application code
├── Users.txt                 # User credentials storage (auto-generated)
├── Admin Random.txt          # Admin verification password (auto-generated)
├── Project Flow. txt          # Project documentation
├── FAST-NU ADMISSION PORTAL. docx  # Detailed project report
└── README.md                 # This file
```

## 🎨 UI Features

- **ASCII Box Borders**: Decorative header with box characters
- **Centered Text**: All messages properly aligned
- **Dynamic Spacing**: Responsive to console width
- **Animated Success Messages**: Character-by-character display with delays
- **Custom Window Title**: "ADMISSION PORTAL"

## 🛠️ Technical Details

### Input Handling
- Real-time character capture using `_getch()`
- Backspace support for error correction
- Enter key submission
- Type-specific validation (digits, alphabets, special characters)

### Data Storage Format
```
Name,NIC_Number,Password
```

### Constants Used
```cpp
#define LOGIN 1
#define SIGNUP 2
#define FORGOT 3
#define EXIT 4
#define ENTER 13
#define BACKSPACE 8
#define BOX 178
#define NOTEXISTS -1
```

## 📝 Validation Rules

| Input Field | Requirements |
|------------|-------------|
| NIC Number | Exactly 13 digits |
| Name | 1-30 characters (letters, spaces, hyphens only) |
| Password | 8-24 characters (alphanumeric + special chars) |
| Admin Code | Exactly 13 characters (auto-generated) |

## 🎯 Future Enhancements

- Role-based access (Admin, Teacher, Student)
- Password recovery functionality
- Encrypted password storage
- Database integration
- Cross-platform compatibility
- Password strength indicator
- Email/phone verification

## 👤 Author

**Abbas Amirza** ([@abbasamirza](https://github.com/abbasamirza))

## 📅 Project Information

- **Created**: April 21, 2023
- **Last Updated**: January 16, 2026
- **Course**: Object-Oriented Programming (OOP) - Semester 2
- **Institution**:  FAST-NU

## 📄 License

This project is available for educational purposes. 

---

**Note**: This project was developed as an academic assignment to demonstrate OOP concepts including encapsulation, file handling, and user input validation in C++. 
