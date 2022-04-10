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

    import discord
    from discord.ext import commands
    from discord.ext.buttons import Paginator


    bot = commands.Bot(command_prefix=';')


    @bot.command()
    async def test(ctx):
        pag = Paginator(
                        title='Paginator +', colour=discord.Colour.blurple(), entries=[1, 2, 3], length=1, format='**',
                        footer='more options!', author='0sir1s#0669', author_url='https://cdn.glassbot.club/glass.png'
                        )

        await pag.start(ctx)


    @bot.event
    async def on_ready():
        print('Ready!')


    bot.run('TOKEN')


