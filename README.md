# Unhandled setInterval in useEffect causing memory leak
This example demonstrates a common issue in React where setInterval is used within the useEffect hook without proper cleanup. This can lead to memory leaks and unexpected behavior.

## Bug
The `MyComponent` function uses `setInterval` to update the count every second. However, it fails to clear the interval when the component unmounts. This results in a memory leak because the interval continues to run even after the component is no longer rendered.

## Solution
The solution involves using the return value of `setInterval` to create a cleanup function within the `useEffect` hook. This function is called when the component unmounts, ensuring that the interval is cleared, preventing the memory leak.