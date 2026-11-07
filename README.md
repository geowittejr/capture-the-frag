# capture-the-frag
A simple idea capture application. Open `index.html` in a browser; there's no build step.

## Formats
| Format | Saved as | Notes |
|---|---|---|
| Markdown (default) | `.md` | Built-in renderer and serializer (CommonMark subset, GFM tables and task lists) |
| HTML | `.html` | Wrapped in a full `<!doctype html>` document on save if it has no `<html>` tags |
| Text | `.txt` | Plain text with soft-wrap, monospace, and case tools |
| Google Doc | `.html` | Content pasted from Google Docs, normalized to clean semantic HTML |

The first paste into an empty document picks the format automatically. Later pastes are converted into the current format. To customize this, override `FragEditor.resolvePaste`. Switching formats uses `FormatConverter`. Pairs that haven't been implemented ask whether to keep the content as-is.

## View modes
- **Preview**: formatted output, read-only (Ctrl+Alt+1)
- **Edit**: plain source text (Ctrl+Alt+2)
- **Preview/Edit**: edit the formatted output inline (Ctrl+Alt+3)

## Saving
Click the folder link in the top bar to choose a save folder. Chrome and Edge remember the folder between sessions. It is stored in IndexedDB, because browsers never reveal a folder's full path. Firefox and Safari download the file instead.
