# partytrax

Choral part track mixer? Eventually? 🤷

## Converting part tracks to stems

The JS file `tracksToStems.mjs` takes all the files in `tracks/raw` and
does the following:
- Determines song title from file names and groups files by song
- Creates a directory for each song in the `tracks` directory
- For each song:
  - Run the demo/balanced track through spleeter to isolate the accompaniment
  - If the predominant part is panned L, create files isolating the left channel
  - If the predominant part is mixed louder, do something Jacob hasn't thought
    of yet
- Generates a manifest file describing the generated files

```sh
node tracksToStems.mjs
```

For copyright reasons, the entire `tracks` directory is gitignore'd.

I didn't account for Windows-style paths, so idk if this'll run on Windows.
Sorry not sorry.

Spleeter is a dependency of this script. The first time you run the script,
spleeter will take some time to download its pre-trained models so be aware that
it'll take a hot sec.