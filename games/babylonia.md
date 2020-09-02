---
game:
    status: "idea"
#   tgc_id: "tgc-url-slug"
    images:
      logo:
        asset: "assets/babylonia-babylon-screen.png"
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
    max_players: "4??"
    min_age: "12"
    time_range: "???"
    type: "Worker placement and resource management"
    blurb: |-
        Babylonia started out as my attempt to remake the old text-based computer game "Hamurabi", and evolved into a worker placement and competitive bidding game.

        Each year, players allocate workers to a variety of possible tasks:  planting and harvesting food, selling or purchasing fields, selling or purchasing beasts of burden, speaking at the forum, or helping to construct buildings.

        planting and harvesting food consumes a small amount of food to be used for seed, and then adds a (usually larger) amount of food based on a random harvest result.

        selling or purchasing fields and beasts of burden both use a market system that changes the price based on the number of buyers and sellers at any one time; the price is paid in food.  Beasts of burden can act as additional workers when paired with an actual worker.

        speaking at the forum is the political action, influencing turn order.

        finally, constructing buildings is the primary way to gain victory points:  when a building is constructed, it is added to the kingdom which contributed the most work into building it by dedicating workers (and beasts of burden) to the building's construction (this is the "competitive bidding" part of the game).  small and medium sized buildings have effects on the yearly management of the kingdom, and the large monuments give bonus victory points at the end of the game.
title: "Babylonia"
sidebar_sort_order: 400 # 200 = production, 300 = testing, 400 = idea, 500 = shelved
sidebar_category: idea
sidebar_link_categories: testing idea shelved site
---
{% include template_game.md game=page.game title=page.title url=page.url %}
