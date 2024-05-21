# GPG y SSH

Este repositorio es para aquellos que quieren que sus commits salgan verified. 

Podras configurarlo con facilidad si sigues los siguientes pasos...

## Configuracion Basica Git

```bash
git config --global user.name "Your Name"
```

```bash
git config --global user.email name@correo.com
```

```bash
git config --global core.editor "code --wait"
```

```bash
git config --global core.autocrlf input
```

## Configurar SSH
### Generar SSH

```bash
ssh-keygen -t rsa -b 4096 -C "name@correo.com"
```
### Optener Codigo
```bash
cat ~/.ssh/id_rsa.pub
```

### Ir a configurar a github copiando el codigo

### Testear conexion
```bash
ssh -T git@github.com
```

## Configurar GPG

### Generar GPG Key
```bash
gpg --full-generate-key
```

### Obtener ID

```bash
gpg --list-secret-keys --keyid-format=long
```

Copia el codigo que esta despues del slash en la seccion de sec

Ejemplo

3AA5C34371567BD2 

### Obtener Llave para github

```bash
gpg --armor --export 3AA5C34371567BD2
```

### Configurar llave en github


## Decirle a git que firme tus commits con gpg

### Git utilice gpg
```bash
git config --global --unset gpg.format
```

### obtener ID gpg 
```bash
gpg --list-secret-keys --keyid-format=long

```

### Configurar clave para git

```bash
git config --global user.signingkey 3AA5C34371567BD2

```

### Firmar commits con gpg
```bash
git config --global commit.gpgsign true
```

