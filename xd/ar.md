# Trabajo Práctico de Metodología de Sistemas

Documentación de comandos, manejo de ramas, resolución de conflictos y extracción de estadísticas.
**Integrantes**:

- David Cardozo,
- Alejo Simos y
- Naim Neman.

# Stats

## Integrante con mayor cantidad de commits

<table>
<tr>
<th>COMANDO</th>
<th>SALIDA</th>
</tr>
<tr>
<td>

```bash
git shortlog -sn --all
```

</td>
<td>

```
12  Naim Neman
9   David Cardozo
7   Alejo Simos
```

</td>
</tr>
</table>

> Naim Neman realizó la mayor cantidad de commits, con un total de **12**.

---

## Cantidad total de merges

<table>
<tr>
<th>COMANDO</th>
<th>SALIDA</th>
</tr>
<tr>
<td>

```bash
git log --all --merges --oneline
```

</td>
<td>

```
345677e Merge pull request #4 from daviddcardozo2006/feature/branching-commands
667af9a Merge pull request #3 from daviddcardozo2006/feature/docs-merging
43369b3 Merge pull request #2 from daviddcardozo2006/feature/commits_commands
10cc376 Merge pull request #1 from daviddcardozo2006/feature/staging_commands
```

</td>
</tr>
</table>

> Se realizaron un total de **3** merges en el repositorio.

---

## Cantidad de conflictos producidos

<table>
<tr>
<th>COMANDO</th>
<th>SALIDA</th>
</tr>
<tr>
<td>

```bash
git status
On branch feature/indice
You have unmerged paths.
  (fix conflicts and run "git commit")
Unmerged paths:
        both modified:   indice.md
## Se forzo y resolvio 1 conflicto critico de sincronizacion en el archivo indice.md

---

## Cantidad de ramas existentes en el repositorio

<table>
<tr>
<th>COMANDO</th>
<th>SALIDA</th>
</tr>
<tr>
<td>

```bash
git branch -r | grep -v HEAD | wc -l
```

</td>
<td>

```
  origin/develop
  origin/feature/branching-commands
  origin/feature/commits_commands
  origin/feature/docs-merging
  origin/feature/staging_commands
  origin/main
```

</td>
</tr>
</table>

---

## Commit con mayor cantidad de archivos modificados

<table>
<tr>
<th>COMANDO</th>
<th>SALIDA</th>
</tr>
<tr>
<td>

```bash
git log --all --shortstat --oneline
```

</td>
<td>

```
...
d5948e4 (origin/feature/branching-commands) fix: separar los comandos en archivos individuales
 6 files changed, 92 insertions(+), 90 deletions(-)
...
```

</td>
</tr>
</table>

> Cuando ejecutamos el comando adjunto buscamos en el listado de todos los commits aquel que tuvo la mayor cantidad de archivos modificados (files changed)

---

## Captura de un conflicto previo a su resolución, indicando el hash del commit asociado

<table>
<tr>
<th>COMANDO</th>
<th>SALIDA</th>
</tr>
<tr>
<td>

```bash
git log --graph --oneline --all -n 5
* 1d912 (HEAD -> feature/indice, origin/feature/indice) fix: resolver colision de sincronizacion en indice
|\
| * 31818 docs: inyectar arbol
| 2c987 feat: inyectar arbol grafico
|/
820bf docs: generar indices de modulos
## Evidencia de colision en el entorno de desarrollo:
### El conflicto detono al colisionar los nodos 31818 y 2c987. El algoritmo de auto-merge fallo, requiriendo depuracion manual. La transaccion final se liquido y sello bajo el hash de integracion 1d912.