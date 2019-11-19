# OpenCompliance Extensions

OpenCompliance requests may contain an `extensions` object, composed of a series of child-objects, keyed by a processor domain.

- The domain of each extension **MUST** match the processor's OpenCompliance domain.
- Extensions **MUST** not be used for or contain authentication information.
- Processors **MUST** only implement an extension for items that do not already fit into the generic spec.

See section the [OpenCompliance spec](OpenCompliance_specification.md) for more information on the use of extensions.

## Published Extensions

### mParticle

Domain: `OpenCompliance.mparticle.com`

Supported keys:

- `mpids`: An array of mParticle IDs. The mParticle ID is a 64-bit signed integer.

### Example

```json
"extensions": {
    "OpenCompliance.mparticle.com": {
      "mpids":[120934871234, 1309487143098]
    }
}
```

### Schema

```json
{
  "type": "object",
  "properties": {
    "OpenCompliance.mparticle.com": {
      "type": "object",
      "properties": {
        "mpids": {
          "type": "array",
          "items": {
            "examples": [
              120934871234,
              1309487143098
            ]
          }
        }
      }
    }
  }
}
```