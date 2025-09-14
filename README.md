# my-eighth-repo
my testing
import o
import shutil
from pathlib import Path

downloads = Path("Downloads")
for file in downloads.iterdir():
    if file.is_file():
        ext = file.suffix[1:] or "others"
        folder = downloads / ext
        folder.mkdir(exist_ok=True)
        shutil.move(str(file), str(folder / file.name))

print("Files organized by extension.")
