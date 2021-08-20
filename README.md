# Koding_Style
Some personal general coding syle explained (not just C/C++)

## Documenting

Documentation. The cornerstone of coders' evolution. Often disregarded, should be the first thing to do instead to go straight typing on the keyboard like a wild monkey. While prototyping is nice to test a concept, a product or a full scale application is more than just a concept. Things should be planned in advance. This planning should leads to structural definition, which leads to exhaustive documentation.

There are several forms of documentation : functional, technical, detail, etc. However, reading through the documentation should always allows to have a broad and/or fine understanding of what the purpose is, what is the context, etc. All too often there are lines of documentation that tells nothing but gibberish, like blatant evidences which can be found just reading the source code.

Another big problem of documentation (when there is some) is that is is scattered all over the place. Like mind maps, post its, drafts, text files, office documents, spreadsheets, diagrams, source code comments (maybe). While you may have at least some sort of information to rely on, the question now is : how relevant, accurate and up to date these informations really are ?

When working on a large scale project, it might be interesting to spread the workload of specification, documentation and coding across several dedicated teams. Yet at one point these informations might diverge, things initially planned are modified or abandoned, some new introduced. Keeping track of the reliance and relevance of these informations is crucial to success.

There are a few IDF (Integrated Development Format) such like Jupyter Notebooks that mix documentation and "experimentation", much like Labview's virtual interface where the source code (diagram) is hidden beneath the front interface, allowing the user/coder to switch between the two seamlessly. Yet that's the exception. The general case is documentation and code are separate.

https://jupyter.org/

Hence keeping track which update of the documentation belongs to which source code is often tricky. If version numbers are not updated with care, one can easily start lagging behind and inconsistencies could arise, leading to bugs difficult to understand, making people loose time and money. As the source code might not be shared, thus the documentation is the reference point.

So, again, everything starts from the documentation. That's what open standards are, documentations and specifications that are not linked to any particular implementation. Those are often technical informations, but functional level documentation shall also be opened to broader review and use. That might help standardise some interaction with the computer and its programs.

There are tools to extract some sort of documentation out of the source code, provided the comments are formatted in a way that allows the tool to detect certain keywords and patterns. The main problem remains, there is inevitable duplication of documentation, prototype definition, whatever. Keeping everything in sync is a mammoth task, that should be structured differently imho.

## Commenting

As seen previously, the source code shall feature comments to explain what is happening, what is the purpose of the lines of code. A comment linking to the respective documentation should always be present somewhere, more often in the header comment. Better have the comments on separate lines, preferably on the line above the code. Do not comment "adding numbers" for an addition.

## Cosmetics

Tastes and colors. While I do agree everyone should see fit in the way things are coded, some programming languages gives too much freedom to artistic wilderness, yet are very strict regarding the code structure. Miss one keyword and your card castle falls on itself shamelessly. A rare few languages, like Python, enforce strict rules regarding what the code should look like. For everyone.

My biggest grievance about this issue was the C/C++ language family. While it is understood that these languages are more or less a cross platform "assembler" with little brain (understand : you have to tell everything to the compiler like it is brain dead), there was so many unfounded debates about how the code should look like. Not speaking about endianess debates there.

Visual cues help developers and readers to delve into the source code, figuring out what is what and their inherent purpose. Comments can help, provided they are not too trivial but explaining the overall goal that would be hard to grasp without them. Indentation also help visually structure the hierarchy and nesting of routines. Line breaks also help to give the code some air.

Another grievance is the absolute clusterfuck of inherent "decoration" of some language. Mostly what needs to be written to get a working code. Try a "Hello World!" in Python and Java, then compare. While you cannot change the language, Java is full of prototype definitions, brackets, semicolons. Python is smooth and sleek (until you start using asyncio, lint, decorators, etc).

For C/C++ and similar languages with brackets/parentheses structuring the code, please -pretty please- try to align them vertically and/or horizontally. The K&R indentation style is one kind of a clusterfuck, you constantly have to visually track where it starts and where it ends. Allmann is more "orthogonal", Horstmann saves you one line (but prevent you from swapping their order).

https://en.wikipedia.org/wiki/Indentation_style

Python, for that regard, is pretty straightforward. No "decoration", hierarchy is achieved through indentation, operation separation with line breaks (or optionally semicolons *pwah*). That keeps the code clean from too much noise and can "pack" more lines onto the screen. However commenting in Python can become quite a mess with its various alternative formats. Try to stay relevant.

## Line ending

Unix style (LF). Always. If your code editor cannot deal with different line ending, then you're screwed, a change of occupation shall be required. Windows' line ending (CRLF) is useless. A 20k lines document have 20kb of redundant line breaking character (CR). While there are few 20k lines source files, a project might have it spread across several files, hence we might get the 20k garbage.

Sure, nowadays it's not really an issue, computers have plenty of memory and storage space. But multiply by the number of projects and forks, and you get a pretty amount of wasted space across the globe. All for nothing in fact. I'm a Windows coder, by now we all use Git, develop cross platform applications, hence having line ending consistency should be quite a priority. LF.

