---
game:
    status: "shelved"
    tgc_id: "spods"
    images:
      logo:
        asset: "assets/spods_logo_2.png"
      blurb:
        asset: "assets/spods_blurb.png"
      action_shots: []
    min_players: "2"
    max_players: "3"
    min_age: "12"
    time_range: "30 minutes"
    type: "Tactical tile placement game"
    blurb: "In this tactical tile placement game, join elements together from different tiles to form chains.  Keep track of your longest chain from each element - and then, at the end of the game, whoever has the longest "short" chain wins."
title: "spods™"
sidebar_link: true
sidebar_sort_order: 500 # 200 = production, 300 = testing, 400 = idea, 500 = shelved
sidebar_category: shelved
---
{% include template_game.md game=page.game title=page.title url=page.url %}
