# Contributing — Regeln für dieses Repo

Dieses Repo wird primär von **AndreasHiltner** gepflegt.

## Branch-Modell

| Branch | Zweck | Schutz |
|--------|-------|--------|
| `main` | Aktueller Stand | Branch Protection aktiv |
| `feature/*` | Feature-Entwicklung | frei |

## Regeln

1. **Kein Direct-Push auf `main`.** Änderungen laufen ausschließlich
   über Pull Requests. Die Branch Protection erzwingt das für alle
   Collaborators (Admins ausgenommen).
2. **PR vor Merge.** Jeder Merge auf `main` braucht einen Pull Request
   mit mindestens einer Review durch einen Code-Owner.
3. **Nichts löschen.** Branches, Tags und Dateien werden ausschließlich
   von Andreas gelöscht. Lösch-Wünsche als Issue melden.
4. **Conventional Commits** — `feat:`, `fix:`, `style:`, `chore:`, etc.

## Wie der Schutz technisch umgesetzt ist

GitHub Pro + **Branch Protection** auf `main`:

- **Required PR review** (≥ 1 Approval) + **Code-Owner-Review**
  (`CODEOWNERS` verweist auf `@AndreasHiltner`).
- **Kein Force-Push**, **kein Branch-Deletion**.
- `enforce_admins` ist **aus**: Andreas darf als Admin weiter direkt
  pushen (git meldet dann `remote: Bypassed rule violations` — das ist
  der gewollte Admin-Bypass, kein Fehler).
