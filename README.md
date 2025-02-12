# custom-separators-merge-tool

This is a tool for merging files using specific language separators characters, instead of just '\n', to identify code conflicts.

## Algorithm

1. Break the code putting a new line before and after each separator;
2. Add a marker (e.g. “$$$$$$$”) for these new lines;
3. Call diff3 command for these new files pre processed;
4. Remove the new lines added in step one from the merge result, using the marker added in step two;

## Examples
Run the CSDiff tool for 3 ruby files:
```sh
bash csdiff.sh -s "do begin rescue end { } [ ] ( ) , |" myfile.rb oldfile.rb yourfile.rb
```

Run the CSDiff tool for 3 TypeScript files:
```sh
bash csdiff.sh -s "( ) [ ] , ; { } < > | : ??" path/to/myfile.ts path/to/oldfile.ts path/to/yourfile.ts
```
