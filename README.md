---
description: >-
  A workflow describes an orchestrated and repeatable pattern of business
  activity.
---

# Introduction

![](.gitbook/assets/colored.png)

LetsFlow is a workflow engine for running business processes. A _process_ is modeled as a finite state machine, where an _action_, performed by an _actor_, causes a _state_ transition. The definition of a model is called the _scenario_.

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
    action: complete
    transition: :success
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
            "transition": ":success"
        }
    }
}
```
{% endtab %}
{% endtabs %}



