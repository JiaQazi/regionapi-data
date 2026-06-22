# RegionAPI Data

A structured, open dataset covering countries, cities, banks, telecom operators, 
and public holidays for the South Asia region (SAARC countries).

This repository serves as the data source for the RegionAPI which is a REST API 
providing regional reference data for developers building applications 
for South Asian markets.

---

## Coverage

| Country | Code | Cities | Banks | Telecom | Holidays |
|---|---|---|---|---|---|
| Pakistan | PK | ✅ | ✅ | ✅ | ✅ 2024–2026 |
| India | IN | ✅ | ✅ | ✅ | ✅ 2024–2026 |
| Bangladesh | BD | ✅ | ✅ | ✅ | ✅ 2024–2026 |
| Sri Lanka | LK | ✅ | ✅ | ✅ | ✅ 2024–2026 |
| Nepal | NP | ✅ | ✅ | ✅ | ✅ 2024–2026 |
| Afghanistan | AF | ✅ | ✅ | ✅ | ✅ 2024–2026 |
| Maldives | MV | ✅ | ✅ | ✅ | ✅ 2024–2026 |
| Bhutan | BT | ✅ | ✅ | ✅ | ✅ 2024–2026 |

---

## Data Structure

```
data/
├── countries/
│   └── countries.json          # All 8 countries with metadata
├── cities/
│   ├── PK.json
│   ├── IN.json
│   └── ...                     # One file per country
├── banks/
│   ├── PK.json
│   ├── IN.json
│   └── ...                     # One file per country
├── telecom/
│   ├── PK.json
│   ├── IN.json
│   └── ...                     # One file per country
└── holidays/
    ├── PK/
    │   ├── 2024.json
    │   ├── 2025.json
    │   └── 2026.json
    ├── IN/
    ├── BD/
    └── ...                     # One folder per country
```

---

## Data Formats

### Country
```json
{
  "id": 1,
  "name": "Pakistan",
  "country_code": "PK",
  "capital": "Islamabad",
  "currency_code": "PKR",
  "calling_code": "+92",
  "timezone": "Asia/Karachi",
  "flag_emoji": "🇵🇰"
}
```

### City
```json
{
  "id": 1,
  "name": "Karachi",
  "province": "Sindh",
  "province_code": "SD",
  "capital": false,
  "provincial_capital": true,
  "latitude": 24.8607,
  "longitude": 67.0011,
  "timezone": "Asia/Karachi",
  "population": 14910352
}
```

### Bank
```json
{
  "id": 1,
  "name": "Habib Bank Limited",
  "short_name": "HBL",
  "swift_code": "HABBPKKA",
  "type": "commercial",
  "category": "public",
  "headquarters": "Karachi",
  "founded": 1941,
  "active": true
}
```

### Telecom Operator
```json
{
  "id": 1,
  "name": "Jazz",
  "type": "mobile",
  "technology": ["2G", "3G", "4G"],
  "mcc": "410",
  "mnc": "01",
  "prefixes": ["0300", "0301", "0302"],
  "market_share_percent": 37.2,
  "wallet": "JazzCash"
}
```

### Holiday
```json
{
  "id": 1,
  "name": "Independence Day",
  "local_name": "Independence Day",
  "date": "2026-08-14",
  "type": "Public",
  "regions": ["National"],
  "tentative": false
}
```

---

## API

This dataset powers the RegionAPI, a hosted REST API serving this 
data via clean endpoints. Coming soon.

Example endpoints:
- `GET /api/countries`
- `GET /api/cities/{countryCode}`
- `GET /api/banks/{countryCode}`
- `GET /api/telecom/{countryCode}`
- `GET /api/holidays/{countryCode}/{year}`

---

## Contributing

Found an error or missing data? Contributions are welcome:

1. Fork the repository
2. Update the relevant JSON file
3. Submit a pull request with a brief description of the change

Please verify data accuracy before submitting — especially for Islamic 
holiday dates and telecom prefix assignments.

---

## Notes

- Islamic holidays marked `tentative: true` for future years are 
  subject to moon sighting and may shift by a day
- Past holidays have `tentative: false` as dates are confirmed
- India's holidays vary significantly by state — national holidays 
  are marked `regions: ["National"]`
- Population figures are approximate based on latest available census data
- Telecom market share figures are approximate and subject to change

---

## License

MIT License — free to use in personal and commercial projects.
