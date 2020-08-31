{% capture game_action_asset %}assets/{{include.game.abbr}}_action.png{% endcapture %}
{% capture game_box_asset %}assets/{{include.game.abbr}}_box.png{% endcapture %}
{% capture game_shop_asset %}assets/{{include.game.abbr}}_shop.png{% endcapture %}
{% capture game_unboxed_asset %}assets/{{include.game.abbr}}_unboxed.png{% endcapture %}
<div class="row">
### [{{include.title}}]({{include.url | relative_url}})

<div style="float:left">
[![{{include.title}} Shop Logo]({{ game_shop_asset | relative_url }})]({{include.url | relative_url}})
{: style="margin-right: 10px"}
</div>
<div style="float:left">

| Players | {{include.game.min_players}} - {{include.game.max_players}} |
| Age | {{include.game.min_age}} + |
| Time | {{include.game.time_range}} |
| Type | {{include.game.type}} |
{% if include.game.status != "production" -%}
| Status | <span class="status {{include.game.status|slugify}}">{{ include.game.status }}</span> |
{% endif %}
{: width="50%"}

</div>
</div>
