# 🎨 Business Central Extension - Color Emoji for Items

## 📦 Overview

This extension introduces a visual tagging system in Microsoft Dynamics 365 Business Central by leveraging emoji symbols. It includes:

- A custom enum **`50330 Color Emoji`** containing color-themed and symbolic emojis.
- A **field extension to the Item table** for storing color tags.
- A **page extension to the Item Card** for displaying and selecting emoji tags in the UI.

---

## 🧾 Features

### 1. `Enum 50330 "Color Emoji"`

An extensible enum with emoji-based values for visual categorization and enhanced user interface interaction.

| Value     | Caption         | Description              |
|-----------|------------------|--------------------------|
| None      | (empty)          | No emoji selected        |
| Red       | 🔴 Red           | Represents red category  |
| Blue      | 🔵 Blue          | Represents blue category |
| Purple    | 🟣 Purple         | Represents purple tag    |
| Green     | 🟢 Green          | Represents green tag     |
| Black     | ⚫ Black          | Represents black marker  |
| Fish      | 🐠 Fish           | Symbolic marker          |
| Smile     | 😄 Smile          | Represents positivity    |
| Hundred   | 💯 100            | Represents excellence    |
| Hand      | 🫳 Hand           | Generic indicator        |

---

### 2. `TableExtension 50442 "ColorExtension"` (extends `Item`)

Adds a new field `Color` (of type `Color Emoji`) to the `Item` table for storing the selected tag.

```al
field(50220; Color; Enum "Color Emoji")
{
}

### 3. PageExtension 50445 "ColorExtension" (extends Item Card)
Displays the Color field on the Item Card page, right after the No. field, making it easy to view and assign emoji tags.
addafter("No.")
{
    field(Color; Rec.Color)
    {
        ApplicationArea = All;
    }
}
