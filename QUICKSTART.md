# Quick Start Guide - AI Testing Project

## Get Started in 15 Minutes

This guide will help you quickly set up and run your first AI-powered tests.

---

## Prerequisites

- Node.js 18+ installed
- Git installed
- GitHub account (for Copilot)
- Basic knowledge of JavaScript/TypeScript

---

## Step 1: Clone and Setup (2 minutes)

```bash
# Clone the repository
git clone https://github.com/yourusername/ai-testing-ecommerce.git
cd ai-testing-ecommerce

# Install dependencies
npm install

# Copy environment template
cp .env.example .env
```

## Step 2: Configure AI Tools (3 minutes)

Edit `.env` file:

```bash
# Required: Get free API keys from respective services
APPLITOOLS_API_KEY=your_applitools_key_here
OPENAI_API_KEY=your_openai_key_here

# Optional: For advanced features
SNYK_API_KEY=your_snyk_key_here
DATADOG_API_KEY=your_datadog_key_here
```

### Get Free API Keys:

1. **Applitools** (Visual Testing): https://applitools.com/users/register
   - Free tier: 100 screenshots/month
   
2. **OpenAI** (GPT-4): https://platform.openai.com/signup
   - Free tier: $5 credit
   
3. **Snyk** (Security): https://snyk.io/signup
   - Free tier: Unlimited scans for open source

## Step 3: Run Sample Application (3 minutes)

```bash
# Start MongoDB (using Docker)
docker run -d -p 27017:27017 --name mongodb mongo:latest

# Start the application
npm run dev

# Application will be available at:
# Frontend: http://localhost:3000
# Backend API: http://localhost:5000
```

## Step 4: Run Your First AI-Powered Test (5 minutes)

### Option A: Visual Testing with Applitools

```bash
# Run visual tests
npm run test:visual

# AI will:
# ✓ Capture screenshots
# ✓ Compare with baseline
# ✓ Detect visual differences
# ✓ Generate report
```

**Expected Output:**
```
Applitools Eyes Test Results:
✓ Homepage layout - PASSED
✓ Product page responsive - PASSED
✓ Checkout flow - PASSED

View detailed results: https://eyes.applitools.com/...
```

### Option B: AI Test Generation with Copilot

1. Open VS Code
2. Install GitHub Copilot extension
3. Open `tests/example.test.js`
4. Type a comment: `// Test user can add product to cart`
5. Press Enter and watch Copilot generate the test!

```javascript
// Test user can add product to cart
// Copilot will generate:
test('user can add product to cart', async () => {
  await page.goto('/products/123');
  await page.click('[data-testid="add-to-cart"]');
  const cartCount = await page.textContent('[data-testid="cart-count"]');
  expect(cartCount).toBe('1');
});
```

### Option C: AI API Testing

```bash
# AI generates and runs API tests
npm run test:api-ai

# AI will:
# ✓ Read OpenAPI spec
# ✓ Generate test cases
# ✓ Create test data
# ✓ Execute tests
# ✓ Validate responses
```

### Option D: Security Scan with AI

```bash
# Run AI-powered security scan
npm run test:security

# AI will:
# ✓ Scan for vulnerabilities
# ✓ Check dependencies
# ✓ Suggest fixes
# ✓ Generate report
```

---

## Step 5: View Results (2 minutes)

### Test Report Dashboard

```bash
# Open test report
npm run report:open

# Opens AI-powered test dashboard showing:
# - Test execution results
# - AI insights
# - Failure analysis
# - Recommendations
```

### Sample Report Output:

```
╔════════════════════════════════════════════════════════════╗
║           AI-Powered Test Execution Report                 ║
╠════════════════════════════════════════════════════════════╣
║ Total Tests: 150                                           ║
║ Passed: 147 (98%)                                          ║
║ Failed: 3 (2%)                                             ║
║ Execution Time: 3m 45s (vs 15m traditional)                ║
╠════════════════════════════════════════════════════════════╣
║ AI Insights:                                               ║
║ • Detected 2 flaky tests (auto-fixed)                      ║
║ • Found 1 security vulnerability (high severity)           ║
║ • Recommended 5 performance optimizations                  ║
║ • Predicted 95% confidence for production deployment       ║
╚════════════════════════════════════════════════════════════╝
```

---

## Common Scenarios

### Scenario 1: Generate Tests from User Story

```bash
# Use GPT-4 to generate tests
npm run ai:generate-tests

# Follow prompts:
# > Enter user story: "As a user, I want to checkout with credit card"
# 
# AI generates:
# ✓ 15 test cases
# ✓ Test data
# ✓ Edge cases
# ✓ Security tests
```

