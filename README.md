# Explora Project

Explora is a Java 17 / JavaFX desktop application for travel services. It combines transport booking, hotel reservations, activities, cart management, payments, document verification, SMS/email flows, and admin tools in one workspace.

## What’s Included

- Transport search and booking with dynamic pricing
- Hotel reservations with cart integration
- Activity details, reviews, and cart add support
- Cart and checkout flow
- Payment features and invoice generation
- Admin and agent dashboards
- Email, SMS, OCR, QR, and PDF utilities
- Automatic database migration on startup

## Project Structure

- `src/` - main JavaFX application used by the root Maven module
- `chahd/Explora-gestion-transport/` - transport-specific module
- `emna/`, `Explora/`, `hamza/`, `Maraam/` - feature/module variants used in the workspace
- `src/main/resources/` - FXML, CSS, images, database assets, and theme files
- `explora_db_schema.sql` - root database schema
- `DATABASE_MIGRATION_GUIDE.md` - migration details
- `QUICK_START_DATABASE.md` - database setup quick start

## Requirements

- Java 17
- Maven 3.9+
- MySQL 8+ or a compatible remote MySQL instance

## Run The App

From the repository root:

```bash
mvn clean compile
mvn javafx:run
```

If you want a clean rebuild and launch in one step:

```bash
mvn clean javafx:run -DskipTests
```

## Database Configuration

The root app uses `src/main/java/com/app/config/DatabaseConnection.java`.

You can override connection settings with environment variables:

- `DB_URL`
- `DB_USER`
- `DB_PASSWORD`

If those variables are not set, the application falls back to the values defined in code.

## Main Features

### Transport

- Search by origin, destination, date, and transport type
- Dynamic pricing based on time, popularity, saturation, and seasonality
- Flight and transport views with detailed cards

### Hotels

- Browse hotel offers
- Reserve rooms and add them to the cart

### Activities

- Show activity details and reviews
- Add activities to the cart

### Cart And Payment

- Mixed cart support for multiple product types
- Checkout and payment flow
- Coupon and invoice support

## Useful Notes

- The project runs with JavaFX FXML views and CSS themes.
- Automatic database migration is triggered on first database connection.
- The workspace contains several submodules that may have their own `pom.xml` and runtime entry points.

## Troubleshooting

- If JavaFX fails to start, make sure the correct JDK is selected in VS Code.
- If database connection fails, verify MySQL access and the configured credentials.
- If an FXML page fails to load, rebuild the project with `mvn clean compile` and check the controller imports.

## References

- `IMPLEMENTATION_SUMMARY.md`
- `DATABASE_AUTO_SETUP_README.md`
- `DATABASE_MIGRATION_GUIDE.md`
- `THEME_SYSTEM.md`
