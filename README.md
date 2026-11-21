# Task Tracker CLI

A simple Python command-line task tracker. Tasks are saved in `tasks.json`.

## Requirements

Python 3.9+; no external dependencies.

## Commands

```bash
python main.py add "Study Python"
python main.py update 1 "Study for an hour"
python main.py delete 1
python main.py mark-in-progress 1
python main.py mark-done 1
python main.py list
python main.py list todo
python main.py list in-progress
python main.py list done
```

Each task stores its ID, description, status, creation time, and update time. The JSON file is created automatically when adding the first task. IDs are not reused after deletion.

## Error handling

The CLI validates argument counts, IDs, descriptions, and filters. If the JSON file is corrupted, it shows an error and exits without overwriting it.

## Manual testing

In a separate test folder, copy `main.py` and run the commands above. Also try:

```bash
python main.py add ""
python main.py delete abc
python main.py list banana
python main.py list done extra
```

For a corrupted-file test, write `{invalid` into `tasks.json`, run `python main.py list`, and verify the file is unchanged.

Based on [roadmap.sh Task Tracker](https://roadmap.sh/projects/task-tracker).
