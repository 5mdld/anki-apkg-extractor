# Anki APKG Extractor

Extract Anki `.apkg` packages into notes + templates + media. Supports Anki collection SQLite formats: `collection.anki21b`, `collection.anki21`, `collection.anki2`.

## Requirements
- Python ≥ 3.8
- Optional for 21b: `pip install "zstandard>=0.19" "protobuf>=4.21"`

## Usage

```bash
# scan *.apkg next to the script
python anki_apkg_extract.py

# specify files or a directory; overwrite without prompt
python anki_apkg_extract.py --apkg /path/to/a.apkg /dir/with/apkg --yes

# or skip prompt via env
ANKI_EXTRACT_FORCE=1 python anki_apkg_extract.py
```
## Output

```text
<apkg-basename>/
  notes.csv        # UTF-8 with Anki import hints
  medias/          # reconstructed media files
  templates/       # CSS + per-template HTML
```

## Notes

- 2.1/2.0 work with stdlib only.
- 2.1b requires zstandard + protobuf.

## Acknowledgments

Thanks to Telegram user `@KarasawaKoko` for contributing portions of this project.

## License

MIT
