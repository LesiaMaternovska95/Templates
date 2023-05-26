# Templates

Template for creating meshbot. Which will turn on the device every day at 8 pm in America/New_York timezone

    {
    "call": "scene_set",
    "version": "1",
    "params": {
        "name": "Temp1",
        "enabled": 1,
        "triggers": {
            "name": "schedule",
            "parameters": [
                 // setting up a trigger to run an action
                {
                    "name": "daily",
                    "times": [
                        [
                            20,
                            0
                        ]
                    ]
                },
                {
                    "name": "timezone",
                    "timezone": "America/New_York"
                }
            ]
        },
        "actions": [
            {
                "name": "ac",
                "parameters": [
                    {
                        "abstract": "68b5cc10-39d7-11ed-84de-e5e8a5b87ebe", // id of the device to which the actions will be applied
                        "capability": "power_command", // device capacity name to which the action will be applied
                        "command": "set" // command name to apply
                    },
                    {
                        "value": "1", // value to be applied(1=turn on, 0=turn off)
                        "name": "target_status", // to whom the above value will be applied
                        "transform": "integer"
                    }
                ]
            }
        ],
        "meta": {
            "type": ""
        }
    }}
