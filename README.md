# Expo Image Component: Silent Failure on Inaccessible URIs

This repository demonstrates a subtle bug in Expo's `Image` component where it silently fails to load images from inaccessible or broken URIs. The component doesn't provide informative error messages, making debugging challenging.

## Bug Description
When using the `Image` component with a URI that is not reachable, the image simply won't load.  There's often a lack of clear console errors, leaving developers to struggle to identify the source of the problem.  The behavior is inconsistent depending on the underlying network conditions and the Expo version. 

## Reproduction
1. Clone this repository.
2. Run `npm install`.
3. Run the app using `expo start`. 
4. Observe the image component.  If the network is offline or the image URI is invalid, the image won't display and no easily identifiable error will be present in the console. 

## Solution
The solution involves implementing custom error handling using the `onError` prop of the `Image` component. This allows us to catch and handle loading errors gracefully.