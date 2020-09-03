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
    max_players: "5"
    min_age: "12"
    time_range: "30-60 minutes"
    type: "Cooperative worker placement"
    blurb: |-
        A generic Giant Monster is attacking your city!  Can the players work together to kill it?

        The players each play one (or two) roles in the defense of a city against a rampaging Giant Monster.  The Monster slowly moves through town, killing population right and left.  The idea is to kill the Monster before all the population downtown is killed.

        The downtown part of the city is randomly formed from a set of building cards.  4 blocks each hold two buildings, one on each side of the main street.  The Generic Giant Beast starts at one end.  The players get a few turns of setup before the Beast starts rampaging.  Players control armed forces figures (infantry, armored tanks, light-armored troop carriers, helicopters, jets) plus scientific research of some sort.

        Each role gives an advantage to one particular kind of player action.
title: "Attack of the Radioactive (and Very Very Angry) Generic Giant Monster"
sidebar_sort_order: 500 # 200 = production, 300 = testing, 400 = idea, 500 = shelved
sidebar_category: shelved
sidebar_link_categories: testing development idea shelved site
---
{% include template_game.md game=page.game title=page.title url=page.url %}
