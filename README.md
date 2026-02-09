# 🌍 Global CI/CD Template

Pipeline reutilizable de **CI/CD para proyectos Java (Maven)** que valida calidad de código, construye el JAR y publica releases automáticamente, con control estricto desde Pull Requests.

---

## 🧩 ¿Qué hace este pipeline?

Este workflow define un flujo **end-to-end** que:

1. Valida reglas de la rama
2. Ejecuta **Code Review estático** (SpotBugs, PMD, Checkstyle)
3. Construye el **JAR**
4. Publica un **Release oficial**
5. Comenta el resultado final en el **Pull Request**

Todo el proceso está **encadenado y bloqueante**: si algo falla, lo siguiente **NO se ejecuta**.

---

## ⚙️ Inputs configurables

| Input | Descripción | Default |
|------|------------|---------|
| `java-version` | Versión de JDK | `17` |
| `target-branch` | Rama objetivo | `develop` |
| `artifact-prefix` | Prefijo del artefacto | `project` |
| `version-prefix` | Prefijo del release | `v1.0.` |

---

## 🔁 Flujo General del Pipeline

```text
Validate Branch
      ↓
Code Review (SpotBugs / PMD / Checkstyle)
      ↓
Build JAR
      ↓
Release Público
      ↓
Comentario Final en PR
