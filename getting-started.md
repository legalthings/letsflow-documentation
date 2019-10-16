# Getting started

It's recommended to follow all tutorials, which demonstrate the most-used features of LetsFlows. While it's not necessary to be a star developer to create scenarios, the documentation assumes that readers have at least some basic programming skills.

## Content type

All objects can be formatted as YAML, pretty JSON or normalized _\(aka full\)_ JSON. These three formats are supported for both input and output using the REST API.

Normalized JSON is the JSON as described by the [JSONSchema](https://json-schema.org/). This format is convenient when the data is processed by a computer, but is very verbose and therefor less readable by humans.

Pretty JSON collapses arrays and maps where there is only one option and omits properties that have the default value. This improves readability for humans, but is more difficult for computers are the structure and data types differ based on the data.

The YAML format is similar to pretty JSON with the addition of custom tags for [data instructions](reference/scenario/data-instruction.md).