### Scenario 2: Visual Regression Testing

```bash
# Set baseline
npm run test:visual:baseline

# Make UI changes
# ... edit src/components/ProductCard.tsx ...

# Run visual comparison
npm run test:visual

# AI detects:
# ⚠ Product card layout changed (3px shift)
# ⚠ Color difference detected (#FF0000 vs #FF0001)
```

### Scenario 3: Performance Testing with AI

```bash
# Run AI-powered load test
npm run test:performance

# AI will:
# ✓ Analyze production patterns
# ✓ Generate realistic user behavior
# ✓ Execute load test
# ✓ Provide recommendations

# Output:
# Current capacity: 500 concurrent users
# AI recommendation: Scale to handle 750 users
# Bottleneck: Database query on /api/products
```

---

## Next Steps

### 1. Explore Sample Tests

```bash
# View pre-built AI test examples
ls tests/ai-examples/

# Run specific example
npm run test tests/ai-examples/visual-regression.test.js
```

### 2. Integrate with CI/CD

```bash
# Setup GitHub Actions
cp .github/workflows/ai-testing.example.yml .github/workflows/ai-testing.yml

# Commit and push
git add .
git commit -m "Add AI testing pipeline"
git push

# AI tests run automatically on every commit
```

### 3. Customize for Your Project

```bash
# Edit configuration
vim ai-testing-config.yml

# Customize:
# - Test coverage targets
# - AI model preferences
# - Performance thresholds
# - Security rules
```

---

## Troubleshooting

### Issue: Applitools API Key Invalid

```bash
# Verify API key
echo $APPLITOOLS_API_KEY

# Re-generate key at: https://eyes.applitools.com/app/admin/teams
```

### Issue: Tests Running Slowly

```bash
# Enable AI test selection (runs only relevant tests)
npm run test:smart

# This uses AI to select tests based on code changes
# Result: 70% faster execution
```

### Issue: Flaky Tests

```bash
# Run AI flaky test detector
npm run ai:detect-flaky

# AI analyzes test history and provides fixes
# Example output:
# ⚠ login.test.js is flaky (15% failure rate)
# 💡 AI Recommendation: Add explicit wait for element
```

---

## Learn More

### Documentation

1. [Full Installation Guide](./docs/INSTALLATION.md) - Detailed setup instructions
2. [AI Testing Points](./docs/AI_TESTING_POINTS.md) - Where to use AI in testing
3. [Test Scenarios](./docs/TEST_SCENARIOS.md) - Practical examples
4. [Architecture](./docs/ARCHITECTURE.md) - System design

### Video Tutorials

- [AI Visual Testing Demo](https://youtube.com/...)
- [AI Test Generation Walkthrough](https://youtube.com/...)
- [Performance Testing with AI](https://youtube.com/...)

### Community

- [GitHub Discussions](https://github.com/yourusername/ai-testing-ecommerce/discussions)
- [Discord Community](https://discord.gg/...)
- [Stack Overflow Tag](https://stackoverflow.com/questions/tagged/ai-testing)

---

## Cheat Sheet

### Quick Commands

```bash
# Run all AI tests
npm run test:ai:all

# Visual testing
npm run test:visual

# API testing
npm run test:api

# Security scan
npm run test:security

# Performance test
npm run test:performance

# Generate test report
npm run report:generate

# AI test generation
npm run ai:generate

# Smart test selection
npm run test:smart
```

### AI Tool Quick Reference

| Tool | Purpose | Command |
|------|---------|---------|
| Applitools | Visual Testing | `npm run test:visual` |
| GPT-4 | Test Generation | `npm run ai:generate` |
| Snyk | Security Scan | `npm run test:security` |
| k6 | Performance Test | `npm run test:performance` |
| Cypress AI | E2E Testing | `npm run test:e2e` |

---

## Tips for Success

1. **Start Small**: Begin with visual testing or test generation
2. **Use AI Suggestions**: Trust AI-generated tests but verify critical paths
3. **Monitor Costs**: Use free tiers initially, upgrade as needed
4. **Iterate**: AI improves with more data and feedback
5. **Combine Tools**: Use multiple AI tools for comprehensive coverage

---

## Support

Need help? 

- 📧 Email: support@example.com
- 💬 Chat: [Discord Community](https://discord.gg/...)
- 🐛 Issues: [GitHub Issues](https://github.com/yourusername/ai-testing-ecommerce/issues)
- 📚 Docs: [Full Documentation](./docs/)

---

**Ready to experience AI-powered testing? Start with Step 1! 🚀**
