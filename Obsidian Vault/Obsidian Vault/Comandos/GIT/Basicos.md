<h2>1. Crear y conectar nuevo repositorio</h2>
``git init``

```
git remote add origin https://github.com/DiegoMiguelanez/obsidian_vault.git
```

```
git add .
```


```
git commit -m "Primer commit"
```


```
git push -u origin main
```


miguelanez.diego@gmail.com
token_en_keepass2
***
<h2>2. Actualizar repositorio</h2>
```
git add .
```

```
git commit -m "Segundo commit"
```

```
git push -u origin main
```

*** 

Para evitar tener que ingresar el Token en cada cambio, en el parámetro 'timeout' se especifica la duración en segundos.

```
git config --global credential.helper 'cache --timeout=3600'
```

