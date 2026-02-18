# RLBot v5 C# Example

This is a simple example of a RLBot bot written in C#.
It is designed to be easy to understand and modify,
making it a great starting point for anyone looking to create their own RLBot bot in C#.

## Getting Started

To get started, you will need to have the following software installed on your computer:

- [Visual Studio](https://visualstudio.microsoft.com/) (or any C# IDE of your choice)
- [.NET 10 SDK](https://dotnet.microsoft.com/download)
- [RLBot v5](https://www.rlbot.org/v5)

Source code for this example can be found in the `Bot` directory.

## Running the Bot

To run the bot, follow these steps:

1. In RLBot's GUI, click "Add" in the top right.
2. Click "Add Folder" in the menu that pops up and select this folder.
    - You can also click "Add File" and select "atba.bot.toml" but if you rename the file then you will have to re-add your bot.
    - [See the RLBot wiki](https://wiki.rlbot.org/v5/botmaking/config-files/#bot-script-config-files) for more information on `bot.toml` files.
3. Your bot should now appear in the GUI; drag it onto either the blue or orange team.
4. Click "Start Match" to start a match with your bot.
    - If you click "Extra" in the bottom left and select "Continue and Spawn" for "Existing match behaviour" then you can reload your bot without restarting the match.

## Bob

The `bob.toml` file is a required config file for submitting bots to the botpack and tournaments.
It tells our automated build system how to build your bot from its source code.

```toml
[[config]]
project_name = "Atba"
bot_configs = ["atba.bot.toml"]

[config.builder_config]
builder_type = "csharp"
# Optional, use if there are multiple sub-projects that can be built
# base_dir = "Bot"
```

- `project_name` is the name of your bot project. It can be anything you like, but try to make it unique.
- `bot_configs` is a list of all the `bot.toml` files that are associated with this project. In this example, we only have one bot, so we only have one `bot.toml` file.
- `builder_type` is the type of builder to use for this project. In this case, we are using the `csharp` builder, which is designed for C# projects. This builder will look for a `.csproj` file in the same directory as the `bob.toml` file and use it to build the bot.
- `base_dir` is an optional field that can be used if there are multiple sub-projects that can be built. If you have multiple sub-projects, you can specify the correct base directory for the project using this field. We only have one folder, `Bot/`, so we don't need to use this field.
