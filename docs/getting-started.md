# Getting Started with HeadlessKit

Welcome to HeadlessKit! This guide will help you set up authentication and/or payments in your application.

## Choose Your Stack

HeadlessKit packages work independently or together. Choose what you need:

### Option 1: Authentication Only
- **Frontend:** [`@headlesskits/react-headless-auth`](https://github.com/Dhruvagnihotri/react-headless-auth)
- **Backend:** [`flask-headless-auth`](https://github.com/Dhruvagnihotri/flask-headless-auth)

### Option 2: Payments Only
- **Frontend:** [`@headlesskits/react-headless-payments`](https://github.com/Dhruvagnihotri/react-headless-payments)
- **Backend:** [`flask-headless-payments`](https://github.com/Dhruvagnihotri/flask-headless-payments)

### Option 3: Both
Use all packages together for a complete solution.

---

## Quick Start: Authentication

### 1. Install Packages

**Backend:**
```bash
pip install flask-headless-auth
```

**Frontend:**
```bash
npm install @headlesskits/react-headless-auth
```

### 2. Backend Setup (Flask)

```python
from flask import Flask
from flask_headless_auth import AuthSvc

app = Flask(__name__)

# Basic configuration
app.config['SECRET_KEY'] = 'your-secret-key-change-this'
app.config['JWT_SECRET_KEY'] = 'your-jwt-secret-change-this'
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///app.db'

# Initialize authentication (20+ routes automatically created!)
auth = AuthSvc(app)

if __name__ == '__main__':
    app.run(debug=True)
```

### 3. Frontend Setup (React)

```tsx
import React from 'react';
import { AuthProvider, useAuth } from '@headlesskits/react-headless-auth';

// Wrap your app
function App() {
  return (
    <AuthProvider config={{ apiBaseUrl: 'http://localhost:5000' }}>
      <AppContent />
    </AuthProvider>
  );
}

// Use authentication anywhere
function AppContent() {
  const { user, login, logout, signup, isAuthenticated, isLoading } = useAuth();

  if (isLoading) return <div>Loading...</div>;

  if (!isAuthenticated) {
    return (
      <div>
        <h1>Login</h1>
        <button onClick={() => login('user@example.com', 'password123')}>
          Login
        </button>
        <button onClick={() => signup('user@example.com', 'password123')}>
          Sign Up
        </button>
      </div>
    );
  }

  return (
    <div>
      <h1>Welcome {user.email}!</h1>
      <button onClick={logout}>Logout</button>
    </div>
  );
}

export default App;
```

### 4. Run Your App

**Backend:**
```bash
python app.py
```

**Frontend:**
```bash
npm start
```

Visit `http://localhost:3000` and you have full authentication! 🎉

---

## Quick Start: Payments

### 1. Install Packages

**Backend:**
```bash
pip install flask-headless-payments
```

**Frontend:**
```bash
npm install @headlesskits/react-headless-payments
```

### 2. Backend Setup

```python
from flask import Flask
from flask_headless_payments import PaymentSvc

app = Flask(__name__)
app.config['SECRET_KEY'] = 'your-secret-key'

# Configure payment gateway
app.config['PAYMENT_GATEWAY'] = 'stripe'  # or 'paypal', etc.
app.config['STRIPE_SECRET_KEY'] = 'your-stripe-secret-key'

payments = PaymentSvc(app)

if __name__ == '__main__':
    app.run(debug=True)
```

### 3. Frontend Setup

```tsx
import { PaymentProvider, PaymentForm } from '@headlesskits/react-headless-payments';

function CheckoutPage() {
  const handleSuccess = (payment) => {
    console.log('Payment successful!', payment);
    // Redirect to success page
  };

  const handleError = (error) => {
    console.error('Payment failed:', error);
  };

  return (
    <PaymentProvider config={{ apiBaseUrl: 'http://localhost:5000' }}>
      <div>
        <h1>Checkout</h1>
        <PaymentForm
          amount={1999}  // $19.99 in cents
          currency="USD"
          onSuccess={handleSuccess}
          onError={handleError}
        />
      </div>
    </PaymentProvider>
  );
}
```

---

## Using Both Together

See the [integration guide](./integration/combined.md) for using authentication and payments together.

---

## Next Steps

- **Authentication:** Read the [React Auth Guide](./auth/react.md) or [Flask Auth Guide](./auth/flask.md)
- **Payments:** Read the [React Payments Guide](./payments/react.md) or [Flask Payments Guide](./payments/flask.md)
- **Examples:** Check out the [examples folder](../examples) for complete apps
- **Security:** Review [security best practices](./auth/security.md)

---

## Need Help?

- 📖 [Full Documentation](../README.md)
- 💬 [GitHub Discussions](https://github.com/Dhruvagnihotri/headlesskits/discussions)
- 🐛 [Report Issues](https://github.com/Dhruvagnihotri/headlesskits/issues)
- 📧 [Email Support](mailto:dagni@umich.edu)
