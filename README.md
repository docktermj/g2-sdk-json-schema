# g2-sdk-json-schema

## Development cycle

1. In [senzingapi-responses.json](senzingapi-responses.json),
    1. Add response in `$defs` section.
    1. Change bottom `$ref`, to refere to new section in `$defs`.
       Example:

        ```json
        "$ref": "#/$defs/G2configListDataSourcesResponse"
        ```

1. In [Hyperjump - JSON Schema Validator](https://json-schema.hyperjump.io/),
    1. Copy/paste JSON schema to validate
    1. Copy/paste JSON "instance" to validate.

When completely finished, add `anyOf` as top-level JSON key/value.
Example:

```json
{
    :
    "anyOf": [
        {
            "$ref": "#/$defs/G2configAddDatasourceResponse"
        },
        {
            "$ref": "#/$defs/G2configListDataSourcesResponse"
        },
        :
    ],
    :
}
```

## References

1. JSON Schema
    1. [JSON-schema.org](https://json-schema.org/)
1. JSON to JSON Schema
    1. [Free Online JSON to JSON Schema Converter](https://www.liquid-technologies.com/online-json-to-schema-converter)
1. JSON Schema bundling
    1. [JSON Schema bundling finally formalised](https://json-schema.org/blog/posts/bundling-json-schema-compound-documents)
1. Online JSON Schema Validators
    1. [Hyperjump - JSON Schema Validator](https://json-schema.hyperjump.io/)
