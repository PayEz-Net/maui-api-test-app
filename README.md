# PayEzMauiDemo Installation Guide

## Prerequisites
- Windows 10 or later
- Administrator privileges for certificate installation

## Installation Steps

### 1. Install the Certificate
1. Download the certificate:
```
https://github.com/PayEz-Net/maui-api-test-app/releases/download/untagged-07c2222454e65859dcce/PayEzMauiDemo_1.0.0.0_x64.cer
```

2. Install the certificate:
- Right-click `PayEzMauiDemo_1.0.0.0_x64.cer`
- Select "Install Certificate"
- Choose "Local Machine"
- Select "Place all certificates in the following store"
- Click "Browse"
- Select "Trusted Root Certification Authorities"
- Click "OK" to complete the wizard

### 2. Install the Application
1. Download and run the MSIX:
```
https://github.com/PayEz-Net/maui-api-test-app/releases/download/untagged-07c2222454e65859dcce/PayEzMauiDemo_1.0.0.0_x64.msix
```
2. If Windows Defender SmartScreen shows a warning:
- Click "More info"
- Click "Run anyway"
3. Click "Install" in the App Installer window

## Video Walkthrough
Watch our detailed usage walkthrough:
[PayEz API Test App Walkthrough](https://www.upsilonpayments.com/API-Test-Walkthrough.mp4)

## Uninstallation
To remove the application:
1. Open Windows Settings
2. Navigate to Apps → Apps & Features
3. Search for "PayEzMauiDemo"
4. Click the three dots (⋮)
5. Select "Uninstall"

## Troubleshooting
If you encounter installation issues:
- Ensure you've installed the certificate first
- Run the installer with administrator privileges
- Check Windows Event Viewer for detailed error messages
