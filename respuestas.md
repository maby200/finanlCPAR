# Resoluci√n de ejercicios
---

## Pregunta 1
```bash
$ ssh devcloud
$ git clone https://github.com/oneapi-src/oneAPI-samples.git
```
Salida:
```bash
$ git clone https://github.com/oneapi-src/oneAPI-samples.git
Cloning into 'oneAPI-samples'...
remote: Enumerating objects: 30303, done.
remote: Counting objects: 100% (1121/1121), done.
remote: Compressing objects: 100% (499/499), done.
remote: Total 30303 (delta 611), reused 1061 (delta 593), pack-reused 29182
Receiving objects: 100% (30303/30303), 361.26 MiB | 33.47 MiB/s, done.
Resolving deltas: 100% (19636/19636), done.
Checking out files: 100% (4727/4727), done.
```

## Pregunta 2

```bash
cd oneAPI-samples/
# no devuelve m√s porque es ingresar al folder
```
## Pregunta 3
```bash
cd DirectProgramming/C++SYCL/DenseLinearAlgebra/matrix_mul
# no devuelve m√°s porque es ingresar al folder
```

## Pregunta 4

### 4.1
Salida:

```bash
diff --git a/DirectProgramming/C++SYCL/DenseLinearAlgebra/matrix_mul/src/matrix_mul_omp.cpp b/DirectProgramming/C++SYCL/DenseLinearAlgebra/matrix_mul/src/matrix_mul_omp.cpp
index f34edad6..dd56d455 100644
--- a/DirectProgramming/C++SYCL/DenseLinearAlgebra/matrix_mul/src/matrix_mul_omp.cpp
+++ b/DirectProgramming/C++SYCL/DenseLinearAlgebra/matrix_mul/src/matrix_mul_omp.cpp
@@ -54,9 +54,9 @@ int main(void) {
   cout << "Result of matrix multiplication using OpenMP: ";
   Result1 = VerifyResult(c);
 
-  MatrixMulOpenMpGpuOffloading();
-  cout << "Result of matrix multiplication using GPU offloading: ";
-  Result2 = VerifyResult(c);
+  // MatrixMulOpenMpGpuOffloading();
+  // cout << "Result of matrix multiplication using GPU offloading: ";
+  // Result2 = VerifyResult(c);
 
   return Result1 || Result2;
 }
```

### 4.2
El comando `git diff` permite conocer las diferencias en el repositorio local con el √∫ltimo git pull que se hizo del repositorio remoto. De esta manera sirve como un historial de cambios que se han hecho.

## Pregunta 5
Salida
```bash
icpx -fiopenmp -fopenmp-targets=spir64 -D__STRICT_ANSI__ -g -o matrix_mul_omp src/matrix_mul_omp.cpp 
icpx: remark: Note that use of '-g' without any optimization-level option will turn off most compiler optimizations similar to use of '-O0'; use '-Rno-debug-disables-optimization' to disable this remark [-Rdebug-disables-optimization]
```
## Pregunta 6

### 6.1 JobID: 
`2348542.v-qsvr-1.aidevcloud`
### 6.2 .e y .o archivos: 
- `run_a.sh.o2348542`
- `run_a.sh.e2348542`
### 6.3. Mostrar el contenido de ambos archivos error y output stream (.e y .o) generados
- `.o`:
```bash
########################################################################
#      Date:           Wed 26 Jul 2023 12:58:23 PM PDT
#    Job ID:           2348542.v-qsvr-1.aidevcloud
#      User:           u196560
# Resources:           cput=75:00:00,neednodes=1:xeon:ppn=2,nodes=1:xeon:ppn=2,walltime=06:00:00
########################################################################


start: 230726.125829.602

Problem size: c(150,600) = a(150,300) * b(300,600)
Running on 0 device(s)
The default device id: 0
Result of matrix multiplication using OpenMP: Success - The results are correct!

stop: 230726.125832.203


########################################################################
# End of output for job 2348542.v-qsvr-1.aidevcloud
# Date: Wed 26 Jul 2023 12:58:32 PM PDT
########################################################################

```

- `.e`:
```bash
/var/spool/torque/mom_priv/jobs/2348542.v-qsvr-1.aidevcloud.SC: line 7: cd: /home/u196560/INICTEL/oneAPI-samples/DirectProgramming/C++SYCL/DenseLinearAlgebra/matrix_mul: No such file or directory
```

## Pregunta 7
### Pregunta 7.1. Cu√°les son las locaciones de git?
1. Working tree
2. Staging area (area de preparacion)
3. Repositorio local
4. Repositorio Global (o tambi√n repositorio remoto)
### Pregunta 7.2. Qu√© es el speedup y c√≥mo se calcula?
 El speedup es una m√trica que se usa para conocer el rendimiento entre estrategias de paralelizaci√n enfocadas a un mismo problema. Se calcula:
$$ Speedup = \frac{T_{base}}{T_{optimizado}}$$
### Pregunta 7.3. Mencione dos t√©cnicas de paralelizaci√
1. Paralelizaci√n basada en datos
2. Paralelizaci√≥n basada en tareas
### Pregunta 7.4. Cu√°les son las dos leyes fundamentales de la computaci√≥n paralela?
 ---

### Pregunta 8

Comandos utilizados
- Dentro de la carpeta a subir
- git init 
- git add . # puesto que voy a subir todos los archivos que he trabajado
- git commit -m "emisi√n de examen final"
- git branch -M main (para cambiar el nombre a la rama)
- git remote add origin git@github.com:maby200/finanlCPAR.git
- git push -u origin main

## 8.2
Link [al repositorio.](https://github.com/maby200/finanlCPAR)
