Summary: Project folder layout, clean architecture naming conventions, and structural rules.

# Project Structure

This project follows a strict feature-driven Clean Architecture under the `lib/` directory.

## Directory Tree

```
lib/
├── application/       # Global application-level components (router, view_model, di, lifecycle)
├── domain/            # Core business logic
│   ├── model/         # Plain Dart objects (e.g., Coin)
│   └── repository/    # Abstract interfaces for data access
├── local/             # Local data layer (storage, local data sources, and repositories)
├── network/           # External data layer
│   ├── configuration/ # API endpoints and constants
│   ├── data_source/   # Retrofit @RestApi data sources
│   ├── dto/           # Data Transfer Objects for API requests/responses
│   └── repository_implementation/ # Concrete implementations of domain repositories
├── presentation/      # UI Layer
│   ├── animation/     # Shared animations
│   ├── common/        # Shared base classes, widgets, dialogs
│   │   └── base/      # Base state, base cubit/bloc
│   ├── screen/        # Feature screens (e.g., home, scan, coin_detail)
│   └── theme/         # Design system (colors, text styles, app theme)
├── service/           # Device services (e.g., camera, location)
└── utility/           # Helpers, extensions, constants, and sealed classes
```

## Naming Conventions
- **Folders and files**: `snake_case`
- **Classes**: `PascalCase`
- **Widgets**: `*Page`, `*ViewContent`, `*Section`
- **State Management**: `*ViewModel` (for Cubits), `*State`
- **Network**: `*DataSource`, `*Dto`, `*RepositoryImpl`
- **Domain**: `*Repository`, `Model` names without suffixes (e.g., `Coin`).
