


```

class Program
{
  static void Main(string[] args)
  {
      // This creates a new MySingleton
      MySingleton mySingleton1 = MySingleton.Instance();

      // This only gets the same MySingleton object created above
      MySingleton mySingleton2 = MySingleton.Instance();
  }
}

// Set class accessor to sealed so it cannot be inherited
sealed class MySingleton
{
  // Do not allow any constructor arguments
  private MySingleton(){ }
  
  private static MySingleton _instance;
  
  private static readonly object _lock = new object();
  
  // Static method to create the object
  public static MySingleton Instance()
  {
    // Thread safe
    // Only allow 1 thread at a time
    lock(_lock)
    {
      if(_instance == null)
        {
            _instance = new MySingleton();
            Console.WriteLine("...creating MySingleton()");
        }
    }
  
    return _instance;
  }
}

```
