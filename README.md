# Infotech — Supabase self-hosted (frozen mirror)

Public mirror of `supabase/supabase/docker/` for self-hosted Supabase deployment via Dokploy.

**Source:** [supabase/supabase](https://github.com/supabase/supabase) @ `ed90d2a` (snapshot taken 2026-05-26)

## Why this exists

Dokploy raw-compose deploys ресетят `code/` dir на каждый redeploy, удаляя `volumes/*.sql` файлы. Git-source deploys клонируют весь repo и сохраняют файлы. Этот mirror — публичная Git-точка для Dokploy.

## Использование в Dokploy

Create Application → Compose:
- **Source:** Git Public Repository
- **Repository URL:** `https://github.com/sternmeisterde-ui/infotech-supabase`
- **Branch:** `main`
- **Compose Path:** `docker-compose.yml`
- Env vars: см. `/Users/user/infotech/secrets/supabase-env.txt` в проекте Инфотех

## Обновление с upstream

Раз в 1-3 месяца:
```bash
git clone --depth=1 --filter=blob:none --sparse https://github.com/supabase/supabase.git /tmp/supa
cd /tmp/supa && git sparse-checkout set docker
# затем rsync /tmp/supa/docker/ в clone этого репо и commit
```

## Лицензия

Apache 2.0 (наследуется от supabase/supabase).
