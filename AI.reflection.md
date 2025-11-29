How AI Supported This Project

AI tools played a significant role in the development of this news portal, mainly by simplifying repetitive tasks and helping fine-tune specific sections of the project. Throughout the workflow, AI assisted me in the following areas:

1. Template & Structure Development

AI helped generate the initial wireframe for both the homepage and category-based news pages.
It also provided boilerplate components, which I later tailored to match the look and feel inspired by LiveHindustan and other modern news websites.

2. UI & Styling Guidance

AI assisted in selecting appropriate TailwindCSS utility classes to recreate a clean red-and-white news portal aesthetic.
It also suggested responsive layout techniques, spacing systems, and typography improvements, helping maintain visual clarity across devices.

3. Sample Data Creation

To avoid manually typing placeholder content, I relied on AI to generate realistic article titles, summaries, and body text.
This dummy content made it easier to test layout variations, card components, and category filtering.

Issues Identified & Enhancements Applied

Even though AI accelerated my workflow, some suggestions required adjustments to better align with best practices or project goals.

1. Selecting the Right Next.js Methodology

Some early AI responses were based on older Pages Router techniques (like getStaticProps).
I intentionally migrated everything to the App Router and used modern features such as generateStaticParams, ensuring the project follows the latest Next.js standards.

2. TailwindCSS v4 Compatibility

Newer Next.js setups use Tailwind v4, so I updated global styles accordingly.
I also removed unused dark mode configurations and kept the theme strictly light, which is typical for Indian news platforms.

3. Image Optimization Fixes

AI-generated code examples occasionally missed required image domain settings.
I manually configured next.config.ts to avoid errors related to external images during build and development.

Personal Contributions & Refinements

Beyond AI assistance, I made several key improvements based on real-world testing:

Improved Mock Data: I manually refined the generated news items to test edge cases like missing images, long headlines, and various categories.

Custom Responsive Navbar: I implemented the mobile navigation logic myself using client-side state to ensure smooth menu transitions.

Stronger Branding: I fine-tuned colors, spacing, and component layouts to achieve a professional news-portal appearance while keeping the design original.