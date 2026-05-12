# Exploratory Testing Portfolio

**Objective**: Uncover hidden defects, usability issues, and edge cases not covered by scripted testing.

### Applications Tested
1. **SauceDemo** (E-commerce)
2. **OrangeHRM Demo** (recommended addition)
3. **https://the-internet.herokuapp.com/** (great for exploratory)

### Testing Approach (Session-Based Testing)

- **Time-boxed sessions** (30-60 mins)
- **Charters** with specific focus
- **Note-taking** during session
- **Bug reporting** with severity & priority

### Sample Test Charters

**Charter 1**: Login & Authentication Robustness
- Focus: Security, Usability, Accessibility
- Duration: 45 mins
- Major Findings: [list 3-4 issues]

**Charter 2**: Checkout Flow (SauceDemo)
- Focus: Payment simulation, Error recovery, Mobile responsiveness

**Charter 3**: Data Integrity & Boundary Testing

### Key Defects Found (Examples)

| ID | Severity | Summary | Application | Status |
|----|----------|---------|-------------|--------|
| EXP-01 | High | Password visible in plain text | SauceDemo | Open |
| EXP-02 | Medium | No loading indicator on slow networks | OrangeHRM | Fixed |

→ View full bug reports in [Bug-Reports-Exploratory.md](Bug-Reports-Exploratory.md)
