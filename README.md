# [ChromaDb](https://www.trychroma.com/) systemd

Install ChromaDB server as systemd daemon under linux. This run with your regular linux user.

## Requirements

* miniconda
* chromadb


## Setup airflow

**Step 1**: Clone repo.

```bash
cd ~
git clone https://github.com/adrianmarino/chromadb-systemd.git
mv chromadb-systemd chromadb
cd chromadb
```

**Step 2**: Get chromadb-admin.

```bash
git remote add chromadb-admin https://github.com/flanker/chromadb-admin.gi
git merge chromadb-admin/main --allow-unrelated-histories
```
