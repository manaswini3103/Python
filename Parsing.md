# Parsing
Parsing refers to the process of reading, decoding, and converting data from a text format (like JSON or YAML) into data structures that a programming language can use (arrays, dictionaries, objects, etc.).

## JSON (JavaScript Object Notation)

### What is JSON?
- A lightweight data-format used widely in APIs, configuration files, and data exchange.
- Syntax is strict and based on JavaScript object structure.
- Easy for machines to read and write
**example**
```json
{
  "name": "John",
  "age": 25,
  "skills": ["Python", "Linux", "Docker"]
}
```

**JSON Rules**
- Uses {} for objects
- Uses [] for arrays
- Strings must use double quotes
- Only allows valid data types: string, number, boolean, null, object, array

### Parsing in JSON
- Python's built-in json module handles JSON data.
- We use json.loads() to convert a JSON string into a Python dictionary or list.

**example**
```python
import json
data = json.loads('{"name": "John", "age": 25}')
print(data["name"])
```
## YAML (YAML Ain't Markup Language)

### What is YAML?
- A human-friendly configuration language.
- Used in CI/CD pipelines (GitHub Actions, GitLab CI, Jenkins), Kubernetes manifests, etc.
- More readable and flexible than JSON.
**example**
```yaml
name: John
age: 25
skills:
  - Python
  - Linux
  - Docker
  ```

### YAML Rules
- Uses indentation (spaces only, no tabs!)
- Key-value pairs separated by colon :
- Lists created with hyphens -
- Allows comments with #
- More flexible than JSON (supports complex data structures)

### Parsing in YAML
- Python does not have built-in YAML support. The PyYAML library is commonly used for this purpose.
- Use yaml.safe_load() to convert a YAML string into a Python dictionary or list.
- safe_load() is recommended for security reasons when dealing with untrusted sources.
**eample**
```python
import yaml

data = yaml.safe_load("""
name: John
age: 25
""")
print(data["name"])
```