---
title: "Adapter Pattern"
date: 2024-02-20
---

# Adapter Pattern


```

class Program
{
  static void Main(string[] args)
  {
    ITarget target = new Adapter(new Adaptee());
      target.Print();
  }
}

public interface ITarget
{
  void Print();
}

// This Adpater class handles calling the "real" object
// so that the client can continue calling the Print() method 
// and not the PrintMe() method.
public class Adapter : ITarget
{
  // field
  private Adaptee _adaptee;

  // inject "real" object we want to work with
  public Adapter(Adaptee adaptee)
  {
    _adaptee = adaptee;
  }
  
  // This Print() method is what the client will call
  public void Print()
  {
    // ...but we will call the "real" objects method instead
    _adaptee.PrintMe();
  }
}

// This class represents the "real" object that the client CANNOT call directly
public class Adaptee
{
  public void PrintMe()
  {
    Console.WriteLine("Printing...");
  }
}

```

### References:

[https://www.youtube.com/watch?v=2PKQtcJjYvc](https://www.youtube.com/watch?v=2PKQtcJjYvc)
