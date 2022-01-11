# UnityMainThreadDispatcher

A thread-safe utility for dispatching functions to the main thread in unity. Useful for calling functions and other actions that Unity limits to the main thread from different threads.

### Installation

Just download and import UnityMainThreadDispatcher package to your Unity project. The package contains a prefab and just one script.
Drop the prefab onto the starting scene and you're done.

### Usage
```csharp
// Can be executed from any thread
private void AnyThreadMethod()
{
    // Enqueue method to run in main thread
    MainThreadDispatcher.Enqueue(MainThreadMethod);
    
    // Enqueue action to run in main thread
    MainThreadDispatcher.Enqueue(() =>
    {
        Debug.Log("Executes from main Unity thread");
    });
}

private void MainThreadMethod()
{
    Debug.Log("Executes from main Unity thread");
}
```
