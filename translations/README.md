# Translating MaxFlow

MaxFlow (Blender Max) follows Blender's interface language. Translations are plain
`.po` files, the standard format of translation tools such as
[Poedit](https://poedit.net/). Translation support starts with version 0.8.3.

## What gets translated

- Text MaxFlow draws itself: the Command Panel, Main Toolbar, ribbon, Scene
  Explorer, quad menus, the menu bar and its Max menus, and the editors (Slate and
  Compact Material Editors, Track View, Edit UVWs, Render Setup).
- MaxFlow's buttons and tooltips in Blender's own widgets, for the words Blender
  does not translate already.

MaxFlow text uses only MaxFlow's translation: a label without one stays in English,
even where Blender has a word for it, so a translation is never mixed with
Blender's choice of terms. Without a file for your language, MaxFlow is in English.

## Make a translation

1. Download the template [`maxflow.pot`](maxflow.pot) from this folder (the
   download button on its page). It lists every interface string (about 2,400,
   most of them short menu items), each with the source file and line where it is
   used.
2. Save it as `<locale>.po`, with the code Blender uses for your language:
   `zh_HANT.po` for Traditional Chinese, `zh_HANS.po` for Simplified Chinese,
   `ja_JP.po`, `ko_KR.po`, `de_DE.po`, `fr_FR.po`... To see the code, choose the
   language in Preferences → Interface → Translation, then type
   `bpy.context.preferences.view.language` in Blender's Python Console.
3. Fill in each `msgstr`. An empty `msgstr` keeps the English text, so you can
   translate in parts. Entries marked fuzzy are not used.
4. Keep what follows the words as it is: `...` (opens a dialog), a final `:`, and
   key hints such as `(Q)`.

Use your own words, or the terms your language's 3D artists use. Do not copy text
from 3ds Max's language packs or Autodesk's documentation: they belong to Autodesk.

## Try it in Blender

1. Put the file in the `translations` folder of the installed extension, for
   example
   `%APPDATA%\Blender Foundation\Blender\5.2\extensions\user_default\blender_max\translations\zh_HANT.po`
   (create the folder if it is missing).
2. Restart Blender.
3. In Preferences → Interface → Translation, choose the language and tick
   **Interface**.

Long translations can be cut short in places where Max's layout has a fixed width.

## Send it

Attach the `.po` file to an issue at
<https://github.com/neom315/blender-max/issues>. It ships in the next version.

When a new version adds text, the template here is updated; Poedit's
**Catalog → Update from POT File** adds the new entries and keeps your work.
