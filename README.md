# GameBot-Lab-extension

Публичный источник обновления расширения GameBot Lab. **Публичный — обязателен**:
Chrome скачивает `update.json` и `.crx` без аутентификации.

- `gamebot-lab.crx` — пакет расширения (собирается из `extension/` основного
  репозитория ключом `keys/gamebot-lab.key`, от этого ключа зависит ID; лежит и на
  Pages, и на raw — содержимое идентично);
- `update.json` и `update.xml` — манифест обновления для self-hosted установок
  (app_id, адрес `.crx`, file_hash, версия). Один и тот же ответ в двух форматах:
  часть сборок Chrome ждёт JSON, часть — XML;
- `update-raw.json` и `update-raw.xml` — те же манифесты, но с адресом `.crx` на
  `raw.githubusercontent.com` (запасной канал: raw отдаёт files как `text/plain` /
  `octet-stream`, а Pages — как `application/json` / `application/x-chrome-extension`);
- `version.json` — версия + sha256 каждого файла пакета (читает панель, чтобы
  показать «доступна новая версия»).

Не правь руками: всё это кладёт `scripts/pack-extension-release.sh` из основного
репозитория.
