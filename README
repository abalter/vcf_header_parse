# Parse a VCF Header to JSON

# Motivation
My primary motivation to write this was to simplify uploading VCF files
to BigQuery. The GCP variant upload tool has features I don't like (such
as switching to 0-based and renaming chromosome to "reference"), and is
in fact not working at this moment at all (3/14/2022).

However, as an intermediate step I decided it could be useful to also be able 
to output a "raw" version in which the entire header is parsed to JSON
with no reformatting or assumptions for BigQuery. (See "to do")

# BigQuery Schema
The correct format for BigQuery schema is a flat list of JSON object literals
in the following format:

```
{
    "name": "Name of the variable",
    "type": "Type of the variable in all-caps. Chiefly: [INTEGER|FLOAT|STRING|BOOL|DATE|STRUCT]",
    "description": "A description of the variable",
    "mode": "[NULLABLE|REQUIRED|REPEATED]"
}
```

See [here](https://cloud.google.com/bigquery/docs/schemas) for a detailed description of the schema particularly
[type](https://cloud.google.com/bigquery/docs/schemas#standard_sql_data_types) and
[mode](https://cloud.google.com/bigquery/docs/schemas#modes)


To Do:
- [ ] Facilitate other cloud formats (e.g. Azure, AWS) and SQL engines.
- [ ] Options for "flattening" the schema because the schema to upload to
      BigQuery needs to be a simple list of key-value pairs. (see above.
- [ ] R utility to convert the schema to `bq_field` format in the [`bigrquery`
      library]()
- [ ] Option for exporting schema when uploading INFO, FORMAT, and FILTER
      sections as JSON object literals rather than an expanded set of
      columns 
