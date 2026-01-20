# Library App

## Description

The Library App is a console-based application designed to manage a library system. It allows users to perform operations such as searching for patrons, managing book loans, and renewing memberships. The application uses JSON files for data storage and loads the data into memory for processing.

## Structure

- `src/`
  - `Library.ApplicationCore/`
    - `Entities/`
      - `Author.cs`
      - `Book.cs`
      - `BookItem.cs`
      - `Loan.cs`
      - `Patron.cs`
    - `Enums/`
      - `EnumHelper.cs`
      - `LoanExtensionStatus.cs`
      - `LoanReturnStatus.cs`
      - `MembershipRenewalStatus.cs`
    - `Interfaces/`
      - `ILoanRepository.cs`
      - `ILoanService.cs`
      - `IPatronRepository.cs`
      - `IPatronService.cs`
    - `Services/`
      - `LoanService.cs`
      - `PatronService.cs`
    - `Library.ApplicationCore.csproj`
  - `Library.Console/`
    - `Json/`
      - `Authors.json`
      - `Books.json`
      - `BookItems.json`
      - `Loans.json`
      - `Patrons.json`
    - `appSettings.json`
    - `CommonActions.cs`
    - `ConsoleApp.cs`
    - `ConsoleState.cs`
    - `Library.Console.csproj`
    - `Program.cs`
  - `Library.Infrastructure/`
    - `Data/`
      - `JsonData.cs`
      - `JsonLoanRepository.cs`
      - `JsonPatronRepository.cs`
    - `Library.Infrastructure.csproj`
- `tests/`
  - `UnitTests/`
    - `ApplicationCore/`
      - `LoanService/`
        - `ExtendLoan.cs`
        - `ReturnLoan.cs`
      - `PatronService/`
        - `RenewMembership.cs`
    - `LoanFactory.cs`
    - `PatronFactory.cs`
    - `UnitTests.csproj`

## Key Classes and Interfaces

### Core Classes
- `Patron`: Represents a library patron, including membership details and loans.
- `Loan`: Represents a book loan, including due dates and return status.
- `Book`: Represents a book in the library.
- `BookItem`: Represents a specific copy of a book.
- `Author`: Represents an author of books.

### Services
- `LoanService`: Handles operations related to book loans, such as returning and extending loans.
- `PatronService`: Manages patron-related operations, such as renewing memberships.

### Repositories
- `JsonPatronRepository`: Provides data access for patrons using JSON files.
- `JsonLoanRepository`: Provides data access for loans using JSON files.

### Utility
- `JsonData`: Manages loading and saving data from/to JSON files.
- `EnumHelper`: Provides helper methods for working with enums.

## Usage

### Prerequisites
- Install **.NET 8.0** or higher.

### Running the Application
1. Clone the repository.
2. Navigate to the `src/Library.Console` directory.
3. Run the following command:
   ```bash
   dotnet run