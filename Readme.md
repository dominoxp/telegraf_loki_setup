# Telegraf - Loki 

This repository holds a working example of using telegraf to log from docker logs to a running loki instance.
In order to process docker logs, all key arguments MUST not contain non Word chars as . DOT, / Slash, etc.
To replace these keys two approches can be used:

**Replace all tag non word chars with underscore**
This leads to trailing underscores

```
# https://github.com/influxdata/telegraf/blob/release-1.24/plugins/processors/regex/README.md
[[processors.regex]]
  # Rename metric fields
  [[processors.regex.tag_rename]]
    ## Regular expression to match on a field name
    pattern = "((?:\\w+)+).?"
    ## Matches of the pattern will be replaced with this string.  Use ${1}
    ## notation to use the text of the first submatch.
    replacement = "${1}_"
    ## If the new field name already exists, you can either "overwrite" the
    ## existing one with the value of the renamed field OR you can "keep"
    ## both the existing and source field.
    result_key = "overwrite"
```
