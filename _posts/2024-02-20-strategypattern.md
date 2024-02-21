---
title: "Strategy Pattern"
date: 2024-02-20
---

# Strategy Pattern
## Behavioral

```

  class Program
  {
    static void Main(string[] args)
    {
    	// Duck object can have different Fly() implementations or strategies
    	Duck duck = new Duck(new FlyStrategyB());
        duck.Fly();
    }
  }
  
  public class Duck
  {
  	private IFlyStrategy _flyStrategy;
  
  	// Inject strategy object
  	public Duck(IFlyStrategy flyStrategy)
    {
    	_flyStrategy = flyStrategy;
    }
  
  	// Execute Fly() method of injected IFlyStrategy object
  	public void Fly()
    {
    	_flyStrategy.Fly();
    }
  }
  
  public class FlyStrategyA : IFlyStrategy
  {
  	public void Fly()
    {
    	Console.WriteLine("Fly Strategy A executed!");
    }
  }
  
  public class FlyStrategyB : IFlyStrategy
  {
  	public void Fly()
    {
    	Console.WriteLine("Fly Strategy B executed!");
    }
  }
  
  public interface IFlyStrategy
  {
  	void Fly();
  }

```

### Resources:
[https://www.youtube.com/watch?v=v9ejT8FO-7I&list=PLrhzvIcii6GNjpARdnO4ueTUAVR9eMBpc](https://www.youtube.com/watch?v=v9ejT8FO-7I&list=PLrhzvIcii6GNjpARdnO4ueTUAVR9eMBpc)
