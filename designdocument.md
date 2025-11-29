1. Wireframe & Layout Decisions
Overall Layout Strategy

The website’s structure follows modern digital news platforms that emphasize fast content scanning, clear visual hierarchy, and strong readability. The interface is designed to be clean, accessible, and easy to navigate.

Top Navigation Bar

A fixed header that stays visible during scrolling.

Includes a mobile-friendly hamburger menu.

Uses a bold red shade (#b91c1c) to reflect the aesthetic of Indian news sites such as LiveHindustan.

Featured Article (Hero Section)

Dominant visual block positioned at the top of the homepage.

Full-width hero image with a semi-transparent overlay to enhance text visibility.

Draws maximum attention to the most important news item.

Primary Article Feed

Desktop layout uses a structured 2-column grid to maximize content density.

Allows readers to browse multiple headlines easily without feeling cluttered.

Right-Side Sidebar (Desktop)

Displays Trending or Most Viewed articles.

Designed to improve engagement by surfacing high-interest stories and extending user session time.

Footer Section

Minimalistic design containing useful links and credits.

Styled intentionally simple to avoid distracting the reader.

Responsive Layout Behavior
On Mobile Devices

The UI collapses into a single vertical column.

The hero story appears first, followed by recent articles.

The trending section shifts below the article feed for a smooth scrolling experience.

On Larger Screens

The layout expands into a 12-column grid:

Main content uses 8 columns

Sidebar uses 4 columns

This grid division creates balance and matches the structure of professional news portals.

2. Data Fetching Logic
Next.js App Router + Server Components

To follow the latest Next.js guidelines, the project is built using the App Router, providing better performance and simpler data-loading patterns.

Homepage Loading ( / )

Data is fetched inside a Server Component using an async function.

Behaves similarly to server-side rendering but with reduced complexity.

Room for optimization using caching when connecting to real APIs.

Article Pages ( /news/[id] )

Generated using Static Site Generation (SSG) with generateStaticParams.

Ideal for article content that doesn’t update frequently.

All article IDs are collected at build time to pre-render each page, improving speed and SEO.

Mock Backend Module

A local API module (lib/api.ts) provides structured functions for fetching articles.

Includes a tiny artificial delay to simulate real API behavior.

Article objects contain detailed fields (author, timestamps, full content) for accurate UI testing.

3. Codebase Organization
Key UI Components
Navbar

Implemented as a Client Component due to interactive menu toggling.

Fully responsive, adapting seamlessly between desktop and mobile.

Hero Component

Highlights the top story using a strong headline and full-width image.

Uses an overlay for better text contrast and emphasis.

NewsCard

A reusable article preview card.

Includes fallback logic for missing images.

Sidebar

Displays trending/popular news.

Appears only on desktop to enhance navigation depth.

Article Data Model
interface Article {
  id: string;
  title: string;
  summary: string;
  content: string;  // supports HTML formatting
  imageUrl?: string;
  category: string;
  publishedAt: string;
  author: string;
}


This interface standardizes article structure and ensures consistent rendering across components.

4. Challenges Faced & Solutions Implemented
1. Image Optimization Problems

External placeholder images triggered build-time errors.

Resolved by updating next.config.ts with appropriate remotePatterns.

Ensured smooth rendering and avoided Next.js image warnings.

2. Preventing Hydration Errors

The navbar, being a Client Component, could cause mismatches during hydration.

Carefully managed initial states and conditional rendering to avoid such issues.

3. TailwindCSS v4 Adjustments

Tailwind v4 uses CSS variables heavily, replacing older utility-injection behavior.

To maintain a clean light theme:

Removed outdated or redundant styles.

Reorganized global CSS to align with the updated Tailwind system.

