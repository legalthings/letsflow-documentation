# Distributed workflows

LetsFlow can run distributed workflows, where parties are participating on a process on their own on-premise node. All events are shared peer-to-peer between nodes. The LTO Network hybrid blockchain ensures that there is consensus about the order of events and protects against data tempering.

Please read the [LTO Network documentation](https://docs.ltonetwork.com/) for information about creating an event chain and signing events.

Any LetsFlows object can be used as event body

{% tabs %}
{% tab title="JavaScript" %}

{% endtab %}

{% tab title="Typescript" %}

{% endtab %}

{% tab title="PHP" %}
```php
$process = [
  '$schema' => "http://specs.letsflow.io/process#",
  'id' => "b78b2536-e9dc-11e9-9af1-0fd8c4c9c7fd"
  'actors' => [
    'employer' => "234jhakaq472ql234p"
    'employee' => "mnaiuaq457812u23jl"
  ]
],

// Existing chain, see LTO docs for more info
$chainId = "bed470d6-e9dc-11e9-b9ed-d7776408921c";
$chainLastHash = "be24ebf2-e9dc-11e9-acb2-0b17a5467ce1";

$chain = new LTO\EventChain($chainId, $chainLastHash);
$chain->add(new Event($process))->signWith($account);

$response = $httpClient->request(
  'POST',
  'https://mynode.example.com/event-chains',
  ['json' => $chain]
);
```
{% endtab %}

{% tab title="Python" %}

{% endtab %}

{% tab title="Go" %}

{% endtab %}
{% endtabs %}



