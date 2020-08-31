{% capture game_action_asset %}assets/{{include.abbr}}_action.png{% endcapture %}
{% capture game_box_asset %}assets/{{include.abbr}}_box.png{% endcapture %}
{% capture game_shop_asset %}assets/{{include.abbr}}_shop.png{% endcapture %}
{% capture game_unboxed_asset %}assets/{{include.abbr}}_unboxed.png{% endcapture %}
<div>
[_Purchase **{{include.title}}** at The Game Crafter_](https://www.thegamecrafter.com/games/{{include.tgc_id}})
</div>
<div class="row">
<div class="two columns">
![{{include.title}} Shop Logo]({{ game_shop_asset | relative_url }})

| Players | {{include.min_players}} - {{include.max_players}} |
| Age | {{include.min_age}} + |
| Time | {{include.time_range}} |
| Type | {{include.type}} |

</div>
<div class="two columns">
![{{include.title}} Box]({{ game_box_asset | relative_url }}){:align="right"}
{{include.blurb}}
</div>
</div>
<div class="row">
![{{include.title}} Unboxing]({{ game_unboxed_asset | relative_url }}){:width="320" align="left"}
![{{include.title}} Action Shot]({{ game_action_asset | relative_url }}){:width="320" align="right"}
</div>
