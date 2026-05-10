# AGENTS.md

## Cursor Cloud specific instructions

This is a single-file Python/Flask REST API (`main.py`) that scrapes public Facebook profiles. No database, no frontend, no Docker.

### Quick reference

| Action | Command |
|---|---|
| Install deps | `pip install -r requirements.txt` |
| Run dev server | `python3 main.py` (starts on port 5002, debug mode) |
| Run prod server | `gunicorn main:app -b 0.0.0.0:5002` |
| Test root endpoint | `curl http://localhost:5002/` |

### Notes

- The app requires outbound internet access to `facebook.com` for profile scraping. Endpoints will return errors if Facebook is unreachable.
- There are no automated tests, linter configs, or build steps in this repository.
- The `/apps` endpoint requires valid Facebook session cookies (`c_user` and `xs`) to function.
- Flask debug mode with hot-reload is enabled by default when running `python3 main.py`.
