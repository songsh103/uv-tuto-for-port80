---
marp: true
paginate: true
header: '포트80 8월 기술공유회'
footer: 'uv tutorial'
---

# Running scripts

## Running a script without dependencies
```sh
uv run lesson2\example.py
```

Arguments may be provided to the script
```sh
uv run lesson2\example2.py hello!!!
```

a directory with a `pyproject.toml`, it will install the current project before running the script.  
If your script does not depend on the project, use the `--no-project` flag to skip this:
```sh
uv run --no-project lesson2\example.py
```

---

## Running a script with dependencies

If executed without specifying a dependency, this script will fail:
```sh
uv run --no-project lesson2\example3.py
```

Request the dependency using the `--with` option:
```sh
uv run --with rich lesson2\example3.py
```

---

## Declaring script dependencies

```sh
uv add --script lesson2\example4.py "requests<3" "rich"
# check example4.py head
uv run lesson2\example4.py
```