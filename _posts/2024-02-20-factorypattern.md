---
title: "Factory Pattern"
date: 2024-02-20
---

# Factory Pattern


```

class Program
{
  static void Main(string[] args)
  {
      // NOTE: The factory pattern lets the client code decide which payment processor to use.
      IPaymentProcessor paymentProcessor = PaymentProcessorFactory
                                              .Create(
                                                PaymentMethod.GooglePay
                                                // PaymentMethod.PayPal
                                              );
      paymentProcessor.Pay(100.00);
  }
}

// This "factory" class is what creates (or NEWs up) concrete payment processor objects
// The static factory method decides which object to create based on an external input.
public class PaymentProcessorFactory
{
  // Factory method
  public static IPaymentProcessor Create(PaymentMethod paymentMethod)
  {
    // Decide which payment implementation to use
    switch(paymentMethod)
      {
        case PaymentMethod.PayPal:
            return new PayPalPaymentProcessor();
              
          case PaymentMethod.GooglePay:
            return new GooglePaymentProcessor();
          
          default:
            throw new Exception("Payment is not supported.");
      }
  }
}

// Concrete class for PayPal payment processor
// This is where all the PayPal implementation logic lives
public class PayPalPaymentProcessor : IPaymentProcessor
{
  public void Pay(double amount)  	
  {
    // Add implementation here
    Console.WriteLine($"Payment from PayPal received in the amount of ${amount}");
  }
}

// Concrete class for Google Pay payment processor
// This is where all the Google Pay implementation logic lives
public class GooglePaymentProcessor : IPaymentProcessor
{
  public void Pay(double amount)  	
  {
    // Add implementation here
    Console.WriteLine($"Payment from Google Pay received in the amount of ${amount}");
  }
}

public interface IPaymentProcessor
{
  void Pay(double amount);
}

public enum PaymentMethod
{
  PayPal,
  GooglePay
}

```

### Resources
[https://www.youtube.com/watch?v=SLEu6rNdJj0](https://www.youtube.com/watch?v=SLEu6rNdJj0)
