# PayEz .NET SDK and Demo Application

This repository contains the PayEz .NET SDK and a comprehensive MAUI demo application showcasing integration with the PayEz payment processing API.

## MVVM Architecture in the Demo Application

The demo application implements the Model-View-ViewModel (MVVM) pattern using the .NET MAUI framework and CommunityToolkit.Mvvm. This modern approach offers several benefits:

### Key MVVM Features

- **Clean Separation of Concerns**
  - Models: Define the data structure (e.g., `VaultedCard`, `VaultedACH`)
  - ViewModels: Handle business logic and state management (e.g., `VaultViewModel`, `CreditCardViewModel`)
  - Views: Present the UI and handle user interaction (XAML-based pages)

- **Observable Properties**
  - Uses `[ObservableProperty]` attribute for automatic property change notifications
  - Eliminates boilerplate PropertyChanged implementation
  - Example: `[ObservableProperty] private string statusMessage;`

- **Command Pattern**
  - Implements commands using `[RelayCommand]` attribute
  - Automatically handles async operations and command enabling/disabling
  - Example: `[RelayCommand] private async Task LoadVaults()`

### Service Layer

- **Dependency Injection**
  - Services are injected into ViewModels
  - Promotes testability and modularity
  - Example: `PaymentService`, `TestReportService`

- **API Communication**
  - Centralized HTTP client management
  - Consistent error handling and response parsing
  - Typed models for request/response data

### Benefits for Commercial Use

1. **Maintainability**
   - Clear separation of UI, business logic, and data
   - Easy to modify or replace individual components
   - Consistent patterns across the application

2. **Scalability**
   - New features can be added without modifying existing code
   - ViewModels can be reused across different views
   - Services can be extended or modified independently

3. **Testability**
   - ViewModels can be tested without UI dependencies
   - Services can be mocked for isolated testing
   - Commands provide clear entry points for testing

4. **Modern Development**
   - Uses latest .NET features and best practices
   - Leverages source generators for better performance
   - Minimal boilerplate code

### Example Usage

```csharp
// ViewModel with automatic property and command generation
public partial class VaultViewModel : BaseViewModel
{
    [ObservableProperty]
    private ObservableCollection<VaultedCard> cardVaults = new();

    [RelayCommand]
    private async Task LoadVaults()
    {
        var (cards, checks) = await _paymentService.GetPaymentMethodsAsync();
        CardVaults.Clear();
        foreach (var card in cards)
        {
            CardVaults.Add(card);
        }
    }
}

// XAML binding with commands and properties
<Button Text="Load Vaults" 
        Command="{Binding LoadVaultsCommand}"
        IsEnabled="{Binding IsNotBusy}"/>
<CollectionView ItemsSource="{Binding CardVaults}">
    <!-- Item template -->
</CollectionView>
```

Feel free to use this code as a reference for your own commercial applications. The MVVM pattern demonstrated here provides a solid foundation for building maintainable and scalable payment processing solutions.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
