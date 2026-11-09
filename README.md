# GameBot-Lab-extension

Публичный источник обновления расширения GameBot Lab. **Публичный — обязателен**:
Chrome скачивает `update.json` и `.crx` без аутентификации.

- `gamebot-lab.crx` — пакет расширения (собирается из `extension/` основного
  репозитория ключом `keys/gamebot-lab.key`, от этого ключа зависит ID);
- `update.json` — манифест обновления для self-hosted установок (app_id,
  chrome_base_url, file_hash, version);
- `version.json` — версия + sha256 каждого файла пакета (читает панель, чтобы
  показать «доступна новая версия»).

Не правь руками: всё это кладёт `scripts/pack-extension-release.sh` из основного
репозитория.
