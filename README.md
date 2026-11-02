# Chhoto URL (LazyCat LPK)

Fast, simple, self-hosted URL shortener.

- Upstream: https://github.com/SinTan1729/chhoto-url
- Image: `sintan1729/chhoto-url:7.10.6` (mirror mode, digest-matched)
- License: MIT (full text in `content/licenses/LICENSE`)
- Containers: single (SQLite under /data)

## Notes

- `CHHOTO_PASSWORD` comes from a platform stable secret, so there is no shipped default.
  Leaving it empty makes the instance **open to anyone** (upstream documented behaviour);
  this package never ships empty.
- `CHHOTO_SITE_URL` is set to the https app domain.
- `CHHOTO_DB_URL=/data/urls.sqlite`, persisted on `/lzcapp/var/data`.
- `CHHOTO_SQLITE_USE_WAL_MODE=true` per upstream recommendation.
- The password is sent over plain basic auth and is not encrypted in transport; rely on the
  LazyCat HTTPS entrypoint.
- Not yet verified on a real device.
