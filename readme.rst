A simple to use, interactive session and paginator with custom buttons for discord.py built on github.com/EvieePy/buttons.
    
Still in early stages and undergoing rapid production. Feel free to suggest something via Discord.

Support
---------------------------
For support using Buttons, please join the official `support server
<https://discord.gg/9R87syXpZN>`_ on `Discord <https://discordapp.com/>`_.


Installation
---------------------------
**Buttons requires Python 3.6 or higher.**

**Windows**

.. code:: sh

    py -version -m pip install git+https://github.com/0sir1ss/buttons.git

**Linux**

.. code:: sh

    python3 -m pip install git+https://github.com/0sir1ss/buttons.git

Getting Started
----------------------------
A quick and easy paginator example:

.. code:: py3

    from discord.ext import commands
    from discord.ext import buttons


    class MyPaginator(buttons.Paginator):

        def __init__(self, *args, **kwargs):
            super().__init__(*args, **kwargs)

        @buttons.button(emoji='\u23FA')
        async def record_button(self, ctx, member):
            await ctx.send('This button sends a silly message! But could be programmed to do much more.')

        @buttons.button(emoji='my_custom_emoji:1234567890')
        async def silly_button(self, ctx, member):
            await ctx.send('Beep boop...')


    bot = commands.Bot(command_prefix='??')


    @bot.command()
    async def test(ctx):
        pagey = MyPaginator(title='Silly Paginator', colour=0xc67862, embed=True, timeout=90, use_defaults=True,
                            entries=[1, 2, 3], length=1, format='**')

        await pagey.start(ctx)


    @bot.event
    async def on_ready():
        print('Ready!')


    bot.run('TOKEN')


