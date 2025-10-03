# Lab 4: Gas Absorption Status Tracking System

A comprehensive web-based laboratory status tracking and grade management system for the Unit Operations Laboratory II at Chulalongkorn University. This system provides real-time monitoring of lab progress, secure score access for students, and detailed analytics for instructors.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [System Architecture](#system-architecture)
- [Pages & Functionality](#pages--functionality)
- [Data Sources](#data-sources)
- [Technologies Used](#technologies-used)
- [Installation & Setup](#installation--setup)
- [Usage Guide](#usage-guide)
- [Security Features](#security-features)
- [Development Information](#development-information)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This application serves as a digital hub for **Lab 4: Gas Absorption** in the course **2306452 Unit Operations Laboratory II**. It enables seamless tracking of laboratory progress, secure distribution of grades, and comprehensive analytics for both students and instructors.

**Course Information:**
- **Instructor:** Asst. Prof. Dr. Pichaya In-na
- **Teaching Assistant:** Mr. Kantaphan Punnaanan
- **Institution:** Department of Chemical Technology, Faculty of Science, Chulalongkorn University

## ✨ Features

### 🔍 **Real-time Status Monitoring**
- Live tracking of laboratory completion status across all groups
- Visual indicators for submission status (Safety, Prelab, Full Report, Calculations)
- Due date monitoring with overdue alerts
- Comprehensive statistics dashboard

### 🔐 **Secure Score Access**
- Student authentication using Student ID and Group verification
- Temporary access codes with expiration for enhanced security
- Human verification system to prevent automated access
- Individual and group score breakdowns

### 📊 **Advanced Analytics**
- Interactive charts and visualizations
- Performance distribution analysis
- Group comparison metrics
- Individual student progress tracking
- Statistical analysis with normal distribution curves

### 📱 **Responsive Design**
- Mobile-first approach with Tailwind CSS
- Cross-device compatibility
- Thai language support with proper font rendering
- Accessible design with ARIA labels and keyboard navigation

## 🏗️ System Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   index.html    │    │  scores.html    │    │  admin.html     │
│   (Main Status) │    │ (Score Access)  │    │ (Admin Portal)  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         └───────────────────────┼───────────────────────┘
                                 │
                    ┌─────────────────┐
                    │   CSV Data      │
                    │   Sources       │
                    └─────────────────┘
```

## 📄 Pages & Functionality

### 1. **Main Status Page** (`index.html`)
- **Purpose:** Public dashboard showing overall lab progress
- **Features:**
  - Real-time status table with group information
  - Statistics summary (Total, Completed, Pending, Overdue)
  - Quick access buttons for Scores and Admin login
  - Keyboard shortcuts (Ctrl+R, Ctrl+S, Ctrl+A, ?)
  - Auto-refresh capabilities

### 2. **Score Access Page** (`scores.html`)
- **Purpose:** Secure student score viewing portal
- **Features:**
  - Student ID validation (653XXXXXXX format)
  - Group selection and verification
  - Human verification challenge
  - Temporary access code generation (8-character, 1-minute expiry)
  - Detailed score breakdown (Performance, Oral Exam, Prelab, Group Report)
  - Performance analysis and group comparison

### 3. **Admin Portal** (`admin.html`)
- **Purpose:** Comprehensive analytics and management interface
- **Features:**
  - Multi-tab interface (Status, Group Stats, Individual Stats)
  - Interactive charts and visualizations
  - Detailed student performance analysis
  - Group comparison metrics
  - Statistical analysis with distribution curves
  - Individual student detail modals

## 📊 Data Sources

The system integrates multiple CSV data sources:

| File | Purpose | Key Fields |
|------|---------|------------|
| `452-Check List-KTP.csv` | Main status tracking | Status, Group, Safety, Prelab, Full Report, Calculation, Due, Over Due |
| `452-Full Report.csv` | Group report grades | Theory, Results, Appendix, Discussion scores |
| `452-Group-Name.csv` | Student-group mapping | ID, Name, Group |
| `452-Performance.csv` | Lab performance scores | Total (10) points |
| `452-Oral Exam.csv` | Oral examination scores | Oral Exam (20) points |
| `452-Prelab.csv` | Pre-lab preparation scores | Total (20) points |

## 🛠️ Technologies Used

### **Frontend**
- **HTML5** - Semantic markup and structure
- **Tailwind CSS** - Utility-first CSS framework for responsive design
- **JavaScript (ES6+)** - Modern JavaScript with async/await patterns

### **Libraries & APIs**
- **Papa Parse** - Robust CSV parsing with error handling
- **Chart.js** - Interactive charts and data visualizations
- **Google Fonts** - Sukhumvit Set font for Thai language support
- **Google Analytics** - User behavior tracking and analytics

### **Features**
- **Progressive Web App** capabilities
- **Cache management** with 5-minute expiration
- **Retry mechanisms** for network resilience
- **Error handling** with user-friendly messages

## 🚀 Installation & Setup

### Prerequisites
- Modern web browser with JavaScript enabled
- Web server (for local development) or static hosting

### Quick Start
1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/452-lab4-status.git
   cd 452-lab4-status
   ```

2. **Serve the files:**
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Node.js
   npx serve .
   
   # Or simply open index.html in a browser
   ```

3. **Access the application:**
   - Main Status: `http://localhost:8000/`
   - Admin Portal: `http://localhost:8000/admin.html`
   - Score Access: `http://localhost:8000/scores.html`

## 📖 Usage Guide

### For Students
1. Navigate to the **Scores** page
2. Enter your Student ID (format: 653XXXXXXX)
3. Select your group number
4. Complete the human verification challenge
5. Copy the generated access code
6. Enter the code to view your detailed scores

### For Instructors
1. Use **Admin Login** with credentials: `admin` / `@dmin`
2. Explore the three main tabs:
   - **Status**: Overview of lab completion
   - **Group Stats**: Group performance analytics
   - **Individual Stats**: Student-level analysis

### Keyboard Shortcuts
- `Ctrl+R` - Reload data
- `Ctrl+S` - Access Scores page
- `Ctrl+A` - Admin login
- `?` - Show help modal

## 🔒 Security Features

- **Student ID Validation**: Format verification (653XXXXXXX)
- **Group Verification**: Cross-reference with student database
- **Human Verification**: Math challenge to prevent bots
- **Temporary Access Codes**: 8-character codes with 1-minute expiry
- **Secure Admin Access**: Username/password authentication
- **Input Sanitization**: Protection against malicious inputs

## 👨‍💻 Development Information

### **Developer**
**Kantaphan Punnaanan (KTP)**
- Website: [kantaphan.netlify.app](https://kantaphan.netlify.app/)
- Organization: [NIAB LAB](https://niab-lab.works/)
- Email: Kantaphan.P@chula.ac.th

### **Code Structure**
```
├── index.html          # Main status dashboard
├── scores.html         # Student score access portal
├── admin.html          # Admin analytics portal
├── ct_logo.png         # University logo
├── 452-*.csv          # Data source files
└── README.md          # This documentation
```

### **Key Design Patterns**
- **Modular JavaScript** with clear separation of concerns
- **Event-driven architecture** for user interactions
- **Cache-first strategy** for performance optimization
- **Progressive enhancement** for accessibility
- **Mobile-first responsive design**

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

### Development Guidelines
1. Follow existing code style and patterns
2. Test on multiple devices and browsers
3. Ensure Thai language compatibility
4. Maintain accessibility standards
5. Update documentation as needed

## 📄 License

This project is developed for educational purposes at Chulalongkorn University. All rights reserved.

---

**© 2025 Department of Chemical Technology, Faculty of Science, Chulalongkorn University**

*Developed with ❤️ for 2306452 Unit Operations Laboratory II - Lab 4 Gas Absorption*