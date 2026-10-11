# HomeFolio Family Finances

Build HomeFolio — Premium Family Finance Management System

Act as a senior product designer, fintech UX architect, and experienced React engineer. Build a polished, responsive, full-stack-ready website called HomeFolio, a family finance management system for collaboratively tracking household finances.

Do not produce a generic SaaS admin dashboard. The interface should feel like a carefully art-directed financial product inspired by Linear, Vercel, Raycast, and premium digital banking products.

1. Core visual identity

Create two complete, carefully designed themes:

Dark theme — default

Obsidian background: #09090B

Dark violet surface: #120E1E

Border: #2A223E

Primary electric violet: #8B5CF6

Neon orchid: #A855F7

Positive income: #06B6D4

Negative or over-budget: #F43F5E

Primary text: #F8FAFC

Muted text: #94A3B8

Light theme

Warm ivory canvas: #FAF9F6

White cards: #FFFFFF

Primary orange: #F97316

Secondary orange: #FB923C

Primary text: #18181B

Muted text: #71717A

Borders: #E4E4E7

Implement a functional theme toggle. Persist the user's theme preference. Use design tokens/CSS variables so every component, chart, tooltip, dialog, and 3D material adapts to the selected theme.

Use Geist Sans or Plus Jakarta Sans for interface typography and Geist Mono or JetBrains Mono for financial values. Use tabular numerals for currency.

Visual rules:

Compact, high-density financial UI.

Sharp 8px corner radii.

Consistent 4px/8px spacing scale.

Cards with 16–20px padding.

Fine borders and restrained shadows.

Purple glow only for meaningful dark-theme focus/hover states.

Orange accents and subtle shadows in light mode.

No oversized whitespace, bubbly cards, cartoon illustrations, or unnecessary gradients.

Ensure WCAG-conscious text contrast.

2. Main application shell

Design for a 1440px desktop viewport, with a 240px persistent sidebar and a 64px top bar. Make it responsive for tablets and mobile.

Sidebar:

Geometric HomeFolio logo and wordmark.

Family workspace selector: "Sharma Household", with stacked member avatars.

Navigation links with Lucide icons:

Overview

Accounts & Cards

Category Budgets

Shared Splits

Savings Goals

Bill Reminders

Audit Logs

Show a distinct active navigation state.

Bottom profile section with avatar, member name, role badge "Owner", and account menu.

Top bar:

Family liquid worth: ₹2,25,000, accompanied by a subtle status indicator.

Month selector initially set to October 2026.

Notifications bell with unread indicator.

Prominent "+ Log Transaction" button.

Responsive mobile navigation.

3. Overview dashboard

Build a compact 12-column dashboard with clear hierarchy.

Top KPI row — four cards:

Net Worth: large currency figure, month-over-month change, 30-day sparkline.

Monthly Cash Flow: income versus expenses, with compact comparative bars.

Budget Burn Rate: 68% utilization, progress bar, remaining days, and warning state.

Pending Shared Splits: total outstanding amount, member avatars, and a link to settle debts.

Middle region:

Left, 8 columns: "Budget Breakdown vs Actual". Display category-level budgets and actual spending for Groceries, Utilities, Rent, Transport, Dining, and Healthcare. Include progress bars, grouped chart visualization, and near-limit/over-budget states.

Right, 4 columns: "Accounts & Cards". Show HDFC Savings, SBI Credit Card, and Cash Reserve as compact account summaries. Mask account identifiers; never display full banking credentials.

Bottom region:

Left, 7 columns: "Recent Household Transactions". Use a dense accessible table with Date, Description, Logged By, Account, Category, and Amount. Right-align currency. Clearly distinguish income from expenses.

Right, 5 columns: "Savings Goals & Upcoming Bills". Show Annual Family Vacation with ₹25,000 saved toward ₹2,00,000, circular progress, upcoming bills, due dates, and working Mark Paid actions.

