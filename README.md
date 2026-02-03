# HeadlessKit

<div align="center">
  
  <h3>Production-ready, self-hosted solutions for authentication and payments</h3>
  <p>The free alternative to Auth0, Clerk, and Stripe</p>
  
  [![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
  [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
  
  <p>
    <a href="#-packages">Packages</a> •
    <a href="#-quick-start">Quick Start</a> •
    <a href="#-documentation">Documentation</a> •
    <a href="#-examples">Examples</a> •
    <a href="#-contributing">Contributing</a>
  </p>
  
</div>

---

## 💡 Why HeadlessKit?

Building modern web apps requires authentication and payment processing. The options today:

- **Paid SaaS:** Auth0 ($2,880/year) + Stripe (2.9% + $0.30/transaction) = 💸💸💸
- **Build yourself:** Weeks of development + security concerns + maintenance
- **HeadlessKit:** Free, self-hosted, production-ready, MIT licensed ✨

## 📦 Packages

### 🔐 Authentication

Build complete authentication systems in minutes. Includes JWT, OAuth, MFA, RBAC, password reset, email verification, and more.

| Package | Description | Install | Links |
|---------|-------------|---------|-------|
| **React Auth** | Client-side auth with smart cookie fallback | `npm i @headlesskits/react-headless-auth` | [📁 Repo](https://github.com/Dhruvagnihotri/react-headless-auth) • [📦 NPM](https://www.npmjs.com/package/@headlesskits/react-headless-auth) • [📖 Docs](./docs/auth/react.md) |
| **Flask Auth** | Backend with 20+ routes in one line | `pip install flask-headless-auth` | [📁 Repo](https://github.com/Dhruvagnihotri/flask-headless-auth) • [🐍 PyPI](https://pypi.org/project/flask-headless-auth/) • [📖 Docs](./docs/auth/flask.md) |

**Key Features:**
- ✅ JWT authentication with automatic token refresh
- ✅ Smart cookie fallback (httpOnly cookies → localStorage)
- ✅ OAuth (Google, Microsoft, more coming)
- ✅ Multi-factor authentication (MFA/2FA)
- ✅ Role-based access control (RBAC)
- ✅ Email verification & password reset
- ✅ Rate limiting & security headers
- ✅ Works independently or together

### 💳 Payments

Accept payments without Stripe's fees. Process credit cards, subscriptions, and one-time payments.

| Package | Description | Install | Links |
|---------|-------------|---------|-------|
| **React Payments** | Payment forms and components | `npm i @headlesskits/react-headless-payments` | [📁 Repo](https://github.com/Dhruvagnihotri/react-headless-payments) • [📦 NPM](https://www.npmjs.com/package/@headlesskits/react-headless-payments) • [📖 Docs](./docs/payments/react.md) |
| **Flask Payments** | Payment processing backend | `pip install flask-headless-payments` | [📁 Repo](https://github.com/Dhruvagnihotri/flask-headless-payments) • [🐍 PyPI](https://pypi.org/project/flask-headless-payments/) • [📖 Docs](./docs/payments/flask.md) |

**Key Features:**
- ✅ Credit card processing
- ✅ Subscription management
- ✅ Webhook handling
- ✅ Payment forms with validation
- ✅ PCI compliance helpers
- ✅ Multiple payment gateways
- ✅ Works independently or together

---

## 🚀 Quick Start

### Authentication Only

**Backend (Flask):**
```python
from flask import Flask
from flask_headless_auth import AuthSvc

app = Flask(__name__)
app.config['SECRET_KEY'] = 'your-secret-key'
app.config['JWT_SECRET_KEY'] = 'jwt-secret-key'
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///app.db'

# THIS IS THE MAGIC LINE 🪄
auth = AuthSvc(app)  # 20+ routes instantly!

if __name__ == '__main__':
    app.run()
```

**Frontend (React):**
```tsx
import { AuthProvider, useAuth } from '@headlesskits/react-headless-auth';

// Wrap your app
function App() {
  return (
    <AuthProvider config={{ apiBaseUrl: 'http://localhost:5000' }}>
      <YourApp />
    </AuthProvider>
  );
}

// Use anywhere
function Dashboard() {
  const { user, logout, isAuthenticated } = useAuth();
  
  if (!isAuthenticated) return <LoginPage />;
  
  return (
    <div>
      <h1>Welcome {user.email}!</h1>
      <button onClick={logout}>Logout</button>
    </div>
  );
}
```

**Done!** Full authentication in less than 50 lines.

### Payments Only

**Backend (Flask):**
```python
from flask import Flask
from flask_headless_payments import PaymentSvc

app = Flask(__name__)
# ... config ...

payments = PaymentSvc(app)  # Payment routes ready!
```

**Frontend (React):**
```tsx
import { PaymentProvider, PaymentForm } from '@headlesskits/react-headless-payments';

function CheckoutPage() {
  return (
    <PaymentProvider config={{ apiBaseUrl: 'http://localhost:5000' }}>
      <PaymentForm 
        amount={1999} 
        onSuccess={(payment) => console.log('Payment successful!', payment)}
      />
    </PaymentProvider>
  );
}
```

### Both Together

See the [Full Stack Example](./examples/fullstack) for authentication + payments integration.

---

## 📊 Comparison

| Feature | HeadlessKit | Auth0 + Stripe | NextAuth + Stripe | Clerk + Stripe |
|---------|-------------|----------------|-------------------|----------------|
| **Setup Time** | ⚡ **2 minutes** | 30 min | 45 min | 20 min |
| **Annual Cost** | ✅ **$0** | **$2,880+** | **$0+** fees | **$300+** fees |
| **Auth included** | ✅ | ✅ | ✅ | ✅ |
| **Payments included** | ✅ | ❌ (Stripe) | ❌ (Stripe) | ❌ (Stripe) |
| **Transaction Fees** | ✅ **$0** | 2.9% + $0.30 | 2.9% + $0.30 | 2.9% + $0.30 |
| **Self-hosted** | ✅ | ❌ | ✅ | ❌ |
| **Vendor Lock-in** | ✅ **None** | ❌ High | ⚠️ Medium | ❌ High |
| **Smart Cookie Fallback** | ✅ | ❌ | ❌ | ❌ |
| **Custom User Models** | ✅ | ❌ | ✅ | ❌ |

---

## 📖 Documentation

### Getting Started
- [Installation Guide](./docs/getting-started.md)
- [Architecture Overview](./docs/architecture.md)
- [Migration Guide](./docs/migration.md)

### Authentication
- [React Auth Guide](./docs/auth/react.md)
- [Flask Auth Guide](./docs/auth/flask.md)
- [OAuth Setup](./docs/auth/oauth.md)
- [Security Best Practices](./docs/auth/security.md)
- [API Reference](./docs/auth/api-reference.md)

### Payments
- [React Payments Guide](./docs/payments/react.md)
- [Flask Payments Guide](./docs/payments/flask.md)
- [Payment Gateways](./docs/payments/gateways.md)
- [Webhooks](./docs/payments/webhooks.md)
- [API Reference](./docs/payments/api-reference.md)

### Integration
- [Auth + Payments Together](./docs/integration/combined.md)
- [Using with Other Backends](./docs/integration/backends.md)
- [Using with Other Frontends](./docs/integration/frontends.md)

---

## 💼 Real-World Usage

HeadlessKit powers production applications:

### [PDFCourt.com](https://pdfcourt.com) - Legal Document Processing
- Custom user models with subscription tiers
- Quota tracking per user
- Payment processing for premium features
- Self-hosted for data compliance

### [ShuffleTurn.com](https://shuffleturn.com) - Gaming Platform
- OAuth integration (Google, Microsoft)
- Analytics via lifecycle hooks
- Custom user fields for gaming stats
- In-app purchases

**Using HeadlessKit in production?** [Let us know!](https://github.com/Dhruvagnihotri/headlesskits/discussions)

---

## 🎨 Examples

### Basic Examples
- [Auth Only - Full Stack](./examples/auth-fullstack)
- [Auth Only - React](./examples/auth-react-only)
- [Auth Only - Flask](./examples/auth-flask-only)
- [Payments Only - Full Stack](./examples/payments-fullstack)
- [Payments Only - React](./examples/payments-react-only)
- [Payments Only - Flask](./examples/payments-flask-only)

### Advanced Examples
- [Auth + Payments Combined](./examples/combined)
- [Multi-tenant SaaS](./examples/multi-tenant)
- [E-commerce Platform](./examples/ecommerce)
- [Subscription Service](./examples/subscriptions)
- [Mobile App Backend](./examples/mobile-backend)

### Framework Integrations
- [Vue.js Integration](./examples/vue-integration)
- [Next.js Integration](./examples/nextjs-integration)
- [Django Backend](./examples/django-backend)
- [FastAPI Backend](./examples/fastapi-backend)

---

## 🌟 Features

### Authentication Features
- ✅ JWT authentication with automatic token refresh
- ✅ Smart cookie fallback (industry-first!)
- ✅ OAuth (Google, Microsoft, GitHub coming soon)
- ✅ Multi-factor authentication (MFA/2FA)
- ✅ Role-based access control (RBAC)
- ✅ Email verification
- ✅ Password reset with time-limited tokens
- ✅ Rate limiting
- ✅ Token blacklisting
- ✅ Session management
- ✅ Custom user models
- ✅ Lifecycle hooks
- ✅ Framework-agnostic core

### Payment Features
- ✅ Credit card processing
- ✅ Subscription management
- ✅ One-time payments
- ✅ Recurring billing
- ✅ Webhook handling
- ✅ Payment forms with validation
- ✅ Multiple payment gateways
- ✅ Refund handling
- ✅ Invoice generation
- ✅ Customer portal
- ✅ PCI compliance helpers

---

## 🤝 Contributing

We love contributions! Whether it's:

- 🐛 Bug reports
- 💡 Feature requests
- 📖 Documentation improvements
- 🔧 Code contributions

See our [Contributing Guide](./CONTRIBUTING.md) to get started.

### Development Setup

```bash
# Clone the repo
git clone https://github.com/Dhruvagnihotri/headlesskits.git
cd headlesskits

# Install dependencies (if running examples)
npm install  # for React packages
pip install -r requirements.txt  # for Flask packages
```

---

## 📚 Resources

- 📰 [Blog Post: Building HeadlessKit](https://dev.to/dhruv_agnihotri_064dad7e4/i-built-a-free-auth0-alternative-that-gives-you-20-routes-in-one-line-of-code-28nl)
- 💬 [GitHub Discussions](https://github.com/Dhruvagnihotri/headlesskits/discussions)
- 🐛 [Issue Tracker](https://github.com/Dhruvagnihotri/headlesskits/issues)
- 📧 [Email](mailto:dagni@umich.edu)

---

## 🗺️ Roadmap

### Q1 2026
- [ ] Vue.js SDK for authentication
- [ ] Svelte SDK for authentication
- [ ] Magic links (passwordless auth)
- [ ] WebAuthn/Passkeys support
- [ ] GitHub OAuth provider
- [ ] Apple OAuth provider

### Q2 2026
- [ ] Express.js backend for authentication
- [ ] FastAPI backend for authentication
- [ ] React Native SDK
- [ ] Flutter SDK
- [ ] Admin dashboard UI
- [ ] Stripe payment gateway integration

### Future
- [ ] More OAuth providers (LinkedIn, Twitter, etc.)
- [ ] Biometric authentication
- [ ] Passwordless SMS auth
- [ ] Email service (Headless Mail?)
- [ ] Analytics service (Headless Analytics?)

**Want to contribute to the roadmap?** Open a [discussion](https://github.com/Dhruvagnihotri/headlesskits/discussions)!

---

## 📄 License

MIT License - see [LICENSE](./LICENSE) for details.

---

## 🙏 Acknowledgments

Built by [@Dhruvagnihotri](https://github.com/Dhruvagnihotri) with inspiration from the open-source community.

Special thanks to all [contributors](https://github.com/Dhruvagnihotri/headlesskits/graphs/contributors)!

---

## ⭐ Star History

If HeadlessKit helps you, please consider:

- ⭐ Starring the repos on GitHub
- 🐛 Reporting issues or suggesting features
- 💬 Joining our [Discussions](https://github.com/Dhruvagnihotri/headlesskits/discussions)
- 🔄 Sharing on social media

---

<div align="center">
  <p>Made with ❤️ by indie developers, for indie developers</p>
  <p>No venture capital • No pricing tiers • No vendor lock-in</p>
  <p><strong>Just great open-source software</strong></p>
</div>
