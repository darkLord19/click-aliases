# click-aliases

Add (multiple) aliases to a click_ group or command.

In your click_ app:

```python
import click
from click_aliases import ClickAliasedGroup

@click.group(cls=ClickAliasedGroup)
def cli():
    pass

@cli.command(aliases=['bar', 'baz', 'qux'])
def foo():
    """Run a command."""
    click.echo('foo')
```
Will result in:
```
Usage: cli [OPTIONS] COMMAND [ARGS]...

Options:
    --help  Show this message and exit.

Commands:
    foo (bar,baz,qux)  Run a command.
```
