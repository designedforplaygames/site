---
game:
    status: "idea"
    tgc_id: "freedom-building-the-next-space-station"
    images:
      logo:
        asset: "assets/freedom-shop-ad.png"
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
    min_players: "2"
    max_players: "2"
    min_age: "12"
    time_range: "15-30 minutes"
    type: "Micro card-based building game"
    blurb: "Work together to build the next international space station, but make sure you build more of it to claim international bragging rights!"
title: "Freedom - building the next space station"
sidebar_link: true
sidebar_sort_order: 400 # 200 = production, 300 = testing, 400 = idea, 500 = shelved
sidebar_category: idea
---
{% include template_game.md game=page.game title=page.title url=page.url %}
