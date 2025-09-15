# OrderMe Test Automation Suite 🍔

Automated UI testing suite for the OrderMe food ordering application using [Maestro](https://maestro.mobile.dev/) framework.

## 📱 Overview

This repository contains automated test flows for the OrderMe mobile application due to Engenious University challenge, covering critical user journeys including authentication, restaurant browsing, table reservations, and food ordering.

## 🚀 Prerequisites

- **Maestro CLI** installed ([Installation Guide](https://maestro.mobile.dev/getting-started/installing-maestro))
- **iOS Simulator** (for iOS testing) or **Android Emulator/Device** (for Android testing)
- **OrderMe app** installed on the simulator/device
- Test credentials for Facebook login

## 📂 Project Structure
```
orderMe/
├── flows/
│   ├── login.yaml                 # App launch and initial setup
│   ├── loginWithFacebook.yaml     # Facebook authentication flow
│   ├── loginProcess.yaml          # Complete login orchestration
│   ├── tableReservation.yaml      # Restaurant table booking flow
│   ├── detectTable.yaml           # Table detection and selection
│   ├── orderFood.yaml             # Food ordering workflow
│   └── reservation.yaml           # Reservation confirmation subflow
├── screenshots/                    # Test execution screenshots
└── README.md
```

## 🔧 Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/orderme-tests.git
cd orderme-tests
```

2. Install Maestro:
```bash
# macOS
brew tap mobile-dev-inc/tap
brew install maestro

# Other platforms
curl -fsSL "https://get.maestro.mobile.dev" | bash
```

3. Verify installation:
```bash
maestro --version
```

## 🏃‍♂️ Running Tests

### Run all tests:
```bash
maestro test flows/
```

### Run specific test flow:
```bash
maestro test flows/loginProcess.yaml
maestro test flows/tableReservation.yaml
maestro test flows/orderFood.yaml
```

### Run with specific device:
```bash
# iOS Simulator
maestro test flows/loginProcess.yaml --device="iPhone 16 Pro"

# Android
maestro test flows/loginProcess.yaml --device="Pixel_7"
```

## 🔑 Test Data

Test credentials are configured in the flows:
- **Facebook Test Account**: `zkpedymhza_1614299001@tfbnw.net`
- **Password**: `orderme12345`

⚠️ **Note**: Never commit real credentials. Use test accounts only.

### Debug Mode
```bash
maestro studio
```
Opens interactive UI explorer for element inspection and flow recording.

## 📊 CI/CD Integration

### GitHub Actions Example
```yaml
name: UI Tests
on: [push, pull_request]

jobs:
  test:
    runs-on: macos-latest
    steps:
      - uses: actions/checkout@v2
      - name: Install Maestro
        run: |
          brew tap mobile-dev-inc/tap
          brew install maestro
      - name: Run Tests
        run: maestro test flows/
```

## 📄 License

This project is licensed under the MIT License - see LICENSE file for details.

## 🔗 Resources

- [Maestro Documentation](https://maestro.mobile.dev/)
- [OrderMe App Repository](https://github.com/yourusername/orderme)
- [Engenious University](https://university.engenious.io/courses)
- [Test Reports](./reports/)

---

**Last Updated**: September 2024  
**Maestro Version**: 1.36.0  
**App Version**: com.assesment.orderme v1.0.0
