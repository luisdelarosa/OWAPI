# OWAPI API Docs

## Notes

Regions and platforms can be overridden with URL parameters.

#### Regions *(V2)

For example, if you wanted to force fetching of US stats, add `?region=us`:

```
$ http GET "https://owapi.net/api/v2/u/SunDwarf-21353/stats/general?region=us"
```

Note that if they are not overridden, the API will automatically determine which region to use.

#### Regions *(V3)

In V3, all regions are automatically checked. Data is returned for any regions the user is in. The other regions return `null`. See V3 results below.

#### Platforms

You can override the platform with `?platform=<pc|xbl|psn>`. This defaults to `pc`.

#### Formatting

The default output is standard JSON, but you can prettify it with `?format=json_pretty"` to have it in a more readable format. (The other option is installing a browser plugin, such as [JSONView](https://jsonview.com/).

---

## V3

### `GET /api/v3/u/:battletag/blob`
**Get a blob of information about user stats, achievements, and heroes.**

*Example:*

`https://owapi.net/api/v3/u/Dad-12262/blob`

*Result:*

```json
{

    "_request": {
        "api_ver": 3,
        "route": "/api/v3/u/Dad-12262/blob"
    },
    "kr": null,
    "eu": null,
    "us": {
        "stats": {},
        "heroes": {},
        "achievements": {},
    "any": null

}
```

See below for detailed response on `stats`, `heroes`, and `achievements`.

### `GET /api/v3/u/:battletag/stats`
**Get user stats, both competitive & quickplay**

*Example:*

`https://owapi.net/api/v3/u/Dad-12262/stats`

*Result:*

```json
{

    "_request": {
        "api_ver": 3,
        "route": "/api/v3/u/Dad-12262/stats"
    },
    "kr": null,
    "eu": null,
    "us": {
        "stats": {
            "competitive": {
                "overall_stats": {
                    "win_rate": 52,
                    "level": 20,
                    "prestige": 1,
                    "avatar": "https://blzgdapipro-a.akamaihd.net/game/unlocks/0x0250000000000BBA.png",
                    "wins": 9,
                    "games": 17,
                    "comprank": 2395,
                    "losses": 8
                },
                "game_stats": {
                    "objective_kills": 121.0,
                    "games_won": 9.0,
                    "kpd": 1.92,
                    "objective_kills_most_in_game": 26.0,
                    "time_spent_on_fire_most_in_game": 0.075,
                    "healing_done": 15798.0,
                    "defensive_assists": 20.0,
                    "offensive_assists": 4.0,
                    "final_blows_most_in_game": 22.0,
                    "objective_time": 0.37027777777777776,
                    "melee_final_blows": 3.0,
                    "medals": 37.0,
                    "cards": 4.0,
                    "multikill_best": 4.0,
                    "overwatch.guid.0x086000000000042e": 8.0,
                    "multikills": 4.0,
                    "defensive_assists_most_in_game": 11.0,
                    "offensive_assists_most_in_game": 2.0,
                    "melee_final_blow_most_in_game": 1.0,
                    "damage_done": 201576.0,
                    "medals_silver": 12.0,
                    "medals_gold": 12.0,
                    "healing_done_most_in_game": 2597.0,
                    "environmental_kills": 5.0,
                    "medals_bronze": 13.0,
                    "solo_kills": 29.0,
                    "time_spent_on_fire": 0.33999999999999997,
                    "eliminations_most_in_game": 44.0,
                    "final_blows": 152.0,
                    "time_played": 3.0,
                    "environmental_deaths": 6.0,
                    "solo_kills_most_in_game": 22.0,
                    "damage_done_most_in_game": 22230.0,
                    "games_played": 17.0,
                    "eliminations": 315.0,
                    "objective_time_most_in_game": 0.060000000000000005,
                    "deaths": 164.0
                },
                "competitive": true,
                "average_stats": {
                    "healing_done_avg": 929.0,
                    "eliminations_avg": 18.52,
                    "melee_final_blows_avg": 0.17,
                    "final_blows_avg": 8.94,
                    "defensive_assists_avg": 1.0,
                    "damage_done_avg": 11857.0,
                    "deaths_avg": 9.64,
                    "objective_time_avg": 0.021666666666666667,
                    "offensive_assists_avg": 0.0,
                    "solo_kills_avg": 1.7,
                    "time_spent_on_fire_avg": 0.02,
                    "objective_kills_avg": 7.11
                }
            },
            "quickplay": {
                "overall_stats": {
                    "win_rate": 0,
                    "level": 20,
                    "prestige": 1,
                    "avatar": "https://blzgdapipro-a.akamaihd.net/game/unlocks/0x0250000000000BBA.png",
                    "wins": 373,
                    "games": null,
                    "comprank": 2395,
                    "losses": null
                },
                "game_stats": {
                    "objective_kills": 3127.0,
                    "games_won": 373.0,
                    "objective_kills_most_in_game": 24.0,
                    "melee_final_blows_most_in_game": 3.0,
                    "time_spent_on_fire_most_in_game": 0.1825,
                    "healing_done": 635470.0,
                    "offensive_assists": 202.0,
                    "final_blows_most_in_game": 23.0,
                    "objective_time": 7.751944444444445,
                    "melee_final_blows": 99.0,
                    "medals": 1866.0,
                    "cards": 220.0,
                    "multikill_best": 4.0,
                    "defensive_assists": 586.0,
                    "recon_assists": 17.0,
                    "multikills": 65.0,
                    "defensive_assists_most_in_game": 15.0,
                    "offensive_assists_most_in_game": 12.0,
                    "damage_done": 3509708.0,
                    "teleporter_pads_destroyed": 28.0,
                    "medals_silver": 649.0,
                    "medals_gold": 604.0,
                    "healing_done_most_in_game": 12482.0,
                    "environmental_kills": 86.0,
                    "medals_bronze": 613.0,
                    "solo_kills": 1632.0,
                    "time_spent_on_fire": 10.516944444444444,
                    "eliminations_most_in_game": 39.0,
                    "final_blows": 4660.0,
                    "time_played": 94.0,
                    "environmental_deaths": 139.0,
                    "solo_kills_most_in_game": 23.0,
                    "damage_done_most_in_game": 15485.0,
                    "kpd": 1.74,
                    "eliminations": 8743.0,
                    "objective_time_most_in_game": 0.06472222222222222,
                    "deaths": 5028.0
                },
                "competitive": false,
                "average_stats": {
                    "healing_done_avg": 879.0,
                    "eliminations_avg": 12.09,
                    "melee_final_blows_avg": 0.13,
                    "final_blows_avg": 6.44,
                    "defensive_assists_avg": 1.0,
                    "damage_done_avg": 4854.0,
                    "deaths_avg": 6.95,
                    "objective_time_avg": 0.010555555555555556,
                    "offensive_assists_avg": 0.0,
                    "solo_kills_avg": 2.25,
                    "time_spent_on_fire_avg": 0.014444444444444446,
                    "objective_kills_avg": 4.32
                }
            }
        },
        "heroes": {
            "stats": {
                "quickplay": { },
                "competitive": { }
            },
            "playtime": {
                "quickplay": { },
                "competitive": { }
            }
        },
        "achievements": { }
    },
    "any": null

}
```

### `GET /api/v3/u/:battletag/achievements`
**Get user achievements status.**

*Example:*

`https://owapi.net/api/v3/u/Dad-12262/achievements`

*Result:*

```json
{

    "_request": {
        "api_ver": 3,
        "route": "/api/v3/u/Dad-12262/achievements"
    },
    "kr": null,
    "eu": null,
    "us": {
        "stats": { },
        "heroes": {
            "stats": {
                "quickplay": { },
                "competitive": { }
            },
            "playtime": {
                "quickplay": { },
                "competitive": { }
            }
        },
        "achievements": {
            "defense": {
                "ice_blocked": true,
                "triple_threat": false,
                "simple_geometry": false,
                "the_dragon_is_sated": false,
                "did_that_sting": true,
                "mine_like_a_steel_trap": true,
                "charge": false,
                "cold_snap": false,
                "raid_wipe": true,
                "armor_up": true,
                "roadkill": true,
                "smooth_as_silk": true
            },
            "offense": {
                "whoa_there": true,
                "die_die_die_die": false,
                "its_high_noon": false,
                "their_own_worst_enemy": false,
                "clearing_the_area": true,
                "target_rich_environment": true,
                "death_from_above": false,
                "total_recall": true,
                "rocket_man": false,
                "slice_and_dice": false,
                "special_delivery": false,
                "waste_not_want_not": false
            },
            "support": {
                "rapid_discord": false,
                "enabler": false,
                "huge_rez": true,
                "supersonic": true,
                "naptime": false,
                "huge_success": false,
                "the_iris_embraces_you": false,
                "the_car_wash": true,
                "the_floor_is_lava": false,
                "group_health_plan": true
            },
            "general": {
                "decorated": true,
                "blackjack": true,
                "centenary": true,
                "undying": true,
                "level_10": true,
                "the_path_is_closed": true,
                "level_50": true,
                "level_25": true,
                "decked_out": false,
                "survival_expert": false,
                "the_friend_zone": true
            },
            "tank": {
                "i_am_your_shield": true,
                "mine_sweeper": false,
                "storm_earth_and_fire": false,
                "giving_you_the_hook": true,
                "power_overwhelming": true,
                "anger_management": false,
                "hog_wild": true,
                "the_power_of_attraction": true,
                "shot_down": false,
                "game_over": false
            },
            "maps": {
                "world_traveler": true,
                "lockdown": true,
                "cant_touch_this": true,
                "shutout": true,
                "escort_duty": true,
                "double_cap": true
            }
        }
    },
    "any": null

}
```

### `GET /api/v3/u/:battletag/heroes`
**Get user hero stats**

*Example:*

`https://owapi.net/api/v3/u/Dad-12262/heroes`

*Result:*

```json
{

    "_request": {
        "api_ver": 3,
        "route": "/api/v3/u/Dad-12262/heroes"
    },
    "kr": null,
    "eu": null,
    "us": {
        "stats": { },
        "heroes": {
            "stats": {
                "quickplay": {
                    "junkrat": {
                        "general_stats": {
                            "objective_kills": 273.0,
                            "overwatch.guid.0x0860000000000031": 2161.0,
                            "objective_kills_most_in_game": 15.0,
                            "medals_gold": 53.0,
                            "eliminations_most_in_life": 11.0,
                            "final_blows_most_in_game": 20.0,
                            "melee_final_blow": 1.0,
                            "overwatch.guid.0x08600000000001bb": "60%",
                            "cards": 9.0,
                            "multikill_best": 4.0,
                            "overwatch.guid.0x086000000000033d": 59.0,
                            "eliminations_per_life": 1.8,
                            "multikills": 4.0,
                            "kill_streak_best": 11.0,
                            "eliminations_most_in_game": 29.0,
                            "damage_done": 425330.0,
                            "teleporter_pads_destroyed": 3.0,
                            "medals_silver": 54.0,
                            "damage_done_most_in_life": 7125.0,
                            "objective_time": "18:56",
                            "environmental_kills": 2.0,
                            "weapon_accuracy": "23%",
                            "medals_bronze": 45.0,
                            "solo_kills": 225.0,
                            "time_spent_on_fire": "31:21",
                            "medals": 152.0,
                            "final_blows": 536.0,
                            "time_played": "7 hours",
                            "environmental_deaths": 10.0,
                            "solo_kills_most_in_game": 11.0,
                            "overwatch.guid.0x0860000000000030": 9172.0,
                            "damage_done_most_in_game": 11795.0,
                            "games_won": 28.0,
                            "eliminations": 827.0,
                            "objective_time_most_in_game": "01:00",
                            "deaths": 459.0
                        },
                        "hero_stats": {
                            "rip-tire_kills_most_in_game": 9.0,
                            "rip-tire_kills": 129.0,
                            "enemies_trapped": 356.0,
                            "enemies_trapped_most_in_game": 12.0,
                            "enemies_trapped_a_minute": 6.08,
                            "melee_final_blow_most_in_game": 1.0
                        }
                    }
                },
                "competitive": {
                    "junkrat": {
                        "general_stats": {
                            "objective_kills": 13.0,
                            "overwatch.guid.0x0860000000000031": 98.0,
                            "objective_kills_most_in_game": 5.0,
                            "medals_gold": 1.0,
                            "overwatch.guid.0x0860000000000430": 1.0,
                            "eliminations_most_in_life": 5.0,
                            "win_percentage": "69%",
                            "final_blows_most_in_game": 8.0,
                            "objective_time": "00:32",
                            "overwatch.guid.0x08600000000001bb": "80%",
                            "eliminations_per_life": 1.2,
                            "kill_streak_best": 5.0,
                            "eliminations_most_in_game": 10.0,
                            "damage_done": 21895.0,
                            "medals_silver": 2.0,
                            "damage_done_most_in_life": 2414.0,
                            "weapon_accuracy": "27%",
                            "medals_bronze": 1.0,
                            "solo_kills": 5.0,
                            "time_spent_on_fire": "00:10",
                            "medals": 3.0,
                            "final_blows": 16.0,
                            "time_played": "16 minutes",
                            "solo_kills_most_in_game": 2.0,
                            "overwatch.guid.0x0860000000000030": 359.0,
                            "damage_done_most_in_game": 5317.0,
                            "games_played": 2.0,
                            "games_won": 1.0,
                            "eliminations": 24.0,
                            "objective_time_most_in_game": "00:09",
                            "deaths": 20.0
                        },
                        "hero_stats": {
                            "enemies_trapped_a_minute": 8.71,
                            "enemies_trapped": 15.0,
                            "enemies_trapped_most_in_game": 4.0
                        }
                    }
                }
            },
            "playtime": {
                "quickplay": {
                    "junkrat": 7.0,
                    "soldier76": 3.0,
                    "hanzo": 0.8333333333333334,
                    "bastion": 0.3333333333333333,
                    "torbjorn": 6.0,
                    "winston": 6.0,
                    "dva": 0.5166666666666667,
                    "ana": 0,
                    "reinhardt": 16.0,
                    "lucio": 3.0,
                    "pharah": 8.0,
                    "zenyatta": 1.0,
                    "reaper": 0.2833333333333333,
                    "zarya": 7.0,
                    "mercy": 7.0,
                    "symmetra": 4.0,
                    "mccree": 3.0,
                    "widowmaker": 3.0,
                    "mei": 1.0,
                    "tracer": 2.0,
                    "roadhog": 8.0,
                    "genji": 0.26666666666666666
                },
                "competitive": {
                    "junkrat": 0.26666666666666666,
                    "soldier76": 0.03333333333333333,
                    "hanzo": 0,
                    "bastion": 0.01,
                    "torbjorn": 0,
                    "winston": 0.03333333333333333,
                    "dva": 0.0005555555555555556,
                    "ana": 0,
                    "reinhardt": 0.6833333333333333,
                    "lucio": 0.11666666666666667,
                    "pharah": 0.7833333333333333,
                    "mccree": 0,
                    "reaper": 0,
                    "zarya": 0.48333333333333334,
                    "mercy": 0.05,
                    "symmetra": 0,
                    "zenyatta": 0.05,
                    "widowmaker": 0,
                    "mei": 0.016666666666666666,
                    "tracer": 0.05,
                    "roadhog": 0.45,
                    "genji": 0
                }
            }
        },
        "achievements": { }
    },
    "any": null

}
```

Each hero has personal `hero_stats` keys.

## V2

** All times are in *HOURS* unless specified otherwise. **


### `GET /api/v2/u/:battletag/stats`
**Get the basic stats of a user.**

*Example:*

```
$ http GET "https://owapi.net/api/v2/u/SunDwarf-21353/stats/general"
```

*Result:*
```json
HTTP/1.1 200 OK
Content-Length: 1788
Content-Type: application/json
Date: Wed, 20 Jul 2016 17:19:37 -0000
Server: Kyoukai/1.3.8 (see https://github.com/SunDwarf/Kyoukai)

{
    "_request": {
        "api_ver": 1,
        "route": "/api/v2/u/SunDwarf-21353/stats/general"
    },
    "average_stats": {
        "damage_done_avg": 3987.0,
        "deaths_avg": 5.68,
        "defensive_assists_avg": 0.0,
        "eliminations_avg": 10.47,
        "final_blows_avg": 6.12,
        "healing_done_avg": 589.0,
        "melee_final_blows_avg": 0.03,
        "objective_kills_avg": 3.06,
        "objective_time_avg": 0.007222222222222223,
        "offensive_assists_avg": 0.0,
        "solo_kills_avg": 2.3,
        "time_spent_on_fire_avg": 0.008055555555555555
    },
    "battletag": "SunDwarf-21353",
    "game_stats": {
        "cards": 36.0,
        "damage_done": 478462.0,
        "damage_done_most_in_game": 13303.0,
        "deaths": 682.0,
        "defensive_assists": 39.0,
        "defensive_assists_most_in_game": 11.0,
        "eliminations": 1257.0,
        "eliminations_most_in_game": 26.0,
        "environmental_deaths": 12.0,
        "environmental_kills": 8.0,
        "final_blows": 735.0,
        "final_blows_most_in_game": 16.0,
        "games_played": 120.0,
        "games_won": 59.0,
        "healing_done": 70670.0,
        "healing_done_most_in_game": 7832.0,
        "kpd": 1.84,
        "medals": 304.0,
        "medals_bronze": 102.0,
        "medals_gold": 100.0,
        "medals_silver": 102.0,
        "melee_final_blows": 4.0,
        "melee_final_blows_most_in_game": 2.0,
        "multikill_best": 3.0,
        "multikills": 5.0,
        "objective_kills": 368.0,
        "objective_kills_most_in_game": 10.0,
        "objective_time": 0.8880555555555555,
        "objective_time_most_in_game": 0.026944444444444444,
        "offensive_assists": 13.0,
        "offensive_assists_most_in_game": 7.0,
        "recon_assists": 9.0,
        "solo_kills": 277.0,
        "solo_kills_most_in_game": 16.0,
        "time_played": 15.0,
        "time_spent_on_fire": 0.9961111111111111,
        "time_spent_on_fire_most_in_game": 0.08833333333333333
    },
    "overall_stats": {
        "avatar": "https://blzgdapipro-a.akamaihd.net/game/unlocks/0x02500000000008E8.png",
        "comprank": null,
        "games": 120,
        "level": 24,
        "losses": 61,
        "prestige": 0,
        "win_rate": 49,
        "wins": 59
    },
    "region": "eu"
}


```

### `GET /api/v2/u/:battletag/stats/competitive`
**Get the basic competitive stats of a user.**

Like all API requests, this will automatically determine the region of the user.

*Example:*

```
$ http GET "https://owapi.net/api/v2/u/Aurelius-1648/stats/competitive"
```

*Result:*
```json
HTTP/1.1 200 OK
Content-Length: 1811
Content-Type: application/json
Date: Wed, 20 Jul 2016 17:24:06 -0000
Server: Kyoukai/1.3.6 (see https://github.com/SunDwarf/Kyoukai)

{
    "_request": {
        "api_ver": 1,
        "route": "/api/v2/u/Aurelius-1648/stats/competitive"
    },
    "average_stats": {
        "damage_done_avg": 7469.0,
        "deaths_avg": 10.35,
        "defensive_assists_avg": 2.0,
        "eliminations_avg": 16.16,
        "final_blows_avg": 8.37,
        "healing_done_avg": 1440.0,
        "melee_final_blows_avg": 0.1,
        "objective_kills_avg": 7.43,
        "objective_time_avg": 0.02027777777777778,
        "offensive_assists_avg": 0.0,
        "solo_kills_avg": 1.78,
        "time_spent_on_fire_avg": 0.01972222222222222
    },
    "battletag": "Aurelius-1648",
    "game_stats": {
        "cards": 5.0,
        "damage_done": 276363.0,
        "damage_done_most_in_game": 22155.0,
        "deaths": 383.0,
        "defensive_assists": 62.0,
        "defensive_assists_most_in_game": 25.0,
        "eliminations": 598.0,
        "eliminations_most_in_game": 50.0,
        "environmental_deaths": 12.0,
        "environmental_kills": 4.0,
        "final_blows": 310.0,
        "final_blows_most_in_game": 24.0,
        "games_played": 37.0,
        "games_won": 15.0,
        "healing_done": 53276.0,
        "healing_done_most_in_game": 10380.0,
        "kpd": 1.56,
        "medals": 74.0,
        "medals_bronze": 29.0,
        "medals_gold": 23.0,
        "medals_silver": 22.0,
        "melee_final_blows": 4.0,
        "melee_final_blows_most_in_game": 2.0,
        "multikill_best": 4.0,
        "multikills": 8.0,
        "objective_kills": 275.0,
        "objective_kills_most_in_game": 27.0,
        "objective_time": 0.7519444444444444,
        "objective_time_most_in_game": 0.05611111111111111,
        "offensive_assists": 13.0,
        "offensive_assists_most_in_game": 7.0,
        "recon_assists": 2.0,
        "solo_kills": 66.0,
        "solo_kills_most_in_game": 24.0,
        "teleporter_pad_destroyed": 1.0,
        "time_played": 7.0,
        "time_spent_on_fire": 0.7347222222222223,
        "time_spent_on_fire_most_in_game": 0.12305555555555556
    },
    "overall_stats": {
        "avatar": "https://blzgdapipro-a.akamaihd.net/game/unlocks/0x02500000000008C1.png",
        "comprank": 52,
        "games": 37,
        "level": 83,
        "losses": 22,
        "prestige": 0,
        "win_rate": 40,
        "wins": 15
    },
    "region": "us"
}


```

### `GET /api/v2/u/:battletag/heroes/general`

**Get the list of heroes that a person has played as, and the time, in quickplay.**

*Example*:
```
$ http GET https://owapi.net/api/v2/u/SunDwarf-21353/heroes/general
```

*Result*:

```json
HTTP/1.1 200 OK
Content-Length: 619
Content-Type: application/json
Date: Wed, 20 Jul 2016 17:19:21 -0000
Server: Kyoukai/1.3.6 (see https://github.com/SunDwarf/Kyoukai)

{
    "_request": {
        "api_ver": 1,
        "route": "/api/v2/u/SunDwarf-21353/heroes/general"
    },
    "battletag": "SunDwarf-21353",
    "heroes": {
        "ana": 0,
        "bastion": 0.2833333333333333,
        "dva": 1.0,
        "genji": 0.1,
        "hanzo": 0.4666666666666667,
        "junkrat": 0.9333333333333333,
        "lucio": 0.85,
        "mccree": 0.7333333333333333,
        "mei": 0.4166666666666667,
        "mercy": 0.38333333333333336,
        "pharah": 3.0,
        "reaper": 0.25,
        "reinhardt": 2.0,
        "roadhog": 0.16666666666666666,
        "soldier76": 1.0,
        "symmetra": 0.010277777777777778,
        "torbjorn": 0.08333333333333333,
        "tracer": 0.4,
        "widowmaker": 0.7333333333333333,
        "winston": 0,
        "zarya": 0,
        "zenyatta": 0.05
    },
    "region": "eu"
}
```

### `GET /api/v2/u/:battletag/heroes/competitive`

**Get the list of heroes that a person has played as, and the time, in competitive.**

*Example*:
```
$ http GET https://owapi.net/api/v2/u/SunDwarf-21353/heroes/competitive
```

*Result*:

```json
HTTP/1.1 200 OK
Connection: keep-alive
Content-Length: 570
Content-Type: application/json
Date: Thu, 11 Aug 2016 10:57:37 GMT
Server: nginx/1.10.0 (Ubuntu)
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
X-Powered-By: Kyoukai

{
    "_request": {
        "api_ver": 2,
        "route": "/api/v2/u/SunDwarf-21353/heroes/competitive"
    },
    "battletag": "SunDwarf-21353",
    "heroes": {
        "ana": 0,
        "bastion": 0,
        "dva": 0,
        "genji": 0.11666666666666667,
        "hanzo": 0,
        "junkrat": 0.03333333333333333,
        "lucio": 0,
        "mccree": 0.35,
        "mei": 0,
        "mercy": 0,
        "pharah": 0.2,
        "reaper": 0.23333333333333334,
        "reinhardt": 0.9166666666666666,
        "roadhog": 0.18333333333333332,
        "soldier76": 0.21666666666666667,
        "symmetra": 0,
        "torbjorn": 0,
        "tracer": 0.03333333333333333,
        "widowmaker": 0.15,
        "winston": 0,
        "zarya": 0,
        "zenyatta": 0
    },
    "region": "eu"
}

```

### `GET /api/v2/u/:battletag/heroes/:heroname/general`

**Get detailed information about a player's performance as a hero, in quickplay.**

Note that hero names do not have special characters (lucio not lúcio) and
are lowercase. Use `d.va` or `dva` for D.va and `s76` or `soldier76` for S76.

*Example*:
```
$ http GET "https://owapi.net/api/v2/u/Aurelius-1648/heroes/reinhardt/general"
```

*Result*:

```json
{
    "hero_stats": {
        "damage_blocked_most_in_game": 27137.0,
        "charge_kills": 385.0,
        "fire_strike_kills_most_in_game": 13.0,
        "earthshatter_kills": 487.0,
        "charge_kills_most_in_game": 9.0,
        "damage_blocked": 2046918.0,
        "earthshatter_kills_most_in_game": 9.0,
        "fire_strike_kills": 690.0
    },
    "battletag": "Aurelius-1648",
    "_request": {
        "api_ver": 1,
        "route": "/api/v2/u/Aurelius-1648/heroes/reinhardt"
    },
    "general_stats": {
        "games_won": 104.0,
        "medals_gold": 204.0,
        "eliminations": 2279.0,
        "damage_done": 882436.0,
        "multikill_best": 5.0,
        "medals_bronze": 139.0,
        "eliminations_most_in_life": 18.0,
        "medals": 513.0,
        "games_played": 197.0,
        "eliminations_per_life": 1.65,
        "objective_time": 13426.0,
        "time_spent_on_fire": 12365.0,
        "final_blows_most_in_game": 20.0,
        "medals_silver": 171.0,
        "solo_kills": 335.0,
        "time_played": "25 hours",
        "teleporter_pads_destroyed": 1.0,
        "eliminations_most_in_game": 33.0,
        "environmental_kills": 13.0,
        "environmental_deaths": 40.0,
        "damage_done_most_in_life": 5630.0,
        "objective_time_most_in_game": 249.0,
        "cards": 91.0,
        "objective_kills_most_in_game": 17.0,
        "multikills": 33.0,
        "win_percentage": "52%",
        "final_blows": 1340.0,
        "solo_kills_most_in_game": 6.0,
        "damage_done_most_in_game": 13569.0,
        "deaths": 1378.0,
        "objective_kills": 957.0
    },
    "region": "us"
}
```

### `GET /api/v2/u/:battletag/heroes/:heroname/competitive`

**Get detailed information about a player's performance as a hero, in competitive.**

Note that hero names do not have special characters (lucio not lúcio) and
are lowercase. Use `d.va` or `dva` for D.va and `s76` or `soldier76` for S76.

*Example*:
```
$ http GET "https://owapi.net/api/v2/u/SunDwarf-21353/heroes/reinhardt/competitive"
```

*Result*:


```json
{
  "battletag": "SunDwarf-21353",
  "region": "eu",
  "_request": {
    "route": "/api/v2/u/SunDwarf-21353/heroes/reinhardt/general",
    "api_ver": 2
  },
  "hero_stats": {
    "charge_kills": 63,
    "earthshatter_kills": 55,
    "damage_blocked": 360541,
    "damage_blocked_most_in_game": 21119,
    "fire_strike_kills_most_in_game": 8,
    "earthshatter_kills_most_in_game": 6,
    "fire_strike_kills": 109,
    "charge_kills_most_in_game": 5
  },
  "general_stats": {
    "damage_done_most_in_life": 3199,
    "final_blows": 190,
    "objective_kills": 121,
    "eliminations_most_in_life": 10,
    "medals_silver": 25,
    "environmental_kills": 3,
    "time_played": "4 hours",
    "medals_bronze": 24,
    "games_played": 35,
    "objective_kills_most_in_game": 11,
    "final_blows_most_in_game": 14,
    "objective_time": "23:49",
    "medals_gold": 20,
    "games_won": 18,
    "eliminations": 308,
    "objective_time_most_in_game": "01:58",
    "environmental_deaths": 13,
    "multikill_best": 3,
    "medals": 70,
    "cards": 15,
    "win_percentage": "52%",
    "eliminations_per_life": 1.61,
    "deaths": 191,
    "damage_done_most_in_game": 6940,
    "solo_kills_most_in_game": 4,
    "multikills": 2,
    "kill_streak_best": 10,
    "solo_kills": 52,
    "damage_done": 114410,
    "time_spent_on_fire": "08:06",
    "eliminations_most_in_game": 18
  },
  "competitive": false
}
```
