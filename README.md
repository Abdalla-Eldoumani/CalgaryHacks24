# Budget Buddy

A small Next.js site about personal finance for young Canadians, built as a team project at CalgaryHacks 2024. It has short explainer pages on TFSAs and FHSAs, a page of sample stock picks with a five-year growth estimate, and a link out to a separate budgeting app.

This is a hackathon prototype. The content is static and written by the team; nothing on the site is financial advice.

## What is in it

- **Sign-in:** Clerk handles sign-up and sign-in. The middleware protects every route, so you sign in before seeing any page.
- **Learn More** (`/learn-more`, `/tfsa`, `/fhsa`): text pages on Tax-Free Savings Accounts, First Home Savings Accounts, and the basics of stocks, bonds and cash.
- **Invest** (`/invest`): stock picks grouped into seven sectors, hard-coded in the page with a description and a "return last year" figure for each. Enter an amount, click a ticker, and an alert shows what that amount would become after five years at last year's return, compounded yearly. There are no live market prices.
- **Budget** (`/budget`): a page that links to the budget tracker, which is a separate app hosted at [budget-buddy-theta.vercel.app](https://budget-buddy-theta.vercel.app/). The tracker's code is not in this repo.
- **Dashboard** (`/dashboard`): a long marketing-style layout explaining the idea, with images served from builder.io.

## Stack

Next.js 14 (App Router), React 18, TypeScript, Tailwind CSS, shadcn/ui, and Clerk (`@clerk/nextjs` v4).

## Run it locally

You need Node.js 18.17 or later and a Clerk application (the free tier works).

1. Install dependencies:

   ```bash
   npm install
   ```

2. Create `.env.local` in the project root with your Clerk keys:

   ```bash
   NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_...
   CLERK_SECRET_KEY=sk_test_...
   ```

3. Start the dev server and open http://localhost:3000:

   ```bash
   npm run dev
   ```

Other scripts: `npm run build`, `npm start`, and `npm run lint`.

## Limitations

- Stock data and returns are fixed values typed into the page, not fetched from a market API.
- The growth estimate assumes last year's return repeats for five years.
- The "Share on Instagram" button opens instagram.com with the text in the URL; Instagram does not read it.
- Several pages turn off ESLint for the whole file.
