# Logs analysis
* For now only `.json` logs can be parsed;
* Implementation of visualization is in progress;

Everything is implemented in `log_analyzer.ipynb`

## The schema (is also presented in the .ipynb)

```json
[
    {
        "game_number": int,
        "mist_episode": int (-1 if a game ended quicker than the mist started),
        "menhir_pos": [int, int],
        "arena_name": string,
        "episodes_number": int,
        "bots": {
            "bot_name_1": {
                "name": string,
                "start_coords": [int, int],
                "last_coords": [int, int],
                "failed_steps": [
                    {
                        "episode": int,
                        "error_text": string,
                        "coords": [int, int]
                    },
                    ...
                ],
                "actions": [string, string, ...],
                "episode_died": int (-1 if a last bot standing),
                "last_attack_type": string (either 'mist' or 'weapon')
            },
            "bot_name_2": ...,
            ...
        }
    },
    ...
]
```