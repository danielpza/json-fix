# json-fix

  Command line utility for parsing and fixing json with commons errors like missing ""

## Installation

    $ npm install json-fix --global

## Option spaces

 You can specify spaces with `--spaces %number of spaces%`, it uses `4` as default
 
## Examples

  This

```js
{ a: "hello",
 b: "world",
}
```

  converts to

```json
{
    "a": "hello",
    "b": "world"
}
```

## IDEs configuration

### Spacemacs/Emacs

```
  (defun fix-errors-with-json-fix-4 ()
    (interactive)
    (shell-command-to-string (format "json-fix -s 4 %s" buffer-file-name))
    (revert-buffer-no-confirm))
  (defun fix-errors-with-json-fix-2 ()
    (interactive)
    (shell-command-to-string (format "json-fix -s 2 --no-sort %s" buffer-file-name))
    (revert-buffer-no-confirm))
  (spacemacs/set-leader-keys "oj" 'fix-errors-with-json-fix-4)
  (spacemacs/set-leader-keys "ok" 'fix-errors-with-json-fix-2)

```
