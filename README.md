<p align="center">

## Table of Contents:

-  [Installation](#installation)
-  [Usage](#usage)
-  [Documentation](#documentation)
-  [Docker](#docker)
-  [Contributing](#contributing)

## Installation

> [!CAUTION]
> These instructions are for the community version _only_. Trying to use these instructions to install [3b1b/manim](https://github.com/3b1b/manim) or instructions there to install this version will cause problems. Read [this](https://docs.manim.community/en/stable/faq/installation.html#why-are-there-different-versions-of-manim) and decide which version you wish to install, then only follow the instructions for your desired version.

Manim requires a few dependencies that must be installed prior to using it. If you
want to try it out first before installing it locally, you can do so

For local installation, please visit the [Documentation](https://docs.manim.community/en/stable/installation.html)
and follow the appropriate instructions for your operating system.

## Usage

Manim is an extremely versatile package. The following is an example `Scene` you can construct:

```python
from manim import *


class SquareToCircle(Scene):
    def construct(self):
        circle = Circle()
        square = Square()
        square.flip(RIGHT)
        square.rotate(-3 * TAU / 8)
        circle.set_fill(PINK, opacity=0.5)

        self.play(Create(square))
        self.play(Transform(square, circle))
        self.play(FadeOut(square))
```

In order to view the output of this scene, save the code in a file called `example.py`. Then, run the following in a terminal window:

```sh
manim -p -ql example.py SquareToCircle
```

You should see your native video player program pop up and play a simple scene in which a square is transformed into a circle. You may find some more simple examples within this
[GitHub repository](example_scenes). You can also visit the [official gallery](https://docs.manim.community/en/stable/examples.html) for more advanced examples.

Manim also ships with a `%%manim` IPython magic which allows to use it conveniently in JupyterLab (as well as classic Jupyter) notebooks. See the
[corresponding documentation](https://docs.manim.community/en/stable/reference/manim.utils.ipython_magic.ManimMagic.html) for some guidance and
[try it out online](https://mybinder.org/v2/gh/ManimCommunity/jupyter_examples/HEAD?filepath=basic_example_scenes.ipynb).

## Command line arguments

The general usage of Manim is as follows:

![manim-illustration](https://raw.githubusercontent.com/ManimCommunity/manim/main/docs/source/_static/command.png)

The `-p` flag in the command above is for previewing, meaning the video file will automatically open when it is done rendering. The `-ql` flag is for a faster rendering at a lower quality.

Some other useful flags include:

-  `-s` to skip to the end and just show the final frame.
-  `-n <number>` to skip ahead to the `n`'th animation of a scene.
-  `-f` show the file in the file browser.

For a thorough list of command line arguments, visit the [documentation](https://docs.manim.community/en/stable/guides/configuration.html).

## Documentation

Documentation is in progress at [ReadTheDocs](https://docs.manim.community/).

## Docker

The community also maintains a docker image (`manimcommunity/manim`), which can be found [on DockerHub](https://hub.docker.com/r/manimcommunity/manim).
Instructions on how to install and use it can be found in our [documentation](https://docs.manim.community/en/stable/installation/docker.html).



## Contributing

Contributions to Manim are always welcome. In particular, there is a dire need for tests and documentation. For contribution guidelines, please see the [documentation](https://docs.manim.community/en/stable/contributing.html).

However, please note that Manim is currently undergoing a major refactor. In general,
contributions implementing new features will not be accepted in this period.
The contribution guide may become outdated quickly; we highly recommend joining our
[Discord server](https://www.manim.community/discord/) to discuss any potential
contributions and keep up to date with the latest developments.

Most developers on the project use `poetry` for management. You'll want to have poetry installed and available in your environment.
Learn more about `poetry` at its [documentation](https://python-poetry.org/docs/) and find out how to install manim with poetry at the [manim dev-installation guide](https://docs.manim.community/en/stable/contributing/development.html) in the manim documentation.



