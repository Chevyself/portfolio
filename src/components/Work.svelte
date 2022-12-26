<script>
    import Job from "./Job.svelte";
</script>

<div class="container-fluid p-0">
    <Job
        name="starbox commands"
        description="A rich feature command framework. It allows to create complex commands in a few minutes for Bukkit, BungeeCord and JDA."
        links={[
            {
                href: "https://github.com/Chevyself/starbox-commands",
                text: "Github",
                icon: "github",
            },
        ]}
        tecnologies={["Java", "Bukkit", "BungeeCord", "JDA"]}
        role="In my early development journey I noticed how important is the interface of commands for the user, thus, I wanted to have a reliable way to create and manage commands."
        difficulties="The main challenge was to create a framework that could be used in different platforms, such as Bukkit, BungeeCord and JDA."
        solutions="I created a common interface for all platforms and then I created a wrapper for each platform. The wrapper implements the common interface and then it uses the platform specific methods to execute the command."
        features={[
            "Annotations",
            "Tab completion",
            "Subcommands",
            "Permissions",
            "Customizable messages",
            "Customizable help",
            "Flags",
            "Middlewares",
            "Cooldown",
        ]}
        darker={false}
    />
    <Job
        name="starfish bot"
        description="Created for the Starfish Studios. This bot has simple moderation and it manages tickets and freelancers."
        tecnologies={["Java", "MongoDB", "JDA"]}
        role="I had to create a Bot that could support many kind of tickets, such as: commissions, quotes, and applications; it required a freelancer system to present them to the users neatly."
        difficulties="As the bot was also being sold, I had to make it as customizable as possible, so I had to create a system that could be easily extended."
        solutions="I created an API that supported Addons"
        features={[
            "Tickets",
            "Freelancers",
            "Customizable messages",
            "Addons",
            "Freelancer ratings",
            "Customizable prefix",
            "Reliable MongoDB database",
            "Ticket Transcript",
        ]}
    />
    <Job
        name="guido"
        description="This is a Matchmaing bot, it uses the PGM plugin to create the matches. Players join the queue in Discord, the match is created and it is assigned to a Minecraft server."
        tecnologies={["Java", "TCP Sockets", "MongoDB", "JDA", "BungeeCord", "Bukkit"]}
        role="I had to create a bot that acted as a bridge between the Minecraft server and Discord, it needed to support stats, elo, and many other competitive features. It also meant that the Minecraft servers had to have a plugin to receive the information."
        difficulties="The communitaction between the bot and the servers had to be reliable and fast, TCP Sockets were the best option."
        solutions="I had to learn how to use TCP Sockets. The Bot became the server of the network. It had to be able to handle many connections at the same time."
        features={[
            "Matchmaking",
            "Elo",
            "Stats",
            "Customizable messages",
            "Localized messages",
            "Reliable MongoDB database",
            "Reliable and Fast TCP Sockets",
            "Pretty interface"
        ]}
        darker={false}
    />
</div>
