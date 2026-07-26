# Country Codes Database

Comprehensive country codes database: ISO 3166, calling codes, capitals, currencies, languages, and more. 249 countries.

## What is this?

This repository provides a **ready-to-use database** of country codes database with **249 records**. Available as SQLite database and SQL dumps — ideal for developers, data analysts, and fintech applications.

## Downloads

| Format | Description | Link |
|---|---|---|
| **SQLite** | Single database file, ready to query | [Releases](../../releases) |
| **SQL** | SQL dump, import into MySQL/PostgreSQL/etc. | [Releases](../../releases) |
| **Excel / CSV / PDF** | Formatted spreadsheets | [listbase.org](https://listbase.org/en/geography/) |

## Database Schema

```sql
CREATE TABLE countries (
  name TEXT NOT NULL,
  iso_alpha_2 TEXT,
  iso_alpha_3 TEXT,
  iso_numeric TEXT,
  capital TEXT,
  continent TEXT,
  region TEXT,
  sub_region TEXT,
  dial_code TEXT,
  currency_code TEXT,
  tld TEXT,
  languages TEXT,
  fifa TEXT,
  ioc TEXT,
  fips TEXT
);
CREATE INDEX idx_countries_iso_alpha_2 ON countries (iso_alpha_2);
CREATE INDEX idx_countries_iso_alpha_3 ON countries (iso_alpha_3);
CREATE INDEX idx_countries_name ON countries (name);
```

## Stats

- **249** records
- **1** datasets
- Updated: **2026-07-26**

## Preview

| name | iso_alpha_2 | iso_alpha_3 | iso_numeric | capital | continent | region | sub_region | dial_code | currency_code | tld | languages | fifa | ioc | fips |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Afghanistan | AF | AFG | 4 | Kabul | AS | Asia | Southern Asia | 93 | AFN | .af | fa-AF,ps,uz-AF,tk | AFG | AFG | AF |
| Kepulauan Aland | AX | ALA | 248 | Mariehamn | EU | Europe | Northern Europe | 358 | EUR | .ax | sv-AX | ALD |   |   |
| Albania | AL | ALB | 8 | Tirana | EU | Europe | Southern Europe | 355 | ALL | .al | sq,el | ALB | ALB | AL |
| Algeria | DZ | DZA | 12 | Algiers | AF | Africa | Northern Africa | 213 | DZD | .dz | ar-DZ | ALG | ALG | AG |
| Samoa Amerika | AS | ASM | 16 | Pago Pago | OC | Oceania | Polynesia | 1-684 | USD | .as | en-AS,sm,to | ASA | ASA | AQ |
| Andorra | AD | AND | 20 | Andorra la Vella | EU | Europe | Southern Europe | 376 | EUR | .ad | ca | AND | AND | AN |
| Angola | AO | AGO | 24 | Luanda | AF | Africa | Sub-Saharan Africa | 244 | AOA | .ao | pt-AO | ANG | ANG | AO |
| Anguilla | AI | AIA | 660 | The Valley | NA | Americas | Latin America and the Caribbean | 1-264 | XCD | .ai | en-AI | AIA | AIA | AV |
| Antartika | AQ | ATA | 10 |  | AN |  |  | 672 |  | .aq |  | ROS3 |   | AY |
| Antigua dan Barbuda | AG | ATG | 28 | St. John&#39;s | NA | Americas | Latin America and the Caribbean | 1-268 | XCD | .ag | en-AG | ATG | ANT | AC |
| Argentina | AR | ARG | 32 | Buenos Aires | SA | Americas | Latin America and the Caribbean | 54 | ARS | .ar | es-AR,en,it,de,fr,gn | ARG | ARG | AR |
| Armenia | AM | ARM | 51 | Yerevan | AS | Asia | Western Asia | 374 | AMD | .am | hy | ARM | ARM | AM |
| Aruba | AW | ABW | 533 | Oranjestad | NA | Americas | Latin America and the Caribbean | 297 | AWG | .aw | nl-AW,pap,es,en | ARU | ARU | AA |
| Australia | AU | AUS | 36 | Canberra | OC | Oceania | Australia and New Zealand | 61 | AUD | .au | en-AU | AUS | AUS | AS |
| Austria | AT | AUT | 40 | Vienna | EU | Europe | Western Europe | 43 | EUR | .at | de-AT,hr,hu,sl | AUT | AUT | AU |
| ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |

*Showing 15 of 249 records*

## Release Files

| File | Records | Description |
|---|---|---|
| `country-codes.db` | 249 | SQLite database (all data) |
| `country-codes.sql` | 1-249 | SQL dump |


## Usage

### SQLite
```bash
sqlite3 country-codes.db "SELECT * FROM countries WHERE country_code = 'US' LIMIT 10;"
```

### Import SQL (MySQL)
```bash
mysql -u root -p your_database < country-codes.sql
```

### Import SQL (PostgreSQL)
```bash
psql -U postgres -d your_database -f country-codes.sql
```

## Use Cases

- **International wire transfers** — Look up SWIFT/BIC codes before sending money abroad
- **Payment system integration** — Validate bank codes in fintech and payment applications
- **Banking directory** — Build a searchable bank directory for any country
- **Compliance & KYC** — Verify financial institution identifiers
- **Data enrichment** — Enrich transaction data with bank names and locations

## FAQ

### What is a SWIFT/BIC code?
A SWIFT/BIC code is an 8-11 character identifier used to identify banks and financial institutions globally for international wire transfers. SWIFT stands for Society for Worldwide Interbank Financial Telecommunication.

### How often is this data updated?
The database is updated monthly. Check the [Releases](../../releases) page for the latest version.

### Can I use this data commercially?
Yes. This data is released under the [MIT License](LICENSE) — free to use for any purpose, including commercial applications.

### How do I look up a SWIFT code for a specific bank?
```sql
SELECT * FROM countries WHERE bank LIKE '%KASIKORN%';
```

### How do I get all banks in a specific country?
```sql
SELECT * FROM countries WHERE country_code = 'TH' ORDER BY bank;
```

## Countries (1)


## Browse Online

Explore and download individual datasets at **[listbase.org](https://listbase.org/en/geography/)**.

## License

[MIT](LICENSE) — Free to use for any purpose.

## Source

ISO 3166, ITU, FIFA, IOC via public registries

---

Made with data from [ListBase.org](https://listbase.org/en/geography/) — Free Reference Tables & Lists
