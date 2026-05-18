# GameStore API

A RESTful API for managing a game store built with ASP.NET Core and Entity Framework Core.

## Prerequisites

- .NET 10.0 SDK or later
- Git

## Project Structure

```
first-proj/
├── GameStore.Api/
│   ├── Data/
│   │   ├── GameStoreContext.cs      # Entity Framework DbContext
│   │   ├── DataExtensions.cs        # Database helper extensions
│   │   └── migrations/              # Database migrations
│   ├── Dtos/
│   │   ├── GameDto.cs               # Data Transfer Object
│   │   ├── CreateGameDto.cs         # Create request DTO
│   │   └── UpdateGameDto.cs         # Update request DTO
│   ├── Endpoints/
│   │   └── GameEndpoints.cs         # API endpoint mappings
│   ├── Models/
│   │   └── Game.cs                  # Game entity model
│   ├── Program.cs                   # Application entry point
│   ├── appsettings.json             # Configuration
│   └── GameStore.Api.csproj         # Project file
├── .gitignore                       # Git ignore rules
└── README.md                        # This file
```

## Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd first-proj
   ```

2. **Restore dependencies**
   ```bash
   dotnet restore
   ```

3. **Run migrations**
   ```bash
   dotnet ef database update
   ```

4. **Run the application**
   ```bash
   dotnet run --project GameStore.Api
   ```

The API will start at `https://localhost:5081`

## API Endpoints

### Get all games
```
GET /games
```

### Get game by ID
```
GET /games/{id}
```

### Create a new game
```
POST /games
Content-Type: application/json

{
  "name": "Game Name",
  "genre": "Genre",
  "price": 29.99,
  "releaseDate": "2024-01-01"
}
```

### Update a game
```
PUT /games/{id}
Content-Type: application/json

{
  "name": "Updated Name",
  "genre": "Updated Genre",
  "price": 39.99,
  "releaseDate": "2024-01-01"
}
```

### Delete a game
```
DELETE /games/{id}
```

## Database

This project uses SQLite with Entity Framework Core. The database file (`GameStore.db`) is automatically created when you run migrations.

### Create a new migration
```bash
dotnet ef migrations add <MigrationName> --output-dir Data/migrations
```

### Apply migrations
```bash
dotnet ef database update
```

## Technologies

- **Framework**: ASP.NET Core (.NET 10.0)
- **ORM**: Entity Framework Core
- **Database**: SQLite
- **Language**: C# 12

## License

This project is open source and available under the MIT License.
