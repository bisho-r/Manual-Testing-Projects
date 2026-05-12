# Test Charter 1: Login & Authentication Robustness

**Application**: https://www.saucedemo.com/  
**Session Duration**: 45 minutes  
**Date**: May 2026  
**Tester**: Bishwanath Rana  
**Mission**: Explore login functionality for security, usability, accessibility, and error handling issues.

### Areas Explored
- Valid / Invalid credentials
- Error message clarity and security (password masking)
- Accessibility (keyboard navigation, screen reader)
- Boundary values (very long username/password)
- Network interruption simulation
- Multiple failed login attempts

### Observations & Findings
1. **High** - Password is visible in plain text when copied from password field (security issue)
2. **Medium** - No rate limiting on failed login attempts
3. **Low** - Error message says "Epic sadface: Username and password do not match" – reveals too much information
4. **Positive** - Strong password masking by default

**Screenshots**: See `/Screenshots/login-issues/`
