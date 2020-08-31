{% capture game_action_asset %}assets/{{page.game.abbr}}_action.png{% endcapture %}
{% capture game_box_asset %}assets/{{page.game.abbr}}_box.png{% endcapture %}
{% capture game_shop_asset %}assets/{{page.game.abbr}}_shop.png{% endcapture %}
{% capture game_unboxed_asset %}assets/{{page.game.abbr}}_unboxed.png{% endcapture %}
<div>
[_Purchase **{{page.title}}** at The Game Crafter_](https://www.thegamecrafter.com/games/{{page.game.tgc_id}})
</div>
<div class="row">
<div class="two columns">
![{{page.title}} Shop Logo]({{ game_shop_asset | relative_url }})

| Players | {{page.game.min_players}} - {{page.game.max_players}} |
| Age | {{page.game.min_age}} + |
| Time | {{page.game.time_range}} |
| Type | {{page.game.type}} |
{% if page.game.status != "production" -%}
| Status | <span class="{{page.game.status|slugify}}">{{ page.game.status }}</span> |
{% endif %}

</div>
<div class="two columns">
![{{page.title}} Box]({{ game_box_asset | relative_url }}){:align="right"}
{{page.game.blurb}}
</div>
</div>
<div class="row">
![{{page.title}} Unboxing]({{ game_unboxed_asset | relative_url }}){:width="320" align="left"}
![{{page.title}} Action Shot]({{ game_action_asset | relative_url }}){:width="320" align="right"}
</div>
