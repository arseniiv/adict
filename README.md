# aDict

[Update] NB: Above all, please note this package is very, very old and not maintained currently. As time flew, I had made a more flexible version of this format backed by some C# code only, and then after some more time I left it where it accumulates the dust till now, as it had no use by me or anybody I heard from. The repository here may vanish in the future but I don’t see a reason to do that right now, nor a reason to unregister the package from PyPI. But you better not use this old thing: if you ever want something like this up-to-date, please open an issue here so I would know what features you’re interested in. But this would require a complete rewrite, at least to use some great parser combinator things.

I don’t even remember what version of Python this requires, 2.something?.. :) I made this readme more bearable, though.

## Description

aDict provides interface to reading and writing a simple dictionary format. (Like, for conlanging purposes.)
Typical usage:

    from adict import *                # data classes
    from adict.parser import Parser    # text to data
    from adict.printer import Printer  # data to text
    
    with open('some file') as f:
        a = Article('Python')
        a.classes.append('n')
        a.transcriptions.append('ˈpaɪθən')
        d1 = Definition('a kind of programming language')
        d2 = Definition('a kind of Snake')
        d2.links.append('hyperonym', 'Snake')
        a.content = [d1, d2]
        
        dictionary = Parser(f).parse()
        dictionary.articles.append(a)
    
    with open('some other file', 'w') as f:
        f.write(str(Printer(dictionary)))

The format specification in English has not written yet. :)

However, I think, this format is pretty simple to understand by trial and error or by looking on this implementation.

# Contributors

Only me = arseniiv so far.
