# React Router Dom v6 Nested Routes and Wildcard Route Conflict

This repository demonstrates a bug in React Router Dom v6 where nested routes and a wildcard catch-all route (`/*`) conflict.  The wildcard route unintentionally matches nested paths, preventing the nested routes from working correctly.

The issue occurs when a nested route's path might be a prefix of the wildcard route's path. In this instance, navigation to nested routes is intercepted by the wildcard route resulting in an incorrect component rendering.

The solution showcases a more appropriate routing strategy for handling nested routes and the wildcard route, ensuring all routes function correctly without conflicts.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Navigate to `/about` - this works as expected.
5. Navigate to `/about/contact` - this should show a contact component (which is missing in the buggy implementation), but instead shows the 404 component.