## Indenting

My Lord. This. Debate. Again. TABULATION for Christ's sake ! There is no valid point in using space as indentation characters. Are you doing ascii art inside your source code ? What if someone wants the indentation at 8 instead of 4 ? TABULATION is relative, you can even have ELASTIC TABULATION. Not with space as indentation. Should I tell you about the waste of "space" ?

https://nickgravgaard.com/elastic-tabstops/

No, really, when you click somewhere on screen, the caret sets on TABULATION start or end, not in the middle of nowhere, forcing you to navigate to the next "stop". Try coding in Python and mistyping an indentation (ie. through a misplaced copy/paste) with 3 spaces indentation on one line and 5 on the next. Try running the code. You will never have this issue with genuine TABULATION.

Not only it's easier to edit (navigation is faster, alignment is "automatic"), nicer to edit (alignment remains until the TABULATION width threshold is reached), did I told you it also save "space" ? Have you compared a file using space as indentation character with the same using TABULATION ? You'd be surprised how much you can save "space". Keep in mind tabulation is only (but for Python) a visual aid.

## Typing

Humans deals with numbers, words and arrays. Computers deals with numbers and arrays. Standards were defined to fit words into numbers (ascii, ansi, unicode, etc). But even numbers are weirdos, with size, sign or endianess (we get there finally) that forms a legion of different data types, there are broad families (integers, reals, complexes, dates, etc). To name only a few.

Then if it is not enough, you can create complex data types by combining simpler types together into structures. Or classes. Whatever. You'll get screwed one way or another if you don't follow the White Rabbit. Well, if you don't keep track of what goes with what. Python can be nice to prototype things, but you can easily start to mix (mess ?) up strings and numbers without noticing.

Hence even dynamic typed languages should be somewhat typed (Python's mypy) not just for the rigorist's sake. The use of proxy macros to create a set of user defined types shall help to mass modify a source code in case of typing change (poor's man refactoring). Use generic types for the common cases, do not over-engineer things too early if types aren't really set at the beginning of a project.

Did I told you to document before, and to, one amongst others, anticipate the typing of your structures ? While the string type is very flexible (Tcl) as a data container, you cannot do much with it, hence you'll rely one way or another on more suitable data types. But choose them carefully. Not only they might waste space, but require more processing power, even just being misaligned in memory.

Endianess shouldn't be an issue anymore. Try to stay native to the processor used, little endian has won the battle, get used to it. While watching a little endian memory dump is ugly, debuggers can now display memory in "integer array" format of the chosen size. Plus little endian have the "advantage" to always have the LSB at the same location, regardless of the integer size (byte, word, int).

## Coding

Where is your documentation ? Don't start typing if you don't have a minimum of documentation. Even a commented pseudo code should do as a starting point. But always tell what's the purpose of the project is, file, class, method, definition, whatever. You'll come back to it 5 years later and won't understand shit about what happened. Document for your future self. Or anyone else.

Structuring the code is important. Very important. Damn fucking it is. Just follow some common sense practices. Define your variables at one location (beginning of the function), reuse them as much as possible, don't allocate more after. Use the code structure with care to construct the code flow. Separate the nominal case from the error handling. Mirror it as much as possible (fold pattern).

One return per function, store the value in a local variable with the right type, preferably set to its default value. You should start a function at the top and always end at the bottom. Never quit the function prematurely. Use an error code or any mean to propagate the error to be handled at the right level and/or log it for the user/coder to get a feedback and behave accordingly.

Use a compact notation as naming convention. Also use Hungarian notation with type and scope as prefix. For instance 'int_line' and 'str_line' tells pretty much what it is and how to use it, even if their definition is not in sight. Write 'int_from_bytes' instead of 'bytes_to_int', hence function names should match like dominoes (reading left to right : int_from_bytes(bytes_from_string())).

Avoid early optimisation, leave the compiler something to do. Avoid doing too much on one line, spread the workload across several lines. It's cheap, it will do the same. Benefit is you can watch each step when debugging. Using intermediate local variables allows to check their content and use them several times in calculation. When asking the compiler to optimize, it will combine them anyway.

## Debugging

Not all debuggers worth a penny. Well, it changed since the 80s. Poor's man debugging is printf. Yet it is often easier and faster to use printf (or logs) to debug live, enabling/disabling the debug using macros. Plus that force to instrument the source code, which can be turned into legacy logging system with a little refactoring (even easier if already using proxy macros).

Step-by-step, breakpoint, debugging is also necessary, but should be kept at its minimum. Most notably because breakpoint aren't always saved in the project file (Labview) or because we don't always needs to inspect that accurately the working of a function or a program. Plus some microcontrollers don't have many hardware breakpoints (4 usable on stm32) so avoid it as much as possible.

Modern debuggers allows to watch memory, constants and variables according to their defined type. You can "explore" structures in a tree-like fashion. Even arrays can be expanded. Complex expressions can be used as well, even using local variables of the current context. Hence you can watch deeply nested data just like your code will. But again, avoid too nested computation, keep it simple and stupid.
