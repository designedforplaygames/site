---
game:
    status: "published"
    tgc_id: "roads-rails-rivers-trails"
    images:
      logo:
        asset: "assets/rrrt_shop.png"
        title: Logo
      blurb:
        asset: "assets/rrrt_box.png"
        title: Box
      action_shots:
        - asset: "assets/rrrt_unboxed.png"
          title: Unboxed
          display_width: 320
        - asset: "assets/rrrt_action.png"
          title: In Play
          display_width: 320
    min_players: "2"
    max_players: "4"
    min_age: "12"
    time_range: "15-30 minutes"
    type: "Tactical tile placement game"
    blurb: "Play your cards to build a shared network of roads and rails, rivers and trails.  Block your opponents while scoring paths for yourself - but don't foget about any of your own paths, or you'll be caught short at the end!"
title: "Roads and Rails, Rivers and Trails"
sidebar_link: true
sidebar_sort_order: 200 # 200 = production, 300 = testing, 400 = idea, 500 = shelved
category: published
---
{% include template_game.md game=page.game title=page.title url=page.url %}
