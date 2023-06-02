# AnubisCLI

Fork of [Anubis](https://github.com/0sir1ss/Anubis), the Python obfuscator. Main difference is providing a sane CLI, to allow the tool to be used as part of scripts, and remove bells and whistles (as nice as color ASCII is, ultimately it doesn't add much to the practicality of the tool). Also, the .exe packaging was removed for simplicity (the resulting files are just normal Python source code, so all common packaging tools still work as intended, so the integration into Anubis doesn't add much IMO).

## License

MIT (unchanged from original Anubis). See the file `LICENSE` for details.

## Usage

```bash
cd AnubisCLI
pip install .

# go to some folder with Python code
anubis-cli --output some_file_obf.py some_file.py
# or to replace file
anubis-cli --replace some_file.py
```

There are more flags for disabling certain steps.

```bash
anubis-cli --no-carbonate --replace some_file.py
anubis-cli --no-junk --replace some_file.py
```
These flags can be combined.

If neither `--output FILE` nor `--replace` is provided, the resulting source code will be pushed to STDOUT.

To start the output file with the contents of another file (like a copyright notice) use the following:
```bash
anubis-cli --start some_notice.txt --replace some_file.py
```

You can also use `--replace` on all .py files in a folder, like

```bash
anubis-cli --replace ./some_folder/
```