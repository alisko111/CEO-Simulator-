# CEO Simulator — MVP vertical slice

Flutter app scaffold for a Russian-language business management simulator. This first slice includes the CEO dashboard, departments list, individual department detail pages, bottom navigation, demo data, and a dark premium design system.

## Requirements
- Flutter stable (Dart 3.3+)
- Internet access for the first `flutter pub get`

## Run
```bash
flutter pub get
flutter run
```

## Check
```bash
flutter analyze
flutter test
```

## Current scope
- Dashboard with demo financial KPIs, interactive chart, business health indicators, recent events and quick actions.
- Five persistent bottom-navigation branches: Company, Departments, Decisions, Reports and Profile.
- Seven individual department pages, each with its own copy, key metric and action list.
- Demo action sheets and quarter-close confirmation.
- Data/models separated from UI; no real business results or economic calculations are implied.

All figures are fictional demo data. The economic engine, persistence between app launches, full financial reports, decision engine, game modes and backend are intentionally out of scope for this iteration.

## State and architecture
- `core/state/game_state_provider.dart` provides a Riverpod state controller for mode and decision inputs.
- `models/` contains plain Dart data models.
- `data/demo_data.dart` is the single source for the demo figures used in the UI.
- `data/repositories/company_repository.dart` defines a repository boundary for replacing demo data later.
- `core/navigation/app_router.dart` uses `StatefulShellRoute.indexedStack` so the five primary branches preserve their navigation stacks when switching tabs.
