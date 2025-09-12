# @gladpros/dashboard

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A comprehensive dashboard module for GladPros applications, providing analytics, metrics, charts, and business intelligence components.

## 🚀 Features

- 📊 Interactive charts and graphs with Chart.js
- 📈 Real-time metrics and KPIs
- 🎯 Business intelligence dashboards
- 📱 Responsive dashboard components
- 🔄 Real-time data updates
- 🎨 Customizable widgets and layouts
- 📊 Advanced analytics and reporting
- 🔒 TypeScript support with full type safety

## 📦 Installation

```bash
npm install @gladpros/dashboard
# or
yarn add @gladpros/dashboard
# or
pnpm add @gladpros/dashboard
```

## 🛠️ Peer Dependencies

This package requires the following peer dependencies:

```json
{
  "react": "^18.0.0 || ^19.0.0",
  "react-dom": "^18.0.0 || ^19.0.0",
  "next": "^14.0.0 || ^15.0.0"
}
```

## 📋 Prerequisites

This module requires the following packages:
- `@gladpros/ui` - UI components library
- `@gladpros/auth` - Authentication module
- `@gladpros/proposals` - Proposals management
- `@gladpros/clients` - Client management

And database access for analytics data.

## 🎯 Usage

```tsx
import {
  DashboardProvider,
  useDashboard,
  DashboardCards,
  MetricsChart,
  RevenueChart
} from '@gladpros/dashboard'

function App() {
  return (
    <DashboardProvider>
      <MyDashboard />
    </DashboardProvider>
  )
}

function MyDashboard() {
  const { metrics, charts, loading } = useDashboard()

  if (loading) return <div>Loading dashboard...</div>

  return (
    <div>
      <DashboardCards metrics={metrics} />
      <MetricsChart data={charts.userGrowth} />
      <RevenueChart data={charts.revenue} />
    </div>
  )
}
```

## 📚 API Reference

### Components

#### DashboardCards
Overview cards displaying key metrics and KPIs.

```tsx
<DashboardCards
  metrics={dashboardMetrics}
  layout="grid"
/>
```

#### MetricsChart
Line/bar chart component for displaying metrics over time.

```tsx
<MetricsChart
  data={chartData}
  type="line"
  title="User Growth"
/>
```

#### RevenueChart
Specialized chart for revenue and financial data.

```tsx
<RevenueChart
  data={revenueData}
  currency="BRL"
  period="monthly"
/>
```

### Hooks

#### useDashboard
Main hook for dashboard data and operations.

```tsx
const {
  metrics,
  charts,
  loading,
  error,
  refreshData,
  exportData
} = useDashboard()
```

#### useMetrics
Hook for specific metrics operations.

```tsx
const {
  userMetrics,
  proposalMetrics,
  clientMetrics,
  dateRange,
  setDateRange
} = useMetrics()
```

### Types

#### DashboardMetrics
Main dashboard metrics interface.

```typescript
interface DashboardMetrics {
  totalUsers: number
  activeUsers: number
  totalProposals: number
  approvedProposals: number
  totalRevenue: number
  monthlyGrowth: number
  conversionRate: number
}
```

#### ChartData
Chart data structure for visualizations.

```typescript
interface ChartData {
  labels: string[]
  datasets: {
    label: string
    data: number[]
    backgroundColor?: string
    borderColor?: string
  }[]
}
```

## 🏗️ Development

### Prerequisites

- Node.js 18+
- npm, yarn, or pnpm

### Setup

```bash
# Clone the repository
git clone https://github.com/Gladiston-Porto/gladpros-dashboard.git
cd gladpros-dashboard

# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Run tests
npm test
```

### Available Scripts

- `npm run build` - Build the library
- `npm run dev` - Start development mode with watch
- `npm run lint` - Run ESLint
- `npm run test` - Run Jest tests
- `npm run type-check` - Run TypeScript type checking

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### Development Workflow

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Make your changes and add tests
4. Run the test suite: `npm test`
5. Submit a pull request

## 📄 License

MIT © GladPros Team

---

*📦 Primeira publicação automática - 12 de setembro de 2025*

## 🔗 Links

- [GitHub Repository](https://github.com/Gladiston-Porto/gladpros-dashboard)
- [Issues](https://github.com/Gladiston-Porto/gladpros-dashboard/issues)
- [Discussions](https://github.com/Gladiston-Porto/gladpros-dashboard/discussions)
- [Main GladPros Repository](https://github.com/Gladiston-Porto/GladPros)