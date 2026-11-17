# Supabase setup — Bulk OCR v2.0

This is optional. Without it, duplicate counts work within the current browser session only.

1. Create or open a project at https://supabase.com/
2. Open **SQL Editor** → **New query**.
3. Run:

```sql
create table if not exists public.duplicate_history (
  phone text primary key,
  first_seen_at timestamptz not null default now()
);

alter table public.duplicate_history enable row level security;

-- The browser app uses the anon key and inserts numbers.
create policy "Allow anon insert duplicate history"
on public.duplicate_history
for insert
to anon
with check (phone ~ '^[6-9][0-9]{9}$');

-- Optional: permit the browser app to read its history for duplicate matching.
create policy "Allow anon read duplicate history"
on public.duplicate_history
for select
to anon
using (true);

grant select, insert on public.duplicate_history to anon;
```

4. In Project Settings → API, copy the **Project URL** and the **anon/public key**.
5. In Bulk OCR, paste them into the Supabase settings and press **Save cloud settings**.
6. Press **Sync duplicate history** after extracting contacts.

## Security and privacy
- Do not use the `service_role` key in a public browser app.
- The provided policies allow anonymous reads and inserts of phone numbers. Anyone who can access your public app and its anon key may be able to read the table. For a private dataset, do not enable the read policy; use a server-side authenticated function instead.
- Supabase stores phone numbers in your project. Enable this only if you consent.
- This setup syncs inserts; it does not yet merge/download the full history into the browser's local duplicate checks.
