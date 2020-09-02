---
game:
    status: "shelved"
#   tgc_id: "tgc-url-slug"
#   images:
#     logo:
#       asset: "logo-image-above-game-stats"
#       title: Logo
#       display_width: optional width in pixels
#       display_height: optional height in pixels
#     blurb:
#       asset: "image-next-to-blurb"
#       title: Image
#       display_width: optional width in pixels
#       display_height: optional height in pixels
#     action_shots:
#       - asset: "action-shot"
#         title: Action Shot Name
#         display_width: optional width in pixels
#         display_height: optional height in pixels
#       - asset: "action-shot"
#         title: Action Shot Name
#         display_width: optional width in pixels
#         display_height: optional height in pixels
    min_players: "3"
    max_players: "4?"
    min_age: "12?"
    time_range: "2 hours?"
    type: "Worker placement and resource management game"
    blurb: "This will be a multi-stage game in which the players evolve from amoebas to multi-celled sea creatures, to land animals, to sentient beings.  The winner will be the player who gets into space first."
title: "Danny Amoeba™ Evolves!"
sidebar_sort_order: 500 # 200 = production, 300 = testing, 400 = idea, 500 = shelved
sidebar_category: shelved
sidebar_link_categories: testing idea shelved site
---
{% include template_game.md game=page.game title=page.title url=page.url %}
