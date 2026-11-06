# Dolores Hoy

Tablero en Flutter que consume 5 APIs gratuitas (Open-Meteo, Frankfurter, Nager.Date, Wikipedia y NASA APOD) con TDD y buenas prácticas de seguridad.

Desarrollo Móvil Integral · UTNG

## Requisitos
- Flutter 3.x (Dart >= 3.0)

## Configuración
```bash
flutter create . --platforms=android,ios
flutter pub get
cp secrets.json.example secrets.json   # pon tu clave de api.nasa.gov (secrets.json NO se sube a git)
```

## Ejecutar
```bash
flutter run --dart-define-from-file=secrets.json
```

## Pruebas (sin internet)
```bash
flutter test
```

## Estructura
- `lib/dominio`: excepciones y modelos
- `lib/datos`: ClienteSeguro (https, timeout, límite de tamaño), ConfigClaves, servicios
- `lib/presentacion`: ViewModel y pantalla
- `test`: pruebas con MockClient

## Seguridad
Claves fuera del código (`--dart-define`), https obligatorio, entradas/salidas validadas, logs sin secretos (`ClienteSeguro.redactar`).
