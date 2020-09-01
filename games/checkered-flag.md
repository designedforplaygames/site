---
game:
    status: "idea"
#   tgc_id: "tgc-url-slug"
    images:
#     logo:
#       asset: "logo-image-above-game-stats"
#       title: Logo
#       display_width: optional width in pixels
#       display_height: optional height in pixels
      blurb:
        asset: "assets/checkered-flag.png"
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
    max_players: "4"
    min_age: "12"
    time_range: "???"
    type: "Racing game"
    blurb: |-
        Main idea:  Inspired by Atari® Pole Position™, by Descartes™ Formula De™,  and by Wizards of the Coast® Robo Rally®.

        Each player is a driver controlling a car racing around a circuit track.  Each turn, players decide how their car is going to move that turn, playing between 1 and 4 cards in a specific order to direct their car down the track.
title: "Checkered Flag"
---
{% include template_game.md game=page.game title=page.title url=page.url %}
