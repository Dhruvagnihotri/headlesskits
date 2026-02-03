# HeadlessKit Examples

This directory contains example projects showing how to use HeadlessKit packages.

## 🔐 Authentication Examples

### Basic Examples
- [`auth-fullstack/`](./auth-fullstack) - Complete React + Flask authentication
- [`auth-react-only/`](./auth-react-only) - React with existing backend
- [`auth-flask-only/`](./auth-flask-only) - Flask backend for any frontend

### Advanced Authentication
- [`oauth-integration/`](./oauth-integration) - Google & Microsoft OAuth
- [`mfa-example/`](./mfa-example) - Multi-factor authentication
- [`custom-user-model/`](./custom-user-model) - Extended user model with custom fields
- [`role-based-access/`](./role-based-access) - RBAC implementation

## 💳 Payment Examples

### Basic Examples
- [`payments-fullstack/`](./payments-fullstack) - Complete React + Flask payments
- [`payments-react-only/`](./payments-react-only) - React with existing backend
- [`payments-flask-only/`](./payments-flask-only) - Flask backend for any frontend

### Advanced Payments
- [`subscription-service/`](./subscription-service) - Recurring subscriptions
- [`one-time-payment/`](./one-time-payment) - Single transaction
- [`webhook-handling/`](./webhook-handling) - Payment gateway webhooks
- [`invoice-generation/`](./invoice-generation) - Generate invoices

## 🔄 Combined Examples

- [`combined/`](./combined) - Authentication + Payments together
- [`saas-template/`](./saas-template) - Complete SaaS boilerplate
- [`ecommerce/`](./ecommerce) - E-commerce platform
- [`multi-tenant/`](./multi-tenant) - Multi-tenant application

## 🎨 Framework Integrations

### Frontend Frameworks
- [`vue-integration/`](./vue-integration) - Vue.js with HeadlessKit
- [`nextjs-integration/`](./nextjs-integration) - Next.js with HeadlessKit
- [`svelte-integration/`](./svelte-integration) - Svelte with HeadlessKit

### Backend Frameworks
- [`django-backend/`](./django-backend) - Django with React frontend
- [`fastapi-backend/`](./fastapi-backend) - FastAPI with React frontend
- [`express-backend/`](./express-backend) - Express.js with React frontend

## 🚀 Running Examples

Each example has its own README with setup instructions. General steps:

### 1. Clone the repository
```bash
git clone https://github.com/Dhruvagnihotri/headlesskits.git
cd headlesskits/examples/[example-name]
```

### 2. Install dependencies

**Backend:**
```bash
cd backend
pip install -r requirements.txt
```

**Frontend:**
```bash
cd frontend
npm install
```

### 3. Configure environment

Copy `.env.example` to `.env` and add your configuration:
```bash
cp .env.example .env
# Edit .env with your settings
```

### 4. Run the application

**Backend:**
```bash
cd backend
python app.py
```

**Frontend:**
```bash
cd frontend
npm start
```

## 📝 Example Structure

Each example follows this structure:

```
example-name/
├── README.md           # Setup instructions
├── backend/            # Flask backend
│   ├── app.py
│   ├── requirements.txt
│   └── .env.example
├── frontend/           # React frontend
│   ├── src/
│   ├── package.json
│   └── .env.example
└── docker-compose.yml  # Optional Docker setup
```

## 🤝 Contributing Examples

Have a useful example? We'd love to include it!

1. Fork the repository
2. Create your example in `examples/your-example-name/`
3. Follow the standard structure above
4. Add a clear README
5. Submit a pull request

See [CONTRIBUTING.md](../CONTRIBUTING.md) for more details.

## 📚 Need Help?

- Read the [Getting Started Guide](../docs/getting-started.md)
- Check the [Documentation](../docs/)
- Ask in [GitHub Discussions](https://github.com/Dhruvagnihotri/headlesskits/discussions)
- Open an [Issue](https://github.com/Dhruvagnihotri/headlesskits/issues)

---

## 🎯 Quick Links

- [HeadlessKit Hub](https://github.com/Dhruvagnihotri/headlesskits)
- [React Auth](https://github.com/Dhruvagnihotri/react-headless-auth)
- [Flask Auth](https://github.com/Dhruvagnihotri/flask-headless-auth)
- [React Payments](https://github.com/Dhruvagnihotri/react-headless-payments)
- [Flask Payments](https://github.com/Dhruvagnihotri/flask-headless-payments)
