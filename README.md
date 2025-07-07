// ============================
// Vite + React + Tailwind Boilerplate for Financial Web App
// ============================

// 1. Create your Vite app:
// npm create vite@latest finance-tracker-frontend -- --template react
// cd finance-tracker-frontend
// npm install

// 2. Install Tailwind CSS:
// npm install -D tailwindcss postcss autoprefixer
// npx tailwindcss init -p

// Edit tailwind.config.js:
// content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"]

// src/index.css
/* Add this to index.css */
@tailwind base;
@tailwind components;
@tailwind utilities;


// ============================
// src/main.jsx
// ============================

import React from 'react'
import ReactDOM from 'react-dom/client'
import { BrowserRouter } from 'react-router-dom'
import App from './App'
import './index.css'

ReactDOM.createRoot(document.getElementById('root')).render(
  <BrowserRouter>
    <App />
  </BrowserRouter>
)


// ============================
// src/App.jsx
// ============================

import React from 'react'
import Sidebar from './components/Sidebar'
import Navbar from './components/Navbar'
import { Routes, Route } from 'react-router-dom'
import Dashboard from './pages/Dashboard'
import Transactions from './pages/Transactions'
import Budget from './pages/Budget'
import Investments from './pages/Investments'
import AIInsights from './pages/AIInsights'

const App = () => {
  return (
    <div className="flex h-screen">
      <Sidebar />
      <div className="flex-1 flex flex-col">
        <Navbar />
        <main className="p-6 overflow-auto">
          <Routes>
            <Route path="/" element={<Dashboard />} />
            <Route path="/transactions" element={<Transactions />} />
            <Route path="/budget" element={<Budget />} />
            <Route path="/investments" element={<Investments />} />
            <Route path="/ai-insights" element={<AIInsights />} />
          </Routes>
        </main>
      </div>
    </div>
  )
}

export default App


// ============================
// src/components/Sidebar.jsx
// ============================

import React from 'react'
import { NavLink } from 'react-router-dom'

const Sidebar = () => {
  const links = [
    { name: 'Dashboard', path: '/' },
    { name: 'Transactions', path: '/transactions' },
    { name: 'Budget', path: '/budget' },
    { name: 'Investments', path: '/investments' },
    { name: 'AI Insights', path: '/ai-insights' },
  ]

  return (
    <aside className="w-64 bg-gray-800 text-white min-h-screen">
      <h1 className="text-2xl font-bold p-4">Finance Tracker</h1>
      <nav className="flex flex-col space-y-2 p-4">
        {links.map(link => (
          <NavLink
            key={link.path}
            to={link.path}
            className={({ isActive }) =>
              isActive
                ? 'bg-gray-700 px-3 py-2 rounded'
                : 'hover:bg-gray-700 px-3 py-2 rounded'
            }
          >
            {link.name}
          </NavLink>
        ))}
      </nav>
    </aside>
  )
}

export default Sidebar


// ============================
// src/components/Navbar.jsx
// ============================

import React from 'react'

const Navbar = () => {
  return (
    <header className="bg-white shadow px-6 py-4 flex justify-between items-center">
      <h2 className="text-xl font-semibold">Finance Dashboard</h2>
      <div className="text-gray-600">User Profile</div>
    </header>
  )
}

export default Navbar


// ============================
// src/pages/Dashboard.jsx
// ============================

import React from 'react'

const Dashboard = () => {
  return (
    <div>
      <h1 className="text-2xl font-bold mb-4">Dashboard</h1>
      <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
        <div className="bg-green-100 p-4 rounded">Balance Sheet Card</div>
        <div className="bg-blue-100 p-4 rounded">Profit & Loss Card</div>
        <div className="bg-yellow-100 p-4 rounded">Budget Card</div>
      </div>
      <div className="mt-6">
        <div className="bg-white shadow p-4 rounded">Pie Chart Placeholder</div>
      </div>
      <div className="mt-6">
        <div className="bg-white shadow p-4 rounded">Recent Transactions Table Placeholder</div>
      </div>
      <div className="mt-6">
        <div className="bg-purple-100 p-4 rounded">AI Suggestions Box</div>
      </div>
    </div>
  )
}

export default Dashboard


// ============================
// src/pages/Transactions.jsx
// ============================

import React from 'react'

const Transactions = () => {
  return (
    <div>
      <h1 className="text-2xl font-bold mb-4">Transactions</h1>
      <p>Transaction Table or CRUD operations will go here.</p>
    </div>
  )
}

export default Transactions


// ============================
// src/pages/Budget.jsx
// ============================

import React from 'react'

const Budget = () => {
  return (
    <div>
      <h1 className="text-2xl font-bold mb-4">Budget</h1>
      <p>Budget table and charts will go here.</p>
    </div>
  )
}

export default Budget


// ============================
// src/pages/Investments.jsx
// ============================

import React from 'react'

const Investments = () => {
  return (
    <div>
      <h1 className="text-2xl font-bold mb-4">Investments</h1>
      <p>Investments list and performance charts will go here.</p>
    </div>
  )
}

export default Investments


// ============================
// src/pages/AIInsights.jsx
// ============================

import React from 'react'

const AIInsights = () => {
  return (
    <div>
      <h1 className="text-2xl font-bold mb-4">AI Insights</h1>
      <p>AI-generated suggestions and analytics will go here.</p>
    </div>
  )
}

export default AIInsights