Use realistic Indian financial demo data. Label all mock data clearly as demo data. Do not imply actual bank connectivity.

4. Functional navigation and interactions

Create complete navigable pages for:

Overview

Accounts & Cards

Category Budgets

Shared Splits

Savings Goals

Bill Reminders

Audit Logs

The sidebar links must navigate to working pages, not placeholders.

Implement:

Add transaction modal/drawer with amount, type, date, account, category, member, description, and optional notes.

Form validation and meaningful success/error feedback.

Search, filters, and sorting for transactions.

Month selection that updates relevant dashboard data.

Budget progress and threshold warnings.

Shared expense split details and settlement actions.

Savings goal contribution flow.

Bill paid/unpaid status and due-date indicators.

Audit log entries for relevant mutations.

Notification menu and functional theme toggle.

Responsive layouts, loading states, empty states, and error states.

Do not leave important buttons inert. Where backend integration is not configured, implement realistic local demo behavior and clearly identify it as demo mode.

5. Three.js visual signature

Use Three.js through React Three Fiber and Drei to create a small number of tasteful decorative 3D objects.

Hero object: a sculptural, metallic violet/magenta torus-knot or interlocking-orbit object in a compact dashboard welcome region. Use realistic reflections, subtle rim lighting, restrained glow, and slow continuous rotation.

Savings object: a translucent glass orb with an inner rotating ring representing a savings goal. Keep all financial labels as accessible HTML rather than rendering text inside WebGL.

Light-theme variation: reuse the same geometric objects with polished chrome, white, and orange materials under warmer lighting.

Motion:

Slow rotation, roughly 20–40 seconds per full revolution.

Gentle pointer-responsive parallax on desktop.

Pause when outside the viewport.

Respect reduced-motion settings.

Lazy-load the 3D scene and avoid blocking dashboard interaction.

Provide static fallbacks if WebGL is unavailable.

Keep 3D objects decorative and never place them over essential financial data or controls.

Do not use 3D on every card. Prioritize product performance and readability.

6. Technology and architecture

Use:

React + TypeScript + Vite.

Tailwind CSS and shadcn/ui.

Lucide icons.

Recharts for charts.

React Three Fiber and Drei for 3D.

React Hook Form and Zod for form validation.

Supabase/PostgreSQL for authentication and persistence when configured.

Build reusable components: MetricCard, CurrencyValue, Sparkline, BudgetProgress, TransactionTable, AccountCard, MemberAvatarStack, SavingsGoalCard, BillReminderRow, and ThreeDHero.

Use a centralized theme token system and shared date/currency utilities. Format currency with the Indian locale. Separate UI components from business logic and database access.

7. Database-ready domain model

Design the data layer around:

Family

Family_Member

Account

Category

Transaction

Budget

Savings_Goal

Goal_Contribution

Bill_Subscription

Expense_Split

Audit_Log

Every financial record should be scoped to the appropriate family. Design access control for Owner, Adult, and Dependent roles. Never trust client-side role checks alone: enforce permissions on the server/database with appropriate row-level security policies.

Avoid exposing secrets in frontend code. Use only masked account identifiers and synthetic demo data.

8. Delivery sequence

Build incrementally rather than generating a giant untested application in one pass.

Phase 1: Design system, sidebar, top bar, responsive Overview dashboard, both themes, realistic mock data.

Phase 2: Complete navigation, transaction modal, filters, charts, account summaries, savings goals, bills, and shared splits using local demo state.

Phase 3: Three.js hero sculpture, goal orb, animation optimization, reduced-motion behavior, and fallback rendering.

Phase 4: Supabase schema, authentication, family membership, persistence, audit logging, and database security.

Prioritize visual polish, accessibility, correctness of financial calculations, and maintainable code. At the end of each phase, verify that the application builds and that all visible controls behave as expected.

Start by implementing Phase 1 with excellent visual quality, then continue through the phases without replacing the established design system.

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/e98cdfaa-f355-597e-aec0-3575deeb871c).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
