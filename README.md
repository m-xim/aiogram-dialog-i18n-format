# aiogram-dialog-i18n-format

> [!WARNING]
> **This repository is archived.** The widget has moved to [m-xim/aiogram-dialog-i18n](https://github.com/m-xim/aiogram-dialog-i18n)
> and is published on PyPI as [`aiogram-dialog-i18n`](https://pypi.org/project/aiogram-dialog-i18n).

A widget for [aiogram_dialog](https://github.com/Tishka17/aiogram_dialog) that adds i18n support
using [aiogram_i18n](https://github.com/aiogram/aiogram_i18n).

## Migration

```bash
uv add aiogram-dialog-i18n
# or
pip install aiogram-dialog-i18n
```

## Migration

```python
# before (copied i18n_format.py)
from i18n_format import I18NFormat

I18NFormat("bot-settings", None, F["show"], url=Format("t.me/{bot.username}?start=settings"))

# after
from aiogram_dialog_i18n import I18nFormat

I18nFormat("bot-settings", when=F["show"], url=Format("t.me/{bot.username}?start=settings"))
```

Breaking changes:

- `I18NFormat` is now `I18nFormat` (short alias: `T`);
- `when` is keyword-only, it used to be the third positional argument.

What is new:

- package on PyPI instead of a copied file
- fixed magic filters as params on Python 3.10 and 3.11
- faster rendering
- `render_preview` support
- typed and tested
