# aiogram-dialog-i18n-format

> [!WARNING]
> **This repository is archived.** The widget has moved to [m-xim/aiogram-dialog-i18n](https://github.com/m-xim/aiogram-dialog-i18n),
> a package on PyPI instead of a copied file. See its README for installation and usage.

A widget for [aiogram_dialog](https://github.com/Tishka17/aiogram_dialog) that adds i18n support
using [aiogram_i18n](https://github.com/aiogram/aiogram_i18n).

## Migration

```bash
uv add "aiogram-dialog-i18n[aiogram-i18n]"
# or
pip install "aiogram-dialog-i18n[aiogram-i18n]"
```

```python
# before
from i18n_format import I18NFormat

I18NFormat("bot-settings", None, F["show"], url=Format("t.me/{bot.username}?start=settings"))

# after
from aiogram_dialog_i18n.aiogram_i18n import I18nFormat

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
