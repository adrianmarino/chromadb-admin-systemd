# [ChromaDb](https://www.trychroma.com/) systemd

Install ChromaDB server as systemd daemon under linux. This run with your regular linux user.

## Requirements

* miniconda
* chromadb
* pnpm


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

**Step 3**: Set service port into `package.json` file:

```bash
  "dev": "next dev -p 6060"
```

**Step 4**: install service dependencies:

```bash
npm install
```

**Step 5**: Check service start:

```bash
bin/start

Start airflow scheduler

> chromadb-admin@0.1.0 dev
> next dev -p 6060

  ▲ Next.js 14.2.3
  - Local:        http://localhost:6060

 ✓ Starting...
 ✓ Ready in 1565ms
 ```

**Step 6**: `ctrl+c`to stop service.


**Step 7**: Copy service file user level systemd config path:

```bash
cp chromadbadmin.service ~/.config/systemd/user/
```

**Step 8**: Refresh systemd daemon with updated config.

```bash
systemctl --user daemon-reload
```

**Step 9**: Start service on boot.

```bash
systemctl --user enable chromadb-admin
```

**Step 14**: Start chromadb-admin as systemd daemon.

```bash
systemctl --user start chromadbadmin
```