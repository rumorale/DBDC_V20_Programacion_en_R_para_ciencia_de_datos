# 💻 Usar R como kernel en Jupyter Notebooks (VS Code - Windows)

## 1. Introducción
Este documento explica cómo configurar **R como kernel** dentro de **Jupyter Notebooks** en **Visual Studio Code (VS Code)**, usando **Windows** como sistema operativo.

---

## 2. Instalar R
> 🔹 R es el motor que usaremos como lenguaje dentro de Jupyter.

1. Descarga R desde el sitio oficial:  
   👉 https://cran.r-project.org/bin/windows/base/
2. Instálalo con la configuración por defecto (por ejemplo, C:\Program Files\R\R-x.x.x).

---

## 3. Instalar Jupyter

Tienes tres formas principales: con **pip**, **conda** o **winget**.

### Opción A — Usando Python (pip)
Ejecuta estos comandos en **PowerShell** o el **Símbolo del sistema (cmd)**:

```bash
python -m pip install notebook jupyterlab jupyter_client jupyter_core
```

Verifica la instalación:

```bash
jupyter --version
```

---

### Opción B — Usando Conda
Si tienes **Anaconda** o **Miniconda**, ejecuta:

```bash
conda install -c conda-forge notebook jupyterlab jupyter_client jupyter_core
```

---

### Opción C — Usando Winget
Si tienes `winget` disponible en tu Windows 10 u 11:

```bash
winget install -e --id JupyterLab.JupyterLab
```

---

## 4. Instalar el paquete IRkernel en R

Ejecuta estos comandos dentro de **R** o **RStudio**:

```r
install.packages("IRkernel")
IRkernel::installspec()
```

> 🔹 Si no tienes permisos de administrador:
> ```r
> IRkernel::installspec(user = TRUE)
> ```

Esto registra R como un “kernel” disponible para Jupyter.

---

## 5. Verificar instalación del kernel

Ejecuta en la **terminal** (fuera de R):

```bash
jupyter kernelspec list
```

Deberías ver algo como:

```
Available kernels:
  python3    -> C:\Users\<usuario>\AppData\Roaming\jupyter\kernels\python3
  ir         -> C:\Users\<usuario>\AppData\Roaming\jupyter\kernels\ir
```

✅ Si aparece `ir`, el kernel de R está correctamente registrado.

---

## 6. Configurar VS Code

1. Instala las extensiones:
   - **Python** (Microsoft)
   - **Jupyter** (Microsoft)
   - **R** (Yuki Ueda o R Editor Support)

2. Abre tu archivo `.ipynb` en VS Code.  
3. En la esquina superior derecha, haz clic en **Select Kernel** → elige **R** o **ir**.

---

## 7. Probar el kernel de R

Ejecuta en una celda del notebook:

```r
x <- 1:5
mean(x)
```

Resultado esperado:

```
[1] 3
```

🎉 ¡Listo! Ya puedes trabajar con R dentro de VS Code y Jupyter.



---

**Archivo:** instalacion_R_kernel_windows.md  
**Última actualización:** Octubre 2025
