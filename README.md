---
description: LetsFlow · the workflow engine developers love
---

# Introduction

![](.gitbook/assets/Colored.png)

LetsFlow is a workflow engine for running processes, described in YAML or JSON.

{% tabs %}
{% tab title="YAML" %}
```yaml
schema: "https://specs.letsflow.io/v0.3.0/scenario#"
title: My first scenario

actors:
  user:
    title: The user

actions:
  complete:
    title: Complete the process

states:
  initial:
    on: complete
    goto: (success)
```
{% endtab %}

{% tab title="JSON" %}
```javascript
{
    "schema": "https://specs.letsflow.io/v0.3.0/scenario#",
    "title": "My first scenario",
    "actors": {
        "user": {
            "title": "user"
        }
    },
    "actions": {
        "complete": {
            "title": "Complete the process"
        }
    },
    "states": {
        "initial": {
            "action": "complete",
            "transition": "(success)"
        }
    }
}
```
{% endtab %}

{% tab title="JSON (full)" %}
```javascript
{
    "$schema": "https://specs.letsflow.io/v0.3.0/scenario#",
    "title": "My first scenario",
    "actors": {
        "user": {
            "$schema": "https://specs.letsflow.io/v0.3.0/actor#",
            "title": "user"
        }
    },
    "actions": {
        "complete": {
            "title": "Complete the process",
            "responses": {
                "ok": {
                    "title": null,
                    "display": "always"
                    "update": [ ]
                }
            }
        }
    },
    "states": {
        "initial": {
            "actions": [
                "complete"
            ],
            "transitions": [
                {
                    "on": "*.*"
                    "goto": "(success)"
                }
            ]
        }
    }
}
```
{% endtab %}
{% endtabs %}

The _scenario_ models a _process_ as a fine state machine. The _actors_ are persons, organizations or systems that are allowed to participate on the process by performing _actions_. Which actions can be performed depends on the current _state_ of the process. After an action has been, the process will transition to a different state.
