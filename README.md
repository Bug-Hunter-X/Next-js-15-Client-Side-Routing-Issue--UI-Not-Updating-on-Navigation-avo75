# Next.js 15 Client-Side Navigation Bug

This repository demonstrates a bug encountered in a Next.js 15 application involving client-side navigation. The issue revolves around the UI failing to update correctly after initial navigation between pages.  The application uses `next/link` for navigation.

## Bug Description

The application consists of two pages, 'Home' and 'About'.  Navigating from 'Home' to 'About' works as expected. However, upon clicking the button on the 'About' page to return to 'Home', the UI does not reflect the change, remaining on the 'About' page visually.  The URL updates correctly, but the content does not.

## Reproduction Steps

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Navigate from the Home page to the About page.
5. Click the button on the About page to go back to the Home page.
6. Observe that the URL changes to the Home page, but the content remains the 'About' page.

## Solution

A potential fix involves leveraging the `useRouter` hook's `events` feature (or similar) to force a re-render after route changes.