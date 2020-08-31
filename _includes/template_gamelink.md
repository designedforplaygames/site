<div class="row">
### [{{include.title}}]({{include.url | relative_url}})

{% if include.game.images.logo != null -%}
<div style="float:left">
{: style="margin-right: 10px"}
![{{include.title}} Logo]({{ include.game.images.logo | relative_url }})
</div>
{% endif -%}
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